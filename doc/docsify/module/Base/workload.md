# 工时(workload)  <!-- {docsify-ignore-all} -->


记录项目执行过程中各类工作的时间消耗。


## 属性
|    中文名col150 | 属性名称col200           | 类型col200     | 长度col100    |允许为空col100    |  备注col500  |
| --------   |------------| -----  | -----  | :----: | -------- |
|建立人|CREATE_MAN|文本，可指定长度|100|否||
|建立时间|CREATE_TIME|日期时间型||否||
|描述|DESCRIPTION|长文本，没有长度限制|1048576|是||
|时长|DURATION|数值||否||
|标识<sup class="footnote-symbol"><font color=orange>[PK]</font></sup>|ID|全局唯一标识，文本类型，用户不可见|100|否||
|需求|IDEA|外键值对象|1048576|是||
|编号<sup class="footnote-symbol">[[序列]](index/sequence_index#seq_work_item_id)</sup>|IDENTIFIER|文本，可指定长度|100|是||
|事项|NAME|文本，可指定长度|500|否||
|所属数据对象|OWNER_TYPE|文本，可指定长度|100|是||
|工时主体标识|PRINCIPAL_ID|文本，可指定长度|100|是||
|工时主体类型|PRINCIPAL_TYPE|文本，可指定长度|100|是||
|访问父类|RECENT_PARENT|文本，可指定长度|100|是||
|访问父类编号|RECENT_PARENT_IDENTIFIER|文本，可指定长度|100|是||
|访问父类名称|RECENT_PARENT_NAME|文本，可指定长度|100|是||
|工作日期|REGISTER_DATE|日期型||否||
|编号|SHOW_IDENTIFIER|文本，可指定长度|200|是||
|用例|TEST_CASE|外键值对象|1048576|是||
|类别|TYPE_ID|外键值|100|是||
|名称|TYPE_NAME|外键值文本|200|是||
|更新人|UPDATE_MAN|文本，可指定长度|100|否||
|更新时间|UPDATE_TIME|日期时间型||否||
|工作项|WORK_ITEM|外键值对象|1048576|是||


###### 索引

<el-row>
<el-tabs v-model="show_index">

<el-tab-pane label="WORKLOAD2" name="index_WORKLOAD2">

|    中文名col150 | 属性名称col200           | 包含属性col100 | 排序方向col100 | 索引长度col100 | 备注col600 |
| --------   |------------| -----  | -----  | :----: | -------- |
|工时主体标识|PRINCIPAL_ID|false|升序|-1||
|工作日期|REGISTER_DATE|false|升序|-1||

</el-tab-pane>
<el-tab-pane label="WORKLOAD" name="index_WORKLOAD">

|    中文名col150 | 属性名称col200           | 包含属性col100 | 排序方向col100 | 索引长度col100 | 备注col600 |
| --------   |------------| -----  | -----  | :----: | -------- |
|建立人|CREATE_MAN|false|升序|-1||
|工时主体标识|PRINCIPAL_ID|false|升序|-1||

</el-tab-pane>

</el-tabs>
</el-row>

## 关系

<el-row>
<el-tabs v-model="show_der">
<el-tab-pane label="从关系" name="minor">

|  名称col350   | 主实体col200   | 关系类型col200   |    备注col500  |
| -------- |---------- |-----------|----- |
|[DER1N_WORKLOAD_WORKLOAD_TYPE_TYPE_ID](der/DER1N_WORKLOAD_WORKLOAD_TYPE_TYPE_ID)|[工时类别(WORKLOAD_TYPE)](module/Base/workload_type)|1:N关系||
|[DERCUSTOM_IDEA_WORKLOAD](der/DERCUSTOM_IDEA_WORKLOAD)|[需求(IDEA)](module/ProdMgmt/idea)|自定义关系||
|[DERCUSTOM_TEST_CASE_WORKLOAD](der/DERCUSTOM_TEST_CASE_WORKLOAD)|[用例(TEST_CASE)](module/TestMgmt/test_case)|自定义关系||
|[DERCUSTOM_WORK_ITEM_WORKLOAD](der/DERCUSTOM_WORK_ITEM_WORKLOAD)|[工作项(WORK_ITEM)](module/ProjMgmt/work_item)|自定义关系||

</el-tab-pane>
</el-tabs>
</el-row>

## 行为
| 中文名col200    | 代码名col150    | 类型col150    | 事务col100   | 批处理col100   | 附加操作col100  | 插件col150    |  备注col300  |
| -------- |---------- |----------- |:----:|:----:|---------| ----- | ----- |
|CheckKey|CheckKey|内置方法|默认|不支持||||
|Create|Create|内置方法|默认|不支持||||
|Get|Get|内置方法|默认|不支持||||
|GetDraft|GetDraft|内置方法|默认|不支持||||
|Remove|Remove|内置方法|默认|支持|[附加操作](index/action_logic_index#workload_Remove)|||
|Save|Save|内置方法|默认|不支持||||
|Update|Update|内置方法|默认|不支持||||
|登记工时并更新剩余工时|create_workload|[实体处理逻辑](module/Base/workload/logic/save_workload "登记工时并更新剩余工时")|默认|不支持||||
|获取已登记工时|get_register_workload|[实体处理逻辑](module/Base/workload/logic/get_register_workload "获取已登记工时")|默认|不支持|||修改实际工时表单获取数据行为|
|修改工时并更新剩余工时|update_workload|[实体处理逻辑](module/Base/workload/logic/save_workload "登记工时并更新剩余工时")|默认|不支持||||

## 处理逻辑
| 中文名col200    | 代码名col150    | 子类型col150    | 插件col200    |  备注col550  |
| -------- |---------- |----------- |------------|----------|
|[产品需求维度工时日历查询](module/Base/workload/logic/idea_dimension)|idea_dimension|无||首页工作台工时日历：产品/产品需求维度查询数据使用|
|[产品需求维度管理工时日历查询](module/Base/workload/logic/idea_management_dimension)|idea_management_dimension|无||工时管理菜单中工时日历：产品/产品需求维度查询数据使用|
|[人员维度工时日历查询](module/Base/workload/logic/member_dimension)|member_dimension|无||工时管理菜单中工时日历：人员维度查询数据使用|
|[删除工时记录前附加逻辑](module/Base/workload/logic/before_remove)|before_remove|无||更新动态存储中的剩余工时|
|[工作类别维度工时日历查询](module/Base/workload/logic/type_of_dimension)|type_of_dimension|无||首页工作台工时日历：工作类型维度查询数据使用|
|[工作类别维度管理工时日历查询](module/Base/workload/logic/type_of_management_dimension)|type_of_management_dimension|无||工时管理菜单中工时日历：工作类型维度查询数据使用|
|[工作项维度工时日历查询](module/Base/workload/logic/work_item_dimension)|work_item_dimension|无||首页工作台工时日历：项目/工作项维度查询数据使用|
|[工作项维度管理工时日历查询](module/Base/workload/logic/work_item_management_dimension)|work_item_management_dimension|无||工时管理菜单中工时日历：项目/工作项维度查询数据使用|
|[测试用例维度工时日历查询](module/Base/workload/logic/test_case_dimension)|test_case_dimension|无||首页工作台工时日历：测试库/测试用例维度查询数据使用|
|[测试用例维度管理工时日历查询](module/Base/workload/logic/test_case_management_dimension)|test_case_management_dimension|无||工时管理菜单中工时日历：测试库/测试用例维度查询数据使用|
|[登记工时并更新剩余工时](module/Base/workload/logic/save_workload)|save_workload|无||保存实际登记工时记录，并计算重置剩余工时属性|
|[获取已登记工时](module/Base/workload/logic/get_register_workload)|get_register_workload|无||查看工时详情时，获取预估、已登记、剩余工时；并计算出工时进度|

## 数据查询
| 中文名col200    | 代码名col150    | 默认查询col100 | 权限使用col100 | 自定义SQLcol100 |  备注col600|
| --------  | --------   | :----:  |:----:  | :----:  |----- |
|[数据查询(DEFAULT)](module/Base/workload/query/Default)|DEFAULT|是|否 |否 ||
|[默认（全部数据）(VIEW)](module/Base/workload/query/View)|VIEW|否|否 |否 ||
|[工时日历(calendar)](module/Base/workload/query/calendar)|calendar|否|否 |否 ||
|[产品需求工时(idea_workload)](module/Base/workload/query/idea_workload)|idea_workload|否|否 |否 ||
|[工时日志(log)](module/Base/workload/query/log)|log|否|否 |否 ||
|[我的工时日历(my_calendar)](module/Base/workload/query/my_calendar)|my_calendar|否|否 |否 ||
|[我的产品需求工时(my_idea_workload)](module/Base/workload/query/my_idea_workload)|my_idea_workload|否|否 |否 ||
|[我登记的工时日志(my_log)](module/Base/workload/query/my_log)|my_log|否|否 |否 ||
|[我的测试用例工时(my_test_case_workload)](module/Base/workload/query/my_test_case_workload)|my_test_case_workload|否|否 |否 ||
|[我的工作类别记录(my_type_of)](module/Base/workload/query/my_type_of)|my_type_of|否|否 |否 ||
|[我的工作项工时(my_work_item_workload)](module/Base/workload/query/my_work_item_workload)|my_work_item_workload|否|否 |否 ||
|[测试用例工时(test_case_workload)](module/Base/workload/query/test_case_workload)|test_case_workload|否|否 |否 ||
|[工作类别记录(type_of)](module/Base/workload/query/type_of)|type_of|否|否 |否 ||
|[工作项工时(work_item_workload)](module/Base/workload/query/work_item_workload)|work_item_workload|否|否 |否 ||

## 数据集合
| 中文名col200  | 代码名col150  | 类型col100 | 默认集合col100 |   插件col200|   备注col500|
| --------  | --------   | :----:   | :----:   | ----- |----- |
|[数据集(DEFAULT)](module/Base/workload/dataset/Default)|DEFAULT|数据查询|是|||
|[工时日历(calendar)](module/Base/workload/dataset/calendar)|calendar|数据查询|否|||
|[产品需求维度(idea_dimension)](module/Base/workload/dataset/idea_dimension)|idea_dimension|[实体逻辑](module/Base/workload/logic/idea_dimension)|否|||
|[产品需求管理维度(idea_management_dimension)](module/Base/workload/dataset/idea_management_dimension)|idea_management_dimension|[实体逻辑](module/Base/workload/logic/idea_management_dimension)|否|||
|[产品需求工时(idea_workload)](module/Base/workload/dataset/idea_workload)|idea_workload|数据查询|否|||
|[工时日志(log)](module/Base/workload/dataset/log)|log|数据查询|否|||
|[人员维度(member_dimension)](module/Base/workload/dataset/member_dimension)|member_dimension|[实体逻辑](module/Base/workload/logic/member_dimension)|否|||
|[我的工时日历(my_calendar)](module/Base/workload/dataset/my_calendar)|my_calendar|数据查询|否|||
|[我的产品需求工时(my_idea_workload)](module/Base/workload/dataset/my_idea_workload)|my_idea_workload|数据查询|否|||
|[我登记的工时日志(my_log)](module/Base/workload/dataset/my_log)|my_log|数据查询|否|||
|[我的测试用例工时(my_test_case_workload)](module/Base/workload/dataset/my_test_case_workload)|my_test_case_workload|数据查询|否|||
|[我的工作类别记录(my_type_of)](module/Base/workload/dataset/my_type_of)|my_type_of|数据查询|否|||
|[我的工作项工时(my_work_item_workload)](module/Base/workload/dataset/my_work_item_workload)|my_work_item_workload|数据查询|否|||
|[测试用例维度(test_case_dimension)](module/Base/workload/dataset/test_case_dimension)|test_case_dimension|[实体逻辑](module/Base/workload/logic/test_case_dimension)|否|||
|[测试用例管理维度(test_case_management_dimension)](module/Base/workload/dataset/test_case_management_dimension)|test_case_management_dimension|[实体逻辑](module/Base/workload/logic/test_case_management_dimension)|否|||
|[测试用例工时(test_case_workload)](module/Base/workload/dataset/test_case_workload)|test_case_workload|数据查询|否|||
|[工作类别记录(type_of)](module/Base/workload/dataset/type_of)|type_of|数据查询|否|||
|[工作类别维度(type_of_dimension)](module/Base/workload/dataset/type_of_dimension)|type_of_dimension|[实体逻辑](module/Base/workload/logic/type_of_dimension)|否|||
|[工作类别管理维度(type_of_management_dimension)](module/Base/workload/dataset/type_of_management_dimension)|type_of_management_dimension|[实体逻辑](module/Base/workload/logic/type_of_management_dimension)|否|||
|[工作项维度(work_item_dimension)](module/Base/workload/dataset/work_item_dimension)|work_item_dimension|[实体逻辑](module/Base/workload/logic/work_item_dimension)|否|||
|[工作项管理维度(work_item_management_dimension)](module/Base/workload/dataset/work_item_management_dimension)|work_item_management_dimension|[实体逻辑](module/Base/workload/logic/work_item_management_dimension)|否|||
|[工作项工时(work_item_workload)](module/Base/workload/dataset/work_item_workload)|work_item_workload|数据查询|否|||

## 数据权限

##### 全部数据（读写） :id=workload-ALL_RW

<p class="panel-title"><b>数据范围</b></p>

* `全部数据`

<p class="panel-title"><b>数据能力</b></p>

* `READ`
* `DELETE`
* `UPDATE`
* `CREATE`




## 搜索模式
|   搜索表达式col350   |    属性名col200    |    搜索模式col200        |备注col500  |
| -------- |------------|------------|------|
|N_CREATE_MAN_EQ|建立人|EQ||
|N_ID_EQ|标识|EQ||
|N_IDEA_EXISTS__N_ASSIGNEE_ID_EQ|需求|EXISTS||
|N_IDEA_EXISTS__N_CREATE_MAN_EQ|需求|EXISTS||
|N_IDEA_EXISTS__N_DESCRIPTION_LIKE|需求|EXISTS||
|N_IDEA_EXISTS__N_IDENTIFIER_LIKE|需求|EXISTS||
|N_IDEA_EXISTS__N_IS_ARCHIVED_EQ|需求|EXISTS||
|N_IDEA_EXISTS__N_PRIORITY_EQ|需求|EXISTS||
|N_IDEA_EXISTS__N_PRODUCT_ID_EQ|需求|EXISTS||
|N_IDEA_EXISTS__N_STATE_EQ|需求|EXISTS||
|N_IDEA_EXISTS__N_TITLE_LIKE|需求|EXISTS||
|N_IDENTIFIER_LIKE|编号|LIKE||
|N_NAME_LIKE|事项|LIKE||
|N_PRINCIPAL_ID_EQ|工时主体标识|EQ||
|N_RECENT_PARENT_EQ|访问父类|EQ||
|N_REGISTER_DATE_GTANDEQ|工作日期|GTANDEQ||
|N_REGISTER_DATE_IN|工作日期|IN||
|N_REGISTER_DATE_LTANDEQ|工作日期|LTANDEQ||
|N_TEST_CASE_EXISTS__N_CREATE_MAN_EQ|用例|EXISTS||
|N_TEST_CASE_EXISTS__N_DESCRIPTION_LIKE|用例|EXISTS||
|N_TEST_CASE_EXISTS__N_IDENTIFIER_EQ|用例|EXISTS||
|N_TEST_CASE_EXISTS__N_IS_ARCHIVED_EQ|用例|EXISTS||
|N_TEST_CASE_EXISTS__N_LEVEL_EQ|用例|EXISTS||
|N_TEST_CASE_EXISTS__N_MAINTENANCE_ID_EQ|用例|EXISTS||
|N_TEST_CASE_EXISTS__N_STATE_EQ|用例|EXISTS||
|N_TEST_CASE_EXISTS__N_TITLE_LIKE|用例|EXISTS||
|N_TEST_CASE_EXISTS__N_TYPE_EQ|用例|EXISTS||
|N_TYPE_ID_EQ|类别|EQ||
|N_TYPE_NAME_EQ|名称|EQ||
|N_TYPE_NAME_LIKE|名称|LIKE||
|N_WORK_ITEM_EXISTS__N_ASSIGNEE_ID_EQ|工作项|EXISTS||
|N_WORK_ITEM_EXISTS__N_CREATE_MAN_EQ|工作项|EXISTS||
|N_WORK_ITEM_EXISTS__N_DESCRIPTION_LIKE|工作项|EXISTS||
|N_WORK_ITEM_EXISTS__N_IS_ARCHIVED_EQ|工作项|EXISTS||
|N_WORK_ITEM_EXISTS__N_PRIORITY_EQ|工作项|EXISTS||
|N_WORK_ITEM_EXISTS__N_PROJECT_ID_EQ|工作项|EXISTS||
|N_WORK_ITEM_EXISTS__N_RISK_EQ|工作项|EXISTS||
|N_WORK_ITEM_EXISTS__N_STATE_EQ|工作项|EXISTS||
|N_WORK_ITEM_EXISTS__N_TITLE_LIKE|工作项|EXISTS||
|N_WORK_ITEM_EXISTS__N_WORK_ITEM_TYPE_ID_EQ|工作项|EXISTS||

## 界面行为
|  中文名col200 |  代码名col150 |  标题col100   |     处理目标col100   |    处理类型col200        |  备注col500       |
| --------| --------| -------- |------------|------------|------------|
| 打开工作类别管理工时记录 | open_management_type_link | 打开工作类别管理工时记录 |单项数据（主键）|<details><summary>打开视图或向导（模态）</summary>[工时](app/view/workload_management_duration_link_grid_view)</details>||
| 打开产品主视图 | open_product_main_view | 打开产品主视图 |单项数据|<details><summary>打开视图或向导（模态）</summary>[产品](app/view/product_main_view)</details>||
| 打开项目管理工时记录 | open_management_project_link | 打开项目管理工时记录 |单项数据（主键）|<details><summary>打开视图或向导（模态）</summary>[工时](app/view/workload_management_duration_link_grid_view)</details>|工时管理->项目维度->总登记时长链接|
| 打开产品管理工时记录 | open_management_product_link | 打开产品管理工时记录 |单项数据（主键）|<details><summary>打开视图或向导（模态）</summary>[工时](app/view/workload_management_duration_link_grid_view)</details>|工时管理->产品维度->总登记时长链接|
| 产品总登记时长链接跳转 | product_duration_link | 产品总登记时长链接跳转 |单项数据（主键）|用户自定义||
| 工时明细返回主表单 | back | 返回 |无数据|用户自定义||
| 工时日历时长链接（管理） | calendar_duration_management_link | 工时日历时长链接（管理） |单项数据（主键）|用户自定义||
| 打开测试用例主视图 | open_test_case_main_view | 打开测试用例主视图 |单项数据（主键）|<details><summary>打开视图或向导（模态）</summary>[用例](app/view/test_case_main_view)</details>||
| 删除工时 | delere | 删除 |单项数据（主键）|<details><summary>后台调用</summary>[Remove](#行为)||
| 测试库总登记时长链接跳转 | library_duration_link | 测试库总登记时长链接跳转 |单项数据（主键）|用户自定义||
| 打开测试库主视图 | open_library_main_view | 打开测试库主视图 |单项数据|<details><summary>打开视图或向导（模态）</summary>[测试库](app/view/library_main_view)</details>||
| 项目总登记时长链接跳转（管理） | management_project_duration_link | 项目总登记时长链接跳转（管理） |单项数据（主键）|用户自定义||
| 成员总登记时长链接跳转 | member_duration_link | 成员总登记时长链接跳转 |单项数据（主键）|用户自定义||
| 项目总登记时长链接跳转 | project_duration_link | 项目总登记时长链接跳转 |单项数据（主键）|用户自定义||
| 产品总登记时长链接跳转（管理） | management_product_duration_link | 产品总登记时长链接跳转（管理） |单项数据（主键）|用户自定义||
| 工作类别总登记时长链接跳转 | workload_type_duration_link | 工作类别总登记时长链接跳转 |单项数据（主键）|用户自定义||
| 工时日历时长链接 | calendar_duration_link | 工时日历时长链接 |单项数据（主键）|用户自定义||
| 工时日历链接日志表格视图 | calendar_link_log_view | 工时日历链接日志表格视图 |单项数据（主键）|<details><summary>打开视图或向导（模态）</summary>[工时](app/view/workload_calendar_duration_link_grid_view)</details>||
| 工时明细返回执行用例主表单 | back_run_main_view | 返回 |无数据|用户自定义||
| 打开成员工时记录 | open_member_workload_detail | 打开成员工时记录 |单项数据（主键）|<details><summary>打开视图或向导（模态）</summary>[工时](app/view/workload_management_duration_link_grid_view)</details>||
| 工时日历链接日志表格视图（管理） | management_calendar_duration_link | 工时日历链接日志表格视图（管理） |单项数据（主键）|<details><summary>打开视图或向导（模态）</summary>[工时](app/view/workload_management_duration_link_grid_view)</details>||
| 打开项目工时记录 | open_project_workload_detail | 打开项目工时记录 |单项数据（主键）|<details><summary>打开视图或向导（模态）</summary>[工时](app/view/workload_calendar_duration_link_grid_view)</details>|工作台->工时日历->项目维度->总登记时长链接|
| 工作类别总登记时长链接跳转（管理） | management_type_duration_link | 工作类别总登记时长链接跳转（管理） |单项数据（主键）|用户自定义||
| 测试库总登记时长链接跳转（管理） | management_library_duration_link | 测试库总登记时长链接跳转（管理） |单项数据（主键）|用户自定义||
| 打开测试库工时记录 | open_library_workload_detail | 打开测试库工时记录 |单项数据（主键）|<details><summary>打开视图或向导（模态）</summary>[工时](app/view/workload_calendar_duration_link_grid_view)</details>|工作台->工时日历->测试库维度->总登记时长链接|
| 打开产品工时记录 | open_product_workload_detail | 打开产品工时记录 |单项数据（主键）|<details><summary>打开视图或向导（模态）</summary>[工时](app/view/workload_calendar_duration_link_grid_view)</details>|工作台->工时日历->产品维度->总登记时长链接|
| 打开工作项主视图 | open_work_item_main_view | 打开工作项主视图 |单项数据（主键）|<details><summary>打开视图或向导（模态）</summary>[工作项](app/view/work_item_main_view)</details>||
| 打开产品需求主视图 | open_idea_main_view | 打开产品需求主视图 |单项数据（主键）|<details><summary>打开视图或向导（模态）</summary>[需求](app/view/idea_main_view)</details>||
| 打开项目主视图 | open_project_main_view | 打开项目主视图 |单项数据|<details><summary>打开视图或向导（模态）</summary>[项目](app/view/project_redirect_view)</details>||
| 打开工作类别工时记录 | open_type_workload_detail | 打开工作类别工时记录 |单项数据（主键）|<details><summary>打开视图或向导（模态）</summary>[工时](app/view/workload_calendar_duration_link_grid_view)</details>||
| 打开测试库管理工时记录 | open_management_library_link | 打开测试库管理工时记录 |单项数据（主键）|<details><summary>打开视图或向导（模态）</summary>[工时](app/view/workload_management_duration_link_grid_view)</details>|工时管理->测试库维度->总登记时长链接|

## 界面逻辑
|  中文名col200 | 代码名col150 | 备注col900 |
| --------|--------|--------|
|[工时日历打开工时日志视图](module/Base/workload/uilogic/calendar_link_log_view)|calendar_link_log_view|获取搜索表单时间范围条件，并打开工时日志表格|
|[工时日历打开工时日志视图（管理）](module/Base/workload/uilogic/calendar_management_link_log_view)|calendar_management_link_log_view|获取搜索表单时间范围条件，并打开工时日志表格|
|[打开产品主视图](module/Base/workload/uilogic/open_product_main_view)|open_product_main_view|调用实体行为，打开产品主视图|
|[打开产品工时记录列表视图](module/Base/workload/uilogic/open_product_workload_detail)|open_product_workload_detail|获取搜索表单时间范围条件，并打开工时记录列表|
|[打开产品管理工时记录列表视图](module/Base/workload/uilogic/open_management_product_detail)|open_management_product_detail|获取搜索表单时间范围条件，并打开工时记录列表|
|[打开工作类别工时记录列表视图](module/Base/workload/uilogic/open_type_detail)|open_type_detail|获取搜索表单时间范围条件，并打开工时记录列表|
|[打开工作类别管理工时记录列表视图](module/Base/workload/uilogic/open_management_type_detail)|open_management_type_detail|获取搜索表单时间范围条件，并打开工时记录列表|
|[打开成员工时记录列表视图](module/Base/workload/uilogic/open_member_detail)|open_member_detail|获取搜索表单时间范围条件，并打开工时记录列表|
|[打开测试库主视图](module/Base/workload/uilogic/open_library_main_view)|open_library_main_view|打开测试库主视图|
|[打开测试库工时记录列表视图](module/Base/workload/uilogic/open_library_workload_detail)|open_library_workload_detail|获取搜索表单时间范围条件，并打开工时记录列表|
|[打开测试库管理工时记录列表视图](module/Base/workload/uilogic/open_management_library_detail)|open_management_library_detail|获取搜索表单时间范围条件，并打开工时记录列表|
|[打开详情视图](module/Base/workload/uilogic/open_main_view)|open_main_view|链接跳转工作项/产品需求/测试用例详情主视图|
|[打开项目主视图](module/Base/workload/uilogic/open_project_main_view)|open_project_main_view|打开项目主视图|
|[打开项目工时记录列表视图](module/Base/workload/uilogic/open_project_workload_detail)|open_project_workload_detail|获取搜索表单时间范围条件，并打开工时记录列表|
|[打开项目管理工时记录列表视图](module/Base/workload/uilogic/open_management_project_detail)|open_management_project_detail|获取搜索表单时间范围条件，并打开工时记录列表|
|[返回](module/Base/workload/uilogic/back)|back|查看工时明细后，返回主表单按钮使用|
|[返回（执行用例表单）](module/Base/workload/uilogic/back_run_main_view)|back_run_main_view|切换显示组件|

<div style="display: block; overflow: hidden; position: fixed; top: 140px; right: 100px;">

##### 导航
<el-anchor >
<el-anchor-link :href="`#/module/Base/workload?id=属性`">
  属性
</el-anchor-link>
<el-anchor-link :href="`#/module/Base/workload?id=关系`">
  关系
</el-anchor-link>
<el-anchor-link :href="`#/module/Base/workload?id=行为`">
  行为
</el-anchor-link>
<el-anchor-link :href="`#/module/Base/workload?id=处理逻辑`">
  处理逻辑
</el-anchor-link>
<el-anchor-link :href="`#/module/Base/workload?id=数据查询`">
  数据查询
</el-anchor-link>
<el-anchor-link :href="`#/module/Base/workload?id=数据集合`">
  数据集合
</el-anchor-link>
<el-anchor-link :href="`#/module/Base/workload?id=数据权限`">
  数据权限
</el-anchor-link>
<el-anchor-link :href="`#/module/Base/workload?id=搜索模式`">
  搜索模式
</el-anchor-link>
<el-anchor-link :href="`#/module/Base/workload?id=界面行为`">
  界面行为
</el-anchor-link>
<el-anchor-link :href="`#/module/Base/workload?id=界面逻辑`">
  界面逻辑
</el-anchor-link>
</el-anchor>
</div>

<script>
 const { createApp } = Vue
  createApp({
    data() {
      return {
show_der:'minor',

show_index:'index_WORKLOAD2',
      }
    },
    methods: {
    }
  }).use(ElementPlus).mount('#app')
</script>