## 测试判断只读用户 <!-- {docsify-ignore-all} -->

   判断当前用户是否为只读用户，调用后台处理逻辑获取当前产品成员并判断返回

### 处理过程

```plantuml
@startuml
hide footbox
<style>
root {
  HyperlinkColor #42b983
}
</style>

hide empty description
state "开始" as Begin <<start>> [[$./test_get_only_read#begin {开始}]]
state "传递是否只读给页面" as PREPAREJSPARAM2  [[$./test_get_only_read#preparejsparam2 {传递是否只读给页面}]]
state "结束" as END1 <<end>> [[$./test_get_only_read#end1 {结束}]]
state "实体行为" as DEACTION1  [[$./test_get_only_read#deaction1 {实体行为}]]
state "VIEW11111" as DEBUGPARAM2  [[$./test_get_only_read#debugparam2 {VIEW11111}]]
state "准备参数" as PREPAREJSPARAM3  [[$./test_get_only_read#preparejsparam3 {准备参数}]]
state "执行获取人员后的返回结果" as DEBUGPARAM1  [[$./test_get_only_read#debugparam1 {执行获取人员后的返回结果}]]
state "准备参数" as PREPAREJSPARAM4  [[$./test_get_only_read#preparejsparam4 {准备参数}]]


Begin --> DEBUGPARAM2
DEBUGPARAM2 --> PREPAREJSPARAM3
PREPAREJSPARAM3 --> DEACTION1 : [[$./test_get_only_read#preparejsparam3-deaction1{连接名称} 连接名称]]
DEACTION1 --> DEBUGPARAM1
DEBUGPARAM1 --> PREPAREJSPARAM2 : [[$./test_get_only_read#debugparam1-preparejsparam2{连接名称} 连接名称]]
PREPAREJSPARAM2 --> END1
PREPAREJSPARAM3 --> PREPAREJSPARAM4 : [[$./test_get_only_read#preparejsparam3-preparejsparam4{连接名称} 连接名称]]
PREPAREJSPARAM4 --> END1


@enduml
```


### 处理步骤说明

#### 开始 :id=Begin<sup class="footnote-symbol"> <font color=gray size=1>[开始]</font></sup>




#### VIEW11111 :id=DEBUGPARAM2<sup class="footnote-symbol"> <font color=gray size=1>[调试逻辑参数]</font></sup>



> [!NOTE|label:调试信息|icon:fa fa-bug]
> 调试输出参数`view`的详细信息

#### 实体行为 :id=DEACTION1<sup class="footnote-symbol"> <font color=gray size=1>[实体行为]</font></sup>



调用实体 [用例(TEST_CASE)](module/TestMgmt/test_case.md) 行为 [获取测试库成员(fill_library_member)](module/TestMgmt/test_case#行为) ，行为参数为`Default(传入变量)`

将执行结果返回给参数`Default(传入变量)`

#### 执行获取人员后的返回结果 :id=DEBUGPARAM1<sup class="footnote-symbol"> <font color=gray size=1>[调试逻辑参数]</font></sup>



> [!NOTE|label:调试信息|icon:fa fa-bug]
> 调试输出参数`传入变量`的详细信息

#### 传递是否只读给页面 :id=PREPAREJSPARAM2<sup class="footnote-symbol"> <font color=gray size=1>[准备参数]</font></sup>



1. 将`true` 设置给  `viewctx(上下文).srfreadonly`

#### 结束 :id=END1<sup class="footnote-symbol"> <font color=gray size=1>[结束]</font></sup>




#### 准备参数 :id=PREPAREJSPARAM3<sup class="footnote-symbol"> <font color=gray size=1>[准备参数]</font></sup>



1. 将`view.params` 绑定给  `view_params(视图参数)`

#### 准备参数 :id=PREPAREJSPARAM4<sup class="footnote-symbol"> <font color=gray size=1>[准备参数]</font></sup>



1. 将`true` 设置给  `viewctx(上下文).srfreadonly`

### 连接条件说明
#### 连接名称 :id=PREPAREJSPARAM3-DEACTION1

```view_params(视图参数).srfversionid``` ISNULL
#### 连接名称 :id=DEBUGPARAM1-PREPAREJSPARAM2

```Default(传入变量).readonly``` EQ ```true```
#### 连接名称 :id=PREPAREJSPARAM3-PREPAREJSPARAM4

```view_params(视图参数).srfversionid``` ISNOTNULL


### 实体逻辑参数

|    中文名   |    代码名    |  数据类型      |备注 |
| --------| --------| --------  | --------   |
|应用对象|app_obj|应用程序变量||
|工单信息|ticket_info|数据对象||
|成员信息|members|分页查询||
|传入变量(<i class="fa fa-check"/></i>)|Default|数据对象||
|上下文|viewctx|导航视图参数绑定参数||
|过滤器|filter|过滤器||
|产品信息|product|数据对象||
|view|view|当前视图对象||
|视图参数|view_params|数据对象||
