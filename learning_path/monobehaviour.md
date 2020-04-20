## 生命周期 {#一monobehaviour-的生命周期}

* Awake：当一个脚本被实例化时，Awake 被调用。
  * 可以在此完成成员变量的初始化。
* Start：仅在 Update 函数第一次被调用前调用。
  * 可以把一些需要依赖 Awake 的变量放在 Start 中初始化。



