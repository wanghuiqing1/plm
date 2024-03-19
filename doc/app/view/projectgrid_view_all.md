# 全部项目(projectgrid_view_all)  <!-- {docsify-ignore-all} -->




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
  * 搜索栏(searchbar)
  * 工具栏(toolbar)
  * CAPTIONBAR(captionbar)
  * 数据表格(grid)
  * 搜索表单(searchform)

## 视图界面逻辑
  * newdata(预置新建数据逻辑)
  * opendata(预置打开数据逻辑)


### 关联界面行为
  * [项目发布(RELEASE)](module/ProjMgmt/Release) : [新建分组](module/ProjMgmt/Release#界面行为)
  * [项目(PROJECT)](module/ProjMgmt/Project) : [项目信息](module/ProjMgmt/Project#界面行为)
  * [项目发布(RELEASE)](module/ProjMgmt/Release) : [编辑](module/ProjMgmt/Release#界面行为)
  * [项目(PROJECT)](module/ProjMgmt/Project) : [编辑基本信息](module/ProjMgmt/Project#界面行为)
  * [项目发布(RELEASE)](module/ProjMgmt/Release) : [删除](module/ProjMgmt/Release#界面行为)
  * [项目(PROJECT)](module/ProjMgmt/Project) : [更多设置](module/ProjMgmt/Project#界面行为)
  * [项目(PROJECT)](module/ProjMgmt/Project) : [项目成员](module/ProjMgmt/Project#界面行为)
  * [项目(PROJECT)](module/ProjMgmt/Project) : [回收站](module/ProjMgmt/Project#界面行为)
  * [项目发布(RELEASE)](module/ProjMgmt/Release) : [编辑](module/ProjMgmt/Release#界面行为)
  * [项目发布(RELEASE)](module/ProjMgmt/Release) : [删除](module/ProjMgmt/Release#界面行为)
  * [项目(PROJECT)](module/ProjMgmt/Project) : [取消星标](module/ProjMgmt/Project#界面行为)
  * [空间(SPACE)](module/Wiki/Space) : [取消关联（其他实体关联）](module/Wiki/Space#界面行为)
  * [空间(SPACE)](module/Wiki/Space) : [产品关联空间](module/Wiki/Space#界面行为)
  * [项目(PROJECT)](module/ProjMgmt/Project) : [打开项目导航页](module/ProjMgmt/Project#界面行为)
  * [项目(PROJECT)](module/ProjMgmt/Project) : [设置星标](module/ProjMgmt/Project#界面行为)
  * [空间(SPACE)](module/Wiki/Space) : [树界面_刷新全部操作](module/Wiki/Space#界面行为)
  * [项目(PROJECT)](module/ProjMgmt/Project) : [新开窗口（项目）](module/ProjMgmt/Project#界面行为)
  * [项目(PROJECT)](module/ProjMgmt/Project) : [取消星标](module/ProjMgmt/Project#界面行为)
  * [项目发布(RELEASE)](module/ProjMgmt/Release) : [新建类别](module/ProjMgmt/Release#界面行为)
  * [项目发布(RELEASE)](module/ProjMgmt/Release) : [编辑](module/ProjMgmt/Release#界面行为)
  * [项目发布(RELEASE)](module/ProjMgmt/Release) : [树界面_刷新全部操作](module/ProjMgmt/Release#界面行为)
  * [项目发布(RELEASE)](module/ProjMgmt/Release) : [删除](module/ProjMgmt/Release#界面行为)
  * [项目(PROJECT)](module/ProjMgmt/Project) : [编辑基本信息](module/ProjMgmt/Project#界面行为)

### 关联视图
  * [工作项甘特图(work_itemgantt_view)](app/view/work_itemgantt_view)
  * [基本信息(projectoverview_view_baseinfo)](app/view/projectoverview_view_baseinfo)
  * [项目(projectRedirectView)](app/view/projectRedirectView)
  * [回收站(work_itemrecycle_bin_grid_iew)](app/view/work_itemrecycle_bin_grid_iew)
  * [缺陷属性分布测试(work_itemtab_exp_view_test)](app/view/work_itemtab_exp_view_test)
  * [概览(projectoverview_view)](app/view/projectoverview_view)
  * [项目快速建立(projectquick_create_view)](app/view/projectquick_create_view)
  * [项目(projectmain_data_kanban)](app/view/projectmain_data_kanban)
  * [工作项(work_itemgrid_view_all_kanban)](app/view/work_itemgrid_view_all_kanban)
  * [全部发布(releasegrid_view_all)](app/view/releasegrid_view_all)
  * [项目成员(project_membergrid_view_config)](app/view/project_membergrid_view_config)
  * [新建项目(projectcreate_wizard_view)](app/view/projectcreate_wizard_view)
  * [关联空间(spaceproduct_choose_re_space)](app/view/spaceproduct_choose_re_space)
  * [自动化规则(PSDELogicflow_grid_view)](app/view/PSDELogicflow_grid_view)
  * [页面(article_pagere_show_view)](app/view/article_pagere_show_view)
  * [项目信息(projectshow_edit_view)](app/view/projectshow_edit_view)
  * [全部计划(test_plangrid_view_project)](app/view/test_plangrid_view_project)
  * [基本信息(projectedit_view_base_information)](app/view/projectedit_view_base_information)
  * [文件夹(portfolioproject_show_view)](app/view/portfolioproject_show_view)
  * [高级设置(projectedit_view_advanced_setting)](app/view/projectedit_view_advanced_setting)
  * [空间(spaceproduct_re_tree_exp_view)](app/view/spaceproduct_re_tree_exp_view)
  * [测试计划(test_plantree_exp_view_project)](app/view/test_plantree_exp_view_project)
  * [工作项看板(work_itemkanban_view)](app/view/work_itemkanban_view)
  * [项目(projectmain_data_scrum)](app/view/projectmain_data_scrum)
  * [项目管理(projecttree_exp_view)](app/view/projecttree_exp_view)
  * [项目(projectmain_data_waterfall)](app/view/projectmain_data_waterfall)
  * [发布模块(releasetree_exp_view)](app/view/releasetree_exp_view)
  * [项目设置(projectsetting_view)](app/view/projectsetting_view)
  * [缺陷属性分布报表测试(work_itembug_state_statement)](app/view/work_itembug_state_statement)
  * [项目(projectEditView)](app/view/projectEditView)
  * [工作项类型(work_item_typesetting_view_scrum)](app/view/work_item_typesetting_view_scrum)

<script>
 const { createApp } = Vue
  createApp({
    data() {
      return {
        message: '!'
      }
    }
  }).use(ElementPlus).mount('#app')
</script>