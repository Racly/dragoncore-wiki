# 中阶-自定义物品模型-弓箭

### 配置文件 ItemModel.yml

```
测试修改弓箭模型:
  # 当物品的 lore 或 name 或 某个nbt【包含】测试弓箭1  -> 就会显示为xxx材质
  match: "测试弓箭1"
  # 模型和材质文件均需要放置在DragonCore/models/items/<path>/文件夹内
  # 模型文件必须命名为 model.json
  # model.json文件需要进行额外的修改,可看wiki下方【打开模型文件修改模型格式】
  path: "测试弓"
```

### 资源文件位置

同章节   [ **初阶-自定义物品模型**](chu-jie-zi-ding-yi-wu-pin-mo-xing.md#zi-yuan-wen-jian-wei-zhi)

### 弓箭模型文件修改格式

```
我们先从贴图弓模型开始学习

1.首先我们需要弓的不同拉伸状态下的不同模型文件
  本教程的示例文件为minecraft原版弓的模型及贴图

2.同[初阶-自定义物品模型]，需要将本处四个模型文件，处理【打开模型文件修改格式】

3.模型文件修改
3.1 将主模型文件[bow.json]修改文件名为[model.json]，这个文件为[未拉弓状态]的物品显示的模型
     Ps: 文件里存在"overrides": 这段文字的就是主模型文件

3.2 如果已经简单了解过模型文件，你会知道overrides就是
     弓在不同拉伸进度下, 可以指向不同的模型文件
     那么我们需要修改内部的model,使其能正确指向到龙核的路径
     将model修改为  dragoncore:items/你放模型的文件夹的名称/模型文件的名字
     比如此处案例我们的文件路径为[测试弓]
     模型文件为[ bow_pulling_0, bow_pulling_1, bow_pulling_2 ]
     那么就是将model修改为 dragoncore:items/测试弓/bow_pulling_0
                        dragoncore:items/测试弓/bow_pulling_1
                        dragoncore:items/测试弓/bow_pulling_2

4.额外注意内容【本教程示例没有这个问题】
  如果你修改后模型还是没能正常显示
  就查看一下各个模型文件内是否有  "parent": "xxxx",
  有的话就把他删了，注意后面的逗号也要删除,否则会导致json格式错误
  
```

### 示例文件下载

{% file src="../.gitbook/assets/弓箭模型示例文件.zip" %}
