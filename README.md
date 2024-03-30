# monitoringMS_HS

Due to my employment with a large "green" organization that deals with large Big Data , I am unable to write code in this space, but I can describe algorithms program. Perhaps this will be of assistance to someone. 
I have been tasked with writing monitoring software for HiveServer and MetaStore. 

For this I used Python stack + little bit bash. 
Python libs: 
"Paramico" for connection ssh. 
"Time" for bachmark method with bash connection beeline.
"Sys" for enter MS and HS andress from console input, if you dont use config file. 

1) First, it is worth mentioning Apach Beeline. One of the remarks. beeline -e "show databases" does not check the performance of your meta stores and hs2_es, just it checks your connection. Therefore, I explicitly specified the connection string to MS and HS (like this: beeline -u jdbc:hive2//localhost:10000/default meta store host:port -e "SELECT COUNT(field) FROM my table;") I used the bash part only for this. Anything beyond Python.

2) Subsequently, I obtain all the logs after processing the request and add them to the list. 

2) Next, I get all the logs after processing the request and added to list. 

3) During this process, I formed the following terms: (for example, if 'Error' === str && elif 'Time taken' === str.) In other words, I take the str from the list. 

4) If str === error, then I take the Error string from the list and match it with known errors in the dictionary. If the match is found, send the text with the known error to the Email. If not, send a list of Error logs. 
If str === Time taken, then take the float count from the list, match it with the threshold, and if the threshold is exceeded, send the text on the Email with the timeout. 

   P.S. I have skipped a lot of lines related to transformations (list to string, list to float, etc.), try-catch statements, and terms.
