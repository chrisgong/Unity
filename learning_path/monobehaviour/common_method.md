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

一个协程程序在执行过程中,可以在任意位置使用 yield 语句。yield 的返回值控制何时恢复协同程序向下执行。协同程序在对象自有帧执行过程中堪称优秀。协同程序在性能上没有更多的开销。StartCoroutine函数是立刻返回的, 但是yield可以延迟结果。直到协同程序执行完毕。

