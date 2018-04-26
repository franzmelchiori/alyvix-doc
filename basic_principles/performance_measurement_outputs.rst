***********************************
Performance measurement and outputs
***********************************


Transaction thresholds and performance
======================================

It is necessary to define the **timeout** for every keyword as the amount of seconds that Alyvix waits continuously looking on screen for detecting the defined graphic elements of the running keyword.

The **performance measurement** for each keyword starts immediately after its execution, which basically equals (i.e. in the middle of a test case with a sequence of keywords) with the interaction phase end of the previous keyword. When timeout thresholds are exceeded because Alyvix detects anything, keywords fail and break test cases.

For each critical user transactions, one has to enable the Alyvix performance measurement and to set their own performance **warning and critical thresholds**. That means Alyvix returns three numbers (i.e. amounts of seconds about one performance and two thresholds) for all keywords with enabled performances, so that monitoring systems know all of those transactions that have exceeded their thresholds.

In case of one keyword fails or if one or more keywords pass their thresholds, monitoring systems can show a proper **status tag** for each test case (e.g. OK, WARNING, CRITICAL, UNKNOWN), give a detailed description about the last successful transaction and send email notifications to promptly alert system administrators.


Command line output and HTML report
===================================

The Alyvix deployment provides a **command line tool** to execute already built test cases (i.e. through Alyvix RIDE, which is the Alyvix test case editor). System integrators can script a command to execute one test case and to get its performances.

The **command line output** of an Alyvix test case has the **Nagios Plugins format**. The first row is a text string pipe with the overall exit tag about the test case status, a verbose description about the last successful transaction in case of failed tests and then all the transaction performances (name and seconds) each of them coupled with its warning and critical thresholds. From the second to the last row all transaction performances are listed with their exit status tag, their name and their amount of seconds.

It is also possible to provide an output folder as argument to the Alyvix command line tool in order to save an **HTML report**, after a test case execution, with the details about all the executed transactions. For each keyword the **screenshot** of its detection is reported, certifying the screen appearance in that moment: component selections and regions of interest are also drawn. In case of test case failures an **animation** visually explain which component has not been detected, blinking its region of interest where it should be.


Performance database and Windows Performance Monitor
====================================================

Alyvix basic keywords allow users to store **test case data and performances** in a database and to publish them in a **CSV file** or in **Windows Performance Monitor**. In the latter way, a generic monitoring system can get that data as any other system statistic (e.g. CPU load, memory usage).

Store Perfdata keyword organizes data coming from test cases in four tables of a single-file **SQLite database** (one for each test case). In the table runs, every executed keyword takes place as a column: every test case execution generates a new row with a time stamp and a performance for every transaction.

The sorting table reports serial integer numbers (starting from 0) as execution order of keywords, a -1 under a keyword that fails or a NULL in case a keyword has not been executed. In the thresholds table there are the warning, critical and timeout thresholds for every executed keyword. Alyvix adds a new row in the latter two tables just in case something is changed from the previous test case execution.

The timestamp table contains the absolute timestamps of the beginning of each transaction. In case a transaction breaks there will write a NULL for it and the subsequent ones.

Installing Alyvix (through the Internet) also deploys **Alyvix WPM Service** by default in the list of available Windows Services (the service runs automatically at boot). Publish Perfdata relies on that service in order to expose all data form the database tables to Windows Performance Monitor. Every test case transaction is a counter that can be added to the ongoing time series chart, but mostly it can be fetched through monitoring agents (e.g. NSClient++) by monitoring systems.
