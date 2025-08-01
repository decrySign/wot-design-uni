# Textarea 文本域

用于输入多行文本信息。

## 基本用法

可以通过 `v-model` 双向绑定输入框的值，通过 `placeholder` 设置占位提示文字。

```html
<wd-textarea v-model="value" placeholder="请填写评价" />
```

```typescript
const value = ref<string>('')
```

## 禁用

通过设置 `disabled` 属性，实现禁用文本域。

```html
<wd-textarea v-model="value" disabled></wd-textarea>
```

## 只读

通过设置 `readonly` 属性，实现文本域只读。

```html
<wd-textarea v-model="value" readonly></wd-textarea>
```

## 清空按钮

通过设置 `clearable` 属性实现清空按钮，设置`show-word-limit`与`maxlength`实现字数限制。

```html
<wd-textarea v-model="value" :maxlength="120" clearable show-word-limit />
```


## 有值且聚焦时展示清空按钮
设置 `clear-trigger` 属性，可以控制是否聚焦时才展示清空按钮。

:::warning 注意
支付宝小程序暂不支持 `clear-trigger` 属性，且某种情况下清空按钮无法点击，原因参考此[issue](https://github.com/ant-design/ant-design-mini/issues/1255)（希望可以早点解决，所以直接给蚂蚁的组件库提了个issue）。
:::


```html
<wd-textarea clear-trigger="focus" v-model="value14" :maxlength="120" clearable show-word-limit />
```

## 点击清除按钮时不自动聚焦

设置`focus-when-clear` 属性，可以控制点击清除按钮时是否自动聚焦。

```html
 <wd-textarea v-model="value" :focus-when-clear="false" :maxlength="120" clearable show-word-limit />
```


## 高度自适应

通过设置 `auto-height` 属性，实现高度自适应。

```html
<wd-textarea v-model="value" auto-height />
```

## 前置 icon

设置前置 icon `prefix-icon`，icon 为 [icon](/component/icon) 章节中的图标，如果没有你需要的图标，则使用 `prefix` 插槽进行自定义插入。

```html
<wd-textarea v-model="value" prefix-icon="dong"></wd-textarea>
```

## 设置 label 标题

设置 `label` 标题，可以和 `cell-group` 组合使用，形成 `cell` 展示类型。可以通过 `label-width` 设置标题宽度，默认为 '33%'。

```html
<wd-cell-group border>
  <wd-textarea label="基本用法" clearable v-model="value" placeholder="请输入..." />
</wd-cell-group>
```

## 必填样式

设置了 `label` 的情况下，设置 `required` 属性，展示必填样式。

```html
<wd-textarea v-model="value" placeholder="请输入..." label="必填" required></wd-textarea>
```

## 输入框大小

通过设置 `size` 修改输入框大小，将 `size` 设置为 'large' 时字号为 16px。

```html
<wd-textarea label="基本用法" size="large" v-model="value" placeholder="请输入..." />
```

## 错误状态

设置 `error` 属性，输入框的值显示为红色。

```html
<wd-textarea v-model="value" placeholder="请输入用户名" error />
```

## 垂直居中

当设置 `label` 标题时，默认为顶部居中，设置 `center` 属性可以使标题和输入框垂直居中。

```html
<wd-textarea label="基本用法" v-model="value" center />
```

## Attributes

| 参数                    | 说明                                                                                              | 类型              | 可选值                             | 默认值    | 最低版本 |
|-------------------------|---------------------------------------------------------------------------------------------------|-------------------|------------------------------------|-----------|----------|
| v-model                 | 绑定值                                                                                            | string / number    | -                                  | -         | -        |
| placeholder             | 占位文本                                                                                          | string            | -                                  | 请输入... | -        |
| placeholderStyle        | 原生属性，指定 placeholder 的样式                                                                 | string            | -                                  | -         | -        |
| placeholderClass        | 原生属性，指定 placeholder 的样式类                                                               | string            | -                                  | -         | -        |
| disabled                | 原生属性，禁用                                                                                    | boolean           | -                                  | false     | -        |
| maxlength               | 原生属性，最大输入长度，设置为 -1 时不限制最大长度                                                | number            | -                                  | -         | -        |
| auto-focus              | 原生属性，自动聚焦，拉起键盘                                                                      | boolean           | -                                  | false     | -        |
| focus                   | 原生属性，获取焦点                                                                                | boolean           | -                                  | false     | -        |
| auto-height             | 原生属性，是否自动增高（设置时 style.height 不生效）                                              | boolean           | -                                  | false     | -        |
| fixed                   | 在 position:fixed 区域时需要设置为 true                                                           | boolean           | -                                  | false     | -        |
| cursorSpacing           | 原生属性，指定光标与键盘的距离（取 textarea 底部距离和该值的最小值）                              | number            | -                                  | 0         | -        |
| cursor                  | 原生属性，指定 focus 时的光标位置                                                                 | number            | -                                  | -1        | -        |
| confirm-type            | 设置键盘右下角按钮的文字                                                                          | string            | `done`/`go`/`next`/`search`/`send` | -         | -        |
| confirm-hold            | 点击键盘右下角按钮时是否保持键盘不收起                                                            | boolean           | -                                  | false     | -        |
| show-confirm-bar        | 是否显示键盘上方"完成"栏                                                                          | boolean           | -                                  | true      | -        |
| selection-start         | 原生属性，光标起始位置（需与 selection-end 搭配使用）                                             | number            | -                                  | -1        | -        |
| selection-end           | 原生属性，光标结束位置（需与 selection-start 搭配使用）                                           | number            | -                                  | -1        | -        |
| adjust-position         | 原生属性，键盘弹起时是否自动上推页面                                                              | boolean           | -                                  | true      | -        |
| disable-default-padding | 原生属性，是否去掉 iOS 默认内边距                                                                 | boolean           | -                                  | false     | -        |
| hold-keyboard           | 原生属性，focus 时点击页面不收起键盘                                                              | boolean           | -                                  | false     | -        |
| show-password           | 显示为密码框                                                                                      | boolean           | -                                  | false     | -        |
| clearable               | 显示清空按钮                                                                                      | boolean           | -                                  | false     | -        |
| readonly                | 只读                                                                                              | boolean           | -                                  | false     | -        |
| prefix-icon             | 前置图标（使用 icon 组件类名）                                                                    | string            | -                                  | -         | -        |
| show-word-limit         | 显示字数限制（需设置 maxlength）                                                                  | boolean           | -                                  | false     | -        |
| label                   | 设置左侧标题                                                                                      | string            | -                                  | -         | -        |
| label-width             | 设置左侧标题宽度                                                                                  | string            | -                                  | 33%       | -        |
| size                    | 设置输入框大小                                                                                    | string            | -                                  | -         | -        |
| error                   | 设置输入框错误状态（红色标识）                                                                    | boolean           | -                                  | false     | -        |
| center                  | 有 label 时设置标题和输入框垂直居中（默认顶部居中）                                               | boolean           | -                                  | false     | -        |
| no-border               | 非 cell 类型下是否隐藏下划线                                                                      | boolean           | -                                  | false     | -        |
| required                | cell 类型下必填样式                                                                               | boolean           | -                                  | false     | -        |
| prop                    | 表单域 `model` 字段名（表单校验必填）                                                             | string            | -                                  | -         | -        |
| rules                   | 表单验证规则                                                                                      | FormItemRule[]    | -                                  | []        | -        |
| clearTrigger            | 显示清除图标的时机：always（输入框非空时展示）/ focus（聚焦且非空时展示）                         | InputClearTrigger | `focus`/`always`                   | `always`  | 1.3.7    |
| focusWhenClear          | 点击清除按钮时是否聚焦输入框                                                                      | boolean           | -                                  | true      | 1.3.7    |
| ignoreCompositionEvent  | 是否忽略文本合成系统事件处理（为 false 时触发 composition 相关事件，且在合成期间触发 input 事件） | boolean           | -                                  | true      | 1.3.11   |
| inputmode               | 输入数据类型提示                                                                                  | InputMode         | -                                  | text      | 1.5.0    |

### InputMode 可选值

>新增于 uni-app 3.6.16+ inputmode是html规范后期更新的内容。各家小程序还未支持此属性。

在符合条件的高版本webview里，uni-app的web和app-vue平台中可使用本属性，参见[inputmode](https://uniapp.dcloud.net.cn/component/input.html#inputmode)。

| 值      | 说明                                                                                                                 |
|---------|----------------------------------------------------------------------------------------------------------------------|
| none    | 无虚拟键盘。在应用程序或者站点需要实现自己的键盘输入控件时很有用。                                                   |
| text    | 使用用户本地区域设置的标准文本输入键盘。                                                                             |
| decimal | 小数输入键盘，包含数字和分隔符（通常是“ . ”或者“ , ”），设备可能也可能不显示减号键。                                 |
| numeric | 数字输入键盘，所需要的就是 0 到 9 的数字，设备可能也可能不显示减号键。                                               |
| tel     | 电话输入键盘，包含 0 到 9 的数字、星号（*）和井号（#）键。表单输入里面的电话输入通常应该使用 <input type="tel"> 。   |
| search  | 为搜索输入优化的虚拟键盘，比如，返回键可能被重新标记为“搜索”，也可能还有其他的优化。                                 |
| email   | 为邮件地址输入优化的虚拟键盘，通常包含"@"符号和其他优化。表单里面的邮件地址输入应该使用 <input type="email">。       |
| url     | 为网址输入优化的虚拟键盘，比如，“/”键会更加明显、历史记录访问等。表单里面的网址输入通常应该使用 <input type="url">。 |


### FormItemRule 数据结构

| 键名      | 说明                                                    | 类型                                  |
| --------- | ------------------------------------------------------- | ------------------------------------- |
| required  | 是否为必选字段                                          | `boolean`                             |
| message   | 错误提示文案                                            | `string`                              |
| validator | 通过函数进行校验，可以返回一个 `Promise` 来进行异步校验 | `(value, rule) => boolean \| Promise` |
| pattern   | 通过正则表达式进行校验，正则无法匹配表示校验不通过      | `RegExp`                              |

## Events

| 事件名称             | 说明                             | 参数                                         | 最低版本 |
| -------------------- | -------------------------------- | -------------------------------------------- | -------- |
| input                | 监听输入框 input 事件            | ` {value, cursor, keyCode}`                  | -        |
| focus                | 监听输入框 focus 事件            | ` { value, height }`, height 为键盘高度      | -        |
| blur                 | 监听输入框 blur 事件             | ` { value }`                                 | -        |
| clear                | 监听输入框清空按钮事件           | -                                            | -        |
| linechange           | 监听输入框行数变化               | ` { height: 0, heightRpx: 0, lineCount: 0 }` | -        |
| confirm              | 点击完成时， 触发 confirm 事件   | ` { value }`                                 | -        |
| keyboardheightchange | 键盘高度发生变化的时候触发此事件 | ` { height, duration }`                      | -        |
| clickprefixicon      | 点击前置图标时触发               | -                                            | -        |
| clicksuffixicon      | 点击后置图标时触发               | -                                            | -        |

## Slot

| name   | 说明         | 最低版本 |
| ------ | ------------ | -------- |
| label  | 左侧标题插槽 | -        |
| prefix | 前置插槽     | -        |

## 外部样式类

| 类名                            | 说明                        | 最低版本 |
| ------------------------------- | --------------------------- | -------- |
| custom-class                    | 根节点样式                  | -        |
| custom-textarea-container-class | textarea 容器外部自定义样式 | -        |
| custom-textarea-class           | textarea 外部自定义样式     | -        |
