# 中阶-生物头顶标签(血条)

### 配置文件 HeadTag/xxx.yml

* 需要在plugins/DragonCore/内自行创建文件夹HeadTag后创建任意名字的yml文件
* 注意虽然这个配置长的很像Gui的配置,但实际上是不一样的

```
# 匹配实体名(忽略颜色空格)
match: 
  - "实体名称"
# 名称判定是否为包含模式
contains: true
# 显示模式
display: "always"

# 总体Y坐标偏移,同时也作为你在不同角度看着
# 该tag的旋转基准点使用,默认值为 方法.取实体高度+0.25
offsetY: "方法.取实体高度+0.5"

Functions:
  # 初始化时触发
  open: |-

  # 每tick执行一次,1秒=20tick
  tick: |-
    
  # 血量变化触发, 局部变量.参数.0 为变化前血量   局部变量.参数.1 为变化后血量
  health: |-
    

血量背景:
  type: texture
  # xy轴偏移(位置并不像gui那样是基于屏幕左上角,而是实体正中间,所以需要多加调试)
  x: "0-血量背景.width/2"
  y: "-10"
  width: 100
  height: 10
  texture: "blood/背景.png"
  
血量填充:
  type: texture
  x: "-98/2"
  y: "-9"
  width: "98*方法.取实体血量比例"
  height: 8
  # 指定图片宽高,此时width和height将截取显示
  textureWidth: 98
  textureHeight: 8
  texture: "blood/血条.png"

# 组件是按顺序显示的,所以写在后面的组件的显示层级比较高,才不会被血条盖住
第一行:
  # 类型: label(文本)  texture(图片)
  type: label
  x: "-第一行.width/2"
  y: "-9"
  # 显示内容(注意这里如果使用  方法.取变量   取的变量都是自己的哦,是取不到其他玩家的)
  text: "方法.取实体名"
  # 背景颜色(rgba),不想显示可以写hide,否则默认为0,0,0,63
  background: "20,146,228,255"

```

### 资源文件位置

<figure><img src="../.gitbook/assets/WL(YP@WBL(TR]M&#x60;0_2TW[4L.png" alt=""><figcaption></figcaption></figure>

### 示例文件下载

{% file src="../.gitbook/assets/背景.png" %}

{% file src="../.gitbook/assets/血条.png" %}

## 进阶-HeadTag组件类型

> #### 可用组件只有两种：label和texture

```
两种组件的通用属性

# xy轴偏移(位置并不像gui那样是基于屏幕左上角,而是实体脚部正中间,所以需要多加调试)
x: "0-背景组件名称.width/2"
y: "-10"
scale: 1        缩放大小
glow: true      是否发光
visible: true   是否显示组件


图片组件属性(texture)
texture: "图片路径.png"
width: 100                绘制宽度
height: 10                绘制高度
textureWidth: 100         指定图片大小,此时width将裁剪显示
textureHeight: 10         比如textureWidth: 100,width: 50 那么将只显示图片的一半
u: 0
v: 0

文字组件属性(label)
text: "显示的文字"
background: "0,0,0,63"            文字背景颜色(rgba),写入hide时将不显示
font: "字体.ttf"
```

```
可用方法大全(基本上同UI的方法大全,在这基础上有所增加)

方法.取实体名
方法.取实体UUID
方法.取实体高度
方法.取实体血量
方法.取实体最大血量
方法.取实体血量比例    也就是 方法.取实体血量/方法.取实体最大血量 的值

需要注意的方法

方法.取变量  该功能取的变量是自己的变量哦,是取不到其他玩家的,可自行写插件获取或龙核星球群内下载
           DragonPlayerTag 插件
```

