# 产品管理(product_tree_exp_view)  <!-- {docsify-ignore-all} -->


<el-skeleton style="width:60%">
	<template #template>
		<div style="padding-bottom: 5px;display: flex;">
			<div style="display: flex;align-items: center;justify-content: space-between;flex-direction: column;">
				<el-tooltip content="页面标题">
					<el-skeleton-item variant="text" style="width:180px;height:40px;"></el-skeleton-item>
				</el-tooltip>
				<el-tooltip content="树视图">
					<el-skeleton-item variant="text" style="margin-top: 10px;width:180px;height:300px;"></el-skeleton-item>
				</el-tooltip>
			</div>
			<el-tooltip content="导航区域">
				<el-skeleton-item variant="p" style="margin-left: 10px;height:350px"></el-skeleton-item>
			</el-tooltip>
		</div>
	</template>
</el-skeleton>


## 控件
#### CAPTIONBAR(captionbar)

#### 搜索栏(searchbar)

#### 树视图导航栏(treeexpbar)


## 视图界面逻辑
  * newdata(预置新建数据逻辑)
  * opendata(预置打开数据逻辑)


### 关联界面行为
  * [产品(PRODUCT)](module/ProdMgmt/product) : [设置星标](module/ProdMgmt/product#界面行为)
  * [需求(IDEA)](module/ProdMgmt/idea) : [新建子产品](module/ProdMgmt/idea#界面行为)
  * [客户(CUSTOMER)](module/ProdMgmt/customer) : [删除](module/ProdMgmt/customer#界面行为)
  * [产品(PRODUCT)](module/ProdMgmt/product) : [取消星标](module/ProdMgmt/product#界面行为)
  * [产品(PRODUCT)](module/ProdMgmt/product) : [回收站](module/ProdMgmt/product#界面行为)
  * [需求(IDEA)](module/ProdMgmt/idea) : [编辑](module/ProdMgmt/idea#界面行为)
  * [排期(PRODUCT_PLAN)](module/ProdMgmt/product_plan) : [删除](module/ProdMgmt/product_plan#界面行为)
  * [需求(IDEA)](module/ProdMgmt/idea) : [编辑](module/ProdMgmt/idea#界面行为)
  * [排期(PRODUCT_PLAN)](module/ProdMgmt/product_plan) : [编辑](module/ProdMgmt/product_plan#界面行为)
  * [排期(PRODUCT_PLAN)](module/ProdMgmt/product_plan) : [新建类别](module/ProdMgmt/product_plan#界面行为)
  * [空间(SPACE)](module/Wiki/space) : [产品关联空间](module/Wiki/space#界面行为)
  * [产品(PRODUCT)](module/ProdMgmt/product) : [更多设置](module/ProdMgmt/product#界面行为)
  * [空间(SPACE)](module/Wiki/space) : [取消关联（其他实体关联）](module/Wiki/space#界面行为)
  * [需求(IDEA)](module/ProdMgmt/idea) : [编辑](module/ProdMgmt/idea#界面行为)
  * [需求(IDEA)](module/ProdMgmt/idea) : [删除](module/ProdMgmt/idea#界面行为)
  * [产品(PRODUCT)](module/ProdMgmt/product) : [编辑基本信息](module/ProdMgmt/product#界面行为)
  * [需求(IDEA)](module/ProdMgmt/idea) : [新建模块](module/ProdMgmt/idea#界面行为)
  * [排期(PRODUCT_PLAN)](module/ProdMgmt/product_plan) : [新建分组](module/ProdMgmt/product_plan#界面行为)
  * [产品(PRODUCT)](module/ProdMgmt/product) : [打开产品首页视图](module/ProdMgmt/product#界面行为)
  * [需求(IDEA)](module/ProdMgmt/idea) : [树界面_刷新全部操作](module/ProdMgmt/idea#界面行为)
  * [空间(SPACE)](module/Wiki/space) : [项目关联空间](module/Wiki/space#界面行为)
  * [客户(CUSTOMER)](module/ProdMgmt/customer) : [新建分组](module/ProdMgmt/customer#界面行为)
  * [需求(IDEA)](module/ProdMgmt/idea) : [删除](module/ProdMgmt/idea#界面行为)
  * [产品(PRODUCT)](module/ProdMgmt/product) : [产品信息](module/ProdMgmt/product#界面行为)
  * [排期(PRODUCT_PLAN)](module/ProdMgmt/product_plan) : [编辑](module/ProdMgmt/product_plan#界面行为)
  * [需求(IDEA)](module/ProdMgmt/idea) : [编辑](module/ProdMgmt/idea#界面行为)
  * [排期(PRODUCT_PLAN)](module/ProdMgmt/product_plan) : [编辑](module/ProdMgmt/product_plan#界面行为)
  * [客户(CUSTOMER)](module/ProdMgmt/customer) : [编辑](module/ProdMgmt/customer#界面行为)
  * [客户(CUSTOMER)](module/ProdMgmt/customer) : [新建类别](module/ProdMgmt/customer#界面行为)
  * [产品(PRODUCT)](module/ProdMgmt/product) : [打开产品配置](module/ProdMgmt/product#界面行为)
  * [客户(CUSTOMER)](module/ProdMgmt/customer) : [树界面_刷新全部操作](module/ProdMgmt/customer#界面行为)
  * [需求(IDEA)](module/ProdMgmt/idea) : [删除](module/ProdMgmt/idea#界面行为)
  * [需求(IDEA)](module/ProdMgmt/idea) : [删除](module/ProdMgmt/idea#界面行为)
  * [排期(PRODUCT_PLAN)](module/ProdMgmt/product_plan) : [删除](module/ProdMgmt/product_plan#界面行为)
  * [客户(CUSTOMER)](module/ProdMgmt/customer) : [删除](module/ProdMgmt/customer#界面行为)
  * [排期(PRODUCT_PLAN)](module/ProdMgmt/product_plan) : [删除](module/ProdMgmt/product_plan#界面行为)
  * [客户(CUSTOMER)](module/ProdMgmt/customer) : [编辑](module/ProdMgmt/customer#界面行为)
  * [排期(PRODUCT_PLAN)](module/ProdMgmt/product_plan) : [树界面_刷新全部操作](module/ProdMgmt/product_plan#界面行为)
  * [空间(SPACE)](module/Wiki/space) : [树界面_刷新全部操作](module/Wiki/space#界面行为)
  * [产品(PRODUCT)](module/ProdMgmt/product) : [产品成员](module/ProdMgmt/product#界面行为)
  * [产品(PRODUCT)](module/ProdMgmt/product) : [打开产品导航页](module/ProdMgmt/product#界面行为)

### 关联视图
  * [页面(article_page_re_show_view)](app/view/article_page_re_show_view)
  * [全部客户(customer_all_grid_view)](app/view/customer_all_grid_view)
  * [需求关联客户(customer_idea_re_customer_grid_view)](app/view/customer_idea_re_customer_grid_view)
  * [客户(customer_tree_exp_view)](app/view/customer_tree_exp_view)
  * [全部需求(idea_all_grid_view)](app/view/idea_all_grid_view)
  * [需求模块(idea_tree_exp_view)](app/view/idea_tree_exp_view)
  * [全部产品(product_all_grid_view)](app/view/product_all_grid_view)
  * [产品中心配置(product_config_tree_exp_view)](app/view/product_config_tree_exp_view)
  * [产品详情配置(product_details_setting_view)](app/view/product_details_setting_view)
  * [产品(product_edit_view)](app/view/product_edit_view)
  * [产品(product_index_view)](app/view/product_index_view)
  * [全部计划(product_plan_all_grid_view)](app/view/product_plan_all_grid_view)
  * [排期模块(product_plan_tree_exp_view)](app/view/product_plan_tree_exp_view)
  * [产品配置(product_setting_view)](app/view/product_setting_view)
  * [产品信息(product_show_eidt_view)](app/view/product_show_eidt_view)
  * [关联空间(space_product_re_space_choose_option_view)](app/view/space_product_re_space_choose_option_view)
  * [空间(space_product_re_tree_exp_view)](app/view/space_product_re_tree_exp_view)
  * [全部工单(ticket_all_grid_view)](app/view/ticket_all_grid_view)

<script>
 const { createApp } = Vue
  createApp({
    data() {
      return {

      }
    }
  }).use(ElementPlus).mount('#app')
</script>