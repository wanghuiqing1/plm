## 最近访问跳转其他视图 <!-- {docsify-ignore-all} -->

   首页最近访问点击后跳转其他视图

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
state "开始" as Begin <<start>> [[$./recent_jump_other_view#begin {开始}]]
state "项目类" as PREPAREJSPARAM6  [[$./recent_jump_other_view#preparejsparam6 {项目类}]]
state "结束" as END1 <<end>> [[$./recent_jump_other_view#end1 {结束}]]
state "选取的数据" as DEBUGPARAM2  [[$./recent_jump_other_view#debugparam2 {选取的数据}]]
state "知识类" as PREPAREJSPARAM11  [[$./recent_jump_other_view#preparejsparam11 {知识类}]]
state "获取选中卡片" as PREPAREJSPARAM1  [[$./recent_jump_other_view#preparejsparam1 {获取选中卡片}]]
state "清空父类标识" as PREPAREJSPARAM10  [[$./recent_jump_other_view#preparejsparam10 {清空父类标识}]]
state "测试用例" as PREPAREJSPARAM9  [[$./recent_jump_other_view#preparejsparam9 {测试用例}]]
state "工单" as PREPAREJSPARAM5  [[$./recent_jump_other_view#preparejsparam5 {工单}]]
state "表格" as DEBUGPARAM5  [[$./recent_jump_other_view#debugparam5 {表格}]]
state "获取选中表格行" as PREPAREJSPARAM2  [[$./recent_jump_other_view#preparejsparam2 {获取选中表格行}]]
state "工作项" as PREPAREJSPARAM7  [[$./recent_jump_other_view#preparejsparam7 {工作项}]]
state "产品类" as PREPAREJSPARAM3  [[$./recent_jump_other_view#preparejsparam3 {产品类}]]
state "卡片" as DEBUGPARAM4  [[$./recent_jump_other_view#debugparam4 {卡片}]]
state "重定向跳转" as DEUIACTION1  [[$./recent_jump_other_view#deuiaction1 {重定向跳转}]]
state "获取选中数据详情" as RAWJSCODE1  [[$./recent_jump_other_view#rawjscode1 {获取选中数据详情}]]
state "需求" as PREPAREJSPARAM4  [[$./recent_jump_other_view#preparejsparam4 {需求}]]
state "测试类" as PREPAREJSPARAM8  [[$./recent_jump_other_view#preparejsparam8 {测试类}]]
state "页面" as PREPAREJSPARAM12  [[$./recent_jump_other_view#preparejsparam12 {页面}]]


Begin --> DEBUGPARAM4 : [[$./recent_jump_other_view#begin-debugparam4{最近使用} 最近使用]]
DEBUGPARAM4 --> PREPAREJSPARAM1
PREPAREJSPARAM1 --> DEBUGPARAM2
DEBUGPARAM2 --> RAWJSCODE1
RAWJSCODE1 --> PREPAREJSPARAM3 : [[$./recent_jump_other_view#rawjscode1-preparejsparam3{父类型为产品} 父类型为产品]]
PREPAREJSPARAM3 --> DEUIACTION1 : [[$./recent_jump_other_view#preparejsparam3-deuiaction1{最近访问数据（打开父）} 最近访问数据（打开父）]]
DEUIACTION1 --> PREPAREJSPARAM10
PREPAREJSPARAM10 --> END1
PREPAREJSPARAM3 --> PREPAREJSPARAM4 : [[$./recent_jump_other_view#preparejsparam3-preparejsparam4{子类型为需求} 子类型为需求]]
PREPAREJSPARAM4 --> DEUIACTION1
PREPAREJSPARAM3 --> PREPAREJSPARAM5 : [[$./recent_jump_other_view#preparejsparam3-preparejsparam5{子类型为工单} 子类型为工单]]
PREPAREJSPARAM5 --> DEUIACTION1
RAWJSCODE1 --> PREPAREJSPARAM6 : [[$./recent_jump_other_view#rawjscode1-preparejsparam6{父类型为项目} 父类型为项目]]
PREPAREJSPARAM6 --> DEUIACTION1 : [[$./recent_jump_other_view#preparejsparam6-deuiaction1{最近访问数据（打开父）} 最近访问数据（打开父）]]
PREPAREJSPARAM6 --> PREPAREJSPARAM7 : [[$./recent_jump_other_view#preparejsparam6-preparejsparam7{子类型为工作项} 子类型为工作项]]
PREPAREJSPARAM7 --> DEUIACTION1
RAWJSCODE1 --> PREPAREJSPARAM8 : [[$./recent_jump_other_view#rawjscode1-preparejsparam8{父类型为测试库} 父类型为测试库]]
PREPAREJSPARAM8 --> DEUIACTION1 : [[$./recent_jump_other_view#preparejsparam8-deuiaction1{最近访问数据（打开父）} 最近访问数据（打开父）]]
PREPAREJSPARAM8 --> PREPAREJSPARAM9 : [[$./recent_jump_other_view#preparejsparam8-preparejsparam9{子类型为测试用例} 子类型为测试用例]]
PREPAREJSPARAM9 --> DEUIACTION1
RAWJSCODE1 --> PREPAREJSPARAM11 : [[$./recent_jump_other_view#rawjscode1-preparejsparam11{连接名称} 连接名称]]
PREPAREJSPARAM11 --> PREPAREJSPARAM12 : [[$./recent_jump_other_view#preparejsparam11-preparejsparam12{连接名称} 连接名称]]
PREPAREJSPARAM12 --> DEUIACTION1
PREPAREJSPARAM11 --> DEUIACTION1 : [[$./recent_jump_other_view#preparejsparam11-deuiaction1{连接名称} 连接名称]]
Begin --> DEBUGPARAM5 : [[$./recent_jump_other_view#begin-debugparam5{最近访问} 最近访问]]
DEBUGPARAM5 --> PREPAREJSPARAM2
PREPAREJSPARAM2 --> DEBUGPARAM2


@enduml
```


### 处理步骤说明

#### 需求 :id=PREPAREJSPARAM4<sup class="footnote-symbol"> <font color=gray size=1>[准备参数]</font></sup>



1. 将`selectobj(选中数据).owner_id` 设置给  `ctx(上下文参数).idea`

#### 产品类 :id=PREPAREJSPARAM3<sup class="footnote-symbol"> <font color=gray size=1>[准备参数]</font></sup>



1. 将`selectobj(选中数据).recent_parent` 设置给  `ctx(上下文参数).product`
2. 将`selectobj(选中数据).owner_subtype` 设置给  `ctx(上下文参数).owner_subtype`

#### 工单 :id=PREPAREJSPARAM5<sup class="footnote-symbol"> <font color=gray size=1>[准备参数]</font></sup>



1. 将`selectobj(选中数据).owner_id` 设置给  `ctx(上下文参数).ticket`

#### 卡片 :id=DEBUGPARAM4<sup class="footnote-symbol"> <font color=gray size=1>[调试逻辑参数]</font></sup>



> [!NOTE|label:调试信息|icon:fa fa-bug]
> 调试输出参数`卡片参数`的详细信息

#### 获取选中卡片 :id=PREPAREJSPARAM1<sup class="footnote-symbol"> <font color=gray size=1>[准备参数]</font></sup>



1. 将`DATAVIEW(卡片参数).state` 设置给  `STATE(state)`
2. 将`STATE(state).selectedData` 设置给  `selectedData(选中数据（数组）)`

#### 测试类 :id=PREPAREJSPARAM8<sup class="footnote-symbol"> <font color=gray size=1>[准备参数]</font></sup>



1. 将`selectobj(选中数据).recent_parent` 设置给  `ctx(上下文参数).library`
2. 将`selectobj(选中数据).owner_subtype` 设置给  `ctx(上下文参数).owner_subtype`

#### 选取的数据 :id=DEBUGPARAM2<sup class="footnote-symbol"> <font color=gray size=1>[调试逻辑参数]</font></sup>



> [!NOTE|label:调试信息|icon:fa fa-bug]
> 调试输出参数`选中数据（数组）`的详细信息

#### 获取选中数据详情 :id=RAWJSCODE1<sup class="footnote-symbol"> <font color=gray size=1>[直接前台代码]</font></sup>

用脚本处理，获取第一条数据（因为只有会一条数据）

<p class="panel-title"><b>执行代码</b></p>

```javascript
let selecteddata=uiLogic.selecteddata;
if (selecteddata.length > 0) {
    uiLogic.selectobj = selecteddata[0];
}
```

#### 开始 :id=Begin<sup class="footnote-symbol"> <font color=gray size=1>[开始]</font></sup>




#### 结束 :id=END1<sup class="footnote-symbol"> <font color=gray size=1>[结束]</font></sup>




#### 重定向跳转 :id=DEUIACTION1<sup class="footnote-symbol"> <font color=gray size=1>[实体界面行为调用]</font></sup>



调用实体 [最近访问(RECENT)](module/Base/recent.md) 界面行为 [通过重定向视图跳转](module/Base/recent#界面行为) ，行为参数为`selectedData(选中数据（数组）)`

#### 清空父类标识 :id=PREPAREJSPARAM10<sup class="footnote-symbol"> <font color=gray size=1>[准备参数]</font></sup>



1. 将`空值（NULL）` 设置给  `ctx(上下文参数).library`
2. 将`空值（NULL）` 设置给  `ctx(上下文参数).product`
3. 将`空值（NULL）` 设置给  `ctx(上下文参数).project`

#### 表格 :id=DEBUGPARAM5<sup class="footnote-symbol"> <font color=gray size=1>[调试逻辑参数]</font></sup>



> [!NOTE|label:调试信息|icon:fa fa-bug]
> 调试输出参数`表格部件参数`的详细信息

#### 获取选中表格行 :id=PREPAREJSPARAM2<sup class="footnote-symbol"> <font color=gray size=1>[准备参数]</font></sup>



1. 将`grid(表格部件参数).state` 设置给  `STATE(state)`
2. 将`STATE(state).selectedData` 设置给  `selectedData(选中数据（数组）)`

#### 测试用例 :id=PREPAREJSPARAM9<sup class="footnote-symbol"> <font color=gray size=1>[准备参数]</font></sup>



1. 将`selectobj(选中数据).owner_id` 设置给  `ctx(上下文参数).test_case`

#### 项目类 :id=PREPAREJSPARAM6<sup class="footnote-symbol"> <font color=gray size=1>[准备参数]</font></sup>



1. 将`selectobj(选中数据).recent_parent` 设置给  `ctx(上下文参数).project`
2. 将`selectobj(选中数据).owner_subtype` 设置给  `ctx(上下文参数).owner_subtype`

#### 工作项 :id=PREPAREJSPARAM7<sup class="footnote-symbol"> <font color=gray size=1>[准备参数]</font></sup>



1. 将`selectobj(选中数据).owner_id` 设置给  `ctx(上下文参数).work_item`

#### 知识类 :id=PREPAREJSPARAM11<sup class="footnote-symbol"> <font color=gray size=1>[准备参数]</font></sup>



1. 将`selectobj(选中数据).recent_parent` 设置给  `ctx(上下文参数).space`
2. 将`selectobj(选中数据).owner_subtype` 设置给  `ctx(上下文参数).owner_subtype`

#### 页面 :id=PREPAREJSPARAM12<sup class="footnote-symbol"> <font color=gray size=1>[准备参数]</font></sup>



1. 将`selectobj(选中数据).owner_id` 设置给  `ctx(上下文参数).article_page`

### 连接条件说明
#### 最近使用 :id=Begin-DEBUGPARAM4

```this_obj(当前部件对象).name``` EQ ```dataview```
#### 父类型为产品 :id=RAWJSCODE1-PREPAREJSPARAM3

```selectobj(选中数据).owner_type``` EQ ```product```
#### 最近访问数据（打开父） :id=PREPAREJSPARAM3-DEUIACTION1

```selectobj(选中数据).type``` EQ ```1```
#### 子类型为需求 :id=PREPAREJSPARAM3-PREPAREJSPARAM4

```selectobj(选中数据).owner_subtype``` EQ ```idea```
#### 子类型为工单 :id=PREPAREJSPARAM3-PREPAREJSPARAM5

```selectobj(选中数据).owner_subtype``` EQ ```ticket```
#### 父类型为项目 :id=RAWJSCODE1-PREPAREJSPARAM6

```selectobj(选中数据).owner_type``` EQ ```project```
#### 最近访问数据（打开父） :id=PREPAREJSPARAM6-DEUIACTION1

```selectobj(选中数据).type``` EQ ```1```
#### 子类型为工作项 :id=PREPAREJSPARAM6-PREPAREJSPARAM7

```selectobj(选中数据).owner_subtype``` EQ ```work_item```
#### 父类型为测试库 :id=RAWJSCODE1-PREPAREJSPARAM8

```selectobj(选中数据).owner_type``` EQ ```library```
#### 最近访问数据（打开父） :id=PREPAREJSPARAM8-DEUIACTION1

```selectobj(选中数据).type``` EQ ```1```
#### 子类型为测试用例 :id=PREPAREJSPARAM8-PREPAREJSPARAM9

```selectobj(选中数据).owner_subtype``` EQ ```test_case```
#### 连接名称 :id=RAWJSCODE1-PREPAREJSPARAM11

```selectobj(选中数据).owner_type``` EQ ```space```
#### 连接名称 :id=PREPAREJSPARAM11-PREPAREJSPARAM12

```selectobj(选中数据).owner_subtype``` EQ ```page```
#### 连接名称 :id=PREPAREJSPARAM11-DEUIACTION1

```selectobj(选中数据).owner_subtype``` EQ ```space```
#### 最近访问 :id=Begin-DEBUGPARAM5

```this_obj(当前部件对象).name``` EQ ```grid```


### 实体逻辑参数

|    中文名   |    代码名    |  数据类型      |备注 |
| --------| --------| --------  | --------   |
|卡片参数|DATAVIEW|部件对象||
|选中数据（数组）|selectedData|简单数据列表||
|当前视图|cur_view|当前视图对象||
|选中数据|selectobj|数据对象||
|当前部件对象|this_obj|当前部件对象||
|表格部件参数|grid|部件对象||
|传入变量(<i class="fa fa-check"/></i>)|Default|数据对象||
|上下文参数|ctx|导航视图参数绑定参数||
|state|STATE|数据对象||
