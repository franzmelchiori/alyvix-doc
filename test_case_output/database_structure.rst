.. _database_structure:

******************
Database structure
******************

The data tables are 3: runs contains a row for each execution of the test case and in each row there are an execution timestamp and transaction performances (in milliseconds) related to used keywords. sorting contains a new row just when something is changed in the test case execution (e.g. it fails, it runs different keywords) and in each row there are execution timestamp and the execution sequence of keywords: integer numbers (starting from 0) to sort successful executed keywords, -1 to label failed keywords and NULL to label unused keywords. thresholds contains a new row just when used keywords or keyword thresholds change and in each row there are execution timestamps, warning and critical thresholds of used keywords.
