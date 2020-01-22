## CONNECT 설치([[MySQL] CONNECT Storage Engine Oracle연동](https://cirius.tistory.com/1609))

- MariaDB [(none)]>show engines;  

~~~
+--------------------+---------+----------------------------------------------------------------------------+--------------+------+------------+ 
| Engine | Support | Comment | Transactions | XA | Savepoints | 
+--------------------+---------+----------------------------------------------------------------------------+--------------+------+------------+ 
| CONNECT | YES | Management of External Data (SQL/MED), including many file formats | NO | NO | NO |
~~~

- MariaDB [(none)]> INSTALL SONAME 'ha_connect';

## JSON table type 만들기
  1. xxx.json 파일을 MariaDB Data 폴더 아래에 빈값으로 만든다
  2. CREATE TABLE carts_json engine=CONNECT, table_type=json, file_name='carts.json' AS SELECT * FROM carts; 로 CTAS로 만든다
  3. INSERT INTO VALUES 문으로 데이터를 채운다
  4. 만들어진 json 파일을 활용한다

