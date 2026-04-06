# unity-learning-log
2026.4.6
【Unity学习进度】

当前阶段：
已完成：基础移动（Update + Translate + deltaTime）

已掌握：
- Update / FixedUpdate 区别:
  Update() → 每一帧执行一次
  FixedUpdate() → 固定时间执行（物理用）0.02秒一次
  
- Time.deltaTime：
  通过Time.deltaTime时间增量消除帧率对移动的影响 
  上一帧到这一帧用了多少秒（1秒/每秒帧数）
  
- Vector2 / Vector3：
  Vector = 位置 / 方向 / 速度 的容器
  用途：移动，速度，位置

- transform / Translate：
  transform = 物体在世界中的状态
  position:在世界空间坐标中的位置
  translate:让物体“移动一小段距离”
  
- MonoBehaviour：
  让脚本能挂在物体上并被Unity执行
  
- API 概念
  API 就像“工具箱”
  API = unity帮我写好的功能，直接拿来用

wsad控制2D小方块移动代码：

```csharp
using UnityEngine;//引入unity工具库

public class PlayerMove : MonoBehaviour //创建playermove类，继承monobehaviour类
{
    public float speed = 5f; //定义速度为浮点数5
    
    void Update() //每一帧都会运行一次
    {
        float moveX = Input.GetAxis("Horizontal"); //定义x方向移动变量move，通过a，d改变movex的值
        float moveY = Input.GetAxis("Vertical");  //同上类似
        transform.Translate(new Vector3(moveX, moveY, 0) * speed * Time.deltaTime);  //让物体根据movex，movey进行移动
    }
}
```

下一步：
学习 碰撞 / Rigidbody / 输入控制

当前项目：
无（准备开始：躲避游戏）
