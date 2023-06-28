# 组件属性

```
组件通用属性
【*】代表该属性可使用计算公式，控件每次绘制都会计算最新数值
【/】代表该属性可使用计算公式，但仅为初始化时的一次性计算数值

 y        绘制起始x【*】
 y        绘制起始y【*】
 width    绘制宽度 【*】
 height   绘制高度 【*】

 限制区域的意思是组件的UI不会超过该界限，超出的部分将无法看到，可用于制作滚动框之类的
 limitX       限制区域起始x  【*】
 limitY       限制区域起始Y  【*】
 limitWidth   限制区域宽度   【*】
 limitHeight  限制区域高度   【*】

 maxDistanceX 点击后横向可移动的最大值【*】
 maxDistanceY 点击后竖向可移动的最大值【*】
 minDistanceX 点击后横向可移动的最小值【*】
 minDistanceY 点击后竖向可移动的最小值【*】
 distanceX    当前横向已移动值【/】 该值必然处于 minDistanceX至maxDistanceX 之间
 distanceY    当前竖向可移动值【/】 该值必然处于 minDistanceY至maxDistanceY 之间

 visible  是否可视   【*】
 enable   是否可交互  【*】
 alpha    透明度[0-1]【*】
 scale    缩放大小   【*】

 tip      悬浮于该组件时显示的文本 【*】 若某行为container_xx，则

 以下几项可用于动画效果

 fscale    中心缩放【*】仅显示效果，不具备点击判断
 frotatex  中心旋转【*】仅显示效果，不具备点击判断
 frotatey  中心旋转【*】仅显示效果，不具备点击判断
 frotatez  中心旋转【*】仅显示效果，不具备点击判断
 fx        坐标x偏移【*】仅显示效果，不具备点击判断
 fy        坐标y偏移【*】仅显示效果，不具备点击判断
```

```
组件属性:


 xx_图片:  [或者xx_texture]
   texture: "图片.png"  也可以写成  255,255,255,255  这样会显示为颜色   【*】
   textureHovered: "悬浮着显示的图片"                                   【*】
   textureWidth: 设定图片宽度,之后的width如果小于本宽度,则仅绘制一部分  【*】
   textureHeight: 设定图片高度,之后的width如果小于本高度,则仅绘制一部分 【*】
   v:   【*】
   u:   【*】
   text: "xxx"  用于显示文字,文本换行可用\n【*】
   color: "255,255,255,255"  文本默认颜色【*】
   font: "xxx"  字体文件,需要使用ttf文件【*】
   stencil: "裁剪模板.png"  texture的图片将会被裁剪成stencil指定的图片形状
   stencilWidth: 100 指定裁剪模板大小,默认值=width
   stencilHeight: 100 指定裁剪模板大小,默认值=height

 xx_文本:  [或者xx_label]
   texts:       文本换行可用\n【*】 
     - "我叫做"
     - "方法.玩家名"
   color: "255,255,255,255"  文本默认颜色【*】
   center: true  是否居中绘制   [默认值false]【*】
   shadow: true  是否绘制文字阴影[默认值true]【*】
   length: 100   限制文本长度，过长的会自动换行【*】

 xx_实体:  [或者xx_entity]
   entity: "owner" 【*】
     可填值为 owner 代表自己, aim 代表鼠标指着的生物,firstaim 代表打开界面时鼠标指着的生物
     或者直接使用UUID，若客户端内存在该UUID实体则会显示该实体
   head: true/false 是否强制显示头颅【*】
   followMouse: true/false  是否跟随鼠标【*】

 xx_槽位:  [或者xx_slot]
   identifier: "槽位名称"【*】
     若槽位名称为container_开头，则会读取当前界面本应显示的槽位
     如打开了一个箱子，那么 container_0 就是箱子的第一个槽位
     否则为读取玩家服务端槽位数据,同时你也需要在SlotConfig.yml内填写槽位配置
     该槽位才能使用
   drawBackground: true/false 鼠标指着是否显示背景白板【*】

 xx_文本框:  [或者xx_textbox]
   length: 128  文本框可以写入的最大文本长度[默认值32]【*】
   drawBackground: true  是否绘制背景框[默认值true]【*】
   text: "界面打开时的默认文本" [默认值为空]【/】
   focused: true/false  默认的状态是否是输入状态【/】
```

```
 组件触发器
 actions:
   create:          组件初始化时触发
   remove:          组件被删除时触发
   preRender:       组件每帧绘制前触发
   postRender:      组件每帧绘制后触发
   click_left:      左键点击
   click_right:     右键点击
   click_middle:    中键点击
   click:           任意键点击
   release_left:    左键松开
   release_right:   右键松开
   release_middle:  中键松开
   release:         任意键松开
   enter:           鼠标进入组件范围
   leave:           鼠标离开组件范围
   wheel:           鼠标在组件范围内使用滚轮,配合[方法.取滚轮值]使用
   textChange:      仅textbox组件可用,文本被修改时触发
```

