## Selenium
#### ElementNotVisibleException
* I was crawling a website dynamically loaded by js and I continually got this error everytime I want to click an element with Selenium. I was stuck on this issue for a whole day. I tried different kinds of ways to handle with it and they didn't work! When I almost gave it up, I found the problem. 
* In Selenium, if anlement satisfies all the following conditions, it is visible:
  Referring to [this answer on stackoverflow](https://stackoverflow.com/questions/6101461/how-to-force-selenium-webdriver-to-click-on-element-which-is-not-currently-visib)
  1. visibility != hidden
  2. display != none (is also checked against every parent element)
  3. opacity != 0 (this is not checked for clicking an element)
  4. height and width are both > 0
  5. for an input, the attribute type != hidden
  
  So check these out when you encountered the issue of ElementNotVisibleException. In my case, I used `xxx.find_element_by_xpath('//xpath...').click()` to locate the element, which is not accurate enough. Because there are multiple elements with similar xpath expressions. When I check it with `xxx.find_elements_by_xpath('//xpath...')`, I did get a list with multiple elements. The next step is as simple as getting the specific element I want by using the index of the list.

* Keep learning and don't give up easily.

## Pymysql
#### [PyMySQL]OperationalError: (1045, "Access denied for user 'root'@'localhost' (using password: NO)")
* 连接数据库的代码如下：   
```python
import pymysql
config = {
    'host': 'localhost',
    'user': 'root',
    'password': 'passwd',
    'db': 'metagene',
}
connection = pymysql.connect(**config)
```
* 明明填写了密码，却提示**using password: NO**，到 google 各处转了一大圈，终于锁定了问题所在：使用了最新的 MySQL8.0，而 
  > MySQL8.0 用到了新的密码插件验证方式，5.7叫做mysql_native_password，8.0叫做caching_sha2_password，这种加密方式让很多和MySQL连接的界面工具(如Navicat)或编程语言(如PHP)mysqli接口失效。
  引用自[掘金](https://juejin.im/entry/5adb5deff265da0b9d77cb3b)。
* 两种解决办法，一种是使用 mysql 官方实现的 python 接口 [mysql-connector-python](https://github.com/mysql/mysql-connector-python)，一种是将 MySQL 降级为 5.7 版本。
