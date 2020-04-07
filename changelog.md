# 更新日志

## v0.3b

- ARCamera 支持渲染准星 (Reticle)。 准星在独立层级渲染。 当ARCamera开启准星渲染的时候, 用户可以使用头部瞄准的方式与虚拟对象通过 Unity Event System交互。
- ARCamera 支持 DebugView, 在 DebugView 开启的时候， 头部跟踪信息会以文字的方式显示在用户眼前。
- Dynamic Target 和 GroundPlane : 支持DebugView， 更方便的展示可跟踪物体的跟踪信息。
- Controller支持通过设备的 Serial Number 读取通过Launcher下载的跟踪标定文件。
- Trackable Identity : 重新设计了 Trackable ID 管理界面，更易理解。
- 新的Class : RxInput. RxInput 提供所有的和按键输入相关的可编程 API， 包括 Controller 和 RhinoX 侧边按键。
- 新的组件 : RxButtonEventTrigger , 提供在 Editor 上配置按键事件的Editor UI接口事件
- 新增全局配置文件 : RhinoXGlobalSetting , 此对象必须放置在Resources目录下。 全部配置对象用于配置全局变量和属性。
 
 
 
 ## v0.4b
 - 重构了 RxController 类，另交互API接口更方便使用。
 - 更新了 Low level tracking 库，VPU固件跟踪更稳定。
 - 控制跟踪支持前向预测。
 - 优化了双目渲染效果， 用户眼部更舒适。
 
 
 ## v0.5b
 
- 优化了控制器追踪效果。推荐使用控制器的陀螺仪控制旋转，从Edit/ProjectSettings/RhinoX Setting 中设置 Controller Fusion Mode 为 Semi
- GroundPlane的定位精确度提高，现在GroundPlane定位之后， 地面的中心点就在Beacon的物理中心点。
- RXInputModule ： 现在支持任意控制器按键触发UI事件。
- Demo : 添加了 GrabableDemo ， 标准化抓取操作。 见 Grabable.cs.
- RXButtonEventTrigger : 除了支持UnityEvent外，添加了 C# 事件支持 : OnRhinoXButtonEvent 。 
```bash
        public delegate void RXButtonEventDelegate(RhinoXButton button, EventTriggerType eventType);

        /// <summary>
        /// API event : on RhinoX button event of event trigger type.
        /// </summary>
        public event RXButtonEventDelegate OnRhinoXButtonEvent;
````