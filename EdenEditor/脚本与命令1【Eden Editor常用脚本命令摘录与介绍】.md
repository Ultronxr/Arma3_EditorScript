<!--

 * @Description: 
 * @Version: 
 * @Author: Ultronxr
 * @Date: 2021-01-11 21:25:36
 * @LastEditors: Ultronxr
 * @LastEditTime: 2021-01-15 16:36:23
-->

# Eden Editor编辑器常用脚本命令摘录与介绍

帮助内容请参见【参考文档和官方Wiki】文件中的`脚本与命令`->`脚本命令目录`条目下的内容。

为了便于查找、对应官方文档位置，这里的命令分类与排序全部采用官方文档中的方式。部分命令被归于多个分类，这里只在某个分类中记录一次，不重复记录。

注：

+ 命令中的中括号/方括号、双引号是命令的语法规则，并不表示强调含义，随意省略或添加将会直接导致命令执行出错；
+ 命令中的单词如果在下方有解释说明，则该单词是这条命令的参数，使用命令时需要把这些参数替换为实际内容；
+ 参数中如果注明了“备选值”，请尽量在备选值中选择填写，否则可能会导致命令执行出错；
+ 在描述与讲解命令时使用了很多英文单词，这里并不是不给翻译，而是这些单词是官方在代码/编辑器中定义的专有敏感词，使用原单词可以防止出现谬误；

## 一、*Animations* 动画效果命令

## 二、*Arrays* 数组操作命令

## 三、*Artillery* 火炮命令

## 四、*Briefing* 目标、任务、笔记命令

## 五、*Broken Commands* 执行效果与预期不符、执行错误的命令

## 六、*Camera Control* 相机控制命令（与编辑器、宙斯相关的相机控制不在此列出）

## 七、*Config* 配置命令

## 八、*Containers* 容器操作命令（背包、背心等可以容纳物品的对象）

## 九、*Conversations* 对话、主题命令

## 十、*Custom Panels* 显示面板命令（特指左右两个显示面板）

## 十一、*Custom Radio and Chat* 无线电、通讯命令

## 十二、*Diagnosis (Diag)* 代码诊断命令

## 十三、*Difficulty* 游戏难度命令

## 十四、*DLC* 与DLC相关命令

## 十五、*Dynamic Simulation* 动态模拟命令

## 十六、*Eden Editor* 编辑器命令

## 十七、*Environment* 环境命令（日期、时间、天气等）

### 1.控制环境动物与环境声音

[原链接](https://community.bistudio.com/wiki/enableEnvironment)

```script
enableEnvironment [ambientLife, ambientSound];

ambientLife: Boolean，布尔值。开/关环境动物效果。
        备选值：true/false
ambientSound: Boolean，布尔值。开/关环境声音。
        备选值：true/false

return: 无
```

```script
例：关闭环境动物和环境声音
enableEnvironment [false, false];
```

### 2.修改地形网格分辨率

[原链接](https://community.bistudio.com/wiki/setTerrainGrid)

修改地形网格分辨率（单位：米），从而影响地形中内容的精细复杂程度，例如远处地形的平滑程度、植被覆盖率、是否存在草皮等。

```script
setTerrainGrid grid;

grid: Number，一个0到50之间的数字。数字越小地形越精细，游戏越卡顿，反之地形越粗糙，游戏越流畅。
        备选值：3.125（地形最细致，最卡顿）、6.25、12.5（单人模式默认值）、25（多人模式默认值）、50（地形最平滑，最流畅）
        注：如果所填数字不在上述备选值之中，则会自动填入一个离所填数字最接近的备选值。

return: 无
```

```script
例：去掉所有草皮
setTerrainGrid 50;
```



## 十八、*Event Handlers* 时间监听器命令

## 十九、*Flags* 旗帜命令

## 二十、*Game 2 Editor* 测试版编辑器命令（Arma2编辑器）

## 二十一、*Groups* 小队命令

## 二十二、*GUI Control* 游戏界面命令（对话框、菜单样式）

## 二十三、*GUI Control - Controls Table* 游戏界面控件命令（）

## 二十四、*GUI Control - Event Handlers* 游戏界面控件命令（事件监听器）

## 二十五、*GUI Control - HTML* 游戏界面控件命令（）

## 二十六、*GUI Control - ListNBox* 游戏界面控件命令（）

## 二十七、*GUI Control - ListBox* 游戏界面控件命令（）

## 二十八、*GUI Control - Map* 游戏界面控件命令（）

## 二十九、*GUI Control - Menu* 游戏界面控件命令（）

## 三十、*GUI Control - Object* 游戏界面控件命令（）

## 三十一、*GUI Control - Tree View* 游戏界面控件命令（）

## 三十二、*HashMap* 操作HashMap命令

## 三十三、*High Command* 小队图标命令

## 三十四、*Interaction* 游戏内界面提示消息命令（消息、对话框、菜单等）

## 三十五、*LeaderBoards* 排行榜命令

## 三十六、*Lights* 光源命令

## 三十七、*Locations* 地点、区域命令

## 三十八、*Map* 地图命令

## 三十九、*Markers* 标记点命令

## 四十、*Math* 数学相关命令

## 四十一、*Math - Geometry* 数学相关命令（几何）

## 四十二、*Math - Vectors* 数学相关命令（向量）

## 四十三、*Mission Information* 任务参数命令

## 四十四、*Mods and Addons* 扩展、插件命令

## 四十五、*Multiplayer* 多人游戏命令

## 四十六、*Object Detection* 对象检测命令

## 四十七、*Object Manipulation* 对象操作命令

### 1.创建/生成载具

[原链接](https://community.bistudio.com/wiki/createVehicle)

````script
createVehicle ["type", position, ["markers"], placement, "special"]

type: String，字符串。表示载具对象名称。
position: PositionATL/PositionAGL/Position2D/Object，生成位置。可以使用特殊函数获取位置。
markers: Array，字符串数组。其中可以填写多个标记点（markers）名称。
        注：如果填写了markers参数，载具会在给定位置与这些标记点之间随机选择一个位置生成。
placement: Number，数字。表示载具会生成在指定位置以placement为半径的圆内任意位置。
special: Sting，字符串。特殊状态。
        备选值："NONE"，载具生成时会自动寻找离给定位置最近的空位置，避免与周围模型发生碰撞和交错；"CAN_COLLIDE"，载具生成时不检查是否与周围模型发生碰撞，直接生成；"FLY"，如果待生成的是载具具备飞行能力，且有乘客，那么该载具会生成在默认高度的空中。
        注：该参数的默认值为"NONE"，如果留空或者填写""，那么会自动套用"NONE"值。

return: Object，生成的载具对象。如果生成出错或失败，返回objNull。
````

```script
例1：//TODO
```

### 2.损坏的载具是否能容纳乘客

[原链接](https://community.bistudio.com/wiki/allowCrewInImmobile)

修改当载具受到损坏时，是否能让乘客继续停留在载具中。

对AI的行为影响：如果设置为是，AI会继续待在遭受损坏的地面载具/飞机中继续驾驶，而不是马上逃脱/跳伞；如果设置为否，AI会在载具受到损坏时马上脱离逃生。

```script
vehicle allowCrewInImmobile bool;

vehicle: Object，对象。只能是载具。
bool: Boolean，布尔值。
        备选值：true/false

return: 无。
```

```script
例1：让处于局部（local）的所有载具对象能在损坏时容纳乘客（仅限单人游戏已经开始时使用）
_vehicle allowCrewInImmobile true; 

例2：让处于局部（local）和全局（global）的所有载具对象能在损坏时容纳乘客（用于在Editor的Init时使用）
{
    _x allowCrewInImmobile true;
} forEach vehicles;
```



## 四十八、*Particles* 粒子效果命令

## 四十九、*Performance Logging* 调试、日志命令

## 五十、*Pilot Camera* 载具目标命令（例如吊舱等）

## 五十一、*Positions* 位置坐标、高度命令

## 五十二、*Program Flow* 代码流程命令（循环、条件判断、跳转等）

## 五十三、*Radio and Chat* 无线电、聊天信息命令

## 五十四、*Remote Control* 远程遥控命令

## 五十五、*Render Time Scope* 

## 五十六、*Roads and Airports* 道路、机场命令

## 五十七、*Ropes and Sling Loading* 绳索、悬吊命令

## 五十八、*RTD* 高级飞行模式命令

## 五十九、*Sensors* 传感器命令

### 1.设置车辆雷达开关

[原链接](https://community.bistudio.com/wiki/setVehicleRadar)

```script
vehicle setVehicleRadar rules;

vehicle: Object，对象。一辆由AI驾驶操控的载具。
rules: Number，数字。
        备选值：0，自动操控；1，强制一直开启；2，强制一直关闭

return: 无。
```

```script
例：强制一直开启车辆的雷达
_vehicle setVehicleRadar 1;
```



## 六十、*Sides* 联盟/阵营命令

## 六十一、*Sounds* 声音命令

## 六十二、*Stamina System* 耐力、疲劳命令

## 六十三、*Strings* 字符串操作命令

## 六十四、*Structured Text* 富文本命令

## 六十五、*System* 游戏/战局整体系统命令

## 六十六、*Team Switch* 切换阵营/队伍命令

## 六十七、*Teams* 团队、团队人员命令

## 六十八、*Time* 游戏时间、系统时间命令

## 六十九、*Triggers* 触发器命令

## 七十、*Turrets* 炮塔命令

## 七十一、*Uncategorised* 未分类命令

## 七十二、*Unit Control* 部队单位控制命令

## 七十三、*Unit Identity* 部队单位特征命令（军衔、说话声音等）

## 七十四、*Unit Inventory* 部队单位库存、仓储命令

### 1.移除部队单位装备的武器（global）

[原链接](https://community.bistudio.com/wiki/removeWeaponGlobal)

```script
unit removeWeaponGlobal "weapon";

unit: Object，单位对象。人、载具等。
weapon: String，字符串。武器。
```

```script
例1：删除所有单位对象的镭射发射器
{
    _x removeWeaponGlobal "Laserdesignator";
} forEach allUnits;

例2：删除所有载具的SR和MR两种AA导弹
{
    _x removeWeaponGlobal "weapon_AMRAAMLauncher";
    _x removeWeaponGlobal "weapon_BIM9xLauncher";
} forEach vehicles;

例3：删除所有xxxxxxxxxxxx载具装备的xxxxxxxxxxxx //TODO
{
    if (typeOf _x == "O_Heli_Attack_02_black_F") then {
        _x removeWeaponGlobal "rockets_Skyfire";
    };
} forEach vehicles;
```

### 2.添加弹匣

[原链接](https://community.bistudio.com/wiki/addMagazines)

```script
unit addMagazines ["magazineName", count];

unit: Object，单位。
magazineName: String，字符串。待添加弹匣的名称。
count: Number，数字。待添加弹匣的数量。

return: 无。
```

```script
例1：给玩家添加5个6.5mm 30发弹匣
player addMagazines ["30Rnd_65x39_caseless_mag", 3];

例2：给玩家驾驶的载具添加3个20mm 450发AA机炮弹匣
vehicle player addMagazines ["magazine_Fighter01_Gun20mm_AA_x450", 3];
```

### 3.添加武器

[原链接](https://community.bistudio.com/wiki/addWeapon)

如果待添加的武器对于士兵/载具来说是新加的（原本士兵/载具没有这个武器），那么**必须在添加武器前添加该武器对应的弹匣**。

```script
object addWeapon "weapon";

object: Object，对象。添加武器的对象，可以是士兵、载具。
weapon: String，字符串。待添加的武器名称。

return: 无。
```

```script
例1：给玩家添加2个12.7mm 5发APDS穿甲弹匣，并添加GM6 Lynx反器材狙击步枪
player addMagazines ["5Rnd_127x108_APDS_Mag", 2];
player addWeapon "srifle_GM6_F";

例2：给玩家驾驶的载具添加3个20mm 450发AA机炮弹匣，并添加20mm机炮
vehicle player addMagazines ["magazine_Fighter01_Gun20mm_AA_x450", 10];
vehicle player addWeapon "weapon_Fighter_Gun20mm_AA";
```

### 4.移除武器

[原链接](https://community.bistudio.com/wiki/removeWeapon)

移除对象的武器会/不会把该武器对应的所有弹匣一并移除。//TODO

如果尝试移除对象没有的武器，代码会/不会报错，会/不会忽略这次操作。//TODO

```script
unit removeWeapon "weapon";

unit: Object，对象。士兵或载具。
weapon: String，字符串。待移除的武器名称。

return: 无。
```

```script
例1：移除玩家身上的GM6 Lynx反器材狙击步枪
player removeWeapon "srifle_GM6_F";

例2：移除玩家驾驶的载具上的20mm机炮
vehicle player removeWeapon "weapon_Fighter_Gun20mm_AA";
```



## 七十五、*Variables* 变量操作命令

## 七十六、*Vehicle in Vehicle Transport* 载具运输命令

## 七十七、*Vehicle Loadout* 载具外部装备命令（装甲、外挂等）

## 七十八、*Waypoints* 路径点命令

## 七十九、*Weapon Pool* 武器池命令（操作一个预先设定的武器集合）

## 八十、*Weapons* 武器、供弹命令

## 八十一、*Zeus (Curator)* 宙斯命令
