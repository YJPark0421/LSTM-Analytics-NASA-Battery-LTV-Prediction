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

   |type | ambient_temperature | time | data|
   |:------:|:------:|:------:|:------:|
   |charge|`24℃`|`yyyy-MM-dd HH:mm:ss.SSSSSS`|`data`|
   |discharge |''|''|''|
   |impedance |''|''|''|

   ⏬
   
 - ❸-1) Data : type = charge

   |type | ambient_temperature | time | data
   |:------:|:------:|:------:|:------|
   |charge|`24℃`|`yyyy-MM-dd HH:mm:ss.SSSSSS`|Voltage_measured|
   |''|''|''|Current_measured|
   |''|''|''|Temperature_measured|
   |''|''|''|Current_charge|
   |''|''|''|Voltage_charge|
   |''|''|''|Time|

   ⏬

- ❸-2) Data : type = discharge

   |type | ambient_temperature | time | data
   |:------:|:------:|:------:|:------|
   |discharge|`24℃`|`yyyy-MM-dd HH:mm:ss.SSSSSS`|Voltage_measured|
   |''|''|''|Current_measured|
   |''|''|''|Temperature_measured|
   |''|''|''|Current_charge|
   |''|''|''|Voltage_charge|
   |''|''|''|Time|
   |''|''|''|Capacity|

   ⏬

 - ❸-3) Data : type = impedance

   |type | ambient_temperature | time | data
   |:------:|:------:|:------:|:------|
   |impedance|`24℃`|`yyyy-MM-dd HH:mm:ss.SSSSSS`|Sense_current|
   |''|''|''|Battery_current|
   |''|''|''|Current_ratio|
   |''|''|''|Battery_impedance|
   |''|''|''|Rectified_impedance|
   |''|''|''|Re|
   |''|''|''|Rct|
---
<br>

## 3️⃣ Methodology
### ◽ Part0 : Overview
### ◽ Part1 : 
   > - [Part1_.py](./Part1_.py) **|** [Part1_.ipynb](./Part1_.ipynb)
### ◽ Part2 : Convert .mat to json
   > - [Part2_preprocessing.py](./Part2_preprocessing.py) **|** [Part2_preprocessing.ipynb](./Part2_preprocessing.ipynb)
### ◽ Part3 : LSTM Based Modeling
   > - [Part3_.py](./Part3_.py) **|** [Part3_.ipynb](./Part3_.ipynb)
### ◽ Understanding LSTM Networks
> **Read a Blog** - http://colah.github.io/posts/2015-08-Understanding-LSTMs/
---
<br>

## 4️⃣ Reference
> **URL①** - https://ieeexplore.ieee.org/document/8967059<br>
