# 新建工作项(work_item_quick_create_view)  <!-- {docsify-ignore-all} -->


<el-skeleton style="width:60%">
	<template #template>
		<div style="padding-bottom: 5px;">
			<div style="height:40px;display: flex;align-items: center;justify-content: space-between;">
				<el-tooltip content="页面标题">
					<el-skeleton-item variant="text" style="height:40px;"></el-skeleton-item>
				</el-tooltip>
			</div>
		</div>
		<el-tooltip content="编辑表单">
			<el-skeleton-item variant="p" style="height:300px"></el-skeleton-item>
		</el-tooltip>
		<el-skeleton style="display: flex;align-items: center;justify-content:end">
			<template #template>
				<div style="">
					<el-tooltip content="确认">
						<el-skeleton-item variant="text" style="margin-left: 10px;height:40px;width:80px"></el-skeleton-item>
					</el-tooltip>
					<el-tooltip content="取消">
						<el-skeleton-item variant="text" style="margin-left: 10px;height:40px;width:80px"></el-skeleton-item>
					</el-tooltip>
				</div>
			</template>
		</el-skeleton>
	</template>
</el-skeleton>


## 控件
#### CAPTIONBAR(captionbar)

#### DATAINFOBAR(datainfobar)

#### 编辑表单(form)

##### 部件逻辑
* `onChange` : [计算父工作项类型（表单）](module/ProjMgmt/work_item/uilogic/calc_parent_work_item_type_form)

##### 值规则
* `start_at` : [开始时间](index/value_rule_index)
* `end_at` : [结束时间](index/value_rule_index)

##### 属性注入
* `start_at`

```javascript
(time) => {
    if (!data.end_at) {
        return false;
    }
    const end_at = new Date(data.end_at);
    // 比对天
    time.setHours(0, 0, 0, 0);
    end_at.setHours(0, 0, 0, 0);
    return time.getTime() > end_at.getTime();
}
```

* `end_at`

```javascript
(time) => {
    if (!data.start_at) {
        return false;
    }
    const start_at = new Date(data.start_at);
    // 比对天
    start_at.setHours(0, 0, 0, 0);
    time.setHours(0, 0, 0, 0);
    return time.getTime() < start_at.getTime();
}
```

## 视图界面逻辑
  * [计算父工作项类型（表单）](module/ProjMgmt/work_item/uilogic/calc_parent_work_item_type_form)
  * [设置默认关注人](module/ProjMgmt/work_item/uilogic/set_default_attention)


### 关联界面逻辑
  * [工作项(WORK_ITEM)](module/ProjMgmt/work_item) : [设置默认关注人](module/ProjMgmt/work_item/uilogic/set_default_attention)
  * [工作项(WORK_ITEM)](module/ProjMgmt/work_item) : [计算父工作项类型（表单）](module/ProjMgmt/work_item/uilogic/calc_parent_work_item_type_form)

### 关联视图
  * [看板(board_pick_up_view)](app/view/board_pick_up_view)
  * [项目(project_pick_up_view)](app/view/project_pick_up_view)
  * [选择工作项(work_item_change_parent_pick_up_view)](app/view/work_item_change_parent_pick_up_view)

<script>
 const { createApp } = Vue
  createApp({
    data() {
      return {

      }
    }
  }).use(ElementPlus).mount('#app')
</script>