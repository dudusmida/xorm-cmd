# xorm-cmd2
本项目基于[xorm-cmd](https://github.com/go-xorm/cmd)
依据自身需求在其基础上增加所需要的功能，目前主要针对mysql的代码生成做调整，其他的诸如暂时没有进行自测
原项目讲解可以去[xorm-cmd](https://github.com/go-xorm/cmd)参考

# 新增功能

* 增加注释功能
* 在tag中增加fieldName

## 增加注释功能
可以参考templates/goxorm/config文件中的structNote字段

## 在tag中增加fieldName
原项目生成结构体后字段对应的tag并没有对应的fieldName
```
 // TestTable 测试表
type TestTable struct {
	RoleID   int       `json:"role_id" xorm:"not null pk comment('角色ID')   INT(11)"`
}

```
调整后
```
 // TestTable 测试表
type TestTable struct {
	RoleID   int      `json:"role_id" xorm:"not null pk comment('角色ID') 'role_id'  INT(11)"`
}

```

# 后续更新计划
下个版本计划更新：指定table生成struct