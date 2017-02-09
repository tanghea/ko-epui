### ko-epui

#### 工程师正在抓紧编写文档中

### 运行demo

下载本工程

```
npm install

npm run dev

//访问 http://localhost:8084
```

# 目录
- 容器组件
--
- kero组件

# 1.容器组件

## 1.1 box
页面外层容器会默认添加一些padding和margin
``` css
  .box{
    margin: 0 15px 25px 15px;
    padding: 12px 10px 20px;
  }
```

``` html
<box>
  <div>里面是正常的嵌套</div>
  <input type=text/>
</box>
```

## 1.2 box-content
内容区域
```

```

## 1.3 u-tree
需要依赖uui下的css/tree.min.css 和 js/u-tree.min.js
```
<u-tree class="form-control" params='data:{model:$root.treemodel,treeSetting:$root.treeOption},
  umeta:{"id":"tree","data":"model","idField":"id","pidField":"pid","nameField":"title","setting":"treeSetting"}'>
</u-tree>
viewmodel:{
  treemodel: new window.u.DataTable({
    meta: {
      'id': {
        'value': ''
      },
      'pid': {
        'value': ''
      },
      'title': {
        'value': ''
      }
    }
  }),
  treeOption: {
    callback: {
      beforeClick: function (treeId, treeNode, clickFlag) {
        console.log('before click')
        console.log(treeId)
        console.log(treeNode)
        console.log(clickFlag)
      },
      onClick: function (event, treeId, treeNode, clickFlag) {
        console.log('on click')
        console.log(event)
        console.log(treeId)
        console.log(treeNode)
        console.log(clickFlag)
      }
    }
  }
}
```