# layui 使用手册

## table使用实例

### html：

```html
<table id="search-result" lay-filter="test"></table>
```

### js：

```js
layui.use(['table'],function(){
    var table = layui.table;
    table.render({
        id: 'demo'
        ,elem: '#search-result'//对应table的id值
        , url: '/user/waste_name_search' //数据接口
        , method: 'POST'//接口方法类型
        , where: {wasteName: 'x', cate: 0} //如果无需传递额外参数，可不加该参数
        , request: {
            pageName: 'pageCurrent' //页码的参数名称，默认：page
            ,limitName: 'pageSize' //每页数据量的参数名，默认：limit
        }
//        实际接口为/user/waste_name_search?wasteName=x&cate=0&pageCurrent=1&pageSize=10
        ,parseData: function(res) {	//返回的数据与对应类型连接
            return {
                "code": res.code,	//返回的res中的成功代号
                "msg": res.message,	//返回的res中的成功信息
                "count": res.data.total,	//res中的结果总数
                "data": res.data.records	//res中的结果数组
            }
        }
        , cols: [[ //表头
            {field: 'name', title: '样品名称', fixed: 'left', width: 200}
            , {field: 'mandarin_name', title: '拼音', width: 160}
            , {field: 'latin_name', title: '拉丁文', width: 200}
            , {field: 'cate', title: '种类', width: 120}
            , {field: 'id', title: 'id', width: 120}
        ]],
    });
)}
```

以上代码中如果向后端传输的为json数据（非组装在接口链接上的那种），需要添加

```js
,contentType: 'application/json'
```



### 下面为返回的res数据：

```json
{
    "code": "00000",
    "data": {
        "records": [
            {
                "id": 1,
                "name": "五味子",
                "mandarin_name": "wu wei zi",
                "latin_name": "chinensis",
                "cate": 1
            },
            {
                "id": 2,
                "name": "泽泻",
                "mandarin_name": "ze xie",
                "latin_name": "Alismatis Rhizoma",
                "cate": 2
            }
        ],
        "total": 2,
        "size": 30,
        "current": 1,
        "orders": [],
        "optimizeCountSql": true,
        "searchCount": true,
        "pages": 1
    }
}
```

