# MySQL
## MySQL服务的登录和退出
方式一：通过MySQL自带客户端，仅限root用户  
方式二：通过Mac Terminal，`mysql [-h 主机名 -P端口名] -u 用户名 -p 密码`  
退出：exit或ctrl+c
## MySQL的常见命令
1. 查看当前所有的数据库，`show databases;`
2. 打开指定库，`use 库名`
3. 查看当前库的所有表，`show tables;`
4. 查看其它库的所有表，`show tables from 库名;`
5. 创建表，`create table 表名（
    列名 列类型,
    列名 列类型,
    ......
    ）;`
6. 查看表结构，`desc 表名;`
7. 查看服务器的版本：  
方式一：登录到mysql服务器`select version();`  
方式二：没有登录到mysql服务器`mysql --version`或`mysql -V`  
## MySQL的语法规范
1. **不区分大小写**，但建议关键字大写，表名、列名小写。
2. 每条命令最好用分号结尾！！！
3. 每条命令根据需要，可以进行缩进或换行。建议关键字换行。
4. 注释  
单行注释，`#注释文字`  
单行注释，`-- 注释文字`  
多行注释，`/* 注释文字 */`
## DQL(Database Query Language)
### 1. 基础查询：  
语法：`select 查询列表 from 表名;`  
特点：  
* 查询列表可以是：表中的字段、常量、常量值、表达式、函数。  
* 查询的结果是一个虚拟的表格。
#### (1) 查询表中的单个字段
```SQL
SELECT last_name FROM employees;
```
#### (2) 查询表中的多个字段
```SQL
SELECT last_name, salary,email FROM employees;
```
#### (3) 查询表中的所有字段
```SQL
SELECT * FROM employees;
```
**不足是顺序不变，如果要定义顺序还是用方法(2)**  
当遇到字段又是关键字的时候需要加\`\`
选中哪段代码就执行哪段。
#### (4) 查询常量值
```SQL
SELECT 100;
SELECT 'john';
```
#### (5) 查询表达式
```SQL
SELECT 100*98;
```
```SQL
SELECT 100%98;
```
#### (6) 查询函数
```SQL
SELECT VERSION();
```
