## 生命周期 {#一monobehaviour-的生命周期}

* `Awake`：当一个脚本被实例化时，Awake 被调用。
  * 可以在此完成成员变量的初始化。
* `Start`：仅在 Update 函数第一次被调用前调用。
  * 可以把一些需要依赖 Awake 的变量放在 Start 中初始化。
* `Update`：当开始播放游戏帧时（此时 GameObject 实例化完毕）， Update 在`每一帧`被调用。
* `LateUpdate`：在所有 Update 函数后被调用。
* `FixedUpdate`：当 MonoBehaviour 启用时，其 FixedUpdate 在`每一固定帧`被调用。
* `OnEnable`：当对象变为可用或激活状态时此函数被调用。
* `OnDisable`：当对象变为不可用或非激活状态时此函数被调用。
* `OnDestroy`：当 MonoBehavior 将被销毁时，这个函数被调用。

![](https://tva1.sinaimg.cn/large/007S8ZIlly1ge098uuixej30fr0lc0ts.jpg)

