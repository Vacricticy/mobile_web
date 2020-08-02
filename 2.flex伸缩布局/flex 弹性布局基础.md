# flex 弹性布局

## flex 弹性布局原理

- 父盒子设置为 flex 布局后，子元素的浮动 float,clear,vertical-align 将失效。
- 父元素设置为 flex 布局后，子元素没有行内元素和块元素之分，都可以设置宽高。
- flex 容器与项目：父元素指定为 flex 布局，则父元素被称为容器，其子元素被称为项目。
- 主轴与侧轴：当 flex-direction 的方向改变以后，比如主轴方向改为垂直方向时，侧轴方向将会变成水平方向。

## 一.容器的六大属性

### 1.flex-direction 主轴方向

- 项目是按照主轴的方向排列的
- row 主轴为水平方向（默认值）
- column 主轴为垂直方向
- （了解）row-reverse
- （了解）column-reverse

### 2.justify-content 项目在‘主轴’上的对齐方式

- flex-start 左对齐（默认值）
- flex-end 右对齐
- center
- space-between 两侧对齐
- space-around 平均分配剩余空间，每个项目的间隔相等

### 3.flex-wrap 换行方式

- nowrap 不换行，超出时按比例缩小（默认）
- wrap 换行
- （了解）wrap-reverse

### 4.align-items ‘单行’项目在交叉轴（侧轴）对齐方式

- flex-start 自上而下
- flex-end 自下而上
- center 居中对齐
- stretch（默认值） 使用该属性时，子项目不能设置高度，或者可以设置为 auto，此时子元素将占满整个容器的高度。
- （了解）baseline 每个项目以文字的基线 baseline 对齐

### 5.align-content ‘多行’项目在侧轴的对齐方式

- 注意：单行的项目使用 align-content 是无效的，只能使用 align-items。多行是指存在换行的现象。
- flex-start 自上而下
- flex-end 自下而上
- center 居中对齐
- space-between 两侧对齐。
- space-around 平均分配剩余空间，每一行之间的间隔相等
- （了解）stretch 占满整个侧轴，自上而下平均分配空间。（默认值）

### 4.flex-flow 复合写法

- flex-direction 与 flex-wrap 的结合

## 二.单个项目的属性

### 1.order

- 控制项目的排列顺序，越小越靠前，默认值为 0，可以取负值

### 2.flex-grow 空间有剩余时，怎样撑满

- 默认值为 0，即不撑满剩余的空间
- 若只有一个元素的 flex-grow 值为 1，则该元素撑满该行剩余的空间
- 若有多个元素设置了 flex-grow 值，则这些元素按比例来分割剩下的空间
- 若每个元素都设置了 flex-grow 值，则所有元素均按比例来分割剩下的空间

### 3.flex-shrink 空间爆炸时，怎么压缩

- 默认为 1，当元素在整行撑不下时，若没有设置 flex-wrap 为 wrap,则所有元素会等比例缩小来排下所有元素
- 若 flex-shrink 为 0，表示该元素不采用默认的缩小方式，会按原大小来显示
- 若大于 1，则按该值进行压缩

### 4.flex-basis

- 该元素先占据固有空间，剩余空间留给其他元素分割，默认值 auto 为原元素的大小，可设置值为 px 或%型

### 5.flex 复合写法（一般采用这种形式）

- flex-grow flex-shrink flex-basis 的结合
  - 一般直接设置为 flex:1;这种形式。
  - 默认值为 0 1 auto;------不足时不撑满，超出时挤压，符合日常习惯。
  - auto 表示 1 1 auto ;-------不足时撑满，超出时挤压，符合自动优化。
  - none 表示 0 0 auto;---------不足时不撑满，超出时不挤压，佛系玩法，什么都不干，保持自身原来的模样。
- ♥ 实际应用中 flex 通过设置为 1 或者百分比。表示该元素所占的比分。

### 6.align-self

- 控制单个项目在侧轴的排列方式，可覆盖 align-items 属性。

## 三.应用

### 骰子布局

### 网格布局

- flex:0 0 10%

### 圣杯布局

- 头部 header,尾部 footer,导航 nav，主栏 main,副栏 aside

### 输入框的布局

### 悬挂式布局

- 图片位置左（右）侧固定，剩余部分写内容

### 固定的底栏

- 许可证

### 流式布局
