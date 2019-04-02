[![Say Thanks!](https://img.shields.io/badge/Say%20Thanks-!-1EAEDB.svg)](https://saythanks.io/to/Stefanitsky)  [![PyPI version](https://badge.fury.io/py/dbcw.svg)](https://badge.fury.io/py/dbcw)
# DBCW

DBCW (Database Connection Wrapper) is a python package that allows you to connect to different types of databases and contains methods for getting the necessary data.

This is a good choice for you if you do not want to deal with queries to the database and you just need basic functionality for getting data.

But if you need to send your own query to the database - this is also possible.

Supported engines:  
        - PostgreSQL  
        - MySQL  

## Installation

Use the package manager [pip](https://pip.pypa.io/en/stable/) to install dbcw.

```bash
pip install dbcw
```

## Usage

#### Import:
```python
from dbcw import DBConnectionWrapper
```

#### PostgreSQL connection
```python
connection = DBConnectionWrapper(
            host='localhost', user='root', password='1234')
```

#### MySQL connection
```python
connection = DBConnectionWrapper(
            engine='mysql', host='localhost', user='root', password='1234')
```

#### Get database list
```python
>>> connection.get_db_list()
['db1', 'db2']    # output example
```

#### Get tables list from the database
```python
>>> connection.get_tables_list('db_name')
[('friends', 'numbers')]    # output example
```

#### Get table data
```python
connection.get_table_data('db_name', 'table_name')
```

#### Get database structure (depends on engine)
```python
connection.get_db_structure('db_name')
```

#### Get table structure (depends on engine)
```python
connection.get_table_structure('db_name', 'table_name')
```

#### Execute custom query
```python
connection.execute_query('SELECT * FROM table;')
```

## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

## License
[MIT](https://choosealicense.com/licenses/mit/)