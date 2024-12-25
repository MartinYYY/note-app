# 一、产品功能介绍

本记事本APP，实现了记事本的基本功能，包括记事本增删改查、记事本分类，仅满足了最基本的记事本使用需求。

1. 记事本主界面

   <img src="D:\Martin\APPFiles\TyproPic\d99516bdaca517e28b51257c14e5640.jpg" alt="d99516bdaca517e28b51257c14e5640" style="zoom: 20%;" />

2. 新增记事本

   <img src="D:\Martin\APPFiles\TyproPic\52d91fd30d8144ca2adf8e421dca209.jpg" alt="52d91fd30d8144ca2adf8e421dca209" style="zoom:20%;" />

   

3. 修改记事本

   <img src="D:\Martin\APPFiles\TyproPic\28c40cbca58ad2e2999d493d28d1746.jpg" alt="28c40cbca58ad2e2999d493d28d1746" style="zoom:20%;" />

4. 删除记事本

   <img src="D:\Martin\APPFiles\TyproPic\9fd5b129a59ccef18137b3c27386cc0.jpg" alt="9fd5b129a59ccef18137b3c27386cc0" style="zoom:20%;" />

5. 根据标题或内容查询记事本

   <img src="D:\Martin\APPFiles\TyproPic\a487f1e532d7804f8a061fdc940297a.jpg" alt="a487f1e532d7804f8a061fdc940297a" style="zoom:20%;" />

6. 记事本分类

   <img src="D:\Martin\APPFiles\TyproPic\8d71c2190cc73ce52ed1c5eed5ff485.jpg" alt="8d71c2190cc73ce52ed1c5eed5ff485" style="zoom:20%;" />

# 二、程序概要设计

## 1.系统模块划分

- **用户界面模块**：
  - 展示所有笔记的列表。
  - 提供新增、编辑和删除笔记的功能。
  - 提供分类管理功能，允许用户为笔记添加类别，并按类别查看笔记。
- **笔记管理模块**：
  - **增**：允许用户创建新笔记。
  - **删**：允许用户删除已创建的笔记。
  - **改**：允许用户编辑已存在的笔记。
  - **查**：支持查看所有笔记，按分类查看笔记。
- **分类管理模块**：
  - **增**：允许用户为笔记设置新类别。
  - **查**：支持查看笔记类别并按类别过滤笔记。

## 2.数据库设计

**数据库架构**：使用SQLite进行本地存储，设计两张主要表：

- `notes`（笔记表）：存储笔记的内容、标题和所属分类等字段。
- `categories`（分类表）：存储笔记分类信息。

**表结构**：

- `notes` 表：包括字段 `id`（笔记ID），`title`（标题），`content`（内容），`category_id`（分类ID）。
- `categories` 表：包括字段 `id`（分类ID），`name`（分类名称）。

## 3.功能流程

**笔记操作**：

1. 用户点击“添加笔记”按钮，输入标题和内容，选择分类（可选），保存笔记。
2. 用户可以在笔记列表中选择笔记进行编辑，修改内容后保存。
3. 用户可以删除不需要的笔记。

**分类操作**：

1. 用户点击“添加分类”按钮，输入分类名称，保存分类。
2. 用户可以查看分类列表，并按分类筛选笔记。
3. 分类是可编辑和可删除的。

#三、软件架构图

![image-20241225162546590](D:\Martin\APPFiles\TyproPic\image-20241225162546590.png)