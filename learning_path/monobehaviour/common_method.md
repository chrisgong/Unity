# 常用方法

## 不可重写函数

* #### **Invoke**

funcation Invoke\(methodName: string, time: float\): void

在 time 秒之后，调用 methodName 方法

```C\#
public class example : MonoBehaviour {
    public Rigidbody projectile;

    void LaunchProjectile() {
        Rigidbody instance = Instantiate(projectile);
        instance.velocity = Random.insideUnitSphere * 5;
    }

    public void Awake() {
        Invoke("LaunchProjectile", 2);
    }
}
```

* #### InvokeRepeating

function InvokeRepeating \(methodName : string, time : float, repeatRate : float\) : void

从第一次调用开始,每隔repeatRate时间调用一次.

* #### CancelInvoke

function CancelInvoke \(\) : void

取消这个MonoBehaviour上的所有调用Invoke。

* #### IsInvoking

function IsInvoking \(methodName : string\) : bool

判断某指定函数是否在等候调用。

* #### StartCoroutine

function StartCoroutine \(routine : IEnumerator\) : Coroutine

开启一个协程程序

一个协程的执行可以在任何地方用yield语句来暂停，yield return的值决定了什么时候协程恢复执行。协程在对象自有帧执行过程中非常优秀，几乎没有任何性能开销。StartCoroutine函数是立刻返回的， 但是yield可以延迟结果，直到协同程序执行完毕。

* #### StopCoroutine / StopAllCoroutines

#### 

## 可重写函数：

* Update

当 MonoBehaviour 实例化完成之后，Update 在每一帧被调用。

* LateUpdate

LateUpdate 是在所有 Update 函数调用后被调用。这可用于调整脚本执行顺序。例如:当物体在Update里移动时，跟随物体的相机可以在LateUpdate里实现。

* FixedUpdate

处理 Rigidbody 时，需要用FixedUpdate代替Update。例如:给刚体加一个作用力时，你必须应用作用力在FixedUpdate里的固定帧，而不是Update中的帧。\(两者帧长不同\)

* Awake

Awake 用于在游戏开始之前初始化变量或游戏状态。在脚本整个生命周期内它仅被调用一次。Awake 在所有对象被初始化之后调用，所以你可以安全的与其他对象对话或用诸如 GameObject.FindWithTag 这样的函数搜索它们。每个游戏物体上的Awke以随机的顺序被调用。因此，你应该用Awake来设置脚本间的引用，并用Start来传递信息Awake总是在Start之前被调用。它不能用来执行协同程序。

C\#和Boo用户注意：Awake 不同于构造函数，物体被构造时并没有定义组件的序列化状态。Awake像构造函数一样只被调用一次。

* Start

Start在behaviour的生命周期中只被调用一次。它和 Awake 的不同是，Start 只在脚本实例被启用时调用。你可以按需调整延迟初始化代码。Awake 总是在Start之前执行。



