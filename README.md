# Languages-and-Demographic-Trends-in-India

---------------------
Table of contents
---------------------
1. Introduction
2. Prerequisites
3. Constraints
4. Usage
5. How to execute
6.Approach write-up
7. Output files
8. Web links


Introduction
---------------
The objective of the assignment is to get the population data related to various languages spoken in India using the official census data and
also, mine the data in order to comprehend various patterns and details of languages in different regions,genders,age-groupsand literacy groups of
the country.

Prerequisites
-----------------
Technical : Python,Numpy,Pandas and the Linux environment to run .sh script files.
In Linux bash shell,   "jupyter-nbconvert " command, (if not installed)

Constraints
--------------
1. Data files for languages and population are not pulled directly from the census website as sometimes the website isn't functional.
    -   Instead downloaded files are used.
    -  *** These files and program should have the same path. Please add all files to a common folder .
2. All the output files will be generated in the path "<current directory>/Output_Files/Qx " ; where x is 1,2,3...9
3. State codes are used in all the output files instead of State names.
4. Census file is renamed to "Census2011data.xlsx"
   

Usage
--------
This assignment is handy in knowing various trends in the languages spoken in different regions, genders,age groups and literacy groups in the country
It does the following for all states and overall: 
      - percentage of population speaking only one language, two languages and three lagnuages in  every state(or UT) and overall.
      - percentage of male and female populations speaking only one language, two languages and three lagnuages in  every state(or UT) and overall.
      - percentage of urban and rural populations speaking only one language, two languages and three lagnuages in  every state(or UT) and overall.
      - Finds the top 3 states where people speak three languages more compared to two languages. Also, the bottom 3 states.
      - Age groups and Literacy groups in each state/overall having the  highest percentage of people speaking three languages or more.
      - Finds top 3 most spoken languages in each of the 6 regions in the country(Mother Tongue and total speakers) 
      - Age groups and Literacy groups of males and females speaking highest ratio of three languages, two languages and one language.

How to execute
-------------------
Individual .sh files for each question are created as list below:(file names doesn't include quotations)
Q1.  "percent-india.sh"
Q2.  "gender-india.sh"
Q3.  "geography-india.sh"
Q4a. "3-to-2-ratio.sh"
Q4b. "2-to-1-ratio.sh"
Q5.   "age-india.sh"
Q6.   "literacy-india.sh"
Q7.   "region-india.sh"
Q8.   "age-gender.sh"
Q9.   "literacy-gender.sh"

Note: "assign2.sh" is for running entire Assignment-2 which executes all the above files
Command:   ./<script-file-name>   
                 Example: ./percent-india.sh

Approach write-up
---------------------
      - This assignment demands 10 questions including the requirement of this readme file.
      - Population(male/female/both) speaking only one language = Total population(CENSUS) - Population speaking two languages(Language files)
      - Population(male/female/both) speaking exactly two languages = Population speaking two languages(Language files) - Population speaking three languages(Language files)
      - Population(male/female/both) speaking three languages =Population speaking three languages(Language files)

Q1 -> To Find the percentage of population of India who speaks (a) only one language, (b) exactly two languages, and (c) three languages or more
   
           - Files used: "Census2011data.xlsx" and C18: "DDW-C18-0000.xlsx"
           - Population number is taken from census file and language counts are taken from C18 file.

Q2 -> Percentage of male and female populations speaking only 1 language, 2 languages and 3 lagnuages in  every state(or UT) and overall.
           
           - Files used: "Census2011data.xlsx" and C18: "DDW-C18-0000.xlsx"        
           - Population of male and female is taken from census file and language numbers of male and female are taken from C18 file.
           - P-value is calculated using the scipy stats' ttest_1samp.
 
Q3 -> Percentage of urban and rural populations speaking only one language, two languages and three lagnuages in  every state(or UT) and overall.

           - Files used: "Census2011data.xlsx" and C18: "DDW-C18-0000.xlsx" 
           - Population of urban and rural is taken from census file and language numbers of urban and rural are taken from C18 file.   
           - P-value is calculated using the scipy stats' ttest_1samp.     

Q4a -> Top-3(also bottom 3) states where the ratio of population speaking ratio of three languages or more to exactly two languages.
           - Files used: "Census2011data.xlsx" and C18: "DDW-C18-0000.xlsx" 
           - Output contains 6 rows displaying top-3 states (higher to lower ratio) first and then worst-3 states (lower to higher ratio) 

Q4b -> Top-3(also bottom 3) states where the ratio of population speaking exactly  two languages to only one language
           - Files used: "Census2011data.xlsx" and C18: "DDW-C18-0000.xlsx" 
           - Output contains 6 rows displaying top-3 states (higher to lower ratio) first and then worst-3 states (lower to higher ratio) 

Q5 -> Age group in each state/overall having the  highest percentage of people speaking three languages for each state/overall

           - Files used: C14: "DDW-0000C-14.xls" and C18: "DDW-C18-0000.xlsx" 
           - C14 is used for population of different age groups. C18 is used for language speakers in different age aroups.
           - Age groups in C14 are adjusted to match those of C18.

Q6 -> Literacy group in each state/overall having the  highest percentage of people speaking three languages for each state/overall

           - Files used: C8="DDW-0000C-08.xlsx" and C19="DDW-C19-0000.xlsx"
           - C8 is used for population of different literacy groups. C19 is used for language speakers in different literacy aroups.
           - Literacy groups in C8 are adjusted to match those of C19.

Q7 -> Top 3 most spoken languages in each of the 6 regions in the country(Mother Tongue and total speakers) 
           
           - 6 regions are North,West,Central,East,South,North-East.
           - Files used: C16="DDW-C16-STMT-MDDS-0000.XLSX" and C17 folder containing individual data files for each state/ut.
           - C16 is used for state code- state name mapping and further into region wise mapping. C17 folder is used for language speakers in different states/uts.
         
Q8 -> Age group in males and females speaking highest ratio of three languages, two languages and one language for each state/overall

           - Files used: C14: "DDW-0000C-14-India.xls" and C18: "DDW-C18-0000.xlsx" 
           - C14 is used for male and female population in different age groups. C18 is used for male and female language speakers in different age aroups.
           - Age groups in C14 are adjusted to match those of C18.

Q9 -> Literacy group in males and females speaking highest ratio of three languages, two languages and one language for each state/overall

           - Files used: C8="DDW-0000C-08.xlsx" and C19="DDW-C19-0000.xlsx"
           - C8 is used for male and female population of different literacy groups. C19 is used for male and female language speakers in different literacy aroups.
           - Literacy groups in C8 are adjusted to match those of C19.

Output Files
---------------
Q1 - percent-india.csv

Q2 - gender-india-a.csv - mono language 
      - gender-india-b.csv - bi  language
      - gender-india-c.csv - tri language

Q3 - geography-india-a.csv - mono language
      - geography-india-b.csv - bi language
      - geography-india-c.csv - tri language

Q4a - 3-to-2-ratio.csv

Q4b - 2-to-1-ratio.csv

Q5 - age-india.csv

Q6 - literacy-india.csv

Q7 - region-india-a.csv  - Mother tongue speakers
      - region-india-b.csv - Mother tongue_2ns language+ third language

Q8 - age-gender-a.csv - tri language 
      - age-gender-b.csv - bi language
      - age-gender-c.csv - mono language

Q9 - literacy-gender-a.csv - tri language
      - literacy-gender-b.csv - bi language
      - literacy-gender-c.csv - mono language

Web Links
-------------
CENSUS DATA: http://censusindia.gov.in/pca/DDW_PCA0000_2011_Indiastatedist.xlsx.
C8: https://censusindia.gov.in/2011census/C-series/C-08/DDW-0000C-08.xlsx
C14: https://censusindia.gov.in/2011census/C-series/c-14/DDW-0000C-14.xls
C16: https://censusindia.gov.in/2011census/C-16/DDW-C16-STMT-MDDS-0000.XLSX
C17: https://censusindia.gov.in/2011census/C-17.html
C18: https://censusindia.gov.in/2011Census/Language-2011/DDW-C18-0000.xlsx
C19: https://censusindia.gov.in/2011Census/Language-2011/DDW-C19-0000.xlsx
