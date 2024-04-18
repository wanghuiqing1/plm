# 用例(test_case_this_suite_test_case_grid_view)  <!-- {docsify-ignore-all} -->


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
  * newdata(预置新建数据逻辑)
  * opendata(预置打开数据逻辑)


### 关联界面行为
  * [用例(TEST_CASE)](module/TestMgmt/test_case) : [表格界面_新建操作](module/TestMgmt/test_case#界面行为)
  * [用例(TEST_CASE)](module/TestMgmt/test_case) : [移动](module/TestMgmt/test_case#界面行为)
  * [用例(TEST_CASE)](module/TestMgmt/test_case) : [移入计划（气泡）](module/TestMgmt/test_case#界面行为)
  * [用例(TEST_CASE)](module/TestMgmt/test_case) : [表格界面_拷贝操作](module/TestMgmt/test_case#界面行为)
  * [用例(TEST_CASE)](module/TestMgmt/test_case) : [界面行为支持获取编辑列](module/TestMgmt/test_case#界面行为)
  * [用例(TEST_CASE)](module/TestMgmt/test_case) : [删除](module/TestMgmt/test_case#界面行为)
  * [用例(TEST_CASE)](module/TestMgmt/test_case) : [移动用例](module/TestMgmt/test_case#界面行为)
  * [用例(TEST_CASE)](module/TestMgmt/test_case) : [设置评审状态](module/TestMgmt/test_case#界面行为)
  * [用例(TEST_CASE)](module/TestMgmt/test_case) : [设置重要程度](module/TestMgmt/test_case#界面行为)
  * [用例(TEST_CASE)](module/TestMgmt/test_case) : [表格界面_数据导入栏](module/TestMgmt/test_case#界面行为)
  * [用例(TEST_CASE)](module/TestMgmt/test_case) : [设置维护人](module/TestMgmt/test_case#界面行为)
  * [用例(TEST_CASE)](module/TestMgmt/test_case) : [删除](module/TestMgmt/test_case#界面行为)
  * [用例(TEST_CASE)](module/TestMgmt/test_case) : [移入计划（气泡）](module/TestMgmt/test_case#界面行为)
  * [用例(TEST_CASE)](module/TestMgmt/test_case) : [表格界面_导出操作（Excel）](module/TestMgmt/test_case#界面行为)
  * [用例(TEST_CASE)](module/TestMgmt/test_case) : [复制用例](module/TestMgmt/test_case#界面行为)

### 关联视图
  * [用例(test_case_case_move_plan_option_view)](app/view/test_case_case_move_plan_option_view)
  * [复制用例(test_case_copy_test_case_option_view)](app/view/test_case_copy_test_case_option_view)
  * [用例(test_case_main_view)](app/view/test_case_main_view)
  * [移动用例(test_case_move_case_option_view)](app/view/test_case_move_case_option_view)
  * [移动用例(test_case_move_test_case_view)](app/view/test_case_move_test_case_view)
  * [新建用例(test_case_quick_create_view)](app/view/test_case_quick_create_view)
  * [用例(test_case_set_level_option_view)](app/view/test_case_set_level_option_view)
  * [用例(test_case_set_maintenance_option_view)](app/view/test_case_set_maintenance_option_view)
  * [用例(test_case_set_state_option_view)](app/view/test_case_set_state_option_view)

<script>
 const { createApp } = Vue
  createApp({
    data() {
      return {

      }
    }
  }).use(ElementPlus).mount('#app')
</script>