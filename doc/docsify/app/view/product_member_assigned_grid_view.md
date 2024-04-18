# 产品成员(product_member_assigned_grid_view)  <!-- {docsify-ignore-all} -->


系统自动添加


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

#### 搜索表单(searchform)

#### 工具栏(toolbar)


## 视图界面逻辑
  * [新建产品默认临时成员](module/ProdMgmt/product_member/uilogic/create_default_temp_members)
  * newdata(预置新建数据逻辑)
  * opendata(预置打开数据逻辑)


### 关联界面行为
  * [产品成员(PRODUCT_MEMBER)](module/ProdMgmt/product_member) : [移除成员](module/ProdMgmt/product_member#界面行为)
  * [产品成员(PRODUCT_MEMBER)](module/ProdMgmt/product_member) : [表格界面_新建操作](module/ProdMgmt/product_member#界面行为)

### 关联界面逻辑
  * [产品成员(PRODUCT_MEMBER)](module/ProdMgmt/product_member) : [新建产品默认临时成员](module/ProdMgmt/product_member/uilogic/create_default_temp_members)

### 关联视图
  * [产品成员(product_member_edit_view)](app/view/product_member_edit_view)
  * [产品成员(product_member_redirect_view)](app/view/product_member_redirect_view)
  * [选择成员(user_choose_mpick_up_view)](app/view/user_choose_mpick_up_view)

<script>
 const { createApp } = Vue
  createApp({
    data() {
      return {

      }
    }
  }).use(ElementPlus).mount('#app')
</script>