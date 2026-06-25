# 钉钉文档保护规则

## 规则说明

禁止对钉钉文档执行任何删除、回收、移除类操作。文档的所有删除动作由用户自行操作。

## 适用范围

所有涉及钉钉文档（含知识库）的 MCP 工具调用。

## 禁止的操作

- **禁止调用 `delete_document`**：不得将任何钉钉文档或文件夹移入回收站。
- **禁止调用 `delete_document_block`**：不得删除钉钉文档中的任何块元素（段落、图片、附件等）。
- **禁止调用 `remove_permission`**：不得移除任何用户在钉钉文档上的权限。

## 允许的操作

- 创建文档、创建文件夹、创建文件：`create_document`、`create_folder`、`create_file`
- 读取文档内容、获取文档信息：`get_document_content`、`get_document_info`
- 更新文档内容：`update_document`、`update_document_block`、`insert_document_block`
- 重命名、移动、复制：`rename_document`、`move_document`、`copy_document`
- 搜索、列出节点：`search_documents`、`list_nodes`、`list_document_blocks`
- 权限管理中的增加和修改：`add_permission`、`update_permission`、`list_permission`
- 版本管理：`list_doc_versions`、`save_doc_version`、`revert_doc_version`
- 导出、下载、上传：`submit_export_job`、`download_file`、`download_doc_attachment` 等

## 注意事项

- 即使 `update_document` 使用 overwrite 模式会清空文档内容，该操作本身不在禁止之列，但使用时需向用户确认。
- 如果用户明确要求删除操作，提醒用户自行在钉钉客户端中操作。
