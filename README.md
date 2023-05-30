# project_feederwatch

This is a repository for my data cleaning script of Project FeederWatch observations recorded by citizen-scientists in the USA, Mexico and Canada between 1988 and 2021, written using Python and Jupyter Notebooks.

It imports data freely available at https://feederwatch.org/explore/raw-dataset-requests/ in CSV format, cleans and reorganizes the data into a snowflake-schema database, and then exports each table in the database as a separate CSV file (1 subdimension table, 4 dimension tables and 1 fact table.)

The table schema is as follows...

observations_fact:
|Column|Type|
|---|---|
|Obs Id|text|
|Sub Id|text|
|Proj Period Id|text|
|Month|int|
|Day|int|
|Year|int|
|Species Code|text|
|How Many|int|
|Day1 Am|float|
|Day1 Pm|float|
|Day2 Am|float|
|Day2 Pm|float|
|Effort Id|int|
|Snow Dep Atleast|float|
|Entry Id|int|
|State|text|
|Loc Id|text|
|Latitude|float|
|Longitude|float|


data_dict_dim:
|Column|Type|
|---|---|
|Species Code|text|
|Sci Name|text|
|Primary Com Name|text|
|Order|text|
|Family|text|


family_subgroups_dim:
|Column|Type|
|---|---|
|Family|text|
|Subgroups|text|


effort_dim:
|Column|Type|
|---|---|
|Effort ID|int|
|Effort Hrs|text|


entry_methods_dim:
|Column|Type|
|---|---|
|Entry ID|int|
|Entry Method|text|


extinct_species_dim:
|Column|Type|
|---|---|
|Species Code|text|
|Extinct Year|int|

