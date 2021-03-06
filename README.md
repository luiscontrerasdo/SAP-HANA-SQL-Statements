# SAP-HANA-SQL-Statements
 SAP HANA SQL Statements

SAP Hana SQL Statements for retrieving performance and status information.

To find row  store utilization:

```
SELECT round (sum(USED_FIXED_PART_SIZE + USED_VARIABLE_PART_SIZE)/1024/1024) AS "Row Tables MB" 
FROM M_RS_TABLES;
```

To find column store utilization :- Completado

```
SELECT round (sum(MEMORY_SIZE_IN_TOTAL)/1024/1024) AS "Column Tables MB"  
FROM M_CS_TABLES;
```

To find log segments and services related with its state

```
SELECT b.host, b.service_name, a.state, COUNT(*) 
FROM "PUBLIC"."M_LOG_SEGMENTS" a 
JOIN "PUBLIC"."M_SERVICES" b on (a.host = b.host AND a.port = b.port) 
GROUP BY b.host, b.service_name, a.state;
```

To find Hana DB Size

```
SELECT ROUND (sum(allocated_page_size)/1024/1024/1024) "Value GB" 
FROM m_converter_statistics;
```