#业务类别管理
##1. 新增流程类别
###1.1 使用场景
用户在新增流程类别时
###1.2 请求url
    /back/bpmcategory/addBpmCategory
###1.3 请求方法

POST
###1.4 业务请求参数（JSON报文）
| 参数名        | 类型          | 必须  | 描述|
|:-|:-:|:-:|:-:|
| categoryName | String | 是 | 流程类别名称|
| categoryCode | String | 是 | 流程类别编号|
| parentId | Long | 是 | 父级id|
| sortNo | int | 否 | 排序编号，按照从小到大顺序排列|
| enabled | bool | 是| 启用标志，false禁用，true启用|
| createUser | String | 是 | 用户id|
| remark | String | 否 | 备注|
| tenantId | String | 是 |租户id|

###1.5 业务请求参数示例
	
	{
	"categoryName": "用来测试的分类哟",
	"categoryCode": "test",
	"parentId": 1,
	"remark": "测试使用描述",
	"enabled": true
    }
###1.6 业务响应参数（JSON报文的head部分）
| 参数名        | 类型          | 必须  | 描述|
|:-|:-:|:-:|:-:|
|errorCode|String|是|0为成功|
|errorMsg|String|是|错误信息
|timestamp|
|time|
|gtime|
|error|
|success|bool|是|success为成功|
|redirect|
###1.7 响应报文示例
	{
    "head": {
        "errorCode": "0",
        "errorMsg": "success",
        "timestamp": 1553759880837,
        "time": 31,
        "gtime": 0,
        "error": false,
        "success": true,
        "redirect": false
    	}
    }

----------
##2. 查询流程类别左侧整棵数数据
###2.1 使用场景
进入流程类别管理页面时，与进入流程管理页面时
###2.2 请求url
    /back/bpmcategory/queryCategoryTree
###2.3 请求方法

GET
###2.4 业务请求参数（JSON报文）
| 参数名        | 类型          | 必须  | 描述|
|:-|:-:|:-:|:-:|
|tenantId|Long|是|租户id|
###2.5 业务请求参数示例
	/back/bpmcategory/queryCategoryTree?tenantId=1
###2.6 业务响应参数（JSON报文的body部分）
| 参数名        | 类型          | 必须  | 描述|
|:-|:-:|:-:|:-:|
|categoryId|String|是|类别id|
|categoryCode|String|是|类别编号|
|categoryName|String|是|类别名称|
|parentId|Long|否|父类别id|
|sortNo|String|否|类别排序编号|
|leaf|String|否|是否为子节点|
|enabled|bool|是|启用标志，false禁用，true启用|
|deleted|bool|是|删除状态，false未删除，true已删除|
|createUser|String|否
|createDate|date|否
|updateUser|String|否
|updateDate|date|否
|remark|String|否
|tenantId|String|是
|children|List|否|为子集合数据信息，结构与本身相同|
###2.7 响应报文示例
	{
        "categoryId": 0,
        "categoryCode": null,
        "categoryName": "业务类别",
        "parentId": null,
        "sortNo": null,
        "leaf": null,
        "enabled": true,
        "deleted": false,
        "createUser": null,
        "createDate": null,
        "updateUser": null,
        "updateDate": null,
        "remark": null,
        "tenantId": 1,
        "children": [
            {
                "categoryId": 1,
                "categoryCode": "001",
                "categoryName": "工作流程5",
                "parentId": 0,
                "sortNo": null,
                "leaf": null,
                "enabled": true,
                "deleted": false,
                "createUser": "1",
                "createDate": "2019-01-15 16:31:53",
                "updateUser": "1",
                "updateDate": "2019-03-26 14:41:04",
                "remark": "工作流开发",
                "tenantId": 1,
                "children": [
                    {
                        "categoryId": 11,
                        "categoryCode": "011",
                        "categoryName": "开发工具",
                        "parentId": 1,
                        "sortNo": null,
                        "leaf": null,
                        "enabled": true,
                        "deleted": false,
                        "createUser": "1",
                        "createDate": "2019-01-15 16:25:56",
                        "updateUser": "1",
                        "updateDate": "2019-01-15 16:26:00",
                        "remark": "开发工具",
                        "tenantId": 1,
                        "children": []
                    },
                    {
                        "categoryId": 18,
                        "categoryCode": "018",
                        "categoryName": "add测试",
                        "parentId": 1,
                        "sortNo": null,
                        "leaf": null,
                        "enabled": true,
                        "deleted": false,
                        "createUser": null,
                        "createDate": "2019-03-26 14:56:21",
                        "updateUser": null,
                        "updateDate": "2019-03-26 14:56:21",
                        "remark": "1213",
                        "tenantId": 1,
                        "children": []
                    },
                    {
                        "categoryId": 19,
                        "categoryCode": "019",
                        "categoryName": "add测试",
                        "parentId": 1,
                        "sortNo": null,
                        "leaf": null,
                        "enabled": true,
                        "deleted": false,
                        "createUser": null,
                        "createDate": "2019-03-26 14:59:11",
                        "updateUser": null,
                        "updateDate": "2019-03-26 14:59:11",
                        "remark": "1213",
                        "tenantId": 1,
                        "children": []
                    },
                    {
                        "categoryId": 20,
                        "categoryCode": "20",
                        "categoryName": "add测试1",
                        "parentId": 1,
                        "sortNo": null,
                        "leaf": null,
                        "enabled": true,
                        "deleted": false,
                        "createUser": null,
                        "createDate": "2019-03-26 15:26:54",
                        "updateUser": null,
                        "updateDate": "2019-03-26 15:26:54",
                        "remark": "12",
                        "tenantId": 1,
                        "children": []
                    },
                    {
                        "categoryId": 295949590397292545,
                        "categoryCode": "test",
                        "categoryName": "用来测试的分类1哟",
                        "parentId": 1,
                        "sortNo": null,
                        "leaf": null,
                        "enabled": true,
                        "deleted": false,
                        "createUser": "1",
                        "createDate": "2019-03-28 15:58:01",
                        "updateUser": null,
                        "updateDate": "2019-03-28 15:58:01",
                        "remark": "测试使用描述",
                        "tenantId": 1,
                        "children": []
                    }
                ]
            },
            {
                "categoryId": 2,
                "categoryCode": "002",
                "categoryName": "信息监控",
                "parentId": 0,
                "sortNo": null,
                "leaf": null,
                "enabled": true,
                "deleted": false,
                "createUser": "1",
                "createDate": "2019-01-15 16:35:14",
                "updateUser": "1",
                "updateDate": "2019-01-15 16:35:22",
                "remark": "信息监控",
                "tenantId": 1,
                "children": [
                    {
                        "categoryId": 8,
                        "categoryCode": "008",
                        "categoryName": "价格更新监控",
                        "parentId": 2,
                        "sortNo": null,
                        "leaf": null,
                        "enabled": true,
                        "deleted": false,
                        "createUser": "1",
                        "createDate": "2019-01-15 16:21:38",
                        "updateUser": "1",
                        "updateDate": "2019-01-15 16:21:47",
                        "remark": "价格更新监控",
                        "tenantId": 1,
                        "children": []
                    }
                ]
            },
            {
                "categoryId": 3,
                "categoryCode": "003",
                "categoryName": "工作流平台",
                "parentId": 0,
                "sortNo": null,
                "leaf": null,
                "enabled": true,
                "deleted": false,
                "createUser": "1",
                "createDate": "2019-01-15 16:19:56",
                "updateUser": "1",
                "updateDate": "2019-01-15 16:20:05",
                "remark": "工作流平台",
                "tenantId": 1,
                "children": [
                    {
                        "categoryId": 16,
                        "categoryCode": "016",
                        "categoryName": "业务保障测试",
                        "parentId": 3,
                        "sortNo": null,
                        "leaf": null,
                        "enabled": true,
                        "deleted": false,
                        "createUser": "1",
                        "createDate": "2019-01-15 16:36:27",
                        "updateUser": "1",
                        "updateDate": "2019-01-15 16:36:31",
                        "remark": "业务保障测试",
                        "tenantId": 1,
                        "children": []
                    }
                ]
            },
            {
                "categoryId": 4,
                "categoryCode": "004",
                "categoryName": "业务保障平台",
                "parentId": 0,
                "sortNo": null,
                "leaf": null,
                "enabled": true,
                "deleted": false,
                "createUser": "1",
                "createDate": "2019-01-15 16:29:40",
                "updateUser": "1",
                "updateDate": "2019-01-15 16:29:45",
                "remark": "业务保障平台",
                "tenantId": 1,
                "children": [
                    {
                        "categoryId": 13,
                        "categoryCode": "013",
                        "categoryName": "问题集工单",
                        "parentId": 4,
                        "sortNo": null,
                        "leaf": null,
                        "enabled": true,
                        "deleted": false,
                        "createUser": "1",
                        "createDate": "2019-01-15 16:28:18",
                        "updateUser": "1",
                        "updateDate": "2019-01-15 16:28:23",
                        "remark": "问题集工单",
                        "tenantId": 1,
                        "children": []
                    }
                ]
            },
            {
                "categoryId": 5,
                "categoryCode": "005",
                "categoryName": "开发平台",
                "parentId": 0,
                "sortNo": null,
                "leaf": null,
                "enabled": true,
                "deleted": false,
                "createUser": "1",
                "createDate": "2019-01-15 16:37:27",
                "updateUser": "1",
                "updateDate": "2019-01-15 16:37:30",
                "remark": "开发平台",
                "tenantId": 1,
                "children": [
                    {
                        "categoryId": 15,
                        "categoryCode": "015",
                        "categoryName": "演示流程",
                        "parentId": 5,
                        "sortNo": null,
                        "leaf": null,
                        "enabled": true,
                        "deleted": false,
                        "createUser": "1",
                        "createDate": "2019-01-15 16:33:04",
                        "updateUser": "1",
                        "updateDate": "2019-01-15 16:33:09",
                        "remark": "演示流程",
                        "tenantId": 1,
                        "children": []
                    }
                ]
            },
            {
                "categoryId": 12,
                "categoryCode": "012",
                "categoryName": "工作流开发2",
                "parentId": 0,
                "sortNo": null,
                "leaf": null,
                "enabled": true,
                "deleted": false,
                "createUser": "1",
                "createDate": "2019-01-15 16:27:14",
                "updateUser": "1",
                "updateDate": "2019-01-15 16:27:19",
                "remark": "工作流开发",
                "tenantId": 1,
                "children": []
            }
        ]
    }

----------
##3. 查询流程类别列表数据
###3.1 使用场景
用户在管理流程类别时查询
###3.2 请求url
    /back/bpmcategory/queryBySearchCondition
###3.3 请求方法
GET
###3.4 业务请求参数（JSON报文）
| 参数名        | 类型          | 必须  | 描述|
|:-|:-:|:-:|:-:|
| categoryId | String | 是 | 流程类别id|
| inputParam | String | 否 | 关键字搜索内容|
| pageIndex | int | 是 | 页编号|
| pageSize | int | 是 | 页行数|
| tenantId | String | 是 |租户id|

###3.5 业务请求参数示例
	
	/back/bpmcategory/queryBySearchCondition?categoryId=1&pageIndex=1&pageSize=1
###3.6 业务响应参数（JSON报文的data部分）
| 参数名        | 类型          | 必须  | 描述|
|:-|:-:|:-:|:-:|
|categoryId|String|是|类别id|
|categoryCode|String|是|类别编号|
|categoryName|String|是|类别名称|
|parentId|Long|否|父类别id|
|sortNo|String|否|类别排序编号|
|enabled|bool|是|启用标志，false禁用，true启用|
|deleted|bool|是|删除状态，false未删除，true已删除|
|createUser|String|否
|createDate|date|否
|updateUser|String|否
|updateDate|date|否
|remark|String|否
|tenantId|String|是
|pname|String|否|父类型名称|
###1.7 响应报文示例
	"data": [
            {
                "categoryId": 11,
                "categoryName": "开发工具",
                "categoryCode": "011",
                "parentId": 1,
                "enabled": true,
                "deleted": false,
                "tenantId": 1,
                "sortNo": null,
                "createDate": "2019-01-15 16:25:56",
                "updateDate": "2019-01-15 16:26:00",
                "createUser": "1",
                "updateUser": "1",
                "remark": "开发工具",
                "pname": "工作流程5"
            }
        ]

----------
##4. 更新流程类别信息
###4.1 使用场景
用户在管理流程类别时更新
###4.2 请求url
    /back/bpmcategory/updateBpmCategoryById
###4.3 请求方法
POST
###4.4 业务请求参数（JSON报文）
| 参数名        | 类型          | 必须  | 描述|
|:-|:-:|:-:|:-:|
|categoryId|String|是|类别id|
|categoryCode|String|是|类别编号|
|categoryName|String|是|类别名称|
|sortNo|String|否|类别排序编号|
|updateUser|String|否
###4.5 业务请求参数示例
	{"categoryId":1,"categoryName":"工作流程7"}
	
###4.6 业务响应参数（JSON报文的head部分）
| 参数名        | 类型          | 必须  | 描述|
|:-|:-:|:-:|:-:|
|errorCode|String|是|0为成功|
|errorMsg|String|是|错误信息
|timestamp|
|time|
|gtime|
|error|
|success|bool|是|success为成功|
|redirect|
###4.7 响应报文示例
	{
    "head": {
        "errorCode": "0",
        "errorMsg": "success",
        "timestamp": 1553759880837,
        "time": 31,
        "gtime": 0,
        "error": false,
        "success": true,
        "redirect": false
    	}
    }

----------
##5. 删除流程类别
###5.1 使用场景
用户在管理流程类别时删除
###5.2 请求url
    /back/bpmcategory/deleteByCategoryId
###5.3 请求方法
POST
###5.4 业务请求参数（JSON报文）
| 参数名        | 类型          | 必须  | 描述|
|:-|:-:|:-:|:-:|
|categoryId|String|是|类别id|
###5.5 业务请求参数示例
	{"categoryId":1}
###5.6 业务响应参数（JSON报文的head部分）
| 参数名        | 类型          | 必须  | 描述|
|:-|:-:|:-:|:-:|
|errorCode|String|是|0为成功|
|errorMsg|String|是|错误信息
|timestamp|
|time|
|gtime|
|error|
|success|bool|是|success为成功|
|redirect|
###5.7 响应报文示例
	{
    "head": {
        "errorCode": "0",
        "errorMsg": "success",
        "timestamp": 1553759880837,
        "time": 31,
        "gtime": 0,
        "error": false,
        "success": true,
        "redirect": false
    	}
    }
