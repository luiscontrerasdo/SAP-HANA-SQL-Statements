# SAP-HANA-SQL-Statements
 SAP HANA SQL Statements

SAP Hana SQL Statements for retrieving performance and status information.

To find row  store utilization:

#####**SELECT round (sum(USED_FIXED_PART_SIZE + USED_VARIABLE_PART_SIZE)/1024/1024) AS "Row Tables MB" FROM M_RS_TABLES;**
