# Flex布局

## Flex是什么

Flex 是Flexible Box的缩写，意为弹性布局。

```css
.box{
display:flex;
}

.box{
display:inline-flex;
}
```

Webkit内核浏览器必须加上-webkit前缀
```css
.box{
display:-webkit-flex;/*safari*/
display:flex;
}
```

**注意：**设置为Flex布局以后，子元素的`float`、`clear`和`vertical-align`属性会失效。

## 基本概念

采用Flex布局的元素叫做Flex容器（flex container），简称“容器”；它所有的子元素自动成为容器成员，叫做Flex项目（flex item），简称“项目”。

![flex容器](./assets/flex容器.png)

容器默认有两个轴：水平的主轴（main axis）和垂直的交叉轴（cross axis）。

主轴的起点叫`main start`，结束点叫`main end`。

交叉轴的起点叫`cross start`，结束点叫`cross end`。

项目默认沿着主轴排列，占据的主轴空间叫`main size`，占据的交叉轴空间叫`cross size`。

## 容器的属性

容器有以下6个属性：

```css
flex-direction
flex-wrap
flex-flow
justify-content
align-items
align-content
```

### flex-direction

flex-direction属性决定了项目在主轴上的排列方向。

```css
.box{
    flex-direction: row|row-reverse|column|column-reverse;
}
/*
row（默认值）：从左往右水平排列
row-reverse:从右往左水平排列
column:从上往下垂直排列
column-reverse:从下往上垂直排列
*/
```

![flex-direction](./assets/flex-direction.png)

### flex-wrap

flex-wrap属性定义在一条线上排列不下时如何换行。

```css
.box{
    flex-wrap:nowrap|wrap|wrap-reverse;
}
/*
nowrap(默认)：不换行
wrap：换行，第一行在上面
wrap-reverse：换行，第一行在下面
*/
```

### flex-flow

flex-flow属性是flex-direction和flex-wrap的简写，默认值为：`row nowrap`。

```css
.box{
    flex-flow: <flex-direction> || <flex-wrap>;
}
```

### justify-content

justify-content属性定义了项目在主轴上的对齐方式。

```css
.box{
    justify-content:flex-start|flex-end|center|space-between|space-around;
}
/*
flex-start(默认):左对齐
flex-end：右对齐
center：居中
space-between：两端对齐
space-around：每个项目两侧间隔相等
*/
```





![justify-content](./assets/justify-content.png)

### align-items

align-items属性定义项目在交叉轴上的对齐方式。

```css
.box{
    align-items:flex-start|flex-end|center|baseline|stretch;
}
/*
flex-start:交叉轴的起点对齐
flex-end:交叉轴的终点对齐
center：交叉轴的中心对齐
baseline：项目第一行的文字基线对齐
stretch（默认值）：如果项目未设置高度或者设为auto，将占满整个容器的高度
*/
```

![align-items](./assets/align-items.png)

### align-content

`align-content`属性定义了多根轴线的对齐方式。如果项目只有一根轴线，该属性不起作用。

```css
.box{
    align-content:flex-start|flex-end|center|space-between|space-around|stretch;
}
```

![align-content](./assets/align-content.png)

## 项目的属性

有6个属性可以设置在项目上：

```css
order:定义项目的排列顺序，数值越小越靠前。默认为0。
flex-grow：定义项目的放大比例，默认为0，即如果存在剩余空间也不放大。
flex-shrink：定义项目的缩小比例，默认为1，即空间不足时，项目缩小。
flex-basis：定义项目的主轴占据空间，默认为auto。
flex：是flex-grow、flex-shrink和flex-basis的简写，默认为0 1 auto。
align-self：允许单个项目有与其他项目不一样的对齐方式，可覆盖align-items属性。
```



