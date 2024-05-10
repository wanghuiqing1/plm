## 全部数据(all) <!-- {docsify-ignore-all} -->



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

* `全部数据`






<el-dialog v-model="MYSQL5" title="MYSQL5">

```sql
SELECT
t1.`CHANGE_TYPE`,
t1.`CHANGE_VERSION`,
t1.`CREATE_MAN`,
t1.`CREATE_TIME`,
t11.`CUR_VERSION_ID`,
t1.`ID`,
t1.`NAME`,
t11.`OWNER_TYPE`,
t11.`PARENT_VERSION_ID`,
t11.`PRINCIPAL_ID`,
t11.`PRINCIPAL_TYPE`,
t11.`TARGET_ID`,
t11.`TARGET_TYPE`,
t11.`TARGET_VERSION_ID`,
t1.`UPDATE_MAN`,
t1.`UPDATE_TIME`
FROM `REVIEW_CONTENT_EXTEND` t1 
LEFT JOIN `RELATION` t11 ON t1.`ID` = t11.`ID` 


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