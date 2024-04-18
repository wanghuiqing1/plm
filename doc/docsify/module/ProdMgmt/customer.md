# 客户(customer)  <!-- {docsify-ignore-all} -->


记录客户信息基本信息。


## 属性
|    中文名col150 | 属性名称col200           | 类型col200     | 长度col100    |允许为空col100    |  备注col500  |
| --------   |------------| -----  | -----  | :----: | -------- |
|负责人标识|ASSIGNEE_ID|外键值|100|是||
|负责人|ASSIGNEE_NAME|外键值文本|100|是||
|关注|ATTENTIONS|一对多关系数据集合|1048576|是||
|类别|CATEGORIES|长文本，长度1000|2000|是||
|类别|CATEGORIES_NAME|长文本，长度1000|2000|是||
|建立人|CREATE_MAN|文本，可指定长度|100|否||
|建立时间|CREATE_TIME|日期时间型||否||
|描述|DESCRIPTION|长文本，长度1000|2000|是||
|等级|GRADE_ID|[单项选择(文本值)](index/dictionary_index#customer_level "客户等级")|60|是||
|标识<sup class="footnote-symbol"><font color=orange>[PK]</font></sup>|ID|全局唯一标识，文本类型，用户不可见|100|否||
|行业|INDUSTRY_ID|[单项选择(文本值)](index/dictionary_index#customer_sector "客户行业")|60|是||
|是否已归档|IS_ARCHIVED|是否逻辑||是||
|是否已删除|IS_DELETED|是否逻辑||是||
|品牌标识|LOGO|文本，可指定长度|100|是||
|客户名称|NAME|文本，可指定长度|500|否||
|产品标识|PRODUCT_ID|外键值|100|是||
|产品名称|PRODUCT_NAME|外键值文本|200|是||
|规模|SCALE|整型||是||
|已完成工单数|TICKET_FINISH|整型||是||
|工单总数|TICKET_TOTAL|整型||是||
|更新人|UPDATE_MAN|文本，可指定长度|100|否||
|更新时间|UPDATE_TIME|日期时间型||否||


###### 属性组

<el-row>
<el-tabs v-model="show_field_group">

<el-tab-pane label="负责人" name="field_group_assignee">

|    中文名col150 | 属性名称col200           | 类型col200     | 长度col100    |允许为空col100    |  备注col500  |
| --------   |------------| -----  | -----  | :----: | -------- |
|标识<sup class="footnote-symbol"><font color=orange>[PK]</font></sup>|ID|全局唯一标识，文本类型，用户不可见|100|否||
|负责人标识|ASSIGNEE_ID|外键值|100|是||
|负责人|ASSIGNEE_NAME|外键值文本|100|是||

</el-tab-pane>

</el-tabs>
</el-row>

## 关系

<el-row>
<el-tabs v-model="show_der">
<el-tab-pane label="主关系" name="major">

| 名称col350     |   从实体col200 | 关系类型col200     |   备注col500  |
| -------- |---------- |------------|----- |
|[DER1N_TICKET_CUSTOMER_CUSTOMER_ID](der/DER1N_TICKET_CUSTOMER_CUSTOMER_ID)|[工单(TICKET)](module/ProdMgmt/ticket)|1:N关系||
|[DERCUSTOM_ATTENTION_CUSTOMER_OWNER_ID](der/DERCUSTOM_ATTENTION_CUSTOMER_OWNER_ID)|[关注(ATTENTION)](module/Base/attention)|自定义关系||
|[DERCUSTOM_COMMENT_CUSTOMER_PRINCIPAL_ID](der/DERCUSTOM_COMMENT_CUSTOMER_PRINCIPAL_ID)|[评论(COMMENT)](module/Base/comment)|自定义关系||
|[DERCUSTOM_CUSTOMER_SEARCH_ATTACHMENT](der/DERCUSTOM_CUSTOMER_SEARCH_ATTACHMENT)|[附件搜索(SEARCH_ATTACHMENT)](module/Base/search_attachment)|自定义关系||
|[DERCUSTOM_CUSTOMER_SEARCH_COMMENT](der/DERCUSTOM_CUSTOMER_SEARCH_COMMENT)|[评论搜索(SEARCH_COMMENT)](module/Base/search_comment)|自定义关系||
|[DERCUSTOM_RELATION_CUSTOMER](der/DERCUSTOM_RELATION_CUSTOMER)|[关联(RELATION)](module/Base/relation)|自定义关系||


</el-tab-pane>
<el-tab-pane label="从关系" name="minor">

|  名称col350   | 主实体col200   | 关系类型col200   |    备注col500  |
| -------- |---------- |-----------|----- |
|[DER1N_CUSTOMER_PRODUCT_PRODUCT_ID](der/DER1N_CUSTOMER_PRODUCT_PRODUCT_ID)|[产品(PRODUCT)](module/ProdMgmt/product)|1:N关系||
|[DER1N_CUSTOMER_USER_ASSIGNEE_ID](der/DER1N_CUSTOMER_USER_ASSIGNEE_ID)|[企业用户(USER)](module/Base/user)|1:N关系||

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
|Remove|Remove|内置方法|默认|支持|[附加操作](index/action_logic_index#customer_Remove)|||
|Save|Save|内置方法|默认|不支持||||
|Update|Update|内置方法|默认|不支持||||
|添加至类别|add_categories|[实体处理逻辑](module/ProdMgmt/customer/logic/add_categories "添加至类别")|默认|不支持||||
|客户选择工单|customer_choose_ticket|[实体处理逻辑](module/ProdMgmt/customer/logic/customer_choose_ticket "客户选择工单")|默认|不支持||||
|取消关联|del_relation|[实体处理逻辑](module/ProdMgmt/customer/logic/del_relation "取消关联")|默认|不支持||||
|获取关注人|get_attention|内置方法|默认|不支持||||
|无操作|nothing|[实体处理逻辑](module/ProdMgmt/customer/logic/nothing "无操作")|默认|不支持||||
|其他实体关联客户|others_relation_customer|[实体处理逻辑](module/ProdMgmt/customer/logic/others_relation_customer "其他实体关联客户")|默认|不支持||||
|产品客户关联分页计数器|product_customer_re_counters|[实体处理逻辑](module/ProdMgmt/customer/logic/product_customer_re_counters "产品客户关联分页计数器")|默认|不支持||||

## 处理逻辑
| 中文名col200    | 代码名col150    | 子类型col150    | 插件col200    |  备注col550  |
| -------- |---------- |----------- |------------|----------|
|[产品客户关联分页计数器](module/ProdMgmt/customer/logic/product_customer_re_counters)|product_customer_re_counters|无||产品下的客户主视图的分页计数器数据来源|
|[其他实体关联客户](module/ProdMgmt/customer/logic/others_relation_customer)|others_relation_customer|无||客户实体的关联操作，生成正向，反向关联数据|
|[删除客户发送通知](module/ProdMgmt/customer/logic/remove_customer_notify)|remove_customer_notify|无||根据客户标识触发删除客户发送通知|
|[取消关联](module/ProdMgmt/customer/logic/del_relation)|del_relation|无||客户取消关联数据（正反向关联数据同时删除）|
|[变更负责人附加逻辑](module/ProdMgmt/customer/logic/assignee_onchage)|assignee_onchage|属性逻辑||客户负责人变更时触发相应的通知消息|
|[客户选择工单](module/ProdMgmt/customer/logic/customer_choose_ticket)|customer_choose_ticket|无||客户选择工单操作，更新工单的客户属性|
|[无操作](module/ProdMgmt/customer/logic/nothing)|nothing|无||无操作逻辑，用于替换表单的获取数据行为|
|[添加至类别](module/ProdMgmt/customer/logic/add_categories)|add_categories|无||添加客户类别操作|

## 数据查询
| 中文名col200    | 代码名col150    | 默认查询col100 | 权限使用col100 | 自定义SQLcol100 |  备注col600|
| --------  | --------   | :----:  |:----:  | :----:  |----- |
|[数据查询(DEFAULT)](module/ProdMgmt/customer/query/Default)|DEFAULT|是|否 |否 ||
|[默认（全部数据）(VIEW)](module/ProdMgmt/customer/query/View)|VIEW|否|否 |否 ||
|[评论通知负责人(comment_notify_assignee)](module/ProdMgmt/customer/query/comment_notify_assignee)|comment_notify_assignee|否|否 |否 ||
|[需求未关联的客户(idea_notre_customer)](module/ProdMgmt/customer/query/idea_notre_customer)|idea_notre_customer|否|否 |否 ||
|[需求关联客户(idea_relation_customer)](module/ProdMgmt/customer/query/idea_relation_customer)|idea_relation_customer|否|否 |否 ||
|[正常状态(normal)](module/ProdMgmt/customer/query/normal)|normal|否|否 |否 ||
|[客户通知负责人(notify_assignee)](module/ProdMgmt/customer/query/notify_assignee)|notify_assignee|否|否 |否 ||

## 数据集合
| 中文名col200  | 代码名col150  | 类型col100 | 默认集合col100 |   插件col200|   备注col500|
| --------  | --------   | :----:   | :----:   | ----- |----- |
|[数据集(DEFAULT)](module/ProdMgmt/customer/dataset/Default)|DEFAULT|数据查询|是|||
|[评论通知负责人(comment_notify_assignee)](module/ProdMgmt/customer/dataset/comment_notify_assignee)|comment_notify_assignee|数据查询|否|||
|[需求未关联的客户(idea_noitre_customer)](module/ProdMgmt/customer/dataset/idea_notre_customer)|idea_noitre_customer|数据查询|否|||
|[需求关联客户(idea_relation_customer)](module/ProdMgmt/customer/dataset/idea_relation_customer)|idea_relation_customer|数据查询|否|||
|[正常状态(normal)](module/ProdMgmt/customer/dataset/normal)|normal|数据查询|否|||
|[客户通知负责人(notify_assignee)](module/ProdMgmt/customer/dataset/notify_assignee)|notify_assignee|数据查询|否|||

## 数据权限

##### 操作用户(写) :id=customer-USER_W

<p class="panel-title"><b>数据范围</b></p>

* `无`

<p class="panel-title"><b>数据能力</b></p>

* `CREATE(产品(SUBDATA))`



## 消息通知

|    中文名col200   | 代码名col150       |  消息队列col200   |  消息模板col200 |  通知目标col150     |  备注col350  |
|------------| -----   |  -------- | -------- |-------- |-------- |
|[取消分配负责人通知](module/ProdMgmt/customer/notify/assignee_cancel_notify)|assignee_cancel_notify|[默认消息队列](index/notify_index)|[客户通知模板(取消分配负责人)](index/notify_index#customer_assignee_cancel)|负责人 ||
|[分配负责人通知](module/ProdMgmt/customer/notify/assignee_notify)|assignee_notify|[默认消息队列](index/notify_index)|[客户通知模板(分配负责人)](index/notify_index#customer_assignee)|负责人 ||
|[变更负责人通知](module/ProdMgmt/customer/notify/assignee_onchage_notify)|assignee_onchage_notify|[默认消息队列](index/notify_index)|[客户通知模板(变更负责人)](index/notify_index#customer_assignee_onchange)|负责人 关注人 ||
|[删除客户通知](module/ProdMgmt/customer/notify/remove_notify)|remove_notify|[默认消息队列](index/notify_index)|[客户通知模板(删除客户)](index/notify_index#customer_remove)|关注人 负责人 ||

## 搜索模式
|   搜索表达式col350   |    属性名col200    |    搜索模式col200        |备注col500  |
| -------- |------------|------------|------|
|N_ASSIGNEE_ID_EQ|负责人标识|EQ||
|N_CATEGORYS_ISNULL|类别|ISNULL||
|N_CATEGORYS_LIKE|类别|LIKE||
|N_GRADE_ID_EQ|等级|EQ||
|N_ID_EQ|标识|EQ||
|N_INDUSTRY_ID_EQ|行业|EQ||
|N_NAME_LIKE|客户名称|LIKE||
|N_PRODUCT_ID_EQ|产品标识|EQ||
|N_PRODUCT_NAME_EQ|产品名称|EQ||
|N_PRODUCT_NAME_LIKE|产品名称|LIKE||

## 界面行为
|  中文名col200 |  代码名col150 |  标题col100   |     处理目标col100   |    处理类型col200        |  备注col500       |
| --------| --------| -------- |------------|------------|------------|
| 测试界面行为权限 | test_aciton | 测试 |无数据|用户自定义||
| 添加客户（其他实体关联） | other_add_relation_customer | 添加客户 |无数据|用户自定义||
| 编辑 | toolbar_tree_exp_view_node1_cm_deuiaction1_click | 编辑 |单项数据|用户自定义||
| 取消关联 | del_relation | 取消关联 |单项数据（主键）|<details><summary>后台调用</summary>[del_relation](#行为)||
| 新建类别 | toolbar_tree_exp_view_treeexpbar_toolbar_deuiaction2_click | 新建类别 |单项数据|用户自定义||
| 删除 | delete_customer | 删除 |单项数据（主键）|<details><summary>后台调用</summary>[Remove](#行为)||
| 删除 | toolbar_tree_exp_view_node2_cm_deuiaction2_click | 删除 |单项数据|用户自定义||
| 添加至类别（多选） | add_categories | 设置类别 |多项数据（主键）|<details><summary>后台调用</summary>[add_categories](#行为)||
| 编辑 | toolbar_tree_exp_view_node2_cm_deuiaction1_click | 编辑 |单项数据|用户自定义||
| 新建分组 | toolbar_tree_exp_view_treeexpbar_toolbar_deuiaction1_click | 新建分组 |单项数据|用户自定义||
| 删除 | toolbar_tree_exp_view_node1_cm_deuiaction2_click | 删除 |单项数据|用户自定义||

## 界面逻辑
|  中文名col200 | 代码名col150 | 备注col900 |
| --------|--------|--------|
|[关联客户值变更](module/ProdMgmt/customer/uilogic/relation_customer_change)|relation_customer_change|关联客户值变更时，调用处理逻辑，生成正反向关联数据|
|[删除类别或分组](module/ProdMgmt/customer/uilogic/remove_section_or_category)|remove_section_or_category|调用树节点删除方法，删除当前树节点数据|
|[新建分组](module/ProdMgmt/customer/uilogic/create_section)|create_section|调用树节点新建方法，新建分组|
|[新建类别](module/ProdMgmt/customer/uilogic/create_category)|create_category|调用树节点新建方法新建类别|
|[编辑类别或分组](module/ProdMgmt/customer/uilogic/edit_section_or_category)|edit_section_or_category|调用树节点修改方法，编辑当前树节点的类别或分组|
|[触发计数器刷新](module/ProdMgmt/customer/uilogic/refresh_counter)|refresh_counter|关联数据变更后，触发计数器刷新|
|[选择下拉框区域展示](module/ProdMgmt/customer/uilogic/show_choose_area)|show_choose_area|逻辑控制关联表格下方选项区域动态显示|
|[需求关联客户](module/ProdMgmt/customer/uilogic/idea_relation_customer)|idea_relation_customer|值变更时触发，需求关联客户，调用处理逻辑生成正反向数据|

## 导入模式

* **产品客户导入**


记录客户信息基本信息。


<el-descriptions direction="vertical" :column="6" :size="size" border>
<el-descriptions-item label="客户名称">-</el-descriptions-item>
<el-descriptions-item label="负责人">-</el-descriptions-item>
<el-descriptions-item label="等级">-</el-descriptions-item>
<el-descriptions-item label="规模">-</el-descriptions-item>
<el-descriptions-item label="行业">-</el-descriptions-item>
<el-descriptions-item label="描述">-</el-descriptions-item>
</el-descriptions>

<div style="display: block; overflow: hidden; position: fixed; top: 140px; right: 100px;">

##### 导航
<el-anchor >
<el-anchor-link :href="`#/module/ProdMgmt/customer?id=属性`">
  属性
</el-anchor-link>
<el-anchor-link :href="`#/module/ProdMgmt/customer?id=关系`">
  关系
</el-anchor-link>
<el-anchor-link :href="`#/module/ProdMgmt/customer?id=行为`">
  行为
</el-anchor-link>
<el-anchor-link :href="`#/module/ProdMgmt/customer?id=处理逻辑`">
  处理逻辑
</el-anchor-link>
<el-anchor-link :href="`#/module/ProdMgmt/customer?id=数据查询`">
  数据查询
</el-anchor-link>
<el-anchor-link :href="`#/module/ProdMgmt/customer?id=数据集合`">
  数据集合
</el-anchor-link>
<el-anchor-link :href="`#/module/ProdMgmt/customer?id=数据权限`">
  数据权限
</el-anchor-link>
<el-anchor-link :href="`#/module/ProdMgmt/customer?id=消息通知`">
  消息通知
</el-anchor-link>
<el-anchor-link :href="`#/module/ProdMgmt/customer?id=搜索模式`">
  搜索模式
</el-anchor-link>
<el-anchor-link :href="`#/module/ProdMgmt/customer?id=界面行为`">
  界面行为
</el-anchor-link>
<el-anchor-link :href="`#/module/ProdMgmt/customer?id=界面逻辑`">
  界面逻辑
</el-anchor-link>
<el-anchor-link :href="`#/module/ProdMgmt/customer?id=导入模式`">
  导入模式
</el-anchor-link>
</el-anchor>
</div>

<script>
 const { createApp } = Vue
  createApp({
    data() {
      return {
show_der:'major',
show_field_group:'field_group_assignee',

      }
    },
    methods: {
    }
  }).use(ElementPlus).mount('#app')
</script>