# 工作项看板(work_item_kanban_view)  <!-- {docsify-ignore-all} -->


SRFNAVCTX.BOARD=fdbc1f55-cd26-6bc6-1163-51a0683402ed




## 控件
#### CAPTIONBAR(captionbar)

#### 看板(kanban)

##### 部件逻辑
* `onLoadSuccess` : [计算面板项行为状态](module/ProjMgmt/work_item/uilogic/calc_kanban_item_action_state)* `onSelectionChange` : [计算面板项行为状态](module/ProjMgmt/work_item/uilogic/calc_kanban_item_action_state)
#### 搜索栏(searchbar)

#### 搜索表单(searchform)

#### 工具栏(toolbar)



### 关联界面行为
  * [工作项(WORK_ITEM)](module/ProjMgmt/work_item) : [新建用户故事（kanban）（工具栏）](module/ProjMgmt/work_item#界面行为)
  * [工作项(WORK_ITEM)](module/ProjMgmt/work_item) : [新建缺陷（kanban）（工具栏）](module/ProjMgmt/work_item#界面行为)
  * [工作项(WORK_ITEM)](module/ProjMgmt/work_item) : [新建任务（kanban）（工具栏）](module/ProjMgmt/work_item#界面行为)

### 关联界面逻辑
  * [工作项(WORK_ITEM)](module/ProjMgmt/work_item) : [计算面板项行为状态](module/ProjMgmt/work_item/uilogic/calc_kanban_item_action_state)

### 关联视图
  * [工作项(work_item_edit_view)](app/view/work_item_edit_view)
  * [工作项(work_item_main_view)](app/view/work_item_main_view)

<script>
 const { createApp } = Vue
  createApp({
    data() {
      return {

      }
    }
  }).use(ElementPlus).mount('#app')
</script>