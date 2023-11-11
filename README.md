# Example ways to work with this data set

Here is some example code using `xsv`, a commandline tool, to do some data preparation:

```sh
xsv sample -n 10 data/AllOrderDetail_Aug_clean.csv
xsv stats data/AllOrderDetail_Aug_clean.csv
xsv cat rows `ls data/AllOrderDetail_*.csv` -o data/AllOrderDetails_Aug_Sept_Oct.csv
xsv headers data/AllOrderDetails_Aug_Sept_Oct.csv
xsv select 2,3,5,6,12-22 data/AllOrderDetails_Aug_Sept_Oct.csv > data/AllOrderDetails_Aug_Oct_Sept__selected.csv
```