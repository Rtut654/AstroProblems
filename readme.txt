There is two notebooks - notebook-A and notebook-B.

------ Notebook-A ----------

Notebook-A makes step by step process of downloading, treatment and homogenuous data making.

1) in the initial directory it creates folder 'test' with three subfolders - 1, 2, 4. The name of subfolders represents the number of id in 
the response of such time series.

2) On the next step it downloads data and sort it in this three subfolders.

There are three ways to make homogenuous data:

--zg: From '1' and '2' folder select only zg-objects with more than "hold" observations, from '4' folder take zg with more than "hold" observations. 
--zr: From '1' and '2' folder select only zr-objects with more than "hold" observations, from '4' folder take zr with more than "hold" observations
--summ: From '2' folder select both zg and zr if min(zg,zr)> hold, from '4' folder select max(zg1,zg1), max(zr1,zr1) if min(max(zg1,zg1), max(zr1,zr1)) > hold.

3) "homogen" and "homogen_summ" functions were made to process the files and make single dataframes with such homodenuous data.



------ Notebook-B ----------

1) "Features" function creates new dataframe with features for futher machine learning treatment.

2) "Metrics" function calculates different metrics for dataframe provided. It implies that there are only one type of interest - var_type 
and so it results in balanced dataframe with n object of var_type and n objects of different types (randomly selected from dataframe).

3) "Metrics_classic" function works the same way but instead of "Metrics" it expects already labeled small dataframe. It can be used for example, 
to analyze the differences between the same type ('DCEP') in zg and zr filters (dcep_zg/ dcep_zr).