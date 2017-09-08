# generatorSqlmapCustom
## 本项目说明
本项目用于根据数据库自动生成mybatis的pojo和mapper类。其中包含基本的增删查改语句，以及example的拓展语句（条件查询等）

功能较强大，基本可以完成日常所需的功能：）

## 使用说明
在generatorConfig.xml中配置以下几个地方
```
<!--修改数据库、用户名、密码-->
<!--数据库连接的信息：驱动类、连接地址、用户名、密码 -->
<jdbcConnection driverClass="com.mysql.jdbc.Driver"
	connectionURL="jdbc:mysql://localhost:3306/springmvc" userId="bos"
	password="bos">
</jdbcConnection>
```

```
<!--以下配置中有三处含有forest的包名，这三处可以根据具体情况修改。用于指定pojo、mapper生成后存放的包名-->
<!-- targetProject:生成PO类的位置 -->
<javaModelGenerator targetPackage="com.forest.springmvc.pojo"
	targetProject=".\src">
	<!-- enableSubPackages:是否让schema作为包的后缀 -->
	<property name="enableSubPackages" value="false" />
	<!-- 从数据库返回的值被清理前后的空格 -->
	<property name="trimStrings" value="true" />
</javaModelGenerator>
<!-- targetProject:mapper映射文件生成的位置 -->
<sqlMapGenerator targetPackage="com.forest.springmvc.mapper" 
	targetProject=".\src">
	<!-- enableSubPackages:是否让schema作为包的后缀 -->
	<property name="enableSubPackages" value="false" />
</sqlMapGenerator>
<!-- targetPackage：mapper接口生成的位置 -->
<javaClientGenerator type="XMLMAPPER"
	targetPackage="com.forest.springmvc.mapper" 
	targetProject=".\src">
	<!-- enableSubPackages:是否让schema作为包的后缀 -->
	<property name="enableSubPackages" value="false" />
</javaClientGenerator>
```
