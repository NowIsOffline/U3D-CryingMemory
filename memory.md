# C#namespace找不到定义
不打开U3D，怎么会帮你编译代码呢？不编译，怎么会有命名空间呢？

#不要用New来创建继承于MonoBehaviour脚本的对象
https://www.cnblogs.com/hwx0000/p/14146852.html
如果不继承MoneBehaviour又想使用Instantiate，需要using static UnityEngine.Object;

#using static 用法
https://www.cnblogs.com/linianhui/p/csharp6_using-static.html

#onTriggerEnter没有反应
void OnCollisionEnter（Collision other）
- 需要双方都有Collider或者Rigidbody
- 双方如果有Rigidbody，那么不得勾选isKinematic

void OnTriggerEnter（Collider other）：
- 需要双方至少有一个Rigidbody
- 可以勾选isKinematic
- 双方必须勾选Collider组件上的isTrigger
