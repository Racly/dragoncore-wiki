# 中阶-自定义物品模型

```
测试修改物品模型:
  # 匹配文本，支持 物品名，物品Lore，NBT 任意一个包含【物品材质1】
  match: "测试材质1"
  # 匹配物品名中包含【测试材质1】 注意,除了【测试材质1】这五个字,其他不会别瞎改
  #match: "Name:\".*测试材质1.*\""
  # 匹配物品名等于【测试材质1】
  #match: "Name:\"测试材质1\""
  # 匹配某行lore包含【测试材质1】
  #match: "Lore:\\[.*测试材质1.*]"
  # 匹配某行lore等于【测试材质1】
  #match: "Lore:\\[.*\"测试材质1\".*]"
  # 匹配自定义nbt的【www】节点为【测试材质1】
  #match: "\"www\":\"测试材质1\""
  
  # 指定物品ID为167且满足match才会替换物品贴图
  type: 167
  
  # 模型和材质文件均需要放置在DragonCore/models/items/<path>/文件夹内
  # 模型文件必须命名为 model.json
  # model.json文件需要进行额外的修改,可看wiki下方【打开模型文件修改模型格式】
  path: "测试武器模型"
  # 缩放大小
  scale: 2
  # 当有多个配置的match冲突时,可调整优先级选项,优先匹配到值比较大的
  priority: 10
  # 指定Gui内物品贴图为另一个模型/贴图
  gui: "节点名"
  
节点名:
  match: "测试材质2"
  texture: "22.png"
```

### 发光贴图

同optifine，同一目录下再放一张\_e.png后缀的图片即可
