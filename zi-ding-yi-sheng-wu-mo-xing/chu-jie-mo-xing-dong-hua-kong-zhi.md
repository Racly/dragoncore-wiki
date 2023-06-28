---
coverY: 0
---

# 初阶-模型动画控制

### 配置文件EntityModel.yml

```yaml
# 重要：文件存放目录为resourcepacks/DragonCore/models/entities

人蜘蛛:
  # 匹配的实体名称,当实体名等于 一头人蛛 时会被替换模型
  entity: "一头人蛛"
  # 指定模型文件
  model: "human_spider.geo.json"
  # 指定模型动画文件
  animation: "human_spider.animation.json"
  # 指定模型贴图
  texture: "human_spider.png"
  # 指定模型碰撞箱宽高
  width: 3
  height: 3
```

```yaml
# 通过对比上一章节内容,我们可以发现配置文件多了该选项,该选项就是用于指定模型的动画文件
# 该文件同时也在上一章节内提供的模型压缩包内
animation: "human_spider.animation.json"
```

### 自动触发动画

1.走路时会自动触发动画   walk  【提供测试的模型内已包含】

2.静止时会自动触发动画   idle   【提供测试的模型内已包含】

3.攻击时会自动触发动画   attack

4.死亡时会自动触发动画   death

### 动画必须性设置

1. walk动画必须设置循环模式为永久循环   loop: true  【提供测试的模型内已设置】
2. idle 动画必须设置循环模式为永久循环   loop: true  【提供测试的模型内已设置】

### 测试使用

1.完成EntityModel.yml的修改后，执行重载指令/dragoncore reload

2.完成资源文件放置后,在游戏内同时按下键盘按键**`o和p`**两个按键以清除客户端缓存

3.如果你上一章节的实体还在，此时已经可以看到实体头部会在静止时左右摆动

&#x20;  且移动时脚部会进行移动
