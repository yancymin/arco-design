---
order: 5
title:
  zh-CN: 带时间的日期选择
  en-US: DatePicker showTime
---

## zh-CN

使用 `showTime` 可以使用带时间的日期选择。

## en-US

Use `showTime` to select a date with time.

```js
import { DatePicker } from '@arco-design/web-react';
import dayjs from 'dayjs';

const { RangePicker } = DatePicker;
const style = { width: 220, margin: '0 24px 24px 0' };

function onSelect(dateString, date) {
  console.log('onSelect', dateString, date);
}

function onChange(dateString, date) {
  console.log('onChange: ', dateString, date);
}

function onOk(dateString, date) {
  console.log('onOk: ', dateString, date);
}

ReactDOM.render(
  <div>
    <DatePicker
      style={style}
      showTime={{ defaultValue: dayjs('09:09:06', 'HH:mm:ss') }}
      format="YYYY-MM-DD HH:mm:ss"
      onChange={onChange}
      onSelect={onSelect}
      onOk={onOk}
    />
    <DatePicker
      style={style}
      showTime
      format="YYYY-MM-DD hh:mm A"
      onChange={onChange}
      onSelect={onSelect}
      onOk={onOk}
    />
    <RangePicker
      style={{ ...style, width: 360 }}
      showTime={{ defaultValue: [dayjs('00:00:00', 'HH:mm:ss'), dayjs('09:09:06', 'HH:mm:ss')] }}
      format="YYYY-MM-DD HH:mm"
      onChange={onChange}
      onSelect={onSelect}
      onOk={onOk}
    />
  </div>,
  CONTAINER
);
```
