# 空间(space)  <!-- {docsify-ignore-all} -->


定义PLM系统中用于协作、知识共享和文档管理的虚拟空间。


## 属性
|    中文名col150 | 属性名称col200           | 类型col200     | 长度col100    |允许为空col100    |  备注col500  |
| --------   |------------| -----  | -----  | :----: | -------- |
|分类路径|CATEGORIES|外键值附加数据|2000|是||
|分类|CATEGORY_ID|外键值|100|是||
|分类|CATEGORY_NAME|外键值文本|200|是||
|建立人|CREATE_MAN|文本，可指定长度|100|否||
|建立时间|CREATE_TIME|日期时间型||否||
|描述|DESCRIPTION|长文本，长度1000|2000|是||
|标识<sup class="footnote-symbol"><font color=orange>[PK]</font></sup>|ID|全局唯一标识，文本类型，用户不可见|100|否||
|空间标识|IDENTIFIER|文本，可指定长度|100|否||
|是否已归档|IS_ARCHIVED|是否逻辑||是||
|是否已删除|IS_DELETED|是否逻辑||是||
|是否星标|IS_FAVORITE|文本，可指定长度|200|是||
|成员|MEMBERS|一对多关系数据集合|1048576|是||
|空间名称|NAME|文本，可指定长度|200|否||
|更新人|UPDATE_MAN|文本，可指定长度|100|否||
|更新时间|UPDATE_TIME|日期时间型||否||
|可见范围|VISIBILITY|单项选择(文本值)|60|否||


## 关系

<el-row>
<el-tabs v-model="show_der">
<el-tab-pane label="主关系" name="major">

| 名称col350     |   从实体col200 | 关系类型col200     |   备注col500  |
| -------- |---------- |------------|----- |
|[DER1N_PAGE_SPACE_SPACE_ID](der/DER1N_PAGE_SPACE_SPACE_ID)|[页面(PAGE)](module/Wiki/article_page)|1:N关系||
|[DER1N_SPACE_MEMBER_SPACE_SPACE_ID](der/DER1N_SPACE_MEMBER_SPACE_SPACE_ID)|[空间成员(SPACE_MEMBER)](module/Wiki/space_member)|1:N关系||
|[DER1N_STENCIL_SPACE_SPACE_ID](der/DER1N_STENCIL_SPACE_SPACE_ID)|[页面模板(STENCIL)](module/Wiki/stencil)|1:N关系||
|[DERCUSTOM_RELATION_SPACE](der/DERCUSTOM_RELATION_SPACE)|[关联(RELATION)](module/Base/relation)|自定义关系||


</el-tab-pane>
<el-tab-pane label="从关系" name="minor">

|  名称col350   | 主实体col200   | 关系类型col200   |    备注col500  |
| -------- |---------- |-----------|----- |
|[DER1N_SPACE_CATEGORY_CATEGORY_ID](der/DER1N_SPACE_CATEGORY_CATEGORY_ID)|[类别(CATEGORY)](module/Base/category)|1:N关系||

</el-tab-pane>
</el-tabs>
</el-row>

## 行为
| 中文名col200    | 代码名col150    | 类型col150    | 事务col100   | 批处理col100   | 附加操作col100  | 插件col150    |  备注col300  |
| -------- |---------- |----------- |:----:|:----:|---------| ----- | ----- |
|CheckKey|CheckKey|内置方法|默认|不支持||||
|Create|Create|内置方法|默认|不支持|[附加操作](index/action_logic_index#space_Create)|||
|CreateTemp|CreateTemp|内置方法|默认|不支持||||
|CreateTempMajor|CreateTempMajor|内置方法|默认|不支持||||
|Get|Get|内置方法|默认|不支持|[附加操作](index/action_logic_index#space_Get)|||
|GetDraft|GetDraft|内置方法|默认|不支持||||
|GetDraftTemp|GetDraftTemp|内置方法|默认|不支持||||
|GetDraftTempMajor|GetDraftTempMajor|内置方法|默认|不支持||||
|GetTemp|GetTemp|内置方法|默认|不支持||||
|GetTempMajor|GetTempMajor|内置方法|默认|不支持||||
|Remove|Remove|内置方法|默认|支持||||
|RemoveTemp|RemoveTemp|内置方法|默认|支持||||
|RemoveTempMajor|RemoveTempMajor|内置方法|默认|支持||||
|Save|Save|内置方法|默认|不支持||||
|Update|Update|内置方法|默认|不支持||||
|UpdateTemp|UpdateTemp|内置方法|默认|不支持||||
|UpdateTempMajor|UpdateTempMajor|内置方法|默认|不支持||||
|激活|activate|[实体处理逻辑](module/Wiki/space/logic/activate "激活")|默认|不支持||||
|归档|archive|[实体处理逻辑](module/Wiki/space/logic/archive "归档")|默认|不支持||||
|取消关联|del_relation|[实体处理逻辑](module/Wiki/space/logic/del_relation "取消关联")|默认|不支持||||
|删除|delete|[实体处理逻辑](module/Wiki/space/logic/delete "删除")|默认|不支持||||
|设置星标|favorite|[实体处理逻辑](module/Wiki/space/logic/favorite "设置星标")|默认|不支持||||
|移出分类|move_out_category|[实体处理逻辑](module/Wiki/space/logic/move_out_category "移出分类")|默认|不支持||||
|无操作|nothing|[实体处理逻辑](module/Wiki/space/logic/nothing "无操作")|默认|不支持||||
|其他实体关联空间|other_re_space|[实体处理逻辑](module/Wiki/space/logic/other_re_space "其他实体关联空间")|默认|不支持||||
|恢复|recover|[实体处理逻辑](module/Wiki/space/logic/recover "恢复")|默认|不支持||||
|取消星标|un_favorite|[实体处理逻辑](module/Wiki/space/logic/un_favorite "取消星标")|默认|不支持||||

## 处理逻辑
| 中文名col200    | 代码名col150    | 子类型col150    | 插件col200    |  备注col550  |
| -------- |---------- |----------- |------------|----------|
|[其他实体关联空间](module/Wiki/space/logic/other_re_space)|other_re_space|无||其他实体关联空间操作，生成正反向关联数据|
|[创建之前](module/Wiki/space/logic/before_create)|before_create|无||创建空间之前，对添加的空间成员进行处理|
|[删除](module/Wiki/space/logic/delete)|delete|无||空间数据的逻辑删除，修改产品的是否删除属性值|
|[取消关联](module/Wiki/space/logic/del_relation)|del_relation|无||空间取消关联数据（正反向关联数据同时删除）|
|[取消星标](module/Wiki/space/logic/un_favorite)|un_favorite|无||空间取消星标|
|[归档](module/Wiki/space/logic/archive)|archive|无||未归档空间数据的归档处理，修改空间的归档状态为已归档|
|[恢复](module/Wiki/space/logic/recover)|recover|无||已删除状态空间数据的恢复，修改空间的是否删除属性值，并恢复访问记录|
|[无操作](module/Wiki/space/logic/nothing)|nothing|无||无操作逻辑，用于替换表单的获取数据行为|
|[激活](module/Wiki/space/logic/activate)|activate|无||激活已归档状态空间，修改空间的归档属性|
|[生成最近访问](module/Wiki/space/logic/create_recent)|create_recent|无||在用户对空间数据进行了get或update操作时生成相应的访问记录|
|[移出分类](module/Wiki/space/logic/move_out_category)|move_out_category|无||将空间移除分类|
|[自动创建主页](module/Wiki/space/logic/auto_create_home_page)|auto_create_home_page|无||附加在实体的CREATE行为后，自动生成模板化的主页|
|[设置星标](module/Wiki/space/logic/favorite)|favorite|无||设置为星标产品|

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
|[数据查询(DEFAULT)](module/Wiki/space/query/Default)|DEFAULT|是|否 |否 ||
|[默认（全部数据）(VIEW)](module/Wiki/space/query/View)|VIEW|否|否 |否 ||
|[管理员(admin)](module/Wiki/space/query/admin)|admin|否|否 |否 ||
|[已归档(archived)](module/Wiki/space/query/archived)|archived|否|否 |否 ||
|[目录下空间(category_space)](module/Wiki/space/query/category_space)|category_space|否|否 |否 ||
|[已删除(deleted)](module/Wiki/space/query/deleted)|deleted|否|否 |否 ||
|[查询星标(favorite)](module/Wiki/space/query/favorite)|favorite|否|否 |否 ||
|[未存在目录中的空间(no_category_space)](module/Wiki/space/query/no_category_space)|no_category_space|否|否 |否 ||
|[未关联的空间（产品）(no_re_space_product)](module/Wiki/space/query/no_re_space_product)|no_re_space_product|否|否 |否 ||
|[正常状态(normal)](module/Wiki/space/query/normal)|normal|否|否 |否 ||
|[产品关联的空间(product_re_space)](module/Wiki/space/query/product_re_space)|product_re_space|否|否 |否 ||
|[公开(public)](module/Wiki/space/query/public)|public|否|否 |否 ||
|[只读用户(reader)](module/Wiki/space/query/reader)|reader|否|否 |否 ||
|[操作用户(user)](module/Wiki/space/query/user)|user|否|否 |否 ||

## 数据集合
| 中文名col200  | 代码名col150  | 类型col100 | 默认集合col100 |   插件col200|   备注col500|
| --------  | --------   | :----:   | :----:   | ----- |----- |
|[数据集(DEFAULT)](module/Wiki/space/dataset/Default)|DEFAULT|数据查询|是|||
|[管理员(admin)](module/Wiki/space/dataset/admin)|admin|数据查询|否|||
|[已归档(archived)](module/Wiki/space/dataset/archived)|archived|数据查询|否|||
|[目录下空间(category_space)](module/Wiki/space/dataset/category_space)|category_space|数据查询|否|||
|[已删除(deleted)](module/Wiki/space/dataset/deleted)|deleted|数据查询|否|||
|[查询星标(favorite)](module/Wiki/space/dataset/favorite)|favorite|数据查询|否|||
|[未存在目录中的空间(no_category_space)](module/Wiki/space/dataset/no_category_space)|no_category_space|数据查询|否|||
|[未关联的空间(no_re_space)](module/Wiki/space/dataset/no_re_space)|no_re_space|数据查询|否|||
|[正常状态(normal)](module/Wiki/space/dataset/normal)|normal|数据查询|否|||
|[关联的空间(other_re_space)](module/Wiki/space/dataset/other_re_space)|other_re_space|数据查询|否|||
|[只读用户(reader)](module/Wiki/space/dataset/reader)|reader|数据查询|否|||
|[操作用户(user)](module/Wiki/space/dataset/user)|user|数据查询|否|||

## 数据权限

##### 管理员（读写） :id=space-ADMIN_RW

<p class="panel-title"><b>数据范围</b></p>

* `数据集合` ：[管理员(admin)](module/Wiki/space#数据集合)

<p class="panel-title"><b>数据能力</b></p>

* `READ`
* `SUBDATA`
* `UPDATE`
* `DELETE`



##### 全部数据（读写） :id=space-ALL_RW

<p class="panel-title"><b>数据范围</b></p>

* `全部数据`

<p class="panel-title"><b>数据能力</b></p>

* `CREATE`
* `SUBDATA`
* `READ`
* `UPDATE`
* `DELETE`



##### 全部数据（写） :id=space-ALL_W

<p class="panel-title"><b>数据范围</b></p>

* `全部数据`

<p class="panel-title"><b>数据能力</b></p>

* `CREATE`
* `UPDATE`
* `DELETE`



##### 只读用户（读） :id=space-USER_R

<p class="panel-title"><b>数据范围</b></p>

* `数据集合` ：[只读用户(reader)](module/Wiki/space#数据集合)

<p class="panel-title"><b>数据能力</b></p>

* `READ`



##### 普通用户（读写） :id=space-USER_RW

<p class="panel-title"><b>数据范围</b></p>

* `数据集合` ：[操作用户(user)](module/Wiki/space#数据集合)

<p class="panel-title"><b>数据能力</b></p>

* `SUBDATA`
* `READ`




## 搜索模式
|   搜索表达式col350   |    属性名col200    |    搜索模式col200        |备注col500  |
| -------- |------------|------------|------|
|N_CATEGORY_ID_EQ|分类|EQ||
|N_CATEGORY_NAME_EQ|分类|EQ||
|N_CATEGORY_NAME_LIKE|分类|LIKE||
|N_ID_EQ|标识|EQ||
|N_IS_FAVORITE_EQ|是否星标|EQ||
|N_NAME_LIKE|空间名称|LIKE||
|N_VISIBILITY_EQ|可见范围|EQ||

## 界面行为
|  中文名col200 |  代码名col150 |  标题col100   |     处理目标col100   |    处理类型col200        |  备注col500       |
| --------| --------| -------- |------------|------------|------------|
| 新建目录 | create_category | 新建目录 |无数据|用户自定义||
| 打开空间主页面 | open_space_index | 打开空间主页面 |单项数据（主键）|<details><summary>打开视图或向导（模态）</summary>[空间](app/view/space_index_view)</details>||
| 取消星标 | cancel_favorite | 取消星标 |单项数据（主键）|<details><summary>后台调用</summary>[un_favorite](#行为)||
| 编辑空间基本信息 | edit_space_info | 编辑基本信息 |单项数据（主键）|用户自定义||
| 已删除_恢复 | recover | 恢复 |单项数据（主键）|<details><summary>后台调用</summary>[recover](#行为)||
| 取消关联（其他实体关联） | del_relation | 取消关联 |单项数据（主键）|<details><summary>后台调用</summary>[del_relation](#行为)|其他实体关联需求表格、需求关联需求表格上界面行为组调用；|
| 回收站 | open_deleted_view | 回收站 |单项数据（主键）|用户自定义||
| 设置星标 | add_favorite | 设置星标 |单项数据（主键）|<details><summary>后台调用</summary>[favorite](#行为)||
| 进行中_删除 | in_progress_into_deleted | 删除 |单项数据（主键）|<details><summary>后台调用</summary>[delete](#行为)||
| 打开空间配置 | open_space_setting | 空间配置 |无数据|<details><summary>打开视图或向导（模态）</summary>[配置中心](app/view/space_config_tree_exp_view)</details>||
| 更多设置 | more_setting | 更多设置 |单项数据（主键）|用户自定义||
| 打开空间导航页 | open_space_exp_page | 打开空间导航页 |无数据|<details><summary>打开顶级视图</summary>[知识管理](app/view/space_tree_exp_view)</details>||
| 查看空间信息 | space_info | 空间信息 |单项数据（主键）|<details><summary>打开视图或向导（模态）</summary>[空间信息](app/view/space_info_view)</details>||
| 产品关联空间 | product_relation_space | 添加关联空间 |无数据|<details><summary>打开视图或向导（模态）</summary>[关联空间](app/view/space_product_re_space_choose_option_view)</details>||
| 移出分类 | move_out_category | 移出分类 |多项数据（主键）|<details><summary>后台调用</summary>[move_out_category](#行为)||
| 查看空间成员 | open_space_member | 空间成员 |单项数据（主键）|用户自定义||
| 已归档_删除 | delete | 删除 |单项数据（主键）|<details><summary>后台调用</summary>[delete](#行为)||
| 项目关联空间 | project_relation_space | 添加关联空间 |无数据|<details><summary>打开视图或向导（模态）</summary>[关联空间](app/view/space_product_re_space_choose_option_view)</details>||
| 进行中_归档 | in_progress_into_archived | 归档 |单项数据（主键）|<details><summary>后台调用</summary>[archive](#行为)||
| 已归档_激活 | activate | 激活 |单项数据（主键）|<details><summary>后台调用</summary>[activate](#行为)||
| 新开窗口（空间） | open_new | 新窗口打开 |单项数据（主键）|<details><summary>打开HTML页面</summary>*./#/-/index/space=${data.id}/space_index_view/srfnav=drgroup/article_page_tree_exp_view/srfnavctx=%257B%2522srfdefaulttoroutedepth%2522%253A3%257D;*</details>||

## 界面逻辑
|  中文名col200 | 代码名col150 | 备注col900 |
| --------|--------|--------|
|[产品关联空间](module/Wiki/space/uilogic/product_relation_space)|product_relation_space|调用后台关联逻辑，产品关联空间并生成正反关联数据|
|[刷新当前表格](module/Wiki/space/uilogic/refresh_current_grid)|refresh_current_grid|刷新当前表格|
|[批量删除空间成员临时数据](module/Wiki/space/uilogic/remove_batch_temp)|remove_batch_temp|获取空间内所有临时成员数据并删除|
|[新建目录](module/Wiki/space/uilogic/create_category)|create_category|新建空间目录|
|[计算表格列行为状态](module/Wiki/space/uilogic/calc_column_action_state)|calc_column_action_state|用于动态控制收藏和取消收藏的禁用状态|
|[项目关联空间](module/Wiki/space/uilogic/project_relation_space)|project_relation_space|调用后台关联逻辑，项目关联空间并生成正反关联数据|

<div style="display: block; overflow: hidden; position: fixed; top: 140px; right: 100px;">

##### 导航
<el-anchor >
<el-anchor-link :href="`#/module/Wiki/space?id=属性`">
  属性
</el-anchor-link>
<el-anchor-link :href="`#/module/Wiki/space?id=关系`">
  关系
</el-anchor-link>
<el-anchor-link :href="`#/module/Wiki/space?id=行为`">
  行为
</el-anchor-link>
<el-anchor-link :href="`#/module/Wiki/space?id=处理逻辑`">
  处理逻辑
</el-anchor-link>
<el-anchor-link :href="`#/module/Wiki/space?id=主状态控制`">
  主状态控制
</el-anchor-link>
<el-anchor-link :href="`#/module/Wiki/space?id=数据查询`">
  数据查询
</el-anchor-link>
<el-anchor-link :href="`#/module/Wiki/space?id=数据集合`">
  数据集合
</el-anchor-link>
<el-anchor-link :href="`#/module/Wiki/space?id=数据权限`">
  数据权限
</el-anchor-link>
<el-anchor-link :href="`#/module/Wiki/space?id=搜索模式`">
  搜索模式
</el-anchor-link>
<el-anchor-link :href="`#/module/Wiki/space?id=界面行为`">
  界面行为
</el-anchor-link>
<el-anchor-link :href="`#/module/Wiki/space?id=界面逻辑`">
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