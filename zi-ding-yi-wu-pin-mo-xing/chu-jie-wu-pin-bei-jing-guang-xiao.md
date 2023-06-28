# 初阶-物品背景光效

### 配置文件 ItemEffect.yml

```
极品背景:
  # 匹配文本，支持 物品名，物品Lore，NBT 任意一个包含【极品背景】
  match: "极品背景"
  # 0是背景,1是前景
  mode: 0
  # 图片,可使用gif
  # 序列帧格式: "图片名,持续毫秒数|图片名,持续毫秒数|图片名,持续毫秒数"
  texture: "10.png"
  # width,height默认为16,图片会居中绘制
  width: 16
  height: 16
  # 指定物品ID为167,并且匹配match的物品才会修改贴图
  type: 3
```

### 示例文件

emm还没搞