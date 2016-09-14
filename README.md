## PySpark DataFrame Report Builder

A very simple Python Package to save (small) PySpark DataFrames to one Excel File.

###Usage:

_**Interactive Mode**_

1. Import Package

	```
	import sys
	sys.path.insert(0, '/path/to/report_builder/folder')
	from DfReportBuilder import DataFrameReport
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
5. Done!