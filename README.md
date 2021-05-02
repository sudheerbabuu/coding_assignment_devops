

# Coding Assignment

Using the given sample log file, perform the following tasks:

1. Top 10 requested pages and the number of requests made for each

2. Percentage of successful requests (anything in the 200s and 300s range)

3. Percentage of unsuccessful requests (anything that is not in the 200s or 300s range)

4. Top 10 unsuccessful page requests

5. The top 10 hosts making the most requests, displaying the IP address and number of requests made.

Option parsing to produce only the report for one of the previous points (e.g. only the top 10 urls, only the percentage of successful requests and so on)



## REQUIREMENTS
Install python mock
```
> pip install mock
```


## How To Use 

When you run python main_tool_module inside src/ directory then the default input/output files for this script is to read from:

```
file_name = "../data/input_log_file"
```
and write to:

```
output_file = "../data/report.txt"
```



## Exec/How To

```
> python main_tool_module.py --help
Usage: exec [--top10] [--persucess] [--perfail] [--top10fail] [--top10hosts]

Options:
  -h, --help    show this help message and exit
  --top10       1.  Top 10 requested pages and requests for each
  --persuccess  2.  Percentage of successful requests
  --perfail     3.  Percentage of unsuccessful requests
  --top10fail   4.  Top 10 unsuccessful page requests
  --top10hosts  5.  The top 10 hosts making the most requests
```
### Example 1 (Top10):
```
python main_tool_module.py  --top10
```
Then result report will be the following: 

### output

```
----Top 10 requests----
request : /administrator/index.php  number of requests : 216501
request : /apache-log/access.log  number of requests : 57602
request : /index.php?option=com_contact&view=contact&id=1  number of requests : 22212
request : /  number of requests : 10408
request : /index.php?option=com_easyblog&view=dashboard&layout=write  number of requests : 4393
request : /templates/_system/css/general.css  number of requests : 2376
request : /favicon.ico  number of requests : 2346
request : /robots.txt  number of requests : 2016
request : /media/system/js/mootools.js  number of requests : 715
request : /templates/jp_hotel/css/template.css  number of requests : 672

You can also check output file.., ../data/report.txt
```

### Example 2:
```
python main_tool_module.py  --persuccess
```
Then result report will be the following:
```
Percentage of successful requests: 95.43%

Please check output file i.e., ../data/report.txt
```
### Example 3:
```
python main_tool_module.py  --perfail
```
Then result report will be the following:
```
Percentage of unsuccessful requests: 4.57%

Please check output file i.e., ../data/report.txt

```

### Example 4:
```
python main_tool_module.py --top10fail

```

Then result report will be the following:

```
----Top 10 unsuccessful requests----
request : /index.php?option=com_easyblog&view=dashboard&layout=write
request : /templates/_system/css/general.css
request : /favicon.ico
request : /icons/blank.gif
request : /icons/back.gif
request : /icons/text.gif
request : /wp-login.php
request : /.env
request : /xmlrpc.php?rsd
request : /wordpress/wp-includes/wlwmanifest.xml

```

### Example 5:
```
python main_tool_module.py --top10hosts

```

Then result report will be the following:

```
----Top 10 hosts----
host : 193.106.31.130 , Number of requests :  203333
host : 197.52.128.37 , Number of requests :  40777
host : 173.255.176.5 , Number of requests :  5220
host : 178.44.47.170 , Number of requests :  2824
host : 51.210.183.78 , Number of requests :  2684
host : 193.9.114.182 , Number of requests :  2205
host : 45.15.143.155 , Number of requests :  1927
host : 5.188.62.140 , Number of requests :  1370
host : 102.45.245.173 , Number of requests :  1062
host : 45.144.0.179 , Number of requests :  946

You can also check output file.., ../data/report.txt

```

## Testing

To test code you can run inside test directory

```
run_tests.sh
```

Alternatively you can run explicitily tests:

```
python -m unittest test_collector
```
