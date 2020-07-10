# 知识点

## 实现功能

利用此法可以实现监听任意元素resize

## 原理解析

1. [resize mdn](https://developer.mozilla.org/en-US/docs/Web/API/Window/resize_event)

    mdn原话如下：大概意思就是window绑定resize才能响应到resize的回传事件，而window可以由document.defaultView得到
    
    ```
    In some earlier browsers it was possible to register resize event handlers on any HTML element. It is still possible to set onresize attributes or use addEventListener() to set a handler on any element. However, resize events are only fired on the window object (i.e. returned by document.defaultView). Only handlers registered on the window object will receive resize events.
    ```

2. [document.defaultView](https://developer.mozilla.org/en-US/docs/Web/API/Document/defaultView)

    mdn原话如下：大概意思就是说返回当前document关联的window
    
    ```
    In browsers, document.defaultView returns the window object associated with a document, or null if none is available.
    ```

3. [Object](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/object)

    这里指的是object标签，文档里也没啥特殊的。
    
4. [contentDocument](https://developer.mozilla.org/zh-CN/docs/Web/API/HTMLIFrameElement/contentDocument)
    
    mdn原话如下：大概意思就是说iframe和父元素是同源，返回当前iframe的document，这里可以连接到第二步document.defaultView
    
    ```
    If the iframe and the iframe's parent document are Same Origin, returns a Document (that is, the active document in the inline frame's nested browsing context), else returns null.
    ```

5. document.createElement('object').contentDocument.defaultView.addEventListener('resize', func)
    
    现在还不清楚为什么，但是object标签（在这里可以相当于iframe）获取到contentDocument（因为第四步已经说了iframe的contentDocument），这样就可以监听到resize。

6. 结束

    此时把object元素放到想要监听的任意元素上（object元素的父元素），width和height设置为100%，
    
    这样当任意元素（即父元素）width和height变化时，object元素也会变化，
    
    而object元素可以监听到resize，这样就相当于父元素也监听到resize
