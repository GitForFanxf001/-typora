# GORM[^ go object relationship mapping 对象关系映射]

### 安装

是什么？gorm是go的一个与数据库交互的框架
命令： go get -u -v [http://github.com/jinzhu/gorm](https://link.zhihu.com/?target=http%3A//github.com/jinzhu/gorm)
导包：

~~~ go

// gorm包
"github.com/jinzhu/gorm"
//数据库方言，因为不会直接使用，所以前面要加下划线
_ "github.com/jinzhu/gorm/dialects/mysql"

//调用Open函数连接数据库，第一个参数为对应数据库名称，这里以mysql为例，mariadb也可以使用mysql作为名称。
//第二个参数为刚才设置好的url。
//得到两个结果：第一个为连接后对象，用于操作数据库对象；第二个为错误信息，连接失败会返回内容，连接成功返回nil，空。
dbConn, err := gorm.Open("mysql", "root:123456@tcp(127.0.0.1:3306)/test1?charset=utf8&parseTime=True&loc=Local")
if err != nil {
		panic(err)
}
dbConn.Close()
~~~

## 表操作

### 创建

gorm创建表基于结构体，创建结构体的时候要考虑表结构，默认结构体的第一个字段为主键。

~~~ 
//创建结构体映射表结构
type User struct {
	Id int
	Name string
	Data string
}
// 直接创建表
dbConn.CreateTable(&User{})
// 自定义表名创建表
dbConn.Table("user").Create(&User{})
~~~



