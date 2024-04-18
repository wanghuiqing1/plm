# 全部需求(idea_all_grid_view)  <!-- {docsify-ignore-all} -->


<el-skeleton style="width:60%">
	<template #template>
		<div style="padding-bottom: 5px;">
			<div style="height:40px;display: flex;align-items: center;justify-content: space-between;">
				<el-tooltip content="页面标题">
					<el-skeleton-item variant="text" style="height:40px;"></el-skeleton-item>
				</el-tooltip>
				<el-tooltip content="搜索栏">
				    <el-skeleton-item variant="text" style="margin-left: 10px;height:40px;width:300px;"></el-skeleton-item>
				</el-tooltip>
				<el-skeleton style="width:250px;">
					<template #template>
						<el-tooltip content="工具栏">
							<div style="display: flex;align-items: center;justify-content:end">
								<el-skeleton-item variant="text" style="margin-left: 10px;height:40px;width:80px"></el-skeleton-item>
								<el-skeleton-item variant="text" style="margin-left: 10px;height:40px;width:80px"></el-skeleton-item>
								<el-skeleton-item variant="text" style="margin-left: 10px;height:40px;width:80px"></el-skeleton-item>
							</div>
						</el-tooltip>
					</template>
				</el-skeleton>
			</div>
		</div>
		<el-tooltip content="数据表格">
			<el-skeleton-item variant="p" style="height:300px"></el-skeleton-item>
		</el-tooltip>
	</template>
</el-skeleton>


## 控件
#### CAPTIONBAR(captionbar)

#### 数据表格(grid)

#### 搜索栏(searchbar)

#### 工具栏(toolbar)



### 关联界面行为
  * [需求(IDEA)](module/ProdMgmt/idea) : [表格界面_新建操作](module/ProdMgmt/idea#界面行为)
  * [需求(IDEA)](module/ProdMgmt/idea) : [表格界面_导出操作（Excel）](module/ProdMgmt/idea#界面行为)
  * [需求(IDEA)](module/ProdMgmt/idea) : [需求排期](module/ProdMgmt/idea#界面行为)
  * [需求(IDEA)](module/ProdMgmt/idea) : [表格界面_数据导入栏](module/ProdMgmt/idea#界面行为)
  * [需求(IDEA)](module/ProdMgmt/idea) : [需求移动](module/ProdMgmt/idea#界面行为)
  * [需求(IDEA)](module/ProdMgmt/idea) : [需求归档](module/ProdMgmt/idea#界面行为)
  * [需求(IDEA)](module/ProdMgmt/idea) : [变更需求状态](module/ProdMgmt/idea#界面行为)
  * [需求(IDEA)](module/ProdMgmt/idea) : [激活](module/ProdMgmt/idea#界面行为)
  * [需求(IDEA)](module/ProdMgmt/idea) : [需求复制](module/ProdMgmt/idea#界面行为)
  * [需求(IDEA)](module/ProdMgmt/idea) : [删除](module/ProdMgmt/idea#界面行为)

### 关联视图
  * [需求(idea_change_state_view)](app/view/idea_change_state_view)
  * [复制需求(idea_copy_option_view)](app/view/idea_copy_option_view)
  * [需求(idea_idea_re_plan_option_view)](app/view/idea_idea_re_plan_option_view)
  * [需求(idea_main_view)](app/view/idea_main_view)
  * [移动需求(idea_move_option_view)](app/view/idea_move_option_view)
  * [新建需求(idea_quick_create_view)](app/view/idea_quick_create_view)

<script>
 const { createApp } = Vue
  createApp({
    data() {
      return {

      }
    }
  }).use(ElementPlus).mount('#app')
</script>