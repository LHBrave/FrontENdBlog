## 一：DOM事件级别
#### 1.DOM0级事件
```
bn.onClick = function();
```
**DOM0的事件绑定方法是在冒泡阶段（或者目标阶段）执行的**

#### 2.DOM2级事件
```
bn.adEventListener(event-name,callback,useCapture)
```
+ event-name: 事件名称
+ callback: 回调函数，当事件被触发时，会传入一个参数为当前的事件对象；
+ useCapture：指定事件触发的阶段，默认是false，表示事件句柄在冒泡阶段执行；

#### 3.DOM3级事件
在DOM2级事件的基础上添加了更多的事件类型，比如鼠标事件、滚动事件、焦点事件、文本事件、键盘事件等等；

## 事件模型和事件流
DOM事件模型分为冒泡和捕获，事件发生后，会在子元素和父元素之间传播，传播过程分为三个阶段：
+ 捕获阶段：事件从window对象自上而下向目标节点传播的阶段
+ 目标阶段： 事件处于目标节点的阶段；
+ 冒泡阶段： 事件从目标节点自上而下向window对象传播的阶段；

## 事件代理
由于在冒泡阶段事件会向上传播到父节点，印次可以把子元素的事件处理函数定义在父元素上，由父节点的监听函数统一处理多个子元素的事件；
** 优点： **
  + 可以减少内存消耗
  + 可以动态绑定事件
  
## Event对象
1. event.preventDefault
  阻止默认事件的触发
2. event.stopPropagation()
    阻止事件冒泡到父元素
3. event.stopImmediatePropagation()
    既能阻止事件冒泡到父元素，又能阻止元素同类型事件的其它监听器被触发；
4. event.target 和 event.currentTarget
    event.target指的是事件的真正发出者，event.currentTarget指的是事件的监听者；

