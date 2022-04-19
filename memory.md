## C#namespace找不到定义
不打开U3D，怎么会帮你编译代码呢？不编译，怎么会有命名空间呢？

## 不要用New来创建继承于MonoBehaviour脚本的对象
https://www.cnblogs.com/hwx0000/p/14146852.html
如果不继承MoneBehaviour又想使用Instantiate，需要using static UnityEngine.Object;

## using static 用法
https://www.cnblogs.com/linianhui/p/csharp6_using-static.html

## onTriggerEnter没有反应
void OnCollisionEnter（Collision other）
- 需要双方都有Collider或者Rigidbody
- 双方如果有Rigidbody，那么不得勾选isKinematic

void OnTriggerEnter（Collider other）：
- 需要双方至少有一个Rigidbody
- 可以勾选isKinematic
- 双方必须勾选Collider组件上的isTrigger

## pathfinder
3D寻路很好用，根据地形动态生成可行走区域，但是不适合太精细的路径，例如炸弹人这种四四方方的


##炸弹人AI实现思路：

#应该写成先优先找到最近的可破坏方块或者玩家，碰撞就判断此处放炸弹是否有活命路径，有就放炸弹，无论放置结果，都走活命路径

活命路径：
- 遍历所有没有爆炸的炸弹，保存所有炸弹范围路径
- 遍历所有火焰，保存火焰路径
- 遍历所有可破坏方块
- 最后找玩家位置
算法使用广度搜索，炸弹人是十字交叉，可抽象化为图。