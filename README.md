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
npm i https://github.com/Cacivy/element-datepicker-modified.git --save

// Component ./src/views/Home.vue
import DatePicker from 'element-datepicker-modified'; // 修改后的DatePicker并根据需求引入style
import 'element-datepicker-modified/dist/static/css/index.css'

// Template

<DatePicker
  v-model="value"
  :type="type"
  placeholder="请选择">
</DatePicker>
```

### Thanks

[element-datepicker-modified](https://github.com/wumengqiang/element-datepicker-modified.git)