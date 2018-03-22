# Assignment-18.2

Question 5: Which route genrating the most revenue per year

sqlContext.sql("SELECT From,To,Sum(Fare) Fare from Final Group by From,To ORDER BY 3 DESC").show()

![q1](https://user-images.githubusercontent.com/34162166/37766987-a84a8ba8-2dee-11e8-91fe-529038ce707a.png)


Question 6: What is the total amount spent by every user on air travel per year

sqlContext.sql("SELECT UserID,Year,Sum(Fare) Fare from Final Group by UserID,Year ORDER BY 3 DESC").show()

![q2](https://user-images.githubusercontent.com/34162166/37766988-a887eb38-2dee-11e8-9011-fd0d25a05d1b.png)

Question 7: Consendering age group of <20 ,20-35, 35>, which age is group is travling the most every Year.

val AgeGroup=sqlContext.sql("SELECT CASE WHEN Age < 20 THEN '<20' WHEN Age >=21 and Age <=35 THEN '20-35' WHEN Age>35 then '35>' end AgeGroup ,Year,Fare Fare from Final")
sqlContext.sql("SELECT AgeGroup,Year,Sum(Fare) TotalFare from AgeGroup Group by AgeGroup,Year ORDER BY 3 DESC").show()

![q3](https://user-images.githubusercontent.com/34162166/37766990-a8cdacb8-2dee-11e8-9563-bba7184de859.png)
