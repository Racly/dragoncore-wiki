# 按键执行指令

### 配置文件 KeyConfig.yml

```
# K为按键名, 注意按键名需要大写
K:
  - "[op]say OP身份执行指令"
  - "[console]say 执行控制台指令"
  - "say 玩家身份执行指令"
  
# 在后面加入_release, 则为松开时执行
按键名_release:
  - "[op]say OP身份执行指令"
  - "[console]say 执行控制台指令"
  - "say 玩家身份执行指令"
```

### 进阶格式

```
K:
  # 冷却时间(单位: 秒)
  # 该冷却不会进行保存,玩家退出服务器后自动重置,因此不能做长时间的冷却
  cooldown: 1
  # 执行的指令
  commands:
    - "[op]say 欢迎使用龙之核心-DragonCore"
    - "[console]say 欢迎使用龙之核心-DragonCore"
    - "say 这个指令不是OP没法用啦111"
```

### 按键名大全

```
    MOUSE_LEFT      鼠标左键
    MOUSE_RIGHT     鼠标右键
    MOUSE_MIDDLE    鼠标中键
    
    ESCAPE          
    1               
    2               
    3               
    4               
    5               
    6               
    7               
    8               
    9               
    0               
    MINUS           
    EQUALS          
    BACK            
    TAB             
    Q               
    W               
    E               
    R               
    T               
    Y               
    U               
    I               
    O               
    P               
    LBRACKET       
    RBRACKET        
    RETURN          
    LCONTROL       
    A             
    S             
    D           
    F            
    G            
    H              
    J             
    K               
    L              
    SEMICOLON     
    APOSTROPHE      
    GRAVE          
    LSHIFT        
    BACKSLASH     
    Z           
    X             
    C            
    V           
    B            
    N             
    M              
    COMMA           
    PERIOD        
    SLASH          
    RSHIFT       
    MULTIPLY       
    LMENU           
    SPACE          
    CAPITAL        
    F1              
    F2              
    F3             
    F4           
    F5            
    F6              
    F7            
    F8              
    F9             
    F10            
    NUMLOCK         
    SCROLL         
    NUMPAD7       
    NUMPAD8       
    NUMPAD9        
    SUBTRACT       
    NUMPAD4       
    NUMPAD5        
    NUMPAD6      
    ADD            
    NUMPAD1         
    NUMPAD2       
    NUMPAD3       
    NUMPAD0         
    DECIMAL        
    F11             
    F12           
    F13           
    F14           
    F15            
    F16           
    F17             
    F18             
    KANA          
    F19            
    CONVERT        
    NOCONVERT       
    YEN             
    NUMPADEQUALS    
    CIRCUMFLEX      
    AT              
    COLON           
    UNDERLINE       
    KANJI           
    STOP           
    AX              
    UNLABELED       
    NUMPADENTER     
    RCONTROL        
    SECTION         
    NUMPADCOMMA     
    DIVIDE          
    SYSRQ           
    RMENU          
    FUNCTION        
    PAUSE           
    HOME            
    UP             
    PRIOR           
    LEFT            
    RIGHT           
    END             
    DOWN            
    NEXT            
    INSERT          
    DELETE          
    CLEAR           
    LMETA           
```
