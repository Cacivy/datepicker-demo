<template>
  <div class="home">
    <Select v-model="type" placeholder="请选择">
      <Option
        v-for="item in Object.keys(dateTypes)"
        :key="item"
        :label="dateTypes[item]"
        :value="item">
      </Option>
    </Select>
    <DatePicker
      v-model="value"
      :type="type"
      :placeholder="`请选择${dateTypes[type]}`">
    </DatePicker>
  </div>
</template>

<script lang="ts">
import { Component, Vue, Watch } from 'vue-property-decorator';
import DatePicker from 'element-datepicker-modified';
import { Select, Option } from 'element-ui';
import 'element-ui/lib/theme-default/index.css';
// import 'element-datepicker-modified/src/scss/index.scss';

const dateTypes = {
  date: '日期',
  week: '周',
  month: '月',
  quarter: '季度',
  halfyear: '半年',
  year: '年',
};

@Component({
  components: {
    DatePicker,
    Select,
    Option,
  },
})
export default class Home extends Vue {
  protected dateTypes = dateTypes;
  protected type = 'week';
  protected value = '';

  @Watch('type')
  public log() {
    this.value = '';
    // console.log(this.type);
  }
}
</script>


<style lang="scss">
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
</style>
