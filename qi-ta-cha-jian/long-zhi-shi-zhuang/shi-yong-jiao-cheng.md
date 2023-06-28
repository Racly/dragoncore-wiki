# 使用教程

### 1.  授权码的使用

> 1. 将Plugin-DragonArmourers.jar装入服务端插件后,启动服务端,等待服务端启动完成
>
> &#x20;     此时插件将在plugins内生成插件文件夹 DragonArmourers
>
> &#x20;     你需要打开其中的<mark style="color:red;">**config.yml**</mark>,将你的授权码填入<mark style="color:red;">**code: "xxxx"**</mark>内
>
> 2\.   授权码填入完成后，关闭服务端并重新启动即可
>
> &#x20;     如插件无法使用请检查插件载入时的输出，是否提示了 <mark style="color:red;">**授权码当前已绑定其他机器**</mark>
>
> &#x20;     如遇到该情况需要到\[龙の售后群]发送 <mark style="color:red;">**unbind**</mark> 以解绑插件，然后重启服务端即可
>
> 3\.  授权码<mark style="color:red;">**禁止转卖，出租**</mark>，如出现这两项情况将会停用授权码并踢出售后群

{% hint style="info" %}
如果config.yml内无code: "xxxx"，请检查是否已经安装了旧版本的时装插件

需删除该旧版本插件，并删除DragonArmourers文件夹后重启服务器

以重新生成正确的配置文件
{% endhint %}

### 2. 添加时装文件

> 1. &#x20;首先需要获取到时装文件【时装文件为<mark style="color:red;">**.armour**</mark>后缀的文件】
> 2. 可从群文件/mcbbs/定制等方式获取时装文件
> 3. 打开 <mark style="color:red;">**plugins/DragonArmourers/skin-library**</mark> 文件夹
> 4. 将时装文件放入其内,然后执行命令<mark style="color:red;">**/sz reload**</mark>
> 5. 如时装放置正确，后台将提示<mark style="color:red;">**共载入 x 个时装**</mark>

### 3. 小白快乐使用教程

> 1. &#x20;执行命令   -> <mark style="color:red;">**/sz manager skin**</mark>,拖动时装到背包内获取时装物品
> 2. 打开时装栏-> <mark style="color:red;">**/di shizhuang**</mark>
> 3. 将时装物品，放置到时装栏内的正确槽位，然后关闭界面
> 4. 大功告成，此时按F5后切换视角，即可看到自己身上已经穿着了时装

{% hint style="info" %}
虽然说是时装物品，但其实它只是原版的物品，被添加上了NBT数据

使得mod对物品的外观进行修改而已哦
{% endhint %}

### 4. 进阶-设置物品时装的两种方式

> 4.1 添加物品NBT （skin: "时装文件名")
>
> 打开时装管理器/sz manager skin，拖动时装到物品上即可

> 4.2 添加Lore
>
> 比如想要物品存在某一行Lore为   <mark style="color:red;">**森林的祝福**</mark>  就将物品显示为时装  <mark style="color:red;">**森林套装**</mark>
>
> 打开配置文件skin.yml,在其item节点内填入&#x20;
>
> ```
> item:
>   - "森林的祝福<->森林套装"
> ```
>
> 然后/sz reload重载插件即可，此时使用Lores插件为物品添加Lore, /lore add 森林的祝福
>
> 即可看到物品的外观已变成了**森林套装**这个时装

### 5. 进阶-设置生物时装

{% hint style="info" %}
注意: 生物类型仅支持  骷髅, 僵尸, 猪人, 盔甲架, 玩家

&#x20;        如果你设置了武器时装, 生物手上需要有武器才会显示时装
{% endhint %}

> 1. 设置NPC时装
>
> &#x20;     使用指令/sz manager entity ，左上角选中实体后，将时装拖动至左下角
>
> &#x20;     然后点击保存即可
>
>

> &#x20; 2\.  设置怪物时装( 怪物名称匹配 )
>
> &#x20;     比如想要生物名为  <mark style="color:red;">**森林土著**</mark>  就为其显示时装  <mark style="color:red;">**森林套装**</mark> &#x20;
>
> &#x20;     打开配置文件skin.yml,在其entity节点内填入
>
> ```
> entity:
>   - "森林土著<->森林套装"
> ```

> &#x20; 3\.  设置Mythicmobs生物时装
>
> &#x20;      打开mm的怪物配置文件
>
> ```
> 喵喵人:
>   Type: husk
>   # 为其添加skin节点,注意此处为小写
>   skin:
>     - "时装名"
>     - "时装名"
>     - "时装名"
>   Display: '&4喵喵人'
>   Health: 30
>   Damage: 3
>   Equipment:
>   - 喵喵头:Helmet
> ```

### 6. 展示框及时装方块

> 1. 展示框显示时装
>
> &#x20;     放置一个展示框后，将时装放入其内即可
>
> &#x20; 2\. 头颅时装方块
>
> &#x20;   1\. 在地上放置一个骷髅头颅
>
> &#x20;   2\. 手持任意时装物品右键头颅
>
> &#x20;   3\. 该功能玩家也可使用，如果需要关闭该功能
>
> &#x20;       可在config.yml内修改BlockSkin: false

### 7.  指令大全

DragonArmourers指令

1. /sz give <玩家> <时装名> <数量(可忽略)>    给予玩家一个时装物品
2. /sz manager skin                                           打开时装管理界面
3. /sz manager entity                                        打开实体管理界面
4. /sz setitem <时装名>                                    设置物品时装
5. /sz settemp <玩家> <时装1> <时装n>         设置玩家的临时展示时装

#### DragonInventory指令

1. /di <文件名(.yml不用写)>                             打开Inventory文件夹内的一个界面
2. /di open <玩家> <文件名(.yml不用写)>      令玩家打开界面
3. /di reload                                                     重载数据

### 8. 其他问题

> 1. 关闭动作功能
>
> ```
> 在.minecraft/config/mobends.cfg内添加三行
> animated{
>   B:mobends-player=false
> }
> ```
>
> &#x20; 2\. 禁用按键开关动作功能
>
> ```
> 在.minecraft/config/mobends.cfg内修改
> B:disableKey=true
> ```
>
> &#x20;3\. 仅关闭持剑攻击动作
>
> ```
> 在.minecraft/config/mobends.cfg内修改
> B:playerAttack=false
> ```
>
> 4\. 仅关闭持弓右键的动作
>
> ```
> 在.minecraft/config/mobends.cfg内修改
> B:playerBow=false
> ```
