# Business Case: What affect to Yulu's revenues

I'm interested in trying statistics to solve real-world problems. So I'm going to try to solve why the company's revenue is declining and how to improve it. I use `R` and `SQL` programming with `Hypothesis testing`

This project refers to https://www.kaggle.com/datasets/ranitsarkar01/yulu-bike-sharing-data

## About Yulu

Yulu is India’s leading micro-mobility service provider, which offers unique vehicles for the daily commute. Starting off as a mission to eliminate traffic congestion in India, Yulu provides the safest commute solution through a user-friendly mobile app to enable shared, solo and sustainable commuting. Yulu zones are located at all the appropriate locations (including metro stations, bus stands, office spaces, residential areas, corporate offices, etc) to make those first and last miles smooth, affordable, and convenient!

Yulu has recently suffered considerable dips in its revenues. They have contracted a consulting company to understand the factors on which the demand for these shared electric cycles depends. Specifically, they want to understand the factors affecting the demand for these shared electric cycles in the Indian market.

## 1. Ask 

Here are exemple question

- Which variables are significant in predicting the demand for shared electric cycles in the Indian market?

- How well those variables describe the electric cycle demands?

## 2. Prepare 

- Install package, Load library, Read dataset

## 3. Process 

- Check NA data, Change to date time format, etc..

## 4. Analysis 

- Find correlation with the demand for shared electric cycles
    - season	0.16
    - holiday	-0.01
    - workingday	0.01
    - weather	-0.13
    - temp	0.39
    - atemp	0.39
    - humidity	-0.32
    - windspeed	0.10
    - time	0.40
 
 Correlation of 0.3 or higher is often considered moderately strong. So `temp`, `atemp` ,`humidity` and `time` parameter are moderately correlation to electric cycles depends.
    
![__results___18_3](https://user-images.githubusercontent.com/77894515/232005237-5e610645-b196-465d-af95-483e000610e8.png)

- Most demand in June, July, August and September.

## 5. Hypothesis testing 

#### Has Working Day effect on number of electric cycles rented?

- Define hypothesis
  - H0: There is no significant difference in the number of electric cycles rented on working days and non-working days.
  - Ha: There is a significant difference in the number of electric cycles rented on working days and non-working days.
  
- Prepare data
  - Set workday and no workday data
  
- Statistical test
  - Perform Welch's t-test = 0.2164
  
- Conclusion
  - We can conclude that the means of electric cycles rented on working day and no working day are **not significant difference**.
    
## 6. Conclusion 

Here is my conclusion.

- Most relative parameter to cycle demand are `time` , `temp` , `feeling temp` and `humunity`.
- Most demand in evening time (16PM-19PM).
- Most temperature cycle demand are 28.70, 26.24 and 29.52 celsius.
- Most feeling temperature cycle demand are 31.06 , 32.57 and 33.33 celsius.
- Most humidity cycle demand are 46, 55 and 49.

And

- The number of cycles rented is significant different across seasons by highest rented in Rainy season.
- The number of cycles rented is significant different across weather by highest rented in Clear, Few clouds, partly cloudy, partly cloudy weather.

However

- The means of electric cycles rented on working day and no working day are not significant difference.
- There is no significant relationship between season and weather.

**Please see full paper:** [Click Here](https://github.com/golfung/Data_Analysis/blob/main/What_affect_to_Yulu%E2%80%99s_revenues/business-case-what-affect-to-yulu-s-revenues.ipynb)
