## 客户选择工单 <!-- {docsify-ignore-all} -->

   客户选择工单操作，更新工单的客户属性

### 处理过程

```plantuml
@startuml
hide empty description
<style>
root {
  HyperlinkColor #42b983
}
</style>

hide empty description
state "开始" as Begin <<start>> [[$./customer_choose_ticket#begin {"开始"}]]
state "获取选中数据" as PREPAREPARAM1  [[$./customer_choose_ticket#prepareparam1 {"获取选中数据"}]]
state "循环子调用" as LOOPSUBCALL1  [[$./customer_choose_ticket#loopsubcall1 {"循环子调用"}]] #green {
state "重新建立参数" as RENEWPARAM1  [[$./customer_choose_ticket#renewparam1 {"重新建立参数"}]]
state "填充更新属性" as PREPAREPARAM2  [[$./customer_choose_ticket#prepareparam2 {"填充更新属性"}]]
state "更新工单信息" as DEACTION1  [[$./customer_choose_ticket#deaction1 {"更新工单信息"}]]
}


Begin --> PREPAREPARAM1
PREPAREPARAM1 --> LOOPSUBCALL1
LOOPSUBCALL1 --> RENEWPARAM1
RENEWPARAM1 --> PREPAREPARAM2
PREPAREPARAM2 --> DEACTION1


@enduml
```


### 处理步骤说明

#### 开始 :id=Begin<sup class="footnote-symbol"> <font color=gray size=1>[开始]</font></sup>



*- N/A*
#### 获取选中数据 :id=PREPAREPARAM1<sup class="footnote-symbol"> <font color=gray size=1>[准备参数]</font></sup>



1. 将`Default(传入变量).srfactionparam` 绑定给  `srfactionparam(选中的客户列表)`

#### 循环子调用 :id=LOOPSUBCALL1<sup class="footnote-symbol"> <font color=gray size=1>[循环子调用]</font></sup>



循环参数`srfactionparam(选中的客户列表)`，子循环参数使用`for_temp_obj(循环临时变量)`
#### 重新建立参数 :id=RENEWPARAM1<sup class="footnote-symbol"> <font color=gray size=1>[重新建立参数]</font></sup>



重建参数```update_obj(更新对象)```
#### 填充更新属性 :id=PREPAREPARAM2<sup class="footnote-symbol"> <font color=gray size=1>[准备参数]</font></sup>



1. 将`for_temp_obj(循环临时变量).owner_id` 设置给  `update_obj(更新对象).ID(标识)`
2. 将`Default(传入变量).customer_id` 设置给  `update_obj(更新对象).CUSTOMER_ID`

#### 更新工单信息 :id=DEACTION1<sup class="footnote-symbol"> <font color=gray size=1>[实体行为]</font></sup>



调用实体 [工单(TICKET)](module/ProdMgmt/ticket.md) 行为 [Update](module/ProdMgmt/ticket#行为) ，行为参数为`update_obj(更新对象)`



### 实体逻辑参数

|    中文名   |    代码名    |  数据类型    |  实体   |备注 |
| --------| --------| -------- | -------- | --------   |
|传入变量(<i class="fa fa-check"/></i>)|Default|数据对象|[客户(CUSTOMER)](module/ProdMgmt/customer.md)||
|循环临时变量|for_temp_obj|数据对象|[客户(CUSTOMER)](module/ProdMgmt/customer.md)||
|选中的客户列表|srfactionparam|数据对象列表|[客户(CUSTOMER)](module/ProdMgmt/customer.md)||
|当前工单|this_ticket|数据对象|[客户(CUSTOMER)](module/ProdMgmt/customer.md)||
|更新对象|update_obj|数据对象|[客户(CUSTOMER)](module/ProdMgmt/customer.md)||
