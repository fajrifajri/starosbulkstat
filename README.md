Cisco StarOS Bulkstat Parser to PushGateway

Getting Started
Cisco StarOS Bulkstat is formated in CSV. The bulkstat data is based on bulkstat config, so that the data from 1 node to another node may have different format, depending on the config. This is to parse the CSV data into push gateway based on the config. 

Due to the uniq way of bulkstat implementation, there are custom handlings on this code (I wish I can simplify that):
- identify the main label : sometime bulkstat schema name can be good candidate of label (e.g.: APN name), unfortunately this is not always the case
- converting some metric into label.

reference to Cisco StarOS Bulkstat: https://www.cisco.com/c/dam/en/us/td/docs/wireless/asr_5000/21-16_6-10/Bulkstats-Doc-Spreadsheet/21-16-Bulkstats-Docs-Spreadsheet.pdf



Prerequisites
- Python 3


Running
./bulkstat-exporter.py -config config_bulkstat.log -file bulkstat_data.csv -node PGW1 -pushgateway 1.1.1.1:9091

Authors
Anthony Fajri (anthony.fajri@gmail.com)


