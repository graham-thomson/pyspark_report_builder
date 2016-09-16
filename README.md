## PySpark DataFrame Report Builder

Simple Python Package to save (small) PySpark DataFrames to one Excel File.

### pip Installation:

```
sudo -H pip install pyspark_dfreport
```

###Usage:

_**Interactive Mode**_

1. Import Package

	```
	from pyspark_dfreport.builder import DataFrameReport
	```
2. Instantiate DataFrameReport Object

	```
	report = DataFrameReport("/path/to/report.xlsx")
	```
3. Do some operation on DataFrame

	```
	sql = SQLContext(sc)
	data = sql.read.csv("/path/to/data.csv", header=True, sep="\t")
	byTown = data.groupBy(["Town"]).count()
	```
4. Save to Report

	```
	report.save_df(byTown, name="Count By Town")
	```
5. Try an aggregation

	```
	avgByOwner = data.groupBy(["Owner"]).agg({"Ant Height": "avg"})
	```
6. Save to Report

	```
	report.save_df(avgByOwner) # name is an optional argument
	```
7. Output

	<img src="http://i.imgur.com/hUKSBmP.png" width="250">
	