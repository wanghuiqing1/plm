# 草稿(article_page_draft_show_edit_view)  <!-- {docsify-ignore-all} -->


<el-skeleton style="width:60%">
	<template #template>
		<div style="padding-bottom: 5px;">
			<div style="height:40px;display: flex;align-items: center;justify-content: space-between;">
				<el-tooltip content="页面标题">
					<el-skeleton-item variant="text" style="height:40px;"></el-skeleton-item>
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
		<el-tooltip content="编辑表单">
			<el-skeleton-item variant="p" style="height:300px"></el-skeleton-item>
		</el-tooltip>
	</template>
</el-skeleton>


## 控件
#### CAPTIONBAR(captionbar)

#### DATAINFOBAR(datainfobar)

#### 编辑表单(form)

#### 工具栏(toolbar)



### 关联界面行为
  * [页面(PAGE)](module/Wiki/article_page) : [发布](module/Wiki/article_page#界面行为)
  * [页面(PAGE)](module/Wiki/article_page) : [删除数据](module/Wiki/article_page#界面行为)
  * [页面(PAGE)](module/Wiki/article_page) : [打开界面编辑页](module/Wiki/article_page#界面行为)

### 关联视图
  * [页面(article_page_document_edit_view)](app/view/article_page_document_edit_view)

<script>
 const { createApp } = Vue
  createApp({
    data() {
      return {

      }
    }
  }).use(ElementPlus).mount('#app')
</script>