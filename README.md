### Tabular Data code 

---

# 📜[Pstage_Competition]-Tabular Data

> Public Score : 0.8605 16등

### 👀[대회개요]

---

![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/db560c06-7eeb-4687-abbe-4ab28704dc70/Untitled.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/db560c06-7eeb-4687-abbe-4ab28704dc70/Untitled.png)

### 💡[Date 정보]

---

![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/f349f77e-f5a3-40d4-adad-2852f6231900/Untitled.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/f349f77e-f5a3-40d4-adad-2852f6231900/Untitled.png)

![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/436b0717-f285-4430-84fb-817707e860b6/Untitled.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/436b0717-f285-4430-84fb-817707e860b6/Untitled.png)

- 주어진 Data의 feature들을 이용해서 다음 달 소비자들이 300$이상을 소비 유무를 예측하는 Competion이었습니다
- Data 컬럼 설명
    1. order_id=주문번호, 데이터에서 같은 주문번호는 동일 주문을 나타냄
    2. product_id: 상품 번호 
    3. description: 상품 설명 
    4. quantitiy: 상품 주문 수량 
    5. order_data: 주문 일자 
    6. Price: 상품 가격 
    7. customer_id: 고객 번호 
    8. country: 고객 거주 국가 
    9. total : 총구매액 

# 💡[EDA]

---

> Tabular Data에 있어서 가장 중요한 건 Data에 대한 이해와 분석!

```markdown
💡정형데이터에 있어서 전처리와 데이터 분석, 분포 , 상관 관계, PCA 등 정말 다양한 방법으로
 
data에서 새로운 feature를 만들고 적용 할 수 있다는 것을 깨달을 수 있는 EDA였다. 

또한 EDA를 하면서 정말 data안에서 어떤 일이 일어나고 어떤 상황이었는지에 대해 상상할 수 있다면

data에 대한 이해도가 높아 질 것이다
```

- 각 데이터들의 분포, 평균 , Min, Max ,Std 값들 시각화
- 월 단위 판매량
- 월 단위 Total 300 이상 비율
- Description에 대한 이해
    1. Post,Bank Charges,Test,Adjust,M,Cruk등 product_id와 description에 영문 모를 단어들이 있음 
    2. Test는 임시로 Test해본 결과 즉, root 아이디로 임의로 Test상품을 만든것으로 추정 
    Post는 택배를 보낸 것으로 추정
    Bank_charges 항상 음수 값으로 표기되는 걸로 보아 세금 지불로 추정
    Cruk→ 자선 단체에  기부
    Adjust→ test와 마찬가지로 조정
- 국가별 분포도 시각화→ 90%정도가 United Kingdom 10% 나머지 국가들 → Total과의 연관성은 적어 보인다
- Group_by_customer-quantity→ 많이 산 사람일수록 300$이상 구매 분포가 높음
많이 사면 당연히 구매 금액이 커지니 높을 수 밖에 없다 .
- Customer-order_id→ order_id가 같다면 한번에 같이 구매한 목록 → 많이 구매한 사람은 300$이상 구매 분포가 높음 quantitiy와 비슷한 이유

## 💡[Environment]

---

- Window 10
- VsCode
- GPU-p40
- Python, Notebook

## 💡[Train & Valid Set]

---

- 검증 전략(Validation Test)
    1. StratifiedKFold -10Fold를 사용하여 각 폴드별로 AUC_Score를 계산하여 10폴드에 대해서 각각 best Auc_score를 사용하였습니다
- 사용한 모델 아키텍쳐 및 하이퍼 파라미터
    1. Light_gbm
        - LB_Score: 0.86005
        - Feature 개수 : 55개

        ```markdown
        model_params:
        	'binary' -> 이진분류
        	'gdbt' -> boosting type
        	'auc' -> 평가 지표
        	'feature_fraction'=0.8 -> 피쳐 샘플링 비율
        	'bagging_fraction'=0.8 -> 데이터 샘플링 비율
        	'n_estimators'=10000 -> bagging freq
        	'early_stopping_rounds'=100
        	'seed'=777
        ```

        - Train: 2009-12~2011-10 기간의 유저 data를 통해 학습
        - Valid: 2009-12~2011-10 기간의 유저 data를 통해 2012-11월 label 예측
    2. NN_Model
        - LB Score: 0.8594

        ![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/a55d3b98-aca2-4254-ae5c-a62014484dd5/Untitled.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/a55d3b98-aca2-4254-ae5c-a62014484dd5/Untitled.png)

    - 3계층 layer  model
    - 3번의 dropout, batchnorm 적용
    - Activation funtion으로 Relu 사용
    - 512, 1024 개의 node를 가진 hidden layer 사용
    - Optimizer→ Adam
    - Lr=3e-4
    - Scheduler→ ReduceOnplatue(patience=8, gamma=0.2)

    ### ✔[도전한 기술 및 Feature]

    ---

    ### [Skill]

    - Out_of_fold ensamble→ 10개의 폴드를 통해서 predict값을 구해서 mean한 값을 예측값으로 사용 . 일종의 Regulation기법
    - StratifiedKfold→ label의 0,1의 비율이 imbalance하기에 데이터의 분포를 맞춰서 Kfold사용 →data imbalence를 해결 및 Regulation기법
    - NN_model & Tree_model Ensamble→ 트리모델에서 predict한 값과 nn 모델에서 prdict한 값을 앙상블→ Regulation
    - Batchnorm,Dropout → 피쳐는 50개 정도인데 모델의 node는 512-1024-1024의 node를 가짐   feature에 비해 모델이 너무 복잡함 즉 overfitting이 발생할 가능성이 크므로, batchnorm과 dropout를 모두 사용하여 규제를 강화함

    ### [Feature]

    1. Base Feature agg→ 성공

    ```markdown
    💡 Feature들에 대한 [Min, Max, Mean, Sum, Count, Std, Skew, Quantile] Agg

    1.
    -> 주어진 Feature들에 대해서 numeric형이 아닌 obj Type들에 대해서 Label encoding 혹은
    결측치 값에 대해서 SimpleInputer를 이용하여 결측치 값들을 median값으로 대체 해서 Feature
    의 개수를 늘려 주었습니다. 
    2.
    -> 처음에는 data에 대한 이해도가 부족해서 price, quantity, total 등 모든 feature에 대해서 
    agg를 해주었는데 생각해보면 price*quantitiy=total 인데 굳이 price와 quantity와 total이 
     중복되는 부분들에 대해서는 feature 를 추가 해줄 필요가 없었다. 
    3.
    -> LB 점수 크게 상승 하지만 모든 피쳐에 agg를 사용했기에 상관관계에 대한 이해가 부족했고
    어떤 feature가 중요하고 안중요한지에 대한 이해가 부족했다.

    [배운점]
    ✔ 항상 feature를 추가하거나 agg를 할 때 논리적으로 접근하고 data분석을 통해 납들 할만한 
    근거를 가지고 시도해 볼것 . 마구잡이식 feature추가와 agg는 오히려 더 나은 모델을 만드는데에 
    있어서 독이 될 수 있다. 
    ```

    2. 시간 Feature 추가 → 실패 LB_score 하락

    ```markdown
    💡 Customer_id 별로 어느 시간대에 샀는지 -> 주로 아침에 샀는지, 점심에 샀는지, 저녁에
    샀는지에 대해 나눠서 label_encoding을 통해 feature로써 사용했다. 

    [접근법]
    아침에 사는 사람은 소매상일 경우가 크다-> 일반인의 경우 아침-낮 시간대에 직장, 학교, 
    등 업무를 보는 시간이 많을 것이라는 생각에서 접근하였다. 소매상일 경우는 업무가 물건을
    사고 파는 일이니 업무로써 아침시간대에 물건을 샀을 것이라고 접근 하였다.
    즉 -> 소매상들은 일반인들 보다 물건을 다량 구입하니 , 더 높은 확률로 300달러를 살 것이다

    [실패원인 분석]
    이미 feature로서 사용하는 quantity에 구매 개수가 있다. 즉 quantity를 통해서도 
    그 사람이 소매상인지 일반인인지 구분 가능 할것이라고 추론하였고 quantity의 특성이 
    아무래도 시간으로 나눈 것보다 더 정확하게 구분이 가능해서 오히려 점수가 하락했다고 
    생각한다. 
    ```

    3. 기간 별 Total 300 이상 비율 Feature 추가→ 성공

    ```markdown
    💡 기간별로 나누어서 customer의 300달러 이상의 비율을  feature 로 사용하였다.

    [접근법]
    1. predict는 300달러를 기준으로 그 이상이냐 이하를 predict하는 문제인데 300달러와 
    관련된 feature가 total 하나밖에 없음 -> 300달러에 관한feature가 너무 적다고 생각 

    2. 최근 3, 6, 12,20 개월에 대해서 300달러를 넘는 total값의 비율을 구하여 feature로써 
    추가해 주었다 . 

    왜 기간을 나눴는가? 물건을 어떤 사이트에서 사는데 있어서 최근 구매일 즉 최근에 언제 샀는
    가는 굉장히 중요한 특징이라고 생각했기 때문이다. 즉 1년전에 10번 구매한 것과 최근 3개월간
    10번 구매한 고객이 있다면 당연히 최근 3개월 10번 구매한 고객이 다음달에 구매할 확률이 높다는
    생각으로 접근하였다. 
    하지만 최근 300개월의 기록만 본다면 0의 비율이 너무 높다 즉 모델이 0으로 overfitting
    될 것을 생각하여 그 6,12,20 개월을 분석한 feature들을 추가 하였다. 하지만 정확한 검증을
    하지 못한 탓에 어느 시점이 가장 중요한 feature이 어떤 것이 좋지 못한 feature였는지에 
    대한 확신을 얻지는 못하였다. 

    [아쉬운점]
    좋은 접근 방법이었다고 생각하고 생각대로 LB_score의 향상도 있었다. 하지만, valid_set의
    신빙성이 떨어지는 탓에 검증을 완벽하게 하지 못하고 오직 LB score로만 짐작 할 수 있었다.
    ```

    4. 월 product_id*quantity 비율 Feature 추가 → 실패

    ```markdown
    💡 월별로 product_id*quantity/전체 product_id*quantity 의 비율을 feature 사용

    [접근법]
    상품별로 계절에 따라 잘팔리는 상품과 팔리지 않는 상품들이 있다는 것을 EDA를 통해 
    분석하였다. 즉, 여름 제품을 많이 사는 고객은 겨울 상품을 사지 않을 것이다. 겨울 제품을 
    사는 고객은 여름 제품을 사지 않을 것이다 라는 생각에서 접근 하였다.

    [실패원인]
    Data를 분석해본 결과 확실히 소비자 별로 여름/겨울에 대한 상품 선호도가 있긴 하였다.
    하지만 상품 선호도와 300달러의 연관성이 크지 않았던 것으로 생각된다. 
    ```

    5. PCA 기법으로  feature 추가→ 실패 

    ```markdown
    💡사용하고 있던 feature들을 PCA기법하여 새로운 10개의 PCA feature를 추가 

    [접근법 ]
    사용하고 있던 feature가 30~40개 정도였는데  이 feature들의 관계를 새로운 10차원으로 
    줄여서 10개의 feature로 새로 생성한다면 어떤 시너지 효과를 내지 않을까 라는 생각으로 접근

    [실패 원인]
    사용하고 있던 feature들이 모두 검증된 feature이 아니었다. 즉 feature들간의 상관관계 및
    정확한 특징들을 이해하지 못한 상태에서 PCA를 통해 새로운 feature를 추가한들 그 feature
    들이 어떠한 연관성이나 새로운 특징을 만들었다고 생각하기 어렵다.. 

    [배운점]
    자신이 사용하는 feature의 특징을 명확히 이해해야 PCA기법으로 feature들간의 새로운
    특징을 뽑아 낼 수 있다고 생각한다. 즉 막연하게 여러 skill들을 사용한다고 내 feature에
    맞는 것이 아니라는 것
    ```

    6. 최근/마지막 구매일 feature 추가 → 성공 

    ```markdown
    💡Recent_buy라는 Feature를 추가 -> 고객이 가장 최근에 언제 구매했냐 혹은 가장 마지막 
    구매일 언제인가를 feature로써 추가 했음

    [접근법]
    예측해야 하는 월과 최근 구매일이 가깝다면 또 다시 살확률이 높다는 아이디어에서 착안 
    즉 한달전에 물품을 산 고객이 1년전에 물품을 산 고객보다 다음달에 구매할 확률이 높다고
    생각하였다 .
    [성공이유]
    생각한대로 최근에 산 고객일수록 다음달에도 살 확률이 높다는 결과를 얻었고 , score에도
    상승이 있었다.
    ```

## 😢[아쉬운점]

---

1. Train data의 부족 : 

 학습 데이터는 2년이 안되는 기간이었고 모든 data를 사용하여 11월 하나 만을 예측하는 train과정을 거쳐서 검증을 하였음.
 하지만 관점을 조금 바꿔서 train을  9,10,11월에 대해 train 시켰다면 train_data를 더 늘리면서 좀 더 높은 score를 받을 수 있지 않았을까 라는 생각을 했고, 실제로도 상위권 유저들이 train_set을 늘려서 학습을 시켰다고 한다.
`생각한 것은 어렵더라도 실천해볼것!`

2. 시각화 구현의 부족 : 

사람이 많은 수의 data를 보고 직관적으로 어떤 분포를 갖고 어떤 특성을 갖는지 분석하기는 어렵다.
 그래서 data를 시각 화 하여 분석하면 좀 더 직관적으로 분석할 수 있고 자신의 가설에 대한 신뢰성을 얻을 수 있다.  하지만 시각화를 많이 연습해 보지 않았던 탓에 data를 시각화하는데 어려움을 많이 겪었고 , 내 가설을 시각화하여 검증하지 못한 경우가 종종 있었다.
`시각화는 구현연습을 계속해볼 것!`

3. Tree_Model에 대한 이해도 부족:

Tree_model을 이번 경험을 통해서 처음 접해봤는데, bagging,boosting등 다양한 방법과 entropy, Gini , info_gain등 다양한 방법을 통해서 node들을 생성해 낸다는 것을 배울 수 있었고, deep learning model아닌 분류기의 역할을 하는 만큼
수학적 계산을 요구하는 내용들이 많았다. 아직 모델에 대한 이해가 부족하다는 것을 깨달았고, 모델의 이해가 떨어지니 model_tuning을 제대로 할 수 없었고 sota의 성능을 이끌어내지 못했다고 생각한다. 
`트리모델에 대한 이해도 높이기`

4. DataFrame 조작 미숙:

Pandas의 DataFrame 을 이용하여 csv파일을 다루거나 기본적인 function들만 주로 사용했었다. 이번 경우처럼 feature들을 새로 만들고 해본 경험이 없었던 탓이다. columns들이 계층 구조를 이룰 수 있고 이것에 대해 접근하는 방법 또한 존재했었고  groupby,concat,merge등 sql에서 주로 사용하는 function들이 DataFrame에도 모두 구현되어 있음을 알앗다. DataFrame은 Hash구조를 가지고 있기 때문에 iloc, loc을 통해서 모든 인덱스에 대한 접근이 가능하고 O(1)의 시간복잡도로 column이나 Row를 불러올 수 있는데 , 조작이 미숙하여 for loop를 돌면서 하나하나 비교해가면서 인덱스를 가져오는 등 시간복잡도 측면에서 너무 비효율적인 code들이 많았다. 좀 더 능숙하게 사용할 수 있도록 연습이 필요하다.

## 👍[마무리]

---

Tabular Data를 이용한 Competition을 통해서 부족한 부분과 나의 강점을 파악할 수 있는 기회가 되었습니다. 코드 숙련도의 미숙, DataFrame 조작, 시각화 구현 미숙, Model에 대한 이해의 중요성, Feature분석의 중요성 등에 대해서 깨달았으며, data를 통해 해당 상황에 대한 상상을 하고 새로운 feature를 뽑아내고, validation의 중요성에 대해 특히 중요함을 느꼇습니다. validation의 신뢰성이 없다면 나의 가설을 검증할 방법이 없다는 것. 더 정확한 valid set을 구현해야 한다는 것을 이번 대회를 통해 절실히 느꼈습니다. 
 구현이 어렵다고 포기하지 않은 부분, 여러가지 가설을 세우고 도전한 것. 이 두 가지는 이번 경험을 통해서 나의 강점으로 남을 것 같습니다.



 ---
 
### inference.py
```
~$ python infernence.py --model --num_features --hidden_size --batch_size --seed 
```
### args:
  - model: [light_bgm, nn_model ,type=str, default=light_bgm] 
  > select which model to use 

  - num_features: [type=int , default=55] 
  > select feature nums 

  - hidden_size: [type=int, default=1024] 
  > how many nodes to use in hidden layer 

  - batch_size:[type=int, defalut=512] 
  > select batch_size

  - seed:[type=int, default=777] 
  > seed num for reproduction 

--- 

### utils.py 
  - seed_everything
  > set seed for reproduction

  - print_score
  > matric for evaluating score 
  - make_product_month
  > make obj-> numeric tpye of product_id with group_by month
  - make_month_over_train_300
  > feature extraction by bins of 3,6,9,20 month with groupby [customer_id ,year_month] ratio of over 300$
  - make_month_over_test_300
  > same with above but using year_month 2011-11
  - make_time_corr_train
  > feature extraction by bins of order_data 

  - make-time _corr_train
  > same with above
---
### features.py 

- generate_label
```
return label
```
> making labels by 2011-11 
- make_feature 
```
return x_tr, x_te
```
> transform obj-> numeric tpye and fill None values with Median values 
- feature_engineering1
```
return : x_tr, x_te, all_train_data['label'],features
```
> adding features and agg function for features 



