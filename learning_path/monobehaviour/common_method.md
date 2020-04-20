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





