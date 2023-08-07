```css
// 清除浮动
.clear:after {
    display: block || table;
    clear: both;
    content: '';
}
```

```css
// loading...
// html: <dot>...</dot>
dot {
    display: inline-block; 
    height: 1em;
    line-height: 1;
    text-align: left;
    vertical-align: -.25em;
    overflow: hidden;
}
dot::before {
    display: block;
    content: '...\A..\A.';
    white-space: pre-wrap;
    animation: dot 3s infinite step-start both;
}
@keyframes dot {
    33% { transform: translateY(-2em); }
    66% { transform: translateY(-1em); }
}
```

```javascript
// 切换样式：
dom.classList.toggle('colspan')
```

```css
// 利用margin-left: auto 实现dom右对齐
```

