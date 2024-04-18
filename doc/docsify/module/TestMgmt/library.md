# 测试库(library)  <!-- {docsify-ignore-all} -->


测试管理核心实体，包含测试的基本信息、生命周期状态等。


## 属性
|    中文名col150 | 属性名称col200           | 类型col200     | 长度col100    |允许为空col100    |  备注col500  |
| --------   |------------| -----  | -----  | :----: | -------- |
|主题色|COLOR|文本，可指定长度|100|是||
|建立人|CREATE_MAN|文本，可指定长度|100|否||
|建立时间|CREATE_TIME|日期时间型||否||
|描述|DESCRIPTION|长文本，长度1000|2000|是||
|标识<sup class="footnote-symbol"><font color=orange>[PK]</font></sup>|ID|全局唯一标识，文本类型，用户不可见|100|否||
|测试库标识|IDENTIFIER|文本，可指定长度|100|否||
|是否已归档|IS_ARCHIVED|是否逻辑||是||
|是否已删除|IS_DELETED|是否逻辑||是||
|是否星标|IS_FAVORITE|文本，可指定长度|200|是||
|成员|MEMBERS|一对多关系数据集合|1048576|是||
|测试库名称|NAME|文本，可指定长度|200|否||
|更新人|UPDATE_MAN|文本，可指定长度|100|否||
|更新时间|UPDATE_TIME|日期时间型||否||
|可见范围|VISIBILITY|单项选择(文本值)|60|否||


## 关系

<el-row>
<el-tabs v-model="show_der">
<el-tab-pane label="主关系" name="major">

| 名称col350     |   从实体col200 | 关系类型col200     |   备注col500  |
| -------- |---------- |------------|----- |
|[DER1N_LIBRARY_MEMBER_LIBRARY_LIBRARY_ID](der/DER1N_LIBRARY_MEMBER_LIBRARY_LIBRARY_ID)|[测试库成员(LIBRARY_MEMBER)](module/TestMgmt/library_member)|1:N关系||
|[DER1N_REVIEW_LIBRARY_LIBRARY_ID](der/DER1N_REVIEW_LIBRARY_LIBRARY_ID)|[评审(REVIEW)](module/TestMgmt/review)|1:N关系||
|[DER1N_TEST_CASE_LIBRARY_TEST_LIBRARY_ID](der/DER1N_TEST_CASE_LIBRARY_TEST_LIBRARY_ID)|[用例(TEST_CASE)](module/TestMgmt/test_case)|1:N关系||
|[DER1N_TEST_PLAN_LIBRARY_LIBRARY_ID](der/DER1N_TEST_PLAN_LIBRARY_LIBRARY_ID)|[测试计划(TEST_PLAN)](module/TestMgmt/test_plan)|1:N关系||
|[DER1N_TEST_SUITE_LIBRARY_LIBRARY_ID](der/DER1N_TEST_SUITE_LIBRARY_LIBRARY_ID)|[用例模块(TEST_SUITE)](module/TestMgmt/test_suite)|1:N关系||


</el-tab-pane>
<el-tab-pane label="从关系" name="minor">

|  名称col350   | 主实体col200   | 关系类型col200   |    备注col500  |
| -------- |---------- |-----------|----- |
|[DERINDEX_LIBRARY_REFERENCES_INDEX](der/DERINDEX_LIBRARY_REFERENCES_INDEX)|[引用索引(REFERENCES_INDEX)](module/Base/references_index)|索引关系||

</el-tab-pane>
</el-tabs>
</el-row>

## 行为
| 中文名col200    | 代码名col150    | 类型col150    | 事务col100   | 批处理col100   | 附加操作col100  | 插件col150    |  备注col300  |
| -------- |---------- |----------- |:----:|:----:|---------| ----- | ----- |
|CheckKey|CheckKey|内置方法|默认|不支持||||
|Create|Create|内置方法|默认|不支持|[附加操作](index/action_logic_index#library_Create)|||
|CreateTemp|CreateTemp|内置方法|默认|不支持||||
|CreateTempMajor|CreateTempMajor|内置方法|默认|不支持||||
|Get|Get|内置方法|默认|不支持|[附加操作](index/action_logic_index#library_Get)|||
|GetDraft|GetDraft|内置方法|默认|不支持||||
|GetDraftTemp|GetDraftTemp|内置方法|默认|不支持||||
|GetDraftTempMajor|GetDraftTempMajor|内置方法|默认|不支持||||
|GetTemp|GetTemp|内置方法|默认|不支持||||
|GetTempMajor|GetTempMajor|内置方法|默认|不支持||||
|Remove|Remove|内置方法|默认|支持||||
|RemoveTemp|RemoveTemp|内置方法|默认|支持||||
|RemoveTempMajor|RemoveTempMajor|内置方法|默认|支持||||
|Save|Save|内置方法|默认|不支持||||
|Update|Update|内置方法|默认|不支持|[附加操作](index/action_logic_index#library_Update)|||
|UpdateTemp|UpdateTemp|内置方法|默认|不支持||||
|UpdateTempMajor|UpdateTempMajor|内置方法|默认|不支持||||
|激活|activate|[实体处理逻辑](module/TestMgmt/library/logic/activate "激活")|默认|不支持||||
|归档|archive|[实体处理逻辑](module/TestMgmt/library/logic/archive "归档")|默认|不支持||||
|删除|delete|[实体处理逻辑](module/TestMgmt/library/logic/delete "删除")|默认|不支持||||
|设置星标|favorite|[实体处理逻辑](module/TestMgmt/library/logic/favorite "设置星标")|默认|不支持||||
|恢复|recover|[实体处理逻辑](module/TestMgmt/library/logic/recover "恢复")|默认|不支持||||
|取消星标|un_favorite|[实体处理逻辑](module/TestMgmt/library/logic/un_favorite "取消星标")|默认|不支持||||

## 处理逻辑
| 中文名col200    | 代码名col150    | 子类型col150    | 插件col200    |  备注col550  |
| -------- |---------- |----------- |------------|----------|
|[创建之前](module/TestMgmt/library/logic/before_create)|before_create|无||创建测试库之前，对添加的测试库成员进行处理|
|[删除](module/TestMgmt/library/logic/delete)|delete|无||测试库数据的逻辑删除，修改产品的是否删除属性值|
|[取消星标](module/TestMgmt/library/logic/un_favorite)|un_favorite|无||测试库取消星标|
|[归档](module/TestMgmt/library/logic/archive)|archive|无||未归档测试库数据的归档处理，修改测试库的归档状态为已归档|
|[恢复](module/TestMgmt/library/logic/recover)|recover|无||恢复已删除状态测试库数据，修改测试库的是否删除属性值，并恢复访问记录|
|[批量更新最近访问父名称](module/TestMgmt/library/logic/recent_parent_name)|recent_parent_name|属性逻辑||当测试库名称变更时，触发此逻辑，批量对最近访问的父标识进行更新|
|[批量更新最近访问父标识](module/TestMgmt/library/logic/recent_parent_identifier)|recent_parent_identifier|属性逻辑||当测试库标识变更时，触发此逻辑，批量对最近访问的父标识进行更新|
|[是否删除变更附加逻辑](module/TestMgmt/library/logic/is_deleted_onchange)|is_deleted_onchange|属性逻辑||产品删除或恢复数据时触发相应的通知消息|
|[是否归档变更附加逻辑](module/TestMgmt/library/logic/is_archived_onchange)|is_archived_onchange|属性逻辑||测试库归档或激活时触发相应的通知消息|
|[激活](module/TestMgmt/library/logic/activate)|activate|无||激活已归档状态测试库，修改测试库的归档属性|
|[生成最近访问](module/TestMgmt/library/logic/create_recent)|create_recent|无||在用户对测试库数据进行了get或update操作时生成相应的访问记录|
|[设置星标](module/TestMgmt/library/logic/favorite)|favorite|无||设置为星标测试库|

## 主状态控制

<p class="panel-title"><b>控制属性</b></p>

* `是否星标(IS_FAVORITE)` 




<p class="panel-title"><b>操作标识分布</b></p>
<br>
<table>
  <tr>
    <th>操作标识col350</th>
    <th>是col150</th>
    <th>否col150</th>
    <th>备注col600</th>
  </tr>
  <tr>
    <td>删除(DELETE)</td>
    <td align="center"><i class="fa fa-check"></i></td>
    <td align="center"><i class="fa fa-check"></i></td>
    <td></td>
  </tr>
  <tr>
    <td>取消星标(CANCEL_FAVORITE)</td>
    <td align="center"><i class="fa fa-check"></i></td>
    <td align="center"></td>
    <td></td>
  </tr>
  <tr>
    <td>子数据权限(SUBDATA)</td>
    <td align="center"><i class="fa fa-check"></i></td>
    <td align="center"><i class="fa fa-check"></i></td>
    <td></td>
  </tr>
  <tr>
    <td>建立(CREATE)</td>
    <td align="center"><i class="fa fa-check"></i></td>
    <td align="center"><i class="fa fa-check"></i></td>
    <td></td>
  </tr>
  <tr>
    <td>更新(UPDATE)</td>
    <td align="center"><i class="fa fa-check"></i></td>
    <td align="center"><i class="fa fa-check"></i></td>
    <td></td>
  </tr>
  <tr>
    <td>设置星标(ADD_FAVORITE)</td>
    <td align="center"></td>
    <td align="center"><i class="fa fa-check"></i></td>
    <td></td>
  </tr>
  <tr>
    <td>读取(READ)</td>
    <td align="center"><i class="fa fa-check"></i></td>
    <td align="center"><i class="fa fa-check"></i></td>
    <td></td>
  </tr>

</table>


## 数据查询
| 中文名col200    | 代码名col150    | 默认查询col100 | 权限使用col100 | 自定义SQLcol100 |  备注col600|
| --------  | --------   | :----:  |:----:  | :----:  |----- |
|[数据查询(DEFAULT)](module/TestMgmt/library/query/Default)|DEFAULT|是|否 |否 ||
|[默认（全部数据）(VIEW)](module/TestMgmt/library/query/View)|VIEW|否|否 |否 ||
|[管理员(admin)](module/TestMgmt/library/query/admin)|admin|否|否 |否 ||
|[已归档(archived)](module/TestMgmt/library/query/archived)|archived|否|否 |否 ||
|[已删除(deleted)](module/TestMgmt/library/query/deleted)|deleted|否|否 |否 ||
|[查询星标(favorite)](module/TestMgmt/library/query/favorite)|favorite|否|否 |否 ||
|[正常状态(normal)](module/TestMgmt/library/query/normal)|normal|否|否 |否 ||
|[与项目关联的测试库(project_relation_library)](module/TestMgmt/library/query/project_relation_library)|project_relation_library|否|否 |否 |通过测试计划中进行关联项目展示测试库|
|[公开(public)](module/TestMgmt/library/query/public)|public|否|否 |否 ||
|[只读用户(reader)](module/TestMgmt/library/query/reader)|reader|否|否 |否 ||
|[普通成员(user)](module/TestMgmt/library/query/user)|user|否|否 |否 ||

## 数据集合
| 中文名col200  | 代码名col150  | 类型col100 | 默认集合col100 |   插件col200|   备注col500|
| --------  | --------   | :----:   | :----:   | ----- |----- |
|[数据集(DEFAULT)](module/TestMgmt/library/dataset/Default)|DEFAULT|数据查询|是|||
|[管理员(admin)](module/TestMgmt/library/dataset/admin)|admin|数据查询|否|||
|[已归档(archived)](module/TestMgmt/library/dataset/archived)|archived|数据查询|否|||
|[已删除(deleted)](module/TestMgmt/library/dataset/deleted)|deleted|数据查询|否|||
|[查询星标(favorite)](module/TestMgmt/library/dataset/favorite)|favorite|数据查询|否|||
|[正常状态(normal)](module/TestMgmt/library/dataset/normal)|normal|数据查询|否|||
|[与项目关联的测试库(project_relation_library)](module/TestMgmt/library/dataset/project_relation_library)|project_relation_library|数据查询|否||通过测试计划中进行关联项目展示测试库|
|[只读用户(reader)](module/TestMgmt/library/dataset/reader)|reader|数据查询|否|||
|[操作用户(user)](module/TestMgmt/library/dataset/user)|user|数据查询|否|||

## 数据权限

##### 管理员（读写） :id=library-ADMIN_RW

<p class="panel-title"><b>数据范围</b></p>

* `数据集合` ：[管理员(admin)](module/TestMgmt/library#数据集合)

<p class="panel-title"><b>数据能力</b></p>

* `READ`
* `DELETE`
* `UPDATE`
* `SUBDATA`



##### 全部数据（读写） :id=library-ALL_RW

<p class="panel-title"><b>数据范围</b></p>

* `全部数据`

<p class="panel-title"><b>数据能力</b></p>

* `READ`
* `UPDATE`
* `SUBDATA`
* `CREATE`
* `DELETE`



##### 全部数据（写） :id=library-ALL_W

<p class="panel-title"><b>数据范围</b></p>

* `全部数据`

<p class="panel-title"><b>数据能力</b></p>

* `UPDATE`
* `DELETE`
* `CREATE`



##### 只读用户（读） :id=library-USER_R

<p class="panel-title"><b>数据范围</b></p>

* `数据集合` ：[只读用户(reader)](module/TestMgmt/library#数据集合)

<p class="panel-title"><b>数据能力</b></p>

* `READ`



##### 普通用户（读写） :id=library-USER_RW

<p class="panel-title"><b>数据范围</b></p>

* `数据集合` ：[操作用户(user)](module/TestMgmt/library#数据集合)

<p class="panel-title"><b>数据能力</b></p>

* `READ`
* `SUBDATA`



## 消息通知

|    中文名col200   | 代码名col150       |  消息队列col200   |  消息模板col200 |  通知目标col150     |  备注col350  |
|------------| -----   |  -------- | -------- |-------- |-------- |
|[测试库归档/激活通知](module/TestMgmt/library/notify/library_archive_notify)|library_archive_notify|[默认消息队列](index/notify_index)|[测试库通知模板(归档/激活测试库)](index/notify_index#library_archive)|当前测试库成员 ||
|[测试库删除/恢复通知](module/TestMgmt/library/notify/library_remove_notify)|library_remove_notify|[默认消息队列](index/notify_index)|[测试库通知模板(删除/恢复测试库)](index/notify_index#library_remove)|当前测试库成员 ||

## 搜索模式
|   搜索表达式col350   |    属性名col200    |    搜索模式col200        |备注col500  |
| -------- |------------|------------|------|
|N_ID_NOTEQ|标识|NOTEQ||
|N_ID_EQ|标识|EQ||
|N_IDENTIFIER_EQ|测试库标识|EQ||
|N_IS_ARCHIVED_EQ|是否已归档|EQ||
|N_IS_DELETED_EQ|是否已删除|EQ||
|N_IS_FAVORITE_EQ|是否星标|EQ||
|N_NAME_LIKE|测试库名称|LIKE||
|N_VISIBILITY_EQ|可见范围|EQ||

## 界面行为
|  中文名col200 |  代码名col150 |  标题col100   |     处理目标col100   |    处理类型col200        |  备注col500       |
| --------| --------| -------- |------------|------------|------------|
| 打开测试库配置 | open_global_setting | 测试库配置 |无数据|<details><summary>打开视图或向导（模态）</summary>[测试库配置](app/view/library_config_tree_exp_view)</details>||
| 取消星标 | unstar | 取消星标 |单项数据（主键）|<details><summary>后台调用</summary>[un_favorite](#行为)||
| 更多设置 | open_details_setting_view | 更多设置 |单项数据（主键）|用户自定义||
| 测试库信息 | open_show_edit_view | 测试库信息 |单项数据（主键）|<details><summary>打开视图或向导（模态）</summary>[测试库信息](app/view/library_show_edit_view)</details>||
| 恢复 | recover | 恢复 |单项数据（主键）|<details><summary>后台调用</summary>[recover](#行为)||
| 回收站 | open_deleted_view | 回收站 |单项数据（主键）|用户自定义||
| 设置星标 | star | 设置星标 |单项数据（主键）|<details><summary>后台调用</summary>[favorite](#行为)||
| 进行中_归档 | archive | 归档 |单项数据（主键）|<details><summary>后台调用</summary>[archive](#行为)||
| 删除 | delete | 删除 |单项数据（主键）|<details><summary>后台调用</summary>[delete](#行为)||
| 打开测试库导航页 | open_library_exp_view | 打开测试库导航页 |无数据|<details><summary>打开顶级视图</summary>[测试管理](app/view/library_tree_exp_view)</details>||
| 测试库成员 | setting_library_member | 测试库成员 |单项数据（主键）|用户自定义||
| 已归档_激活 | activate | 激活 |单项数据（主键）|<details><summary>后台调用</summary>[activate](#行为)||
| 编辑基本信息 | setting_base_info | 编辑基本信息 |单项数据（主键）|用户自定义||
| 新开窗口（测试库） | open_new | 新窗口打开 |单项数据（主键）|<details><summary>打开HTML页面</summary>*./#/-/index/library=${data.id}/library_index_view/srfnav=usrdrgroup1227882118/test_plan_tree_exp_view/srfnav=root%3Anode/test_plan_all_grid_view/n_library_id_eq=${data.id}*</details>||
| 打开测试库主视图 | open_index_view | 打开测试库主视图 |单项数据（主键）|<details><summary>打开视图或向导（模态）</summary>[测试库](app/view/library_index_view)</details>||

## 界面逻辑
|  中文名col200 | 代码名col150 | 备注col900 |
| --------|--------|--------|
|[刷新当前表格](module/TestMgmt/library/uilogic/refresh_current_grid)|refresh_current_grid|按钮触发，通过脚本切换显示组件|
|[批量删除测试库成员临时数据](module/TestMgmt/library/uilogic/remove_batch_temp)|remove_batch_temp|获取测试库内所有临时成员数据并删除|

<div style="display: block; overflow: hidden; position: fixed; top: 140px; right: 100px;">

##### 导航
<el-anchor >
<el-anchor-link :href="`#/module/TestMgmt/library?id=属性`">
  属性
</el-anchor-link>
<el-anchor-link :href="`#/module/TestMgmt/library?id=关系`">
  关系
</el-anchor-link>
<el-anchor-link :href="`#/module/TestMgmt/library?id=行为`">
  行为
</el-anchor-link>
<el-anchor-link :href="`#/module/TestMgmt/library?id=处理逻辑`">
  处理逻辑
</el-anchor-link>
<el-anchor-link :href="`#/module/TestMgmt/library?id=主状态控制`">
  主状态控制
</el-anchor-link>
<el-anchor-link :href="`#/module/TestMgmt/library?id=数据查询`">
  数据查询
</el-anchor-link>
<el-anchor-link :href="`#/module/TestMgmt/library?id=数据集合`">
  数据集合
</el-anchor-link>
<el-anchor-link :href="`#/module/TestMgmt/library?id=数据权限`">
  数据权限
</el-anchor-link>
<el-anchor-link :href="`#/module/TestMgmt/library?id=消息通知`">
  消息通知
</el-anchor-link>
<el-anchor-link :href="`#/module/TestMgmt/library?id=搜索模式`">
  搜索模式
</el-anchor-link>
<el-anchor-link :href="`#/module/TestMgmt/library?id=界面行为`">
  界面行为
</el-anchor-link>
<el-anchor-link :href="`#/module/TestMgmt/library?id=界面逻辑`">
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