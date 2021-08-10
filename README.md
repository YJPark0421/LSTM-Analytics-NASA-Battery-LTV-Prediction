# Remaining Useful Life Prediction Using NASA Battery Data Set

## 1️⃣ Overview
### ◽ Objective
   - [x] NASA에서 제공하는 4개 셀 리튬이온 배터리 데이터를 명세하고 분석하여 데이터를 이해한다.
   - [x] 데이터 전처리 및 학습에 알맞은 형태로 가공한다.
   - [x] AI(ML/DL)기반의 다양한 방법론(알고리즘,모델)을 적용한 배터리 잔존수명예측 모델링을 진행한다.
---
### ◽ Development Environment
page_type | languages | products
:------:|:------:|:------:
　　　　　`Dev`　　　　　|　　`pyspark`　`python`　　|`azure`　`azure-databricks`
---
### ◽ NASA PCoE Battery Data
<p align="left"> <img src="https://user-images.githubusercontent.com/88306533/128735382-30fec59a-fcb7-4763-9f89-46c658035fa5.png" width="80%" height="80%"></img></p>

> **Download URL** - https://ti.arc.nasa.gov/tech/dash/groups/pcoe/prognostic-data-repository/
---
<br>

## 2️⃣ PreRequirement
### ◽ Understanding Data 
- SOH : State of Health
- RUL : Remaining Useful Life
- EOL : End of Life

### ◽ Data Structure 
 - ❶ cycle: top level structure array containing the charge, discharge and impedance operations

   |　cycle　|`⇦ Complex Data Structure( Nested Data )` |
   |:------:|:------:|
   
   ⏬

 - ❷ type: operation type, can be charge, discharge or impedance
 - ❸ Data: Nested Data Structure(Many Variables)

   |type | ambient_temperature | time | data|
   |:------:|:------:|:------:|:------:|
   |charge|`24℃`|`yyyy-MM-dd HH:mm:ss.SSSSSS`|`data`|
   |discharge |''|''|''|
   |impedance |''|''|''|
   
---
<br>

## 3️⃣ Methodology
### ◽ Part1 : Convert .mat to json
   > - [Part1_preprocessing.py](./Part2_preprocessing.py) **|** [Part2_preprocessing.ipynb](./Part2_preprocessing.ipynb)
### ◽ Part2 : LSTM Based Modeling
   > - [LSTM_Based_SOH_Prediction.py](https://github.com/YJPark0421/NASA-PCoE-Battery-Analytics/blob/master/Code/LSTM_Based_SOH_Prediction.py) **|** [LSTM_Based_SOH_Prediction.ipynb](https://github.com/YJPark0421/NASA-PCoE-Battery-Analytics/blob/master/Code/LSTM_Based_SOH_Prediction.ipynb)
### ◽ Understanding LSTM Networks
> **Read a Blog** - http://colah.github.io/posts/2015-08-Understanding-LSTMs/
---
<br>

## 4️⃣ Reference
> **URL①** - https://ieeexplore.ieee.org/document/8967059<br>
