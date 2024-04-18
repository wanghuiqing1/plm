## 测试用例关联缺陷(test_case_relation_bug) <!-- {docsify-ignore-all} -->



<p class="panel-title"><b>查看SQL语句</b></p>
<br>

<el-row>
&nbsp;<el-tag @click="MYSQL5 = true">MYSQL5</el-tag>
</el-row>

<br>
<p class="panel-title"><b>是否默认查询</b></p>

* `否`

<p class="panel-title"><b>是否权限使用</b></p>

* `否`

<p class="panel-title"><b>是否自定义SQL</b></p>

* `否`

<p class="panel-title"><b>查询列级别</b></p>

* `默认（全部查询列）`



### 查询条件

(`IS_DELETED(是否已删除)` EQ `'0'`)



### 查询连接
* **RELATION存在1:N（EXISTS (SELECT)）DERCUSTOM_RELATION_WORK_ITEM**<br>
连接关系：[DERCUSTOM_RELATION_WORK_ITEM](der/DERCUSTOM_RELATION_WORK_ITEM)<br>
连接实体：[工作项](module/ProjMgmt/work_item)<br>
连接条件：(`PRINCIPAL_ID(关联主体标识)` EQ `网页请求上下文.principal_id` AND `PRINCIPAL_TYPE(关联主体类型)` EQ `'test_case'` AND `TARGET_TYPE(关联目标类型)` EQ `'bug'`)<br>




<el-dialog v-model="MYSQL5" title="MYSQL5">

```sql
SELECT
t1.`ASSIGNEE_ID`,
t1.`ASSIGNEE_NAME`,
t1.`BACKLOG_FROM`,
t1.`BACKLOG_TYPE`,
t1.`BOARD_ID`,
t61.`NAME` AS `BOARD_NAME`,
t1.`COMPLETED_AT`,
t1.`CREATE_MAN`,
t1.`CREATE_TIME`,
t1.`CUR_VERSION_ID`,
t1.`END_AT`,
t1.`ENTRY_ID`,
t51.`NAME` AS `ENTRY_NAME`,
t1.`ENTRY_POSITION`,
t1.`ENTRY_STATUS`,
t1.`ID`,
t1.`IDENTIFIER`,
t1.`IS_ARCHIVED`,
t1.`IS_DELETED`,
t1.`IS_LEAF`,
t1.`JOB_TYPE`,
t1.`PID`,
t1.`PRIORITY`,
t1.`PROJECT_ID`,
t11.`IDENTIFIER` AS `PROJECT_IDENTIFIER`,
t11.`NAME` AS `PROJECT_NAME`,
t11.`TYPE` AS `PROJECT_TYPE`,
t41.`TITLE` AS `PTITLE`,
t1.`REAPPEAR_PROBABILITY`,
t1.`RELEASE_ID`,
1 AS `REP_NUM`,
t1.`RISK`,
t1.`SEVERITY`,
concat(t11.`IDENTIFIER`,'-',t1.`IDENTIFIER`) AS `SHOW_IDENTIFIER`,
t1.`SPRINT_ID`,
t81.`NAME` AS `SPRINT_NAME`,
t1.`START_AT`,
t1.`STATE`,
t31.`TYPE` AS `STATE_TYPE`,
t1.`SWIMLANE_ID`,
t1.`TAGS`,
t1.`TITLE`,
t1.`TOP_ID`,
t71.`TITLE` AS `TOP_TITLE`,
t1.`UPDATE_MAN`,
t1.`UPDATE_TIME`,
t21.`GROUP` AS `WORK_ITEM_TYPE_GROUP`,
t1.`WORK_ITEM_TYPE_ID`,
t21.`NAME` AS `WORK_ITEM_TYPE_NAME`,
t21.`SEQUENCE` AS `WORK_ITEM_TYPE_SEQUENCE`
FROM `WORK_ITEM` t1 
LEFT JOIN `PROJECT` t11 ON t1.`PROJECT_ID` = t11.`ID` 
LEFT JOIN `WORK_ITEM_TYPE` t21 ON t1.`WORK_ITEM_TYPE_ID` = t21.`ID` 
LEFT JOIN `WORK_ITEM_STATE` t31 ON t1.`STATE` = t31.`ID` 
LEFT JOIN `WORK_ITEM` t41 ON t1.`PID` = t41.`ID` 
LEFT JOIN `ENTRY` t51 ON t1.`ENTRY_ID` = t51.`ID` 
LEFT JOIN `BOARD` t61 ON t1.`BOARD_ID` = t61.`ID` 
LEFT JOIN `WORK_ITEM` t71 ON t1.`TOP_ID` = t71.`ID` 
LEFT JOIN `SPRINT` t81 ON t1.`SPRINT_ID` = t81.`ID` 

WHERE EXISTS(SELECT * FROM `RELATION` t91 
 WHERE 
 t1.`ID` = t91.`TARGET_ID`  AND  ( t91.`PRINCIPAL_ID` = #{ctx.webcontext.principal_id}  AND  t91.`PRINCIPAL_TYPE` = 'test_case'  AND  t91.`TARGET_TYPE` = 'bug' ) ) AND ( t1.`IS_DELETED` = 0 )
```

</el-dialog>

<script>
 const { createApp } = Vue
  createApp({
    data() {
      return {
                MYSQL5 : false
        
      }
    },
    methods: {
    }
  }).use(ElementPlus).mount('#app')
</script>