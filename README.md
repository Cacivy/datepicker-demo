# DatePicker demo

> 该示例项目依赖于element-ui(1.4.13)、vue-cli构建

### Develop

```
// nodejs v8.0+

yarn

yarn serve

// http://localhost:8080

```

### Usage

[Component API](http://element.eleme.io/1.4/#/zh-CN/component/date-picker)

```
npm i element-ui@1.4.13 --save
npm i https://github.com/wumengqiang/element-datepicker-modified.git --save

// Component ./src/views/Home.vue
import DatePicker from 'element-datepicker-modified'; // 修改后的DatePicker
import 'element-ui/lib/theme-default/index.css'; // 引入默认样式

// Template

<DatePicker
  v-model="value"
  :type="type"
  placeholder="请选择">
</DatePicker>

// Style 可自定义

.el-quarter-table,
.el-halfyear-table {
  td {
    text-align: center;
    padding: 20px 3px;
    cursor: pointer;

    .cell {
      width: 48px;
      height: 32px;
      display: block;
      line-height: 32px;
      color: #48576a;
    }

    &.current:not(.disabled) {
      .cell {
        background-color: #20a0ff !important;
        color: #fff;
      }
    }
  }
}
```

### Thanks

[element-datepicker-modified](https://github.com/wumengqiang/element-datepicker-modified.git)