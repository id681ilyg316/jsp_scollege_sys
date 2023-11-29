## 本项目实现的最终作用是基于JSP高校社团信息管理平台网站
## 分为4个角色
### 第1个角色为管理员角色，实现了如下功能：
 - 图片资讯查询
 - 学校器材管理
 - 新闻资讯管理
 - 活动消息管理
 - 用户信息管理
 - 留言信息查询
 - 社团创建审批
 - 社团简介管理
 - 管理员登录
### 第2个角色为设计文稿，实现了如下功能：
 - 论文截图
### 第3个角色为社团管理员角色，实现了如下功能：
 - 我的社团信息查询
 - 社团成员查询
 - 社团新闻管理
 - 社团活动管理
 - 社团管理员登录
### 第4个角色为用户角色，实现了如下功能：
 - 个人信息修改
 - 创建社团
 - 创建社团审批详情
 - 加入社团审批详情
 - 查看所有新闻
 - 查看新闻
 - 查看活动信息
 - 查看社团详细情况
 - 用户注册
 - 申请加入社团
 - 留言板留言
## 数据库设计如下：
# 数据库设计文档

**数据库名：** scollege_sys

**文档版本：** 


| 表名                  | 说明       |
| :---: | :---: |
| [activity](#activity) |  |
| [college](#college) |  |
| [equip](#equip) |  |
| [member](#member) |  |
| [news](#news) |  |
| [picnews](#picnews) |  |
| [sblog](#sblog) |  |
| [user](#user) | 用户表 |

**表名：** <a id="activity">activity</a>

**说明：** 

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | activity_id |   int   | 10 |   0    |    N     |  Y   |       |   |
|  2   | user_id |   int   | 10 |   0    |    Y     |  N   |   NULL    | 用户ID  |
|  3   | activity_title |   varchar   | 225 |   0    |    Y     |  N   |   NULL    |   |
|  4   | activity_content |   text   | 65535 |   0    |    Y     |  N   |   NULL    |   |
|  5   | activity_date |   date   | 10 |   0    |    Y     |  N   |   NULL    |   |
|  6   | activity_address |   varchar   | 255 |   0    |    Y     |  N   |   NULL    |   |
|  7   | activity_equip |   varchar   | 255 |   0    |    Y     |  N   |   NULL    |   |
|  8   | activity_money |   double   | 23 |   0    |    Y     |  N   |   NULL    |   |
|  9   | activity_type |   int   | 10 |   0    |    Y     |  N   |   1    | 1:社团活动2：校园活动  |
|  10   | activity_flag |   int   | 10 |   0    |    Y     |  N   |   1    | 1：待审批2：审批通过  |

**表名：** <a id="college">college</a>

**说明：** 

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | college_id |   int   | 10 |   0    |    N     |  Y   |       |   |
|  2   | college_name |   varchar   | 255 |   0    |    N     |  N   |       |   |
|  3   | college_type |   varchar   | 255 |   0    |    Y     |  N   |   NULL    |   |
|  4   | user_id |   int   | 10 |   0    |    Y     |  N   |   0    |   |
|  5   | create_date |   date   | 10 |   0    |    Y     |  N   |   NULL    | 创建时间  |
|  6   | college_persons |   int   | 10 |   0    |    Y     |  N   |   0    |   |
|  7   | college_money |   double   | 23 |   0    |    Y     |  N   |   0    |   |
|  8   | college_pic |   varchar   | 225 |   0    |    Y     |  N   |   NULL    |   |
|  9   | college_note |   text   | 65535 |   0    |    Y     |  N   |   NULL    |   |
|  10   | college_plan |   text   | 65535 |   0    |    Y     |  N   |   NULL    |   |
|  11   | college_flag |   int   | 10 |   0    |    Y     |  N   |   1    | 1：待审批2：审批通过  |

**表名：** <a id="equip">equip</a>

**说明：** 

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | equip_id |   int   | 10 |   0    |    N     |  Y   |       |   |
|  2   | equip_name |   varchar   | 225 |   0    |    Y     |  N   |   NULL    |   |
|  3   | equip_note |   text   | 65535 |   0    |    Y     |  N   |   NULL    |   |

**表名：** <a id="member">member</a>

**说明：** 

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | member_id |   int   | 10 |   0    |    N     |  Y   |       |   |
|  2   | college_id |   int   | 10 |   0    |    Y     |  N   |   NULL    |   |
|  3   | user_id |   int   | 10 |   0    |    Y     |  N   |   NULL    | 用户ID  |
|  4   | reg_date |   datetime   | 19 |   0    |    Y     |  N   |   NULL    | 注册时间  |
|  5   | member_reason |   varchar   | 255 |   0    |    Y     |  N   |   NULL    |   |
|  6   | member_hobby |   varchar   | 255 |   0    |    Y     |  N   |   NULL    |   |
|  7   | member_flag |   int   | 10 |   0    |    Y     |  N   |   1    | 1：待审批2：审批通过  |

**表名：** <a id="news">news</a>

**说明：** 

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | news_id |   int   | 10 |   0    |    N     |  Y   |       |   |
|  2   | user_id |   int   | 10 |   0    |    Y     |  N   |   NULL    | 用户ID  |
|  3   | news_title |   varchar   | 225 |   0    |    Y     |  N   |   NULL    | 新闻标题  |
|  4   | news_content |   text   | 65535 |   0    |    Y     |  N   |   NULL    | 新闻内容  |
|  5   | news_picture |   varchar   | 225 |   0    |    Y     |  N   |   NULL    |   |
|  6   | news_date |   datetime   | 19 |   0    |    Y     |  N   |   NULL    |   |
|  7   | news_type |   int   | 10 |   0    |    Y     |  N   |   1    | 1:社团新闻2：校园新闻  |
|  8   | news_flag |   int   | 10 |   0    |    Y     |  N   |   1    | 1：待审批2：审批通过  |

**表名：** <a id="picnews">picnews</a>

**说明：** 

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | picnews_id |   int   | 10 |   0    |    N     |  Y   |       |   |
|  2   | picnews_title |   varchar   | 225 |   0    |    Y     |  N   |   NULL    |   |
|  3   | picnews_picture |   varchar   | 225 |   0    |    Y     |  N   |   NULL    |   |
|  4   | picnews_content |   text   | 65535 |   0    |    Y     |  N   |   NULL    |   |
|  5   | picnews_admin |   varchar   | 255 |   0    |    Y     |  N   |   NULL    |   |
|  6   | picnews_date |   datetime   | 19 |   0    |    Y     |  N   |   NULL    |   |
|  7   | picnews_number |   int   | 10 |   0    |    Y     |  N   |   NULL    |   |

**表名：** <a id="sblog">sblog</a>

**说明：** 

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | sblog_id |   int   | 10 |   0    |    N     |  Y   |       |   |
|  2   | user_id |   int   | 10 |   0    |    Y     |  N   |   NULL    | 用户ID  |
|  3   | sblog_title |   varchar   | 225 |   0    |    Y     |  N   |   NULL    |   |
|  4   | sblog_content |   text   | 65535 |   0    |    Y     |  N   |   NULL    |   |
|  5   | sblog_date |   datetime   | 19 |   0    |    Y     |  N   |   NULL    |   |
|  6   | sblog_click |   int   | 10 |   0    |    Y     |  N   |   NULL    |   |
|  7   | sblog_pic |   varchar   | 225 |   0    |    Y     |  N   |   NULL    |   |
|  8   | sblog_flag |   int   | 10 |   0    |    Y     |  N   |   1    | 1：待审批2：审批通过  |

**表名：** <a id="user">user</a>

**说明：** 用户表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | user_id |   int   | 10 |   0    |    N     |  Y   |       |   |
|  2   | user_name |   varchar   | 255 |   0    |    N     |  N   |       | 用户名  |
|  3   | user_pass |   varchar   | 255 |   0    |    N     |  N   |       | 密码  |
|  4   | user_mail |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 邮箱  |
|  5   | nick_name |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 昵称  |
|  6   | REAL_NAME |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 真实名称  |
|  7   | user_sex |   int   | 10 |   0    |    Y     |  N   |   0    | 性别  |
|  8   | user_age |   int   | 10 |   0    |    Y     |  N   |   NULL    | 用户年龄  |
|  9   | user_dept |   varchar   | 255 |   0    |    Y     |  N   |   NULL    |   |
|  10   | reg_date |   datetime   | 19 |   0    |    Y     |  N   |   NULL    | 注册时间  |
|  11   | user_type |   int   | 10 |   0    |    Y     |  N   |   0    | 2：管理员1：注册用户  |

**运行不出来可以微信 javape 我的公众号：源码码头**
