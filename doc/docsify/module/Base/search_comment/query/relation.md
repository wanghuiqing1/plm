## 关联查询(relation) <!-- {docsify-ignore-all} -->



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

* `是`

<p class="panel-title"><b>查询列级别</b></p>

* `全部数据`

> [!ATTENTION|label:存在长文本属性]
>
> `CONTENT(内容)`






<el-dialog v-model="MYSQL5" title="MYSQL5">

```sql
SELECT
t1.`CONTENT`,
t1.`CREATE_MAN`,
t1.`CREATE_TIME`,
t1.`ID`,
t1.`NAME`,
t1.`OWNER_TYPE`,
t1.`PRINCIPAL_ID`,
t1.`PRINCIPAL_NAME`,
t1.`PRINCIPAL_TYPE`,
t1.`UPDATE_MAN`,
t1.`UPDATE_TIME`
FROM `COMMENT` t1
WHERE 
( <choose>
    <when test="ctx.webcontext.search_module != null and ctx.webcontext.search_module == '1'"> 
        exists(select 1 from work_item t2, project_member t3 where t2.project_id = t3.project_id 
        and t3.user_id = #{ctx.sessioncontext.srfpersonid} and t1.principal_id = t2.id 
        and t2.is_deleted = 0 <if test="project_id != null and project_id != ''"> and t2.project_id = #{ctx.webcontext.project_id}  </if>)
    </when>
    <when test="ctx.webcontext.search_module != null and ctx.webcontext.search_module == '2'"> 
        exists(select 1 from idea t2, product_member t3 where t2.product_id = t3.product_id 
        and t3.user_id = #{ctx.sessioncontext.srfpersonid}  
        and t1.principal_id = t2.id and t2.is_deleted = 0 <if test="product_id != null and product_id != ''"> and t2.product_id = #{ctx.webcontext.product_id}  </if>)
        or exists(select 1 from ticket t2, product_member t3 where t2.product_id = t3.product_id 
        and t3.user_id = #{ctx.sessioncontext.srfpersonid}  
        and t1.principal_id = t2.id and t2.is_deleted = 0 <if test="product_id != null and product_id != ''"> and t2.product_id = #{ctx.webcontext.product_id}  </if>)
        or exists(select 1 from customer t2, product_member t3 where t2.product_id = t3.product_id 
        and t3.user_id = #{ctx.sessioncontext.srfpersonid} and t1.principal_type = 'CUSTOMER'  
        and t1.principal_id = t2.id and t2.is_deleted = 0 <if test="product_id != null and product_id != ''"> and t2.product_id = #{ctx.webcontext.product_id}  </if>)
    </when>
    <when test="ctx.webcontext.search_module != null and ctx.webcontext.search_module == '3'"> 
        exists(select 1 from test_case t2, library_member t3 where t2.test_library_id = t3.library_id 
        and t3.user_id = #{ctx.sessioncontext.srfpersonid} and t1.principal_id = t2.id 
        and t2.is_deleted = 0 <if test="library_id != null and library_id != ''"> and t2.test_library_id = #{ctx.webcontext.library_id}  </if>)
    </when>
    <when test="ctx.webcontext.search_module != null and ctx.webcontext.search_module == '4'"> 
        exists(select 1 from page t2, space_member t3 where t2.space_id = t3.space_id 
        and t3.user_id = #{ctx.sessioncontext.srfpersonid} and t1.principal_id = t2.id 
        and t2.is_deleted = 0 <if test="space_id != null and space_id != ''"> and t2.space_id = #{ctx.webcontext.space_id}  </if>)
    </when>
    <otherwise>
        exists(select 1 from work_item t2, project_member t3 where t2.project_id = t3.project_id 
        and t3.user_id = #{ctx.sessioncontext.srfpersonid} 
        and t1.principal_id = t2.id and t2.is_deleted = 0)
        or exists(select 1 from idea t2, product_member t3 where t2.product_id = t3.product_id 
        and t3.user_id = #{ctx.sessioncontext.srfpersonid}  
        and t1.principal_id = t2.id and t2.is_deleted = 0 )
        or exists(select 1 from ticket t2, product_member t3 where t2.product_id = t3.product_id 
        and t3.user_id = #{ctx.sessioncontext.srfpersonid}  
        and t1.principal_id = t2.id and t2.is_deleted = 0 )
        or exists(select 1 from customer t2, product_member t3 where t2.product_id = t3.product_id 
        and t3.user_id = #{ctx.sessioncontext.srfpersonid} and t1.principal_type = 'CUSTOMER'  
        and t1.principal_id = t2.id and t2.is_deleted = 0 )
        or exists(select 1 from test_case t2, library_member t3 where t2.test_library_id = t3.library_id  
        and t3.user_id = #{ctx.sessioncontext.srfpersonid}  
        and t1.principal_id = t2.id and t2.is_deleted = 0 )
        or exists(select 1 from page t2, space_member t3 where t2.space_id = t3.space_id  
        and t3.user_id = #{ctx.sessioncontext.srfpersonid}  
        and t1.principal_id = t2.id and t2.is_deleted = 0 )
    </otherwise>
</choose> )

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