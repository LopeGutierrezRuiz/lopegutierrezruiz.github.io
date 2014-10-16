# 273D - Data Journalism


**Homework: 2014-10-14**
The name "Lope" is not very common, so I'm using the name “Andrea”, given that it has plenty of records both for male and female. 

**01) In the year 2013, find out how many babies had your name**
There were 2808 female and 12 male Andreas born on 2013 = 2830

> SELECT * FROM ssa_baby_names
WHERE name = "Andrea"

**02) Find the highest-rank (and the year) that your name has achieved among baby names**
The highest rank for Andrea (female) was 24th, achieved in 1981; while for Andrea (male) was 694, also achieved in 1981

> SELECT * FROM ssa_baby_names
WHERE name = "Andrea" 

**03) Between the years 1980 and 2013, find how many babies in total have been listed by the Social Security Administration in this data.**
There were a total of 126,036,079 babies listed between 1980 and 2013.

> SELECT count,
	SUM(`count`)
FROM ssa_baby_names

**04) Find out how many babies (roughly) have had your name from 1980 to 2013**
SSA lists 225,499 female and 2,340 male matches, for a total of 227,839 Andreas.

> SELECT * FROM ssa_baby_names
WHERE name = "Andrea"

**05) Find the year that had the most male babies born**
The most male babies in a year were born on 1981 (68,740)

> SELECT  `count`, `sex`, `year`
FROM ssa_baby_names
WHERE sex = "M"
GROUP BY `year`

**06) Find the year in which your name had the highest increase in names-per-100k-babies born**
Highest increase happened in 1981. The name increased in 71-per-100K people that year.

> SELECT * FROM ssa_baby_names
WHERE name = "Andrea"

**07) Find the year in which your name had the highest decrease in names-per-100k-babies born**
Highest decrease happened in 1986. The name decreased in 81-per-100K people that year.

> SELECT * FROM ssa_baby_names
WHERE name = "Andrea"

**08) Make a line chart showing how your name has changed in popularity over the years**

- Female: http://i.imgur.com/KBI6Y6u.png
- Male: http://i.imgur.com/SjUWcv7.png

> SELECT * FROM ssa_baby_names
WHERE name = "Andrea"
AND  sex = "F"

and then

> SELECT * FROM ssa_baby_names
WHERE name = "Andrea"
AND  sex = "M"

**09) Find out who in our class had the most popular baby name in 1980.**
The most popular name in 1980 was Jessica (33,920)

> SELECT  `name`,`count`, `sex`, `year`
FROM ssa_baby_names
WHERE name = "Phoebe"
OR name = "Sabrina"
OR name = "Laura"
OR name = "Alexandra"
OR name = "Farida"
OR name = "Liam"
OR name = "Jay"
OR name = "Allison"
OR name = "Austin"
OR name = "Yuqing"
OR name = "Jessica"
OR name = "Sean"
OR name = "Ariha"
OR name = "Katie"
OR name = "Mary Ann"
OR name = "Carolina"
OR name = "Maren"
OR name = "Akoto"
OR name = "Lope"
HAVING year = 1980

**10) Find out who in our class had the most popular baby name in 2013.**
The most popular name in 2013 was Liam (18,002)

> SELECT  `name`,`count`, `sex`, `year`
FROM ssa_baby_names
WHERE name = "Phoebe"
OR name = "Sabrina"
OR name = "Laura"
OR name = "Alexandra"
OR name = "Farida"
OR name = "Liam"
OR name = "Jay"
OR name = "Allison"
OR name = "Austin"
OR name = "Yuqing"
OR name = "Jessica"
OR name = "Sean"
OR name = "Ariha"
OR name = "Katie"
OR name = "Mary Ann"
OR name = "Carolina"
OR name = "Maren"
OR name = "Akoto"
OR name = "Lope"
HAVING year = 2013

**11) Find out who in our class has the name that the most babies throughout U.S. history have.**
The name Jessica had the most babies (between 1980 and 2013): 876,097

> SELECT  `name`,`count`, `sex`, `year`
FROM ssa_baby_names
WHERE name = "Phoebe"
OR name = "Sabrina"
OR name = "Laura"
OR name = "Alexandra"
OR name = "Farida"
OR name = "Liam"
OR name = "Jay"
OR name = "Allison"
OR name = "Austin"
OR name = "Yuqing"
OR name = "Jessica"
OR name = "Sean"
OR name = "Ariha"
OR name = "Katie"
OR name = "Mary Ann"
OR name = "Carolina"
OR name = "Maren"
OR name = "Akoto"
OR name = "Lope"
GROUP BY name

# **Other**

**Most popular 20 names:**

> SELECT * FROM ssa_baby_names
WHERE rank < 20

**Every single male name:**

> SELECT  name, count, sex, year
FROM ssa_baby_names
WHERE sex = "M"

**All Classmates, all years:**

> SELECT  `name`,`count`, `sex`, `year`
FROM ssa_baby_names
WHERE name = "Phoebe"
OR name = "Sabrina"
OR name = "Laura"
OR name = "Alexandra"
OR name = "Farida"
OR name = "Liam"
OR name = "Jay"
OR name = "Allison"
OR name = "Austin"
OR name = "Yuqing"
OR name = "Jessica"
OR name = "Sean"
OR name = "Ariha"
OR name = "Katie"
OR name = "Mary Ann"
OR name = "Carolina"
OR name = "Maren"
OR name = "Akoto"
OR name = "Lope"
