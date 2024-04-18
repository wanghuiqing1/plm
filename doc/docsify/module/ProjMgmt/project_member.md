# 项目成员(project_member)  <!-- {docsify-ignore-all} -->


记录项目的团队成员及其角色设置。


## 属性
|    中文名col150 | 属性名称col200           | 类型col200     | 长度col100    |允许为空col100    |  备注col500  |
| --------   |------------| -----  | -----  | :----: | -------- |
|建立人|CREATE_MAN|文本，可指定长度|100|否||
|建立时间|CREATE_TIME|日期时间型||否||
|日容量|DAY_CAPACITIES|一对一关系数据对象|1048576|是||
|标识<sup class="footnote-symbol"><font color=orange>[PK]</font></sup>|ID|全局唯一标识，文本类型，用户不可见|100|否||
|姓名|NAME|外键值文本|200|是||
|项目标识|PROJECT_ID|外键值|100|是||
|项目标识（编号）|PROJECT_IDENTIFIER|外键值附加数据|15|是||
|项目名称|PROJECT_NAME|外键值文本|200|是||
|项目类型|PROJECT_TYPE|[外键值附加数据](index/dictionary_index#project_type "项目类型")|60|是||
|角色|ROLE_ID|[单项选择(文本值)](index/dictionary_index#role_type "角色类型")|60|是||
|更新人|UPDATE_MAN|文本，可指定长度|100|否||
|更新时间|UPDATE_TIME|日期时间型||否||
|登录名|USER_ID|外键值|100|是||
|周工作日|WEEKDAY|单项选择(数值)||是||

<p class="panel-title"><b>联合主键</b></p>

  * `项目标识(PROJECT_ID)`
  * `登录名(USER_ID)`

## 关系

<el-row>
<el-tabs v-model="show_der">
<el-tab-pane label="主关系" name="major">

| 名称col350     |   从实体col200 | 关系类型col200     |   备注col500  |
| -------- |---------- |------------|----- |
|[DERCUSTOM_DAY_CAPACITY_PROJECT_MEMBER](der/DERCUSTOM_DAY_CAPACITY_PROJECT_MEMBER)|[日容量(DAY_CAPACITY)](module/ProjMgmt/day_capacity)|自定义关系||


</el-tab-pane>
<el-tab-pane label="从关系" name="minor">

|  名称col350   | 主实体col200   | 关系类型col200   |    备注col500  |
| -------- |---------- |-----------|----- |
|[DER1N_PROJECT_MEMBER_PROJECT_PROJECT_ID](der/DER1N_PROJECT_MEMBER_PROJECT_PROJECT_ID)|[项目(PROJECT)](module/ProjMgmt/project)|1:N关系||
|[DER1N_PROJECT_MEMBER_USER_USER_ID](der/DER1N_PROJECT_MEMBER_USER_USER_ID)|[企业用户(USER)](module/Base/user)|1:N关系||

</el-tab-pane>
</el-tabs>
</el-row>

## 行为
| 中文名col200    | 代码名col150    | 类型col150    | 事务col100   | 批处理col100   | 附加操作col100  | 插件col150    |  备注col300  |
| -------- |---------- |----------- |:----:|:----:|---------| ----- | ----- |
|CheckKey|CheckKey|内置方法|默认|不支持||||
|Create|Create|内置方法|默认|不支持|[附加操作](index/action_logic_index#project_member_Create)|||
|Get|Get|内置方法|默认|不支持||||
|GetDraft|GetDraft|内置方法|默认|不支持||||
|Remove|Remove|内置方法|默认|支持|[附加操作](index/action_logic_index#project_member_Remove)|||
|Save|Save|内置方法|默认|不支持||||
|Update|Update|内置方法|默认|不支持||||
|新建项目成员|create_project_member|[实体处理逻辑](module/ProjMgmt/project_member/logic/create_project_member "新建项目成员")|默认|不支持||||

## 处理逻辑
| 中文名col200    | 代码名col150    | 子类型col150    | 插件col200    |  备注col550  |
| -------- |---------- |----------- |------------|----------|
|[新建项目成员](module/ProjMgmt/project_member/logic/create_project_member)|create_project_member|无||新建项目成员|
|[移除项目成员通知](module/ProjMgmt/project_member/logic/remove_project_member_notify)|remove_project_member_notify|无||移除项目成员时向对应用户发送通知消息|

## 数据查询
| 中文名col200    | 代码名col150    | 默认查询col100 | 权限使用col100 | 自定义SQLcol100 |  备注col600|
| --------  | --------   | :----:  |:----:  | :----:  |----- |
|[数据查询(DEFAULT)](module/ProjMgmt/project_member/query/Default)|DEFAULT|是|否 |否 ||
|[默认（全部数据）(VIEW)](module/ProjMgmt/project_member/query/View)|VIEW|否|否 |否 ||
|[当前项目成员(CUR_PROJECT)](module/ProjMgmt/project_member/query/cur_project)|CUR_PROJECT|否|否 |否 ||

## 数据集合
| 中文名col200  | 代码名col150  | 类型col100 | 默认集合col100 |   插件col200|   备注col500|
| --------  | --------   | :----:   | :----:   | ----- |----- |
|[数据集(DEFAULT)](module/ProjMgmt/project_member/dataset/Default)|DEFAULT|数据查询|是|||
|[当前项目成员(CUR_PROJECT)](module/ProjMgmt/project_member/dataset/cur_project)|CUR_PROJECT|数据查询|否|||

## 数据权限

##### 全部数据（读） :id=project_member-ALL_R

<p class="panel-title"><b>数据范围</b></p>

* `全部数据`

<p class="panel-title"><b>数据能力</b></p>

* `READ`



## 消息通知

|    中文名col200   | 代码名col150       |  消息队列col200   |  消息模板col200 |  通知目标col150     |  备注col350  |
|------------| -----   |  -------- | -------- |-------- |-------- |
|[加入项目成员通知](module/ProjMgmt/project_member/notify/create_member_notify)|create_member_notify|[默认消息队列](index/notify_index)|[项目通知模板(加入项目成员)](index/notify_index#project_member_create)|项目成员 ||
|[移除项目成员通知](module/ProjMgmt/project_member/notify/remove_member_nofity)|remove_member_nofity|[默认消息队列](index/notify_index)|[项目通知模板(移除项目成员)](index/notify_index#project_member_remove)|移除的项目成员 ||

## 搜索模式
|   搜索表达式col350   |    属性名col200    |    搜索模式col200        |备注col500  |
| -------- |------------|------------|------|
|N_ID_EQ|标识|EQ||
|N_NAME_LIKE|姓名|LIKE||
|N_PROJECT_ID_EQ|项目标识|EQ||
|N_PROJECT_NAME_EQ|项目名称|EQ||
|N_PROJECT_NAME_LIKE|项目名称|LIKE||
|N_ROLE_ID_EQ|角色|EQ||
|N_USER_ID_EQ|登录名|EQ||
|N_WEEKDAY_EQ|周工作日|EQ||

## 界面行为
|  中文名col200 |  代码名col150 |  标题col100   |     处理目标col100   |    处理类型col200        |  备注col500       |
| --------| --------| -------- |------------|------------|------------|
| 跳转至成员设置 | jump_to_member_set | 跳转至成员设置 |无数据|用户自定义||
| 移除成员 | remove_member | 移除成员 |单项数据（主键）|<details><summary>后台调用</summary>[Remove](#行为)||

## 界面逻辑
|  中文名col200 | 代码名col150 | 备注col900 |
| --------|--------|--------|
|[新建项目默认临时成员](module/ProjMgmt/project_member/uilogic/create_default_temp_members)|create_default_temp_members|创建临时数据，并将当前用户加入到项目临时成员内|
|[跳转至成员设置](module/ProjMgmt/project_member/uilogic/jump_to_member_set)|jump_to_member_set|通过路由跳转至项目成员设置|

<div style="display: block; overflow: hidden; position: fixed; top: 140px; right: 100px;">

##### 导航
<el-anchor >
<el-anchor-link :href="`#/module/ProjMgmt/project_member?id=属性`">
  属性
</el-anchor-link>
<el-anchor-link :href="`#/module/ProjMgmt/project_member?id=关系`">
  关系
</el-anchor-link>
<el-anchor-link :href="`#/module/ProjMgmt/project_member?id=行为`">
  行为
</el-anchor-link>
<el-anchor-link :href="`#/module/ProjMgmt/project_member?id=处理逻辑`">
  处理逻辑
</el-anchor-link>
<el-anchor-link :href="`#/module/ProjMgmt/project_member?id=数据查询`">
  数据查询
</el-anchor-link>
<el-anchor-link :href="`#/module/ProjMgmt/project_member?id=数据集合`">
  数据集合
</el-anchor-link>
<el-anchor-link :href="`#/module/ProjMgmt/project_member?id=数据权限`">
  数据权限
</el-anchor-link>
<el-anchor-link :href="`#/module/ProjMgmt/project_member?id=消息通知`">
  消息通知
</el-anchor-link>
<el-anchor-link :href="`#/module/ProjMgmt/project_member?id=搜索模式`">
  搜索模式
</el-anchor-link>
<el-anchor-link :href="`#/module/ProjMgmt/project_member?id=界面行为`">
  界面行为
</el-anchor-link>
<el-anchor-link :href="`#/module/ProjMgmt/project_member?id=界面逻辑`">
  界面逻辑
</el-anchor-link>
</el-anchor>
</div>

<script>
 const { createApp } = Vue
  createApp({
    data() {
      return {
show_der:'major',


      }
    },
    methods: {
    }
  }).use(ElementPlus).mount('#app')
</script>