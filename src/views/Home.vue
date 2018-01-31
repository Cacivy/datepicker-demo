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
      :style="{widht: '500px'}"
      ref="datePicker"
      :picker-options="pickerOptions"
      :placeholder="`请选择${dateTypes[type]}`">
    </DatePicker>
  </div>
</template>

<script lang="ts">
import { Component, Vue, Watch } from 'vue-property-decorator';
import DatePicker from 'element-datepicker-modified';
import { Select, Option } from 'element-ui';
import 'element-datepicker-modified/dist/static/css/index.css';
import 'element-ui/lib/theme-default/index.css';

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
  protected pickerOptions = {
    firstDayOfWeek: 3,
  };

  @Watch('type')
  public log() {
    this.value = '';
    console.log('type', this.type);
  }

  @Watch('value')
  public public() {
    this.$nextTick().then(() => {
      console.log('value', this.value);
      console.log('displayValue', (this.$refs.datePicker as any).displayValue);
    });
  }
}
</script>