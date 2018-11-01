# sql-annotation
> 使用装饰器的方式来执行sql操作.

# Install
* pip: `$ pip install sql-annotation`
* source:
    * `$ git clone https://github.com/tomoncle/sql-annotation.git`
    * `$ cd sql-annotation`
    * `$ python setup.py`


# example:
   ```python
   from sql_annotation.annotation import select
   from sql_annotation.conn import connection

   connection(username='tom', password='123456', db='test')


   @select('select * from t_school WHERE id="#{id}"')
   def get_school_by_id(id):
       pass


   @select('select * from t_school WHERE name like "%#{name}%"')
   def get_school_by_name(name):
       pass


   print get_school_by_id(id='60')
   print get_school_by_name(name='乌克兰')
   ```
