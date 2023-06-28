# 中阶-模型进阶配置

```

人蜘蛛1:
  # 匹配的实体名称,当实体名等于 一头人蛛 时会被替换模型
  entity: "一头人蛛"
  # 切换名称判定模式为包含, 也就是实体名中包含 一头人蛛 即会被替换模型
  contains: true
  # 判定名称必须包含§颜色字符的情况下才替换模型
  requireColor: true
  # 指定实体类型
  type:
    - "zombie"
  # 指定模型文件
  model: "human_spider.geo.json"
  # 指定模型动画文件
  animation: "human_spider.animation.json"
  # 指定模型贴图
  texture: "human_spider.png"
  # 指定模型发光贴图
  glowTexture: "human_spider.png"
  # 指定动画控制文件,通常情况下不需要设置
  # controller: "1.yml"
  # 指定模型碰撞箱宽高
  width: 1
  height: 1
  # 是否隐藏实体名称
  hidename: true
  # 是否总是绘制模型,该选项只有模型太大导致不显示时才需要打开
  renderAlways: true
  # 是否渲染实体受伤时的红色效果
  hurtColor: false
  # 是否渲染实体脚部的圆形阴影
  shadow: false
  # 模型缩放大小
  scale: 1
  
```
