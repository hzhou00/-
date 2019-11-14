
# CSS 强制不换行，溢出隐藏显示省略号
```
    text-overflow: ellipsis;
    white-space:nowrap;
    overflow:hidden;
 ```
 ```
    overflow: hidden;
    text-overflow: ellipsis;
    display: -webkit-box;
    -webkit-line-clamp: 1;
    line-clamp: 3;
    -webkit-box-orient: vertical; 
```
