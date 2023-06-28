# 界面属性

```
界面属性
match: "xx"
match:
  - "xx"
- 匹配界面名,hud为自动开启
- GuiInventory可以替换背包,GuiIngameMenu可以替换ESC
- 或者直接填写箱子界面名称，即可替换箱子界面(颜色符号需写为§),也可以用正则表达式
- PS：当你打开任意界面时，客户端的log内会提示本次打开的界面名哦

updateInterval: 100
- 设置组件属性更新间隔, 设置该值可以优化帧率问题, 但同时它会导致组件显示刷新不及时
- 单位为毫秒,也就是每隔100毫秒更新一次组件属性
- 可使用  方法.刷新缓存  来直接刷新属性

through: true/false
- 点击是否穿透组件,达到同时点击多个组件的效果

priority: 数字[1-5]
- hud显示优先级,5为最高,可用于多个hud时的层级问题

interactHud: true/false
- 在Gui内是否允许点击hud

currentItemSize: 数字[默认16,不要超过50]
- 鼠标拿着物品时,物品的大小

allowEscClose: true/false
- 是否允许按ESC关闭界面

hideHud:
  - "xxx"
  - "xxx"
- 需要隐藏的hud,类型如下
- 也可以隐藏龙核hud,只需要填写对应hud文件的文件名(不需要.yml)
- 别问我这些类型是啥意思，问就是百度去
  HELMET
  PORTAL
  CROSSHAIRS
  BOSSHEALTH (boss血条)
  BOSSINFO   
  ARMOR    (护甲值)
  HEALTH   (血量)
  FOOD     (食物)
  AIR      (氧气)
  HOTBAR   (物品快捷栏)
  EXPERIENCE  (经验条)
  TEXT 
  HEALTHMOUNT  (坐骑血量)
  JUMPBAR  (马儿跳跃值)
  CHAT
  PLAYER_LIST  (应该是tab玩家列表)
  DEBUG
  POTION_ICONS (药水图标)
  SUBTITLES
  FPS_GRAPH
  VIGNETTE   启用mc设置的 图像品质:高品质 时,会在阴暗位置时,hud内显示一个阴影图层
             该图层会盖住hud导致hud变得有点黑,因此建议将该类型加入到hideHud内

import:
  - "xx"
  - "xx"
- 将其他界面文件组件并入该界面内(不需要.yml)
```



```
界面触发器

Functions:
  open: 界面被打开时触发
  close: 界面被关闭时触发
  keyPress: 界面打开时,按下任意按键均会触发，配合[方法.取当前按下键]使用
            如果是HUD界面,则未打开gui或打开了聊天栏时按键触发
  wheel: 滚轮滚动时触发,配合[方法.取滚轮值]使用
  chatOpen: 打开聊天栏时触发,仅对HUD界面有效
  chatClose: 关闭聊天栏时触发,仅对HUD界面有效
  message: 玩家受到聊天消息时触发,配合[方法.取当前聊天消息]使用
  tick: 每tick触发一次,可用来检测变速外挂,变速外挂会导致每秒的tick数超出20
  reload: 插件调用了screen.update时触发
  
  resize: 游戏窗口大小变化时触发,可能仅对gui有效,hud无效
  dropItem: 丢弃物品时触发,可能仅对gui有效,hud无效
  
  preRender: 每帧触发一次,但这里取不到鼠标悬浮组件
  postRender: 每帧触发一次,这里可以取到鼠标悬浮组件
  
  click: 鼠标点击时触发,包括左键中键右键
  click_left: 鼠标左键点击时触发
  click_right: 鼠标右键点击时触发
  click_middle: 鼠标中键点击时触发
  release: 鼠标松开时触发,包括左键中键右键
  release_left: 鼠标左键松开时触发
  release_right: 鼠标右键松开时触发
  release_middle: 鼠标中键松开时触发
  mouse_move: 鼠标移动时触发


特殊用法
# 当以下触发器使用 return true; 时,将会拦截本次操作

# 聊天栏将不会显示出消息
message: |-
  return true;
  
# hud内使用时,可拦截对聊天栏滚动
# itemtip内使用时,可拦截对gui滚动
wheel: |-
  return true;

# click,click_left,click_right,click_middle使用时,将拦截对组件点击操作
# release同理
click: |-
  return true;

# 拦截对textbox输入,应该没啥用?
keyPress: |-
  return true;
```
