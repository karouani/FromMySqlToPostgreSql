FromMySqlToPostgreSql - the database migration tool.

WHAT IS IT ALL ABOUT?
FromMySqlToPostgreSql is a tool, intended to make a process of migration 
from MySql to PostgreSql as easy and smooth as possible.


KEY FEATURES 
1. Ease of use - the only thing needed to run this script is the PHP(CLI) interpreter.
   
2. Accuracy of migration the database structure - FromMySqlToPostgreSql converts 
   MySql data types to corresponding PostgreSql data types, creates constraints,
   indeces, primary and foreign keys exactly as they were before migration.

3. In order to migrate data fast - FromMySqlToPostgreSql uses PostgreSQL COPY protocol.
   Note: migration of tables, containing "varbinary" or "blob" columns may be 
   considerably slower.

4. Ease of monitoring - FromMySqlToPostgreSql will provide detailed output
   about every step, it takes during the execution.

5. Ease of configuration - all the parameters required for migration 
   (maximum 7 parameters) should be put in one single file, 
   which can be in either "xml" or "json" format.


SYSTEM REQUIREMENTS
1. PHP (CLI) 5.4 or above.
2. PDO_MYSQL support.
3. PDO_PGSQL support.
4. register_argc_argv should be enabled (check php.ini).


USAGE
1. Create a new database.
   Sample: CREATE DATABASE my_postgresql_database;

2. Download FromMySqlToPostgreSql package and put it on the machine running 
   your PostgreSql.
   Sample: /path/to/FromMySqlToPostgreSql

3. Create configuration file in either "xml" or "json" format and put it on 
   the machine running your PostgreSql. 
   Sample: /path/to/config.json or /path/to/config.xml
   Remarks:
   1. sample_config.json or sample_config.xml are examples of configuration
      file, so you can edit one of them and use for migration. 
      
   2. Brief description of each configuration parameter will be found at 
      sample_config.json and sample_config.xml
     
4. Run the script from a terminal. 
   Sample: php  /path/to/FromMySqlToPostgreSql/index.php  /path/to/config[.xml | .json]
       
5. At the end of migration check log files (described above) if necessary.

6. In case of any remarks, misunderstandings or errors during migration, 
   please feel free to email me <anatolyuss@gmail.com>.


VERSION
Current version is 1.0.0


TEST
Tested using MySql Community Server (5.6.21) and PostgreSql (9.3).
The entire process of migration 59.6 MB database (49 tables, 570750 rows), 
which includes data types mapping, creation of tables, constraints, indeces, 
PKs, FKs, migration of data, garbage-collection and analyzing the newly created 
PostgreSql database took 3 minutes 6 seconds.


LICENSE
FromMySqlToPostgreSql is available under "GNU GENERAL PUBLIC LICENSE" (v. 3) 
<http://www.gnu.org/licenses/gpl.txt>.


REMARKS
Errors/Exceptions are not passed silently.
Any error will be immediately written into the error log file.
