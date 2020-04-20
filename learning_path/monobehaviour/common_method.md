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

