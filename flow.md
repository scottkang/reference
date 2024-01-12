# DB2DB Template
```json
{
  "type": "0",
  "sourceSystem": {
    "id": "MySQLSource",
    "name": "Mysql2Postgres Source System",
    "existing": false,
    "type": 1,
    "db": {
      "id": "MySQLSource",
      "version": 1,
      "type": "6",
      "host": "",
      "port": "3306",
      "databaseName": "",
      "userId": "root",
      "password": "password",
      "poolSize": 10,
      "connectionString": "jdbc:mysql://localhost:23316/employees",
      "driverClass": "",
      "driverUrl": "",
      "validationQuery": ""
    },
    "dupChecked": false
  },
  "targetSystem": {
    "id": "PostgresTarget",
    "name": "Mysql2Postgres Target System",
    "existing": false,
    "type": 1,
    "db": {
      "id": "PostgresTarget",
      "version": 1,
      "type": "11",
      "host": "",
      "port": "5432",
      "databaseName": "",
      "userId": "postgres",
      "password": "password",
      "poolSize": 10,
      "connectionString": "jdbc:postgresql://localhost:15442/employees",
      "driverClass": "",
      "driverUrl": "",
      "validationQuery": ""
    },
    "dupChecked": false
  },
  "flow": {
    "flowId": "Mysql2Postgres",
    "flowName": "",
    "serviceVersion": "",
    "groupId": "Default",
    "retryCount": "10"
  },
  "sourceData": {
    "id": "",
    "version": 1,
    "datas": [
      {
        "fg": {
          "id": "FG01",
          "name": "Mysql2Postgres Source Data",
          "desc": "Mysql2Postgres Source Data",
          "fgms": [
            {
              "fv": {
                "id": "F0",
                "name": "emp_no",
                "type": "INT",
                "length": 10,
                "version": 1
              },
              "fieldIndex": 0,
              "isNull": "N",
              "isKey": "N",
              "isSqlFunction": "N"
            },
            {
              "fv": {
                "id": "F1",
                "name": "birth_date",
                "type": "DATE",
                "length": 10,
                "version": 1
              },
              "fieldIndex": 1,
              "isNull": "N",
              "isKey": "N",
              "isSqlFunction": "N"
            },
            {
              "fv": {
                "id": "F2",
                "name": "first_name",
                "type": "VARCHAR",
                "length": 14,
                "version": 1
              },
              "fieldIndex": 2,
              "isNull": "N",
              "isKey": "N",
              "isSqlFunction": "N"
            },
            {
              "fv": {
                "id": "F3",
                "name": "last_name",
                "type": "VARCHAR",
                "length": 16,
                "version": 1
              },
              "fieldIndex": 3,
              "isNull": "N",
              "isKey": "N",
              "isSqlFunction": "N"
            },
            {
              "fv": {
                "id": "F4",
                "name": "gender",
                "type": "ENUM",
                "length": 1,
                "version": 1
              },
              "fieldIndex": 4,
              "isNull": "N",
              "isKey": "N",
              "isSqlFunction": "N"
            },
            {
              "fv": {
                "id": "F5",
                "name": "hire_date",
                "type": "DATE",
                "length": 10,
                "version": 1
              },
              "fieldIndex": 5,
              "isNull": "N",
              "isKey": "N",
              "isSqlFunction": "N"
            }
          ],
          "version": 1
        },
        "recordDelimiter": "\n"
      }
    ],
    "name": "Mysql2Postgres Source Data",
    "dataStructureType": "D",
    "dataStructureSource": "D",
    "dbvo": {
      "systemId": "MySQLSource",
      "tableName": "employees",
      "query": "SELECT  emp_no , birth_date , first_name , last_name , gender , hire_date FROM  employees"
    }
  },
  "targetData": {
    "id": "",
    "version": 1,
    "datas": [
      {
        "fg": {
          "id": "FG02",
          "name": "Mysql2Postgres Target Data",
          "desc": "Mysql2Postgres Target Data",
          "fgms": [
            {
              "fv": {
                "id": "F0",
                "name": "emp_no",
                "type": "int",
                "length": 10,
                "version": 1
              },
              "fieldIndex": 0,
              "isNull": "N",
              "isKey": "Y",
              "isSqlFunction": "N"
            },
            {
              "fv": {
                "id": "F1",
                "name": "birth_date",
                "type": "date",
                "length": 13,
                "version": 1
              },
              "fieldIndex": 1,
              "isNull": "N",
              "isKey": "N",
              "isSqlFunction": "N"
            },
            {
              "fv": {
                "id": "F2",
                "name": "first_name",
                "type": "varchar",
                "length": 14,
                "version": 1
              },
              "fieldIndex": 2,
              "isNull": "N",
              "isKey": "N",
              "isSqlFunction": "N"
            },
            {
              "fv": {
                "id": "F3",
                "name": "last_name",
                "type": "varchar",
                "length": 16,
                "version": 1
              },
              "fieldIndex": 3,
              "isNull": "N",
              "isKey": "N",
              "isSqlFunction": "N"
            },
            {
              "fv": {
                "id": "F4",
                "name": "gender",
                "type": "gender",
                "length": 2147483647,
                "version": 1
              },
              "fieldIndex": 4,
              "isNull": "N",
              "isKey": "N",
              "isSqlFunction": "N"
            },
            {
              "fv": {
                "id": "F5",
                "name": "hire_date",
                "type": "date",
                "length": 13,
                "version": 1
              },
              "fieldIndex": 5,
              "isNull": "N",
              "isKey": "N",
              "isSqlFunction": "N"
            }
          ],
          "version": 1
        },
        "recordDelimiter": "\n"
      }
    ],
    "name": "Mysql2Postgres Target Data",
    "dataStructureType": "D",
    "dataStructureSource": "D",
    "dbvo": {
      "systemId": "PostgresTarget",
      "tableName": "employees",
      "operation": "I"
    }
  },
  "mapping": {
    "mappings": [
      {
        "srcFieldId": "0-0",
        "srcTaskId": 6,
        "tgtFieldId": "0-0",
        "tgtTaskId": 10,
        "sourceRow": "2",
        "targetRow": "2",
        "sourceCellId": "2",
        "targetCellId": "3",
        "sourceDataId": "",
        "targetDataId": "",
        "srcDetailIndex": -1,
        "tgtDetailIndex": -1
      },
      {
        "srcFieldId": "0-1",
        "srcTaskId": 6,
        "tgtFieldId": "0-1",
        "tgtTaskId": 10,
        "sourceRow": "3",
        "targetRow": "3",
        "sourceCellId": "2",
        "targetCellId": "3",
        "sourceDataId": "",
        "targetDataId": "",
        "srcDetailIndex": -1,
        "tgtDetailIndex": -1
      },
      {
        "srcFieldId": "0-2",
        "srcTaskId": 6,
        "tgtFieldId": "0-2",
        "tgtTaskId": 10,
        "sourceRow": "4",
        "targetRow": "4",
        "sourceCellId": "2",
        "targetCellId": "3",
        "sourceDataId": "",
        "targetDataId": "",
        "srcDetailIndex": -1,
        "tgtDetailIndex": -1
      },
      {
        "srcFieldId": "0-3",
        "srcTaskId": 6,
        "tgtFieldId": "0-3",
        "tgtTaskId": 10,
        "sourceRow": "5",
        "targetRow": "5",
        "sourceCellId": "2",
        "targetCellId": "3",
        "sourceDataId": "",
        "targetDataId": "",
        "srcDetailIndex": -1,
        "tgtDetailIndex": -1
      },
      {
        "srcFieldId": "0-4",
        "srcTaskId": 6,
        "tgtFieldId": "0-4",
        "tgtTaskId": 10,
        "sourceRow": "6",
        "targetRow": "6",
        "sourceCellId": "2",
        "targetCellId": "3",
        "sourceDataId": "",
        "targetDataId": "",
        "srcDetailIndex": -1,
        "tgtDetailIndex": -1
      },
      {
        "srcFieldId": "0-5",
        "srcTaskId": 6,
        "tgtFieldId": "0-5",
        "tgtTaskId": 10,
        "sourceRow": "7",
        "targetRow": "7",
        "sourceCellId": "2",
        "targetCellId": "3",
        "sourceDataId": "",
        "targetDataId": "",
        "srcDetailIndex": -1,
        "tgtDetailIndex": -1
      }
    ],
    "opinfos": [],
    "functions": [],
    "targetDS": "",
    "acceptNullSource": "Y",
    "bulkMapping": "Y"
  },
  "publish": false
}
```
