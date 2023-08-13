# Stroke-analysis-and-Prediction
## Table of Contents
- [Dataset](#dataset)
    - [Data Exploration](#data-exploration)
    - [Data Cleansing](#data-cleansing)
- [Objective](#objective)
- [Techniques](#animals--nature)
    - [Correlation](#travel--places)
    - [Logistic Regression](#activities)
    - Decision Tree
    - F1 Score
- [Conclusion](#food--drink)




### Dataset

- Get the Data From [Kaggle](https://www.kaggle.com/datasets/fedesoriano/stroke-prediction-dataset)

#### Data Exploration
> df.head(5)

| | id | gender | age | hypertension | heart_disease | ever_married |	work_type | Residence_type | avg_glucose_level | bmi | smoking_status |stroke |
| - | - | - | - | - | - | - | - | - | - | - | - | - |
| 0 |	9046 |	Male |	67.0 |	0 |	1 |	Yes |	Private |	Urban |	228.69 |	36.6 |	formerly smoked |	1 |
| 1 |	51676 |	Female | 	61.0 |	0 |	0 |	Yes |	Self-employed |	Rural |	202.21 |	NaN |	never smoked |	1 |
| 2 |	31112 |	Male |	80.0 |	0 |	1 |	Yes |	Private |	Rural |	105.92 |	32.5 |	never smoked |	1 |
| 3 |	60182 |	Female |	49.0 |	0 |	0 |	Yes |	Private |	Urban |	171.23 |	34.4 |	smokes |	1 |
| 4 |	1665 |	Female |	79.0 |	1 |	0 |	Yes |	Self-employed |	Rural |	174.12 |	24.0 |	never smoked |	1 |

> df.hist(bins=30, figsize=(15, 10))

![image](images/histogram.png)

#### Data Cleansing
- ตรวจเช็คค่า Null
- แทนค่าที่เป็น Null ในคอลัมน์ bmi ด้วยค่าเฉลี่ย (Mean)
- แทนเพศ Other ให้เหลือเพียงเพศชายและหญิง โดยแทนด้วยเพศที่มากกว่า (เพศหญิง)
- Mapping กับคอลัมน์ที่มีชนิดข้อมูลเป็น String ให้กลายเป็นข้อมูลชนิด Integer (0 หรือ 1)
- เปลี่ยน Type ของคอลัมน์ age จาก Float ใหเ้ป็น Integer
- Drop คอลัมน์ที่ไม่ได้ใช้ ในที่นี้เลือก drop คอลัมน์ 'id'  เนื่องจากไม่ใช่ตัวแปรที่มีผลต่อการทำนาย

### Objective
- เพศหญิงกับเพศชายเพศไหนมีโอกาสเป็นโรคหลอดเลือดสมองมากกว่ากัน
- โรคหลอดเลือดสมองสามารถเกิดขึ้นในวัยใดมากที่สุด
- ผู้ป่วยที่เป็นโรคหัวใจมีโอกาสเป็นโรคหลอดเลือดสมองด้วยหรือไม่
- ระหว่างคนที่อยู่ในชนบทกับในเมือง อยู่ที่ไหนมีโอกาสเป็นโรคหลอดเลือดสมองมากกว่า
- เพื่อทำนายว่าผู้ป่วยเป็นโรคหลอดเลือดสมองหรือไม่
- ปัจจัยที่ทำให้เป็นโรคหลอดเลือดสมองมีอะไรบ้างและต้องมีลักษณะยังไง (ตัวแปรใดส่งผลต่อ target)





