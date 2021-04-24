Necessary files from repository which used in  the project: 

- gcvs5.txt
- Notebook-A.ipynb
- Notebook-B.ipynb 
- df1_homogen_zg.csv 
- df1_homogen_zr.csv
- df1_homogen_summ.csv 



- gcvs5 

Edited version of General Catalog of Variable Stars.



- Notebook-A 

Notebook-A makes step by step process of downloading, treatment and homogenuous data making.

1) in the initial directory it creates folder 'test' with three subfolders - 1, 2, 4. The name of subfolders represents the number of id in 
the response of such time series.

2) On the next step it downloads data and sort it in this three subfolders.

There are three ways to make homogenuous data:

--zg: From '1' and '2' folder select only zg-objects , from '4' folder take zg with maximum amount of observations among all zg objects. 
--zr: From '1' and '2' folder select only zr-objects , from '4' folder take zr with maximum amount of observations among all zg objects
--summ: From '2' folder select both zg and zr if min(zg,zr)> hold, from '4' folder select max(zg1,zg1), max(zr1,zr1) if min(max(zg1,zg1), max(zr1,zr1)) > hold.

3) "homogen" and "homogen_summ" functions were made to process the files and make single dataframes with such homodenuous data.


- Notebook-B 

1) "Features" (var_type, df) function creates new dataframe with features for futher machine learning treatment.

var_type - variable type of interest
df - initial dataframe

2) "Metrics" (df) function calculates different metrics for dataframe provided. It implies that there are only one type of interest - var_type 
and so it results in balanced dataframe with n object of var_type and n objects of different types (randomly selected from dataframe).

df-dataframe which was returned by "Features".

3) "Metrics_classic"(df) function works the same way but instead of "Metrics" it expects already labeled small dataframe. It can be used for example, 
to analyze the differences between the same type ('DCEP') in zg and zr filters (dcep_zg/ dcep_zr).


df-dataframe which was returned by "Compare".

4) "Compare" (var_type,df1,df2) function works the same way as "Features" but 

var_type - variable type of interest
df1 - dataframe of zg filter
df2 - dataframe of zr filter

In Notebook-B one can find the lines of uploading three files of ready homogenuous data (df1_homogen_zg/ df1_homogen_zr/ df1_homogen_summ). This tables were made 
in the way described above, except 'df1_homogen_summ' file has no selection by 'hold', it contains only min out of two objects.





