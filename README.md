### Tabular Data code 

---

# ๐[Pstage_Competition]-Tabular Data

> Public Score : 0.8605 16๋ฑ

### ๐[๋ํ๊ฐ์]

---

![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/db560c06-7eeb-4687-abbe-4ab28704dc70/Untitled.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/db560c06-7eeb-4687-abbe-4ab28704dc70/Untitled.png)

### ๐ก[Date ์ ๋ณด]

---

![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/f349f77e-f5a3-40d4-adad-2852f6231900/Untitled.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/f349f77e-f5a3-40d4-adad-2852f6231900/Untitled.png)

![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/436b0717-f285-4430-84fb-817707e860b6/Untitled.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/436b0717-f285-4430-84fb-817707e860b6/Untitled.png)

- ์ฃผ์ด์ง Data์ feature๋ค์ ์ด์ฉํด์ ๋ค์ ๋ฌ ์๋น์๋ค์ด 300$์ด์์ ์๋น ์ ๋ฌด๋ฅผ ์์ธกํ๋ Competion์ด์์ต๋๋ค
- Data ์ปฌ๋ผ ์ค๋ช
    1. order_id=์ฃผ๋ฌธ๋ฒํธ, ๋ฐ์ดํฐ์์ ๊ฐ์ ์ฃผ๋ฌธ๋ฒํธ๋ ๋์ผ ์ฃผ๋ฌธ์ ๋ํ๋
    2. product_id: ์ํ ๋ฒํธ 
    3. description: ์ํ ์ค๋ช 
    4. quantitiy: ์ํ ์ฃผ๋ฌธ ์๋ 
    5. order_data: ์ฃผ๋ฌธ ์ผ์ 
    6. Price: ์ํ ๊ฐ๊ฒฉ 
    7. customer_id: ๊ณ ๊ฐ ๋ฒํธ 
    8. country: ๊ณ ๊ฐ ๊ฑฐ์ฃผ ๊ตญ๊ฐ 
    9. total : ์ด๊ตฌ๋งค์ก 

# ๐ก[EDA]

---

> Tabular Data์ ์์ด์ ๊ฐ์ฅ ์ค์ํ ๊ฑด Data์ ๋ํ ์ดํด์ ๋ถ์!

```markdown
๐ก์ ํ๋ฐ์ดํฐ์ ์์ด์ ์ ์ฒ๋ฆฌ์ ๋ฐ์ดํฐ ๋ถ์, ๋ถํฌ , ์๊ด ๊ด๊ณ, PCA ๋ฑ ์ ๋ง ๋ค์ํ ๋ฐฉ๋ฒ์ผ๋ก
 
data์์ ์๋ก์ด feature๋ฅผ ๋ง๋ค๊ณ  ์ ์ฉ ํ  ์ ์๋ค๋ ๊ฒ์ ๊นจ๋ฌ์ ์ ์๋ EDA์๋ค. 

๋ํ EDA๋ฅผ ํ๋ฉด์ ์ ๋ง data์์์ ์ด๋ค ์ผ์ด ์ผ์ด๋๊ณ  ์ด๋ค ์ํฉ์ด์๋์ง์ ๋ํด ์์ํ  ์ ์๋ค๋ฉด

data์ ๋ํ ์ดํด๋๊ฐ ๋์ ์ง ๊ฒ์ด๋ค
```

- ๊ฐ ๋ฐ์ดํฐ๋ค์ ๋ถํฌ, ํ๊ท  , Min, Max ,Std ๊ฐ๋ค ์๊ฐํ
- ์ ๋จ์ ํ๋งค๋
- ์ ๋จ์ Total 300 ์ด์ ๋น์จ
- Description์ ๋ํ ์ดํด
    1. Post,Bank Charges,Test,Adjust,M,Cruk๋ฑ product_id์ description์ ์๋ฌธ ๋ชจ๋ฅผ ๋จ์ด๋ค์ด ์์ 
    2. Test๋ ์์๋ก Testํด๋ณธ ๊ฒฐ๊ณผ ์ฆ, root ์์ด๋๋ก ์์๋ก Test์ํ์ ๋ง๋ ๊ฒ์ผ๋ก ์ถ์  
    Post๋ ํ๋ฐฐ๋ฅผ ๋ณด๋ธ ๊ฒ์ผ๋ก ์ถ์ 
    Bank_charges ํญ์ ์์ ๊ฐ์ผ๋ก ํ๊ธฐ๋๋ ๊ฑธ๋ก ๋ณด์ ์ธ๊ธ ์ง๋ถ๋ก ์ถ์ 
    Crukโ ์์  ๋จ์ฒด์  ๊ธฐ๋ถ
    Adjustโ test์ ๋ง์ฐฌ๊ฐ์ง๋ก ์กฐ์ 
- ๊ตญ๊ฐ๋ณ ๋ถํฌ๋ ์๊ฐํโ 90%์ ๋๊ฐ United Kingdom 10% ๋๋จธ์ง ๊ตญ๊ฐ๋ค โ Total๊ณผ์ ์ฐ๊ด์ฑ์ ์ ์ด ๋ณด์ธ๋ค
- Group_by_customer-quantityโ ๋ง์ด ์ฐ ์ฌ๋์ผ์๋ก 300$์ด์ ๊ตฌ๋งค ๋ถํฌ๊ฐ ๋์
๋ง์ด ์ฌ๋ฉด ๋น์ฐํ ๊ตฌ๋งค ๊ธ์ก์ด ์ปค์ง๋ ๋์ ์ ๋ฐ์ ์๋ค .
- Customer-order_idโ order_id๊ฐ ๊ฐ๋ค๋ฉด ํ๋ฒ์ ๊ฐ์ด ๊ตฌ๋งคํ ๋ชฉ๋ก โ ๋ง์ด ๊ตฌ๋งคํ ์ฌ๋์ 300$์ด์ ๊ตฌ๋งค ๋ถํฌ๊ฐ ๋์ quantitiy์ ๋น์ทํ ์ด์ 

## ๐ก[Environment]

---

- Window 10
- VsCode
- GPU-p40
- Python, Notebook

## ๐ก[Train & Valid Set]

---

- ๊ฒ์ฆ ์ ๋ต(Validation Test)
    1. StratifiedKFold -10Fold๋ฅผ ์ฌ์ฉํ์ฌ ๊ฐ ํด๋๋ณ๋ก AUC_Score๋ฅผ ๊ณ์ฐํ์ฌ 10ํด๋์ ๋ํด์ ๊ฐ๊ฐ best Auc_score๋ฅผ ์ฌ์ฉํ์์ต๋๋ค
- ์ฌ์ฉํ ๋ชจ๋ธ ์ํคํ์ณ ๋ฐ ํ์ดํผ ํ๋ผ๋ฏธํฐ
    1. Light_gbm
        - LB_Score: 0.86005
        - Feature ๊ฐ์ : 55๊ฐ

        ```markdown
        model_params:
        	'binary' -> ์ด์ง๋ถ๋ฅ
        	'gdbt' -> boosting type
        	'auc' -> ํ๊ฐ ์งํ
        	'feature_fraction'=0.8 -> ํผ์ณ ์ํ๋ง ๋น์จ
        	'bagging_fraction'=0.8 -> ๋ฐ์ดํฐ ์ํ๋ง ๋น์จ
        	'n_estimators'=10000 -> bagging freq
        	'early_stopping_rounds'=100
        	'seed'=777
        ```

        - Train: 2009-12~2011-10 ๊ธฐ๊ฐ์ ์ ์  data๋ฅผ ํตํด ํ์ต
        - Valid: 2009-12~2011-10 ๊ธฐ๊ฐ์ ์ ์  data๋ฅผ ํตํด 2012-11์ label ์์ธก
    2. NN_Model
        - LB Score: 0.8594

        ![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/a55d3b98-aca2-4254-ae5c-a62014484dd5/Untitled.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/a55d3b98-aca2-4254-ae5c-a62014484dd5/Untitled.png)

    - 3๊ณ์ธต layer  model
    - 3๋ฒ์ dropout, batchnorm ์ ์ฉ
    - Activation funtion์ผ๋ก Relu ์ฌ์ฉ
    - 512, 1024 ๊ฐ์ node๋ฅผ ๊ฐ์ง hidden layer ์ฌ์ฉ
    - Optimizerโ Adam
    - Lr=3e-4
    - Schedulerโ ReduceOnplatue(patience=8, gamma=0.2)

    ### โ[๋์ ํ ๊ธฐ์  ๋ฐ Feature]

    ---

    ### [Skill]

    - Out_of_fold ensambleโ 10๊ฐ์ ํด๋๋ฅผ ํตํด์ predict๊ฐ์ ๊ตฌํด์ meanํ ๊ฐ์ ์์ธก๊ฐ์ผ๋ก ์ฌ์ฉ . ์ผ์ข์ Regulation๊ธฐ๋ฒ
    - StratifiedKfoldโ label์ 0,1์ ๋น์จ์ด imbalanceํ๊ธฐ์ ๋ฐ์ดํฐ์ ๋ถํฌ๋ฅผ ๋ง์ถฐ์ Kfold์ฌ์ฉ โdata imbalence๋ฅผ ํด๊ฒฐ ๋ฐ Regulation๊ธฐ๋ฒ
    - NN_model & Tree_model Ensambleโ ํธ๋ฆฌ๋ชจ๋ธ์์ predictํ ๊ฐ๊ณผ nn ๋ชจ๋ธ์์ prdictํ ๊ฐ์ ์์๋ธโ Regulation
    - Batchnorm,Dropout โ ํผ์ณ๋ 50๊ฐ ์ ๋์ธ๋ฐ ๋ชจ๋ธ์ node๋ 512-1024-1024์ node๋ฅผ ๊ฐ์ง   feature์ ๋นํด ๋ชจ๋ธ์ด ๋๋ฌด ๋ณต์กํจ ์ฆ overfitting์ด ๋ฐ์ํ  ๊ฐ๋ฅ์ฑ์ด ํฌ๋ฏ๋ก, batchnorm๊ณผ dropout๋ฅผ ๋ชจ๋ ์ฌ์ฉํ์ฌ ๊ท์ ๋ฅผ ๊ฐํํจ

    ### [Feature]

    1. Base Feature aggโ ์ฑ๊ณต

    ```markdown
    ๐ก Feature๋ค์ ๋ํ [Min, Max, Mean, Sum, Count, Std, Skew, Quantile] Agg

    1.
    -> ์ฃผ์ด์ง Feature๋ค์ ๋ํด์ numericํ์ด ์๋ obj Type๋ค์ ๋ํด์ Label encoding ํน์
    ๊ฒฐ์ธก์น ๊ฐ์ ๋ํด์ SimpleInputer๋ฅผ ์ด์ฉํ์ฌ ๊ฒฐ์ธก์น ๊ฐ๋ค์ median๊ฐ์ผ๋ก ๋์ฒด ํด์ Feature
    ์ ๊ฐ์๋ฅผ ๋๋ ค ์ฃผ์์ต๋๋ค. 
    2.
    -> ์ฒ์์๋ data์ ๋ํ ์ดํด๋๊ฐ ๋ถ์กฑํด์ price, quantity, total ๋ฑ ๋ชจ๋  feature์ ๋ํด์ 
    agg๋ฅผ ํด์ฃผ์๋๋ฐ ์๊ฐํด๋ณด๋ฉด price*quantitiy=total ์ธ๋ฐ ๊ตณ์ด price์ quantity์ total์ด 
     ์ค๋ณต๋๋ ๋ถ๋ถ๋ค์ ๋ํด์๋ feature ๋ฅผ ์ถ๊ฐ ํด์ค ํ์๊ฐ ์์๋ค. 
    3.
    -> LB ์ ์ ํฌ๊ฒ ์์น ํ์ง๋ง ๋ชจ๋  ํผ์ณ์ agg๋ฅผ ์ฌ์ฉํ๊ธฐ์ ์๊ด๊ด๊ณ์ ๋ํ ์ดํด๊ฐ ๋ถ์กฑํ๊ณ 
    ์ด๋ค feature๊ฐ ์ค์ํ๊ณ  ์์ค์ํ์ง์ ๋ํ ์ดํด๊ฐ ๋ถ์กฑํ๋ค.

    [๋ฐฐ์ด์ ]
    โ ํญ์ feature๋ฅผ ์ถ๊ฐํ๊ฑฐ๋ agg๋ฅผ ํ  ๋ ๋ผ๋ฆฌ์ ์ผ๋ก ์ ๊ทผํ๊ณ  data๋ถ์์ ํตํด ๋ฉ๋ค ํ ๋งํ 
    ๊ทผ๊ฑฐ๋ฅผ ๊ฐ์ง๊ณ  ์๋ํด ๋ณผ๊ฒ . ๋ง๊ตฌ์ก์ด์ feature์ถ๊ฐ์ agg๋ ์คํ๋ ค ๋ ๋์ ๋ชจ๋ธ์ ๋ง๋๋๋ฐ์ 
    ์์ด์ ๋์ด ๋  ์ ์๋ค. 
    ```

    2. ์๊ฐ Feature ์ถ๊ฐ โ ์คํจ LB_score ํ๋ฝ

    ```markdown
    ๐ก Customer_id ๋ณ๋ก ์ด๋ ์๊ฐ๋์ ์๋์ง -> ์ฃผ๋ก ์์นจ์ ์๋์ง, ์ ์ฌ์ ์๋์ง, ์ ๋์
    ์๋์ง์ ๋ํด ๋๋ ์ label_encoding์ ํตํด feature๋ก์จ ์ฌ์ฉํ๋ค. 

    [์ ๊ทผ๋ฒ]
    ์์นจ์ ์ฌ๋ ์ฌ๋์ ์๋งค์์ผ ๊ฒฝ์ฐ๊ฐ ํฌ๋ค-> ์ผ๋ฐ์ธ์ ๊ฒฝ์ฐ ์์นจ-๋ฎ ์๊ฐ๋์ ์ง์ฅ, ํ๊ต, 
    ๋ฑ ์๋ฌด๋ฅผ ๋ณด๋ ์๊ฐ์ด ๋ง์ ๊ฒ์ด๋ผ๋ ์๊ฐ์์ ์ ๊ทผํ์๋ค. ์๋งค์์ผ ๊ฒฝ์ฐ๋ ์๋ฌด๊ฐ ๋ฌผ๊ฑด์
    ์ฌ๊ณ  ํ๋ ์ผ์ด๋ ์๋ฌด๋ก์จ ์์นจ์๊ฐ๋์ ๋ฌผ๊ฑด์ ์์ ๊ฒ์ด๋ผ๊ณ  ์ ๊ทผ ํ์๋ค.
    ์ฆ -> ์๋งค์๋ค์ ์ผ๋ฐ์ธ๋ค ๋ณด๋ค ๋ฌผ๊ฑด์ ๋ค๋ ๊ตฌ์ํ๋ , ๋ ๋์ ํ๋ฅ ๋ก 300๋ฌ๋ฌ๋ฅผ ์ด ๊ฒ์ด๋ค

    [์คํจ์์ธ ๋ถ์]
    ์ด๋ฏธ feature๋ก์ ์ฌ์ฉํ๋ quantity์ ๊ตฌ๋งค ๊ฐ์๊ฐ ์๋ค. ์ฆ quantity๋ฅผ ํตํด์๋ 
    ๊ทธ ์ฌ๋์ด ์๋งค์์ธ์ง ์ผ๋ฐ์ธ์ธ์ง ๊ตฌ๋ถ ๊ฐ๋ฅ ํ ๊ฒ์ด๋ผ๊ณ  ์ถ๋ก ํ์๊ณ  quantity์ ํน์ฑ์ด 
    ์๋ฌด๋๋ ์๊ฐ์ผ๋ก ๋๋ ๊ฒ๋ณด๋ค ๋ ์ ํํ๊ฒ ๊ตฌ๋ถ์ด ๊ฐ๋ฅํด์ ์คํ๋ ค ์ ์๊ฐ ํ๋ฝํ๋ค๊ณ  
    ์๊ฐํ๋ค. 
    ```

    3. ๊ธฐ๊ฐ ๋ณ Total 300 ์ด์ ๋น์จ Feature ์ถ๊ฐโ ์ฑ๊ณต

    ```markdown
    ๐ก ๊ธฐ๊ฐ๋ณ๋ก ๋๋์ด์ customer์ 300๋ฌ๋ฌ ์ด์์ ๋น์จ์  feature ๋ก ์ฌ์ฉํ์๋ค.

    [์ ๊ทผ๋ฒ]
    1. predict๋ 300๋ฌ๋ฌ๋ฅผ ๊ธฐ์ค์ผ๋ก ๊ทธ ์ด์์ด๋ ์ดํ๋ฅผ predictํ๋ ๋ฌธ์ ์ธ๋ฐ 300๋ฌ๋ฌ์ 
    ๊ด๋ จ๋ feature๊ฐ total ํ๋๋ฐ์ ์์ -> 300๋ฌ๋ฌ์ ๊ดํfeature๊ฐ ๋๋ฌด ์ ๋ค๊ณ  ์๊ฐ 

    2. ์ต๊ทผ 3, 6, 12,20 ๊ฐ์์ ๋ํด์ 300๋ฌ๋ฌ๋ฅผ ๋๋ total๊ฐ์ ๋น์จ์ ๊ตฌํ์ฌ feature๋ก์จ 
    ์ถ๊ฐํด ์ฃผ์๋ค . 

    ์ ๊ธฐ๊ฐ์ ๋๋ด๋๊ฐ? ๋ฌผ๊ฑด์ ์ด๋ค ์ฌ์ดํธ์์ ์ฌ๋๋ฐ ์์ด์ ์ต๊ทผ ๊ตฌ๋งค์ผ ์ฆ ์ต๊ทผ์ ์ธ์  ์๋
    ๊ฐ๋ ๊ต์ฅํ ์ค์ํ ํน์ง์ด๋ผ๊ณ  ์๊ฐํ๊ธฐ ๋๋ฌธ์ด๋ค. ์ฆ 1๋์ ์ 10๋ฒ ๊ตฌ๋งคํ ๊ฒ๊ณผ ์ต๊ทผ 3๊ฐ์๊ฐ
    10๋ฒ ๊ตฌ๋งคํ ๊ณ ๊ฐ์ด ์๋ค๋ฉด ๋น์ฐํ ์ต๊ทผ 3๊ฐ์ 10๋ฒ ๊ตฌ๋งคํ ๊ณ ๊ฐ์ด ๋ค์๋ฌ์ ๊ตฌ๋งคํ  ํ๋ฅ ์ด ๋๋ค๋
    ์๊ฐ์ผ๋ก ์ ๊ทผํ์๋ค. 
    ํ์ง๋ง ์ต๊ทผ 300๊ฐ์์ ๊ธฐ๋ก๋ง ๋ณธ๋ค๋ฉด 0์ ๋น์จ์ด ๋๋ฌด ๋๋ค ์ฆ ๋ชจ๋ธ์ด 0์ผ๋ก overfitting
    ๋  ๊ฒ์ ์๊ฐํ์ฌ ๊ทธ 6,12,20 ๊ฐ์์ ๋ถ์ํ feature๋ค์ ์ถ๊ฐ ํ์๋ค. ํ์ง๋ง ์ ํํ ๊ฒ์ฆ์
    ํ์ง ๋ชปํ ํ์ ์ด๋ ์์ ์ด ๊ฐ์ฅ ์ค์ํ feature์ด ์ด๋ค ๊ฒ์ด ์ข์ง ๋ชปํ feature์๋์ง์ 
    ๋ํ ํ์ ์ ์ป์ง๋ ๋ชปํ์๋ค. 

    [์์ฌ์ด์ ]
    ์ข์ ์ ๊ทผ ๋ฐฉ๋ฒ์ด์๋ค๊ณ  ์๊ฐํ๊ณ  ์๊ฐ๋๋ก LB_score์ ํฅ์๋ ์์๋ค. ํ์ง๋ง, valid_set์
    ์ ๋น์ฑ์ด ๋จ์ด์ง๋ ํ์ ๊ฒ์ฆ์ ์๋ฒฝํ๊ฒ ํ์ง ๋ชปํ๊ณ  ์ค์ง LB score๋ก๋ง ์ง์ ํ  ์ ์์๋ค.
    ```

    4. ์ product_id*quantity ๋น์จ Feature ์ถ๊ฐ โ ์คํจ

    ```markdown
    ๐ก ์๋ณ๋ก product_id*quantity/์ ์ฒด product_id*quantity ์ ๋น์จ์ feature ์ฌ์ฉ

    [์ ๊ทผ๋ฒ]
    ์ํ๋ณ๋ก ๊ณ์ ์ ๋ฐ๋ผ ์ํ๋ฆฌ๋ ์ํ๊ณผ ํ๋ฆฌ์ง ์๋ ์ํ๋ค์ด ์๋ค๋ ๊ฒ์ EDA๋ฅผ ํตํด 
    ๋ถ์ํ์๋ค. ์ฆ, ์ฌ๋ฆ ์ ํ์ ๋ง์ด ์ฌ๋ ๊ณ ๊ฐ์ ๊ฒจ์ธ ์ํ์ ์ฌ์ง ์์ ๊ฒ์ด๋ค. ๊ฒจ์ธ ์ ํ์ 
    ์ฌ๋ ๊ณ ๊ฐ์ ์ฌ๋ฆ ์ ํ์ ์ฌ์ง ์์ ๊ฒ์ด๋ค ๋ผ๋ ์๊ฐ์์ ์ ๊ทผ ํ์๋ค.

    [์คํจ์์ธ]
    Data๋ฅผ ๋ถ์ํด๋ณธ ๊ฒฐ๊ณผ ํ์คํ ์๋น์ ๋ณ๋ก ์ฌ๋ฆ/๊ฒจ์ธ์ ๋ํ ์ํ ์ ํธ๋๊ฐ ์๊ธด ํ์๋ค.
    ํ์ง๋ง ์ํ ์ ํธ๋์ 300๋ฌ๋ฌ์ ์ฐ๊ด์ฑ์ด ํฌ์ง ์์๋ ๊ฒ์ผ๋ก ์๊ฐ๋๋ค. 
    ```

    5. PCA ๊ธฐ๋ฒ์ผ๋ก  feature ์ถ๊ฐโ ์คํจ 

    ```markdown
    ๐ก์ฌ์ฉํ๊ณ  ์๋ feature๋ค์ PCA๊ธฐ๋ฒํ์ฌ ์๋ก์ด 10๊ฐ์ PCA feature๋ฅผ ์ถ๊ฐ 

    [์ ๊ทผ๋ฒ ]
    ์ฌ์ฉํ๊ณ  ์๋ feature๊ฐ 30~40๊ฐ ์ ๋์๋๋ฐ  ์ด feature๋ค์ ๊ด๊ณ๋ฅผ ์๋ก์ด 10์ฐจ์์ผ๋ก 
    ์ค์ฌ์ 10๊ฐ์ feature๋ก ์๋ก ์์ฑํ๋ค๋ฉด ์ด๋ค ์๋์ง ํจ๊ณผ๋ฅผ ๋ด์ง ์์๊น ๋ผ๋ ์๊ฐ์ผ๋ก ์ ๊ทผ

    [์คํจ ์์ธ]
    ์ฌ์ฉํ๊ณ  ์๋ feature๋ค์ด ๋ชจ๋ ๊ฒ์ฆ๋ feature์ด ์๋์๋ค. ์ฆ feature๋ค๊ฐ์ ์๊ด๊ด๊ณ ๋ฐ
    ์ ํํ ํน์ง๋ค์ ์ดํดํ์ง ๋ชปํ ์ํ์์ PCA๋ฅผ ํตํด ์๋ก์ด feature๋ฅผ ์ถ๊ฐํ๋ค ๊ทธ feature
    ๋ค์ด ์ด๋ ํ ์ฐ๊ด์ฑ์ด๋ ์๋ก์ด ํน์ง์ ๋ง๋ค์๋ค๊ณ  ์๊ฐํ๊ธฐ ์ด๋ ต๋ค.. 

    [๋ฐฐ์ด์ ]
    ์์ ์ด ์ฌ์ฉํ๋ feature์ ํน์ง์ ๋ชํํ ์ดํดํด์ผ PCA๊ธฐ๋ฒ์ผ๋ก feature๋ค๊ฐ์ ์๋ก์ด
    ํน์ง์ ๋ฝ์ ๋ผ ์ ์๋ค๊ณ  ์๊ฐํ๋ค. ์ฆ ๋ง์ฐํ๊ฒ ์ฌ๋ฌ skill๋ค์ ์ฌ์ฉํ๋ค๊ณ  ๋ด feature์
    ๋ง๋ ๊ฒ์ด ์๋๋ผ๋ ๊ฒ
    ```

    6. ์ต๊ทผ/๋ง์ง๋ง ๊ตฌ๋งค์ผ feature ์ถ๊ฐ โ ์ฑ๊ณต 

    ```markdown
    ๐กRecent_buy๋ผ๋ Feature๋ฅผ ์ถ๊ฐ -> ๊ณ ๊ฐ์ด ๊ฐ์ฅ ์ต๊ทผ์ ์ธ์  ๊ตฌ๋งคํ๋ ํน์ ๊ฐ์ฅ ๋ง์ง๋ง 
    ๊ตฌ๋งค์ผ ์ธ์ ์ธ๊ฐ๋ฅผ feature๋ก์จ ์ถ๊ฐ ํ์

    [์ ๊ทผ๋ฒ]
    ์์ธกํด์ผ ํ๋ ์๊ณผ ์ต๊ทผ ๊ตฌ๋งค์ผ์ด ๊ฐ๊น๋ค๋ฉด ๋ ๋ค์ ์ดํ๋ฅ ์ด ๋๋ค๋ ์์ด๋์ด์์ ์ฐฉ์ 
    ์ฆ ํ๋ฌ์ ์ ๋ฌผํ์ ์ฐ ๊ณ ๊ฐ์ด 1๋์ ์ ๋ฌผํ์ ์ฐ ๊ณ ๊ฐ๋ณด๋ค ๋ค์๋ฌ์ ๊ตฌ๋งคํ  ํ๋ฅ ์ด ๋๋ค๊ณ 
    ์๊ฐํ์๋ค .
    [์ฑ๊ณต์ด์ ]
    ์๊ฐํ๋๋ก ์ต๊ทผ์ ์ฐ ๊ณ ๊ฐ์ผ์๋ก ๋ค์๋ฌ์๋ ์ด ํ๋ฅ ์ด ๋๋ค๋ ๊ฒฐ๊ณผ๋ฅผ ์ป์๊ณ  , score์๋
    ์์น์ด ์์๋ค.
    ```

## ๐ข[์์ฌ์ด์ ]

---

1. Train data์ ๋ถ์กฑ : 

 ํ์ต ๋ฐ์ดํฐ๋ 2๋์ด ์๋๋ ๊ธฐ๊ฐ์ด์๊ณ  ๋ชจ๋  data๋ฅผ ์ฌ์ฉํ์ฌ 11์ ํ๋ ๋ง์ ์์ธกํ๋ train๊ณผ์ ์ ๊ฑฐ์ณ์ ๊ฒ์ฆ์ ํ์์.
 ํ์ง๋ง ๊ด์ ์ ์กฐ๊ธ ๋ฐ๊ฟ์ train์  9,10,11์์ ๋ํด train ์์ผฐ๋ค๋ฉด train_data๋ฅผ ๋ ๋๋ฆฌ๋ฉด์ ์ข ๋ ๋์ score๋ฅผ ๋ฐ์ ์ ์์ง ์์์๊น ๋ผ๋ ์๊ฐ์ ํ๊ณ , ์ค์ ๋ก๋ ์์๊ถ ์ ์ ๋ค์ด train_set์ ๋๋ ค์ ํ์ต์ ์์ผฐ๋ค๊ณ  ํ๋ค.
`์๊ฐํ ๊ฒ์ ์ด๋ ต๋๋ผ๋ ์ค์ฒํด๋ณผ๊ฒ!`

2. ์๊ฐํ ๊ตฌํ์ ๋ถ์กฑ : 

์ฌ๋์ด ๋ง์ ์์ data๋ฅผ ๋ณด๊ณ  ์ง๊ด์ ์ผ๋ก ์ด๋ค ๋ถํฌ๋ฅผ ๊ฐ๊ณ  ์ด๋ค ํน์ฑ์ ๊ฐ๋์ง ๋ถ์ํ๊ธฐ๋ ์ด๋ ต๋ค.
 ๊ทธ๋์ data๋ฅผ ์๊ฐ ํ ํ์ฌ ๋ถ์ํ๋ฉด ์ข ๋ ์ง๊ด์ ์ผ๋ก ๋ถ์ํ  ์ ์๊ณ  ์์ ์ ๊ฐ์ค์ ๋ํ ์ ๋ขฐ์ฑ์ ์ป์ ์ ์๋ค.  ํ์ง๋ง ์๊ฐํ๋ฅผ ๋ง์ด ์ฐ์ตํด ๋ณด์ง ์์๋ ํ์ data๋ฅผ ์๊ฐํํ๋๋ฐ ์ด๋ ค์์ ๋ง์ด ๊ฒช์๊ณ  , ๋ด ๊ฐ์ค์ ์๊ฐํํ์ฌ ๊ฒ์ฆํ์ง ๋ชปํ ๊ฒฝ์ฐ๊ฐ ์ข์ข ์์๋ค.
`์๊ฐํ๋ ๊ตฌํ์ฐ์ต์ ๊ณ์ํด๋ณผ ๊ฒ!`

3. Tree_Model์ ๋ํ ์ดํด๋ ๋ถ์กฑ:

Tree_model์ ์ด๋ฒ ๊ฒฝํ์ ํตํด์ ์ฒ์ ์ ํด๋ดค๋๋ฐ, bagging,boosting๋ฑ ๋ค์ํ ๋ฐฉ๋ฒ๊ณผ entropy, Gini , info_gain๋ฑ ๋ค์ํ ๋ฐฉ๋ฒ์ ํตํด์ node๋ค์ ์์ฑํด ๋ธ๋ค๋ ๊ฒ์ ๋ฐฐ์ธ ์ ์์๊ณ , deep learning model์๋ ๋ถ๋ฅ๊ธฐ์ ์ญํ ์ ํ๋ ๋งํผ
์ํ์  ๊ณ์ฐ์ ์๊ตฌํ๋ ๋ด์ฉ๋ค์ด ๋ง์๋ค. ์์ง ๋ชจ๋ธ์ ๋ํ ์ดํด๊ฐ ๋ถ์กฑํ๋ค๋ ๊ฒ์ ๊นจ๋ฌ์๊ณ , ๋ชจ๋ธ์ ์ดํด๊ฐ ๋จ์ด์ง๋ model_tuning์ ์ ๋๋ก ํ  ์ ์์๊ณ  sota์ ์ฑ๋ฅ์ ์ด๋์ด๋ด์ง ๋ชปํ๋ค๊ณ  ์๊ฐํ๋ค. 
`ํธ๋ฆฌ๋ชจ๋ธ์ ๋ํ ์ดํด๋ ๋์ด๊ธฐ`

4. DataFrame ์กฐ์ ๋ฏธ์:

Pandas์ DataFrame ์ ์ด์ฉํ์ฌ csvํ์ผ์ ๋ค๋ฃจ๊ฑฐ๋ ๊ธฐ๋ณธ์ ์ธ function๋ค๋ง ์ฃผ๋ก ์ฌ์ฉํ์๋ค. ์ด๋ฒ ๊ฒฝ์ฐ์ฒ๋ผ feature๋ค์ ์๋ก ๋ง๋ค๊ณ  ํด๋ณธ ๊ฒฝํ์ด ์์๋ ํ์ด๋ค. columns๋ค์ด ๊ณ์ธต ๊ตฌ์กฐ๋ฅผ ์ด๋ฃฐ ์ ์๊ณ  ์ด๊ฒ์ ๋ํด ์ ๊ทผํ๋ ๋ฐฉ๋ฒ ๋ํ ์กด์ฌํ์๊ณ   groupby,concat,merge๋ฑ sql์์ ์ฃผ๋ก ์ฌ์ฉํ๋ function๋ค์ด DataFrame์๋ ๋ชจ๋ ๊ตฌํ๋์ด ์์์ ์์๋ค. DataFrame์ Hash๊ตฌ์กฐ๋ฅผ ๊ฐ์ง๊ณ  ์๊ธฐ ๋๋ฌธ์ iloc, loc์ ํตํด์ ๋ชจ๋  ์ธ๋ฑ์ค์ ๋ํ ์ ๊ทผ์ด ๊ฐ๋ฅํ๊ณ  O(1)์ ์๊ฐ๋ณต์ก๋๋ก column์ด๋ Row๋ฅผ ๋ถ๋ฌ์ฌ ์ ์๋๋ฐ , ์กฐ์์ด ๋ฏธ์ํ์ฌ for loop๋ฅผ ๋๋ฉด์ ํ๋ํ๋ ๋น๊ตํด๊ฐ๋ฉด์ ์ธ๋ฑ์ค๋ฅผ ๊ฐ์ ธ์ค๋ ๋ฑ ์๊ฐ๋ณต์ก๋ ์ธก๋ฉด์์ ๋๋ฌด ๋นํจ์จ์ ์ธ code๋ค์ด ๋ง์๋ค. ์ข ๋ ๋ฅ์ํ๊ฒ ์ฌ์ฉํ  ์ ์๋๋ก ์ฐ์ต์ด ํ์ํ๋ค.

## ๐[๋ง๋ฌด๋ฆฌ]

---

Tabular Data๋ฅผ ์ด์ฉํ Competition์ ํตํด์ ๋ถ์กฑํ ๋ถ๋ถ๊ณผ ๋์ ๊ฐ์ ์ ํ์ํ  ์ ์๋ ๊ธฐํ๊ฐ ๋์์ต๋๋ค. ์ฝ๋ ์๋ จ๋์ ๋ฏธ์, DataFrame ์กฐ์, ์๊ฐํ ๊ตฌํ ๋ฏธ์, Model์ ๋ํ ์ดํด์ ์ค์์ฑ, Feature๋ถ์์ ์ค์์ฑ ๋ฑ์ ๋ํด์ ๊นจ๋ฌ์์ผ๋ฉฐ, data๋ฅผ ํตํด ํด๋น ์ํฉ์ ๋ํ ์์์ ํ๊ณ  ์๋ก์ด feature๋ฅผ ๋ฝ์๋ด๊ณ , validation์ ์ค์์ฑ์ ๋ํด ํนํ ์ค์ํจ์ ๋๊ผ์ต๋๋ค. validation์ ์ ๋ขฐ์ฑ์ด ์๋ค๋ฉด ๋์ ๊ฐ์ค์ ๊ฒ์ฆํ  ๋ฐฉ๋ฒ์ด ์๋ค๋ ๊ฒ. ๋ ์ ํํ valid set์ ๊ตฌํํด์ผ ํ๋ค๋ ๊ฒ์ ์ด๋ฒ ๋ํ๋ฅผ ํตํด ์ ์คํ ๋๊ผ์ต๋๋ค. 
 ๊ตฌํ์ด ์ด๋ ต๋ค๊ณ  ํฌ๊ธฐํ์ง ์์ ๋ถ๋ถ, ์ฌ๋ฌ๊ฐ์ง ๊ฐ์ค์ ์ธ์ฐ๊ณ  ๋์ ํ ๊ฒ. ์ด ๋ ๊ฐ์ง๋ ์ด๋ฒ ๊ฒฝํ์ ํตํด์ ๋์ ๊ฐ์ ์ผ๋ก ๋จ์ ๊ฒ ๊ฐ์ต๋๋ค.



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



