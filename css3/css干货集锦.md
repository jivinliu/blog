# CCS干货集锦

## 遮罩效果

```css
.box {
    position: fixed;
    z-index: 100;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
    background: rgba(0,0,0,.5);
}
```

## 均分布局

### 旧的display:box方式

```css
div.box {
    display: -webkit-box;
    height: 300px;
}

.box div:nth-child(1) {
    -webkit-box-flex: 1;
    background: red;
}
.box div:nth-child(2) {
    -webkit-box-flex: 1;
    background: green;
}
.box div:nth-child(3) {
    -webkit-box-flex: 1;
    background: yellow;
}
```
### 新的display:flex方式
```css
.box {
    display: -webkit-flex;
    -webkit-flex-direction: column;
    height: 300px;
}
.box div:nth-child(1) {
    -webkit-flex: 1;
    background: red;
}
.box div:nth-child(2) {
    -webkit-flex: 1;
    background: green;
}
.box div:nth-child(3) {
    -webkit-flex: 1;
    background: yellow;
}
```

## 水平垂直居中

```css
.box {
    display: -webkit-box;
    -webkit-box-orient: vertical;
    -webkit-box-pack: center;
    -webkit-box-align: center;
}
```

## 不定宽的元素水平居中

### 方法一
```css
.box {
    position: absolute;
    left: 50%;
    transform: translateX(-50%);
}
```

### 方法二
```css
.box {
    position: absolute;
    width: 100%;
    display: -webkit-box;
    -webkit-box-pack: center;
}
```

## 匀速旋转

```css
.box {
    width: 100px;
    height: 100px;
    background: red;
    -webkit-animation: rotate 1s linear infinite;
}

@-webkit-keyframes rotate {
    0% {
        -webkit-transform: rotate(0)
    }

    100% {
        -webkit-transform: rotate(360deg)
    }
}
```