# 中阶-基岩粒子(暴雪粒子)

### 粒子文件制作

{% embed url="https://snowstorm.app/" %}

* 可从网站上面Examples选择一个示例文件
* 然后点击File->Download下载出粒子的json文件

### 使用教程

> 将下载得到的json文件,放入客户端资源文件夹内
>
> resourcepacks/DragonCore/models/particle【没有文件夹请自行创建】

> 创建一个MtyhicMobs的技能
>
> ```
> 播放粒子:
>   Skills:
>   - particle_add{s=loading.particle;u=true;time=20;puid=<mob.uuid>剑气;r=0,180,0} @Self
>  
> 移除粒子:
>   # 注意这个功能只会让粒子机不会继续生成粒子,已生成的粒子会等寿命结束才会消失
>   # 如果想要移除粒子机及其粒子,可使用上方的播放粒子,播放一个空的粒子文件
>   Skills:
>   - particle_remove{puid=<mob.uuid>剑气;} @Self
>  
>  
> 关于技能选项的介绍
> s,scheme =       粒子文件名,不需要加上json哦
> puid,puuid =     指定粒子的ID, 如果播放粒子的ID相同,将会覆盖掉上一个
> u,useentitypos = 使用实体坐标的位置,如果为false则是绑定实体坐标
> r,rotation =       旋转方向,值为 x,y,z 如 10,10,10
>                  特殊值为look, 此时将旋转到玩家视角
>                  可用变量为 headyaw yaw pitch
>                 【可能需要在编辑器界面的Space开启local position和local rotation】
>                 【嘛不过我也不会用所以不太清楚捏】
> translate =      额外的坐标移动  x,y,z  比如0,1,0
> t,time =          持续的tick时间
>
> ```

执行指令 /mm test cast 播放粒子  后退一步即可在自己原有位置看到播放的粒子

注意自己不可以是创造模式哦, 否则mm技能选中不到自己
