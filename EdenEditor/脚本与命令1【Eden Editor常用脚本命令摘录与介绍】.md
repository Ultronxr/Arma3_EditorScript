<!--
 * @Description: Eden Editor编辑器常用脚本命令摘录与介绍
 * @Version: 
 * @Author: Ultronxr
 * @Date: 2021-01-11 21:
 * @LastEditors: Ultronxr
 * @LastEditTime: 2021-03-31 16:55:50
-->

# Eden Editor编辑器常用脚本命令摘录与介绍

[TOC]

帮助内容请参见【参考文档和官方Wiki】文件中的`脚本与命令`->`脚本命令目录`条目下的内容。

为了便于查找、对应官方文档位置，这里的命令分类与排序全部采用官方文档中的方式。官方文档把脚本命令按照功能性分类时，有两个分类目录，一个是主分类，另一个是子分类（Subcategories），这里把两种分类合并在一起记录。

部分命令同时被归于多个分类，这里只在某个分类中记录一次，不重复记录。

注：

+ 命令中的中括号/方括号、双引号是命令的语法规则，并不表示强调含义，随意省略或添加将会直接导致命令执行出错；
+ 命令中的单词如果在下方有解释说明，则该单词是这条命令的参数，使用命令时需要把这些参数替换为实际内容；
+ 参数中如果注明了“备选值”，请尽量在备选值中选择填写，否则可能会导致命令执行出错；
+ 在描述与讲解命令时使用了很多英文单词，这里并不是不给翻译，而是这些单词是官方在代码/编辑器中定义的专有敏感词，使用原单词可以防止出现谬误；
+ 部分命令会有多种重载形式，例如传入参数可多可少等情况，部分命令有需要的话我会将多种重载形式都列出，但是大部分都只写了最常用的形式；
+ 命令下面标注的[LocalArgument ![LA](./../assets/img/LA.png)]、[GlobalArgument ![GA](./../assets/img/GA.png)]、[LocalEffect ![LE](./../assets/img/LE.png)]、[GlobalEffect ![GE](./../assets/img/GE.png)]、[ServerExec ![SE](./../assets/img/SE.png)] 标签，含义依次是“本地执行参数”、“全局执行参数”、“执行效果只影响本地”、“执行效果影响全局”、“只能在服务器端执行”，详细信息请查阅文档中的Local与Global内容；

## 一、*Animations* 动画效果命令

## 二、*Arrays* 数组操作命令

## 三、*Artillery* 火炮命令

## 四、*Briefing* 目标、任务、笔记命令

## 五、*Broken Commands* 执行效果与预期不符、执行错误的命令

## 六、*Camera Control* 相机控制命令（与编辑器、宙斯相关的相机控制不在此列出）

## 七、*Config* 配置命令

## 八、*Containers* 容器操作命令（背包、背心等可以容纳物品的对象）

## 九、*Conversations* 对话、主题命令

## [Subcategory子分类]、 *Curator* 游戏策划者界面命令（宙斯模式的game master）

## 十、*Custom Panels* 显示面板命令（特指左右两个显示面板）

## 十一、*Custom Radio and Chat* 无线电、通讯命令

## 十二、*Diagnosis (Diag)* 代码诊断命令

## 十三、*Difficulty* 游戏难度命令

## 十四、*DLC* 与DLC相关命令

## 十五、*Dynamic Simulation* 动态模拟命令

## 十六、*Eden Editor* 编辑器命令

## 十七、*Environment* 环境命令（日期、时间、天气等）

### 1. *enableEnvironment* 控制环境动物与环境声音

[LocalEffect ![LE](./../assets/img/LE.png)]

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

### 2. *setTerrainGrid* 修改地形网格分辨率

[LocalEffect ![LE](./../assets/img/LE.png)]

[原链接](https://community.bistudio.com/wiki/setTerrainGrid)

修改地形网格分辨率（单位：米），从而影响地形中内容的精细复杂程度，例如远处地形的平滑程度、植被覆盖率、是否存在草皮等。

```script
setTerrainGrid grid;

grid: Number，处于(0,50]区间的数字。数字越小地形越精细，游戏越卡顿，反之地形越粗糙，游戏越流畅。
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

## [Subcategory子分类]、*Mines* 地雷命令

## 四十三、*Mission Information* 任务参数命令

## 四十四、*Mods and Addons* 扩展、插件命令

## 四十五、*Multiplayer* 多人游戏命令

### 1. *local* 检查对象是否处于本地状态

[GlobalArgument ![GA](./../assets/img/GA.png)]

[原链接](https://community.bistudio.com/wiki/local)

检查多人游戏中的某个对象是否处于本地状态，从而决定部分local脚本命令应该放在哪台机器上执行。

关于对象的不同状态（本地、全局），请查看这个[链接](https://community.bistudio.com/wiki/Multiplayer_Scripting#Locality)。

一些特殊的状态在此列出：单人游戏中所有对象都是local状态，多人游戏中游戏逻辑、游戏模块对于服务器是local的，多人游戏中地形对象对于所有机器都是local的。

```script
local object;

object: Object/Group，对象或组。被判定是否为local状态的对象/组。

return: Boolean，布尔值。对象是否是local状态，是为true，否为false。
```

```script
例：检查生成的hunter1对象是否是本地对象，如果是，则弹出消息提醒“hunter1 is local.”
hunter1 = "B_MRAP_01_F" createVehicle position player;
if (local hunter1) then { 
 hint format ["hunter1 is local."]; 
};
```

## 四十六、*Object Detection* 对象检测命令

## 四十七、*Object Manipulation* 对象操作命令

### 1. *createVehicle* 生成载具/建筑/物体对象

[GlobalEffect ![GE](./../assets/img/GE.png)]

[原链接](https://community.bistudio.com/wiki/createVehicle)

````script
createVehicle ["type", position, ["markers"], placement, "special"]

type: String，字符串。表示载具或物体对象名称。
position: PositionATL/PositionAGL/Position2D/Object，生成位置。可以使用特殊函数获取位置。
markers: Array，字符串数组。其中可以填写多个标记点名称（markers，且这里的名称指的不是标记点的描述，而是标记点的变量名）。
        注：如果填写了markers参数，载具会在给定位置与这些标记点之间随机选择一个位置生成。
placement: Number，数字。表示载具会生成在指定位置以placement为半径的圆内任意位置。
special: Sting，字符串。特殊状态。
        备选值："NONE"，载具生成时会自动寻找离给定位置最近的空位置，避免与周围模型发生碰撞和交错；"CAN_COLLIDE"，载具生成时不检查是否与周围模型发生碰撞，直接生成；"FLY"，如果待生成的是载具具备飞行能力，且有乘客，那么该载具会生成在默认高度的空中。
        注：该参数的默认值为"NONE"，如果留空或者填写""，那么会自动套用"NONE"值。

return: Object，生成的载具对象。如果生成出错或失败，返回objNull。
````

```script
例1：在玩家所在的位置（周围最近的空地处）生成一辆Hunter运输车
hunter1 = "B_MRAP_01_F" createVehicle position player;

例2：在名为hunter_marker的标记点（周围最近的空地处）生成一辆Hunter运输车
hunter2 = "B_MRAP_01_F" createVehicle getMarkerPos "hunter_marker";

例3：以玩家所在的位置为圆心，半径5米的圆环中任意位置（空地处）生成一辆Hunter运输车
hunter3 = createVehicle ["B_MRAP_01_F", position player, [], 5, "NONE"];

例4：在玩家所在的位置（不检测物品模型碰撞）生成一辆Hunter运输车
hunter4 = createVehicle ["B_MRAP_01_F", position player, [], 0, "CAN_COLLIDE"];

例5：在名为heli_marker的标记点位置生成一辆MH-9 Hummingbird直升机，且悬停在默认高度200米处（但是由于没有驾驶人员，它最终会下降高度直至坠毁）
heli1 = createVehicle ["B_Heli_Light_01_F", getMarkerPos "heli_marker", [], 0, "FLY"];

例6：使用spawn命令在生成载具对象时初始化该载具的属性。这里使用了例5的命令，直升机在生成后经过3秒，直升机自毁
heli1 = createVehicle ["B_Heli_Light_01_F", getMarkerPos "heli_marker", [], 0, "FLY"];
heli1 spawn
{
    sleep 3;
    _this setDamage 1;
};

例7：在spawn命令中直接嵌套生成载具对象并同时初始化载具的属性。这里使用了例6命令的另一种写法，效果与例6相同
[] spawn
{
    heli1 = createVehicle ["B_Heli_Light_01_F", getMarkerPos "heli_marker", [], 0, "FLY"];
    sleep 3;
    heli1 setDamage 1;
};

例8：在玩家所在位置生成一座Shop(Stone)建筑物
building1 = "Land_i_Shop_02_V3_F" createVehicle position player;
```

### 2. *allowCrewInImmobile* 损坏的载具是否能容纳乘客

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

### 3. *setDamage* 设置载具/建筑/物品对象的损坏程度

[GlobalArgument ![GA](./../assets/img/GA.png)] [GlobalEffect ![GE](./../assets/img/GE.png)]

[原链接](https://community.bistudio.com/wiki/setDamage)

```script
object setDamage damage;

object: Object，物品对象（可以是人、载具、建筑、物体）。
damage: Number，处于[0,1]区间的数字，可以为小数或整数。表示物品对象的损坏程度，数字越大损坏程度越大。当载具的损坏程度到达1时，载具会成为一具残骸。
        注：当载具损坏程度曾经到达过1，即已经成为残骸了，再使用这个命令把损坏程度降低，载具将仍旧是一具残骸，而不会被修复成可驾驶的载具；
            如果载具损坏程度到达1（残骸）时，玩家人物仍处于残骸中且未死亡（无敌状态或其他情况），有几率可能会导致玩家人物无法正常从载具中离开；
            如果载具损坏时曾导致油箱漏油，使用这条命令修复载具不会让油箱中的燃油重新加满，若要如此，请参看setFuel命令；
            使用这条命令设置载具损坏程度，载具不同部件的损坏是有先后顺序的，不同载具会有不同情况，请按照实际情况设置。

return: 无。


object setDamage [damage, useEffects];

object: Object，物品对象（可以是人、载具、建筑、物体）。
damage: Number，处于[0,1]区间的数字，可以为小数或整数（可以理解成从0%到100%）。表示物品对象的损坏程度，数字越大损坏程度越大。当载具的损坏程度到达1时，载具会成为一具残骸。
useEffects: Boolean，布尔值。决定物品对象在受到损坏后是否播放损坏过程的动画效果（主要是建筑、物体等对象较为明显，例如房屋倒塌效果）。默认值为true，即默认播放损坏过程的动画效果。
        备选值：true/false

return: 无。
```

```script
例1：设置玩家当前驾驶的载具损耗程度为0，修复至全新（完好无损）
vehicle player setDamage 0;

例2：生成一辆Hunter运输车，并设置这辆车的损耗程度为1（彻底报废，成为爆炸燃烧的残骸）
hunter1 = "B_MRAP_01_F" createVehicle position player;
hunter1 setDamage 1;

例3：在玩家位置生成一座Shop(Stone)建筑物，并彻底摧毁它，同时显示倒塌过程动画直至留下废墟
building1 = "Land_i_Shop_02_V3_F" createVehicle position player;
building1 setDamage [1, true];

例4：在玩家位置生成一座Shop(Stone)建筑物，并彻底摧毁它，只显示倒塌最后留下的废墟
building1 = "Land_i_Shop_02_V3_F" createVehicle position player;
building1 setDamage [1, false];
```

### 4. *setFuel* 设置载具对象的剩余燃油

[LocalArgument ![LA](./../assets/img/LA.png)] [GlobalEffect ![GE](./../assets/img/GE.png)]

[原链接](https://community.bistudio.com/wiki/setFuel)

```script
vehicle setFuel amount;

vehicle: Object，载具对象。
amount: Number，[0,1]区间的数字，可以是小数。数字越小载具燃油量越少，数字越大载具燃油量越多。
        备选值：0，空燃油；1，满燃油；其他0-1之间的小数。

return: 无。
```

```script
例1：设置玩家当前驾驶的载具为满燃油
vehicle player setFuel 1;

例2：设置玩家当前驾驶的载具剩余一半燃油
vehicle player setFuel 0.5;

例3：设置玩家当前驾驶的载具为空燃油
vehicle player setFuel 0;
```

### 5. *setVehicleLock* 设置载具对象是否上锁

[LocalArgument ![LA](./../assets/img/LA.png)] [GlobalEffect ![GE](./../assets/img/GE.png)]

[原链接](https://community.bistudio.com/wiki/setVehicleLock)

```script
vehicleName setVehicleLock lockState;

vehicleName: Object，载具对象。
lockState: String，字符串。
        备选值："UNLOCKED"，未上锁；"DEFAULT"，默认；"LOCKED"，上锁；"LOCKEDPLAYER"，对玩家上锁。

return: 无。
```

```script
例1：给玩家当前驾驶的载具上锁
vehicle player setVehicleLock "LOCKED";
```


## 四十八、*Particles* 粒子效果命令

## 四十九、*Performance Logging* 调试、日志命令

## 五十、*Pilot Camera* 载具目标命令（例如吊舱等）

## 五十一、*Positions* 位置坐标、高度命令

## 五十二、*Program Flow* 代码流程命令（循环、条件判断、跳转等）

### 1. *spawn* 控制/修改生成对象的属性

[原链接](https://community.bistudio.com/wiki/spawn)

这个命令可以用来操作各种对象，包括基本的游戏内对象（人物、载具等），也包括游戏逻辑中的对象（聊天、对话框等）。

使用spawn命令执行操作，该操作不会被立即执行，而是被加入一个调度器（[scheduler](https://community.bistudio.com/wiki/Scheduler)），由调度器控制这条命令何时被执行（取决于调度器的空闲状况）；如果有多条spawn命令加入调度器，并不总是先加入的命令先执行（有可能会乱序），如果你需要顺序执行，请查看[BIS_fnc_spawnOrdered](https://community.bistudio.com/wiki/BIS_fnc_spawnOrdered)命令。

```script
arguments spawn code;

arguments: Any value，任意变量值。在这里列出的变量/参数会被用于传入spawn后面的脚本代码中执行，如果不需要变量/参数，这里可以留空（使用[]留空数组）。
code: Code，脚本代码。需要如何创建对象，或如何修改生成对象的属性，有这里的脚本代码控制。

return: Script Handle，脚本句柄。用于检查这句spawn命令是否被执行完成，使用scriptDone命令可以直接得知是否执行完成，或者使用isNull命令判空从而间接得知。
```

```script
例1：生成一句全局聊天“Hello world!”
_handle = [] spawn {player globalChat "Hello world!"};

例2：生成一辆MH-9 Hummingbird直升机，并在三秒后自毁
heli1 = "B_Heli_Light_01_F" createVehicle position player;
heli1 spawn
{
    sleep 3;
    _this setDamage 1;
};
```

## 五十三、*Radio and Chat* 无线电、聊天信息命令

## 五十四、*Remote Control* 远程遥控命令

## 五十五、*Render Time Scope* 

## 五十六、*Roads and Airports* 道路、机场命令

## 五十七、*Ropes and Sling Loading* 绳索、悬吊命令

## 五十八、*RTD* 高级飞行模式命令

## 五十九、*Sensors* 传感器命令

### 1. *setVehicleRadar* 设置车辆雷达开关

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

### 1. *addMagazines* 添加弹匣

[GlobalArgument ![GA](./../assets/img/GA.png)] [GlobalEffect ![GE](./../assets/img/GE.png)]

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

### 2. *addWeapon* 添加武器

[LocalArgument ![LA](./../assets/img/LA.png)] [GlobalEffect ![GE](./../assets/img/GE.png)]

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

### 3. *removeWeapon* 移除武器

[LocalArgument ![LA](./../assets/img/LA.png)] [GlobalEffect ![GE](./../assets/img/GE.png)]

[原链接](https://community.bistudio.com/wiki/removeWeapon)

移除对象的武器**不会把该武器对应的所有弹匣一并移除**，移除弹匣需要另外操作，否则下次添加相同的武器时原来的弹匣还是存在的。

如果尝试移除对象没有的武器，代码不会报错，而是忽略这次移除操作。

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

### 4. *removeWeaponGlobal* 移除部队单位装备的武器

[GlobalArgument ![GA](./../assets/img/GA.png)] [GlobalEffect ![GE](./../assets/img/GE.png)]

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

例3：删除所有IFV-6a Cheetah大防空车的泰坦地对空AA导弹
{
    if (typeOf _x == "B_T_APC_Tracked_01_AA_F") then {
        _x removeWeaponGlobal "missiles_titan_AA";
    };
} forEach vehicles;
```

### 5. *setAmmo* 设置武器弹匣中的剩余弹药数量

[LocalArgument ![LA](./../assets/img/LA.png)] [GlobalEffect ![GE](./../assets/img/GE.png)]

[原链接](https://community.bistudio.com/wiki/setAmmo)

设置武器已经装载的弹匣中的弹药数量（而不是弹匣数量），且只会修改当前正在使用的弹匣中的弹药数量，其他备弹弹匣中的弹药数量不会受到影响。

```script
unit setAmmo [weapon, count];

unit: Object，对象。可以是人或载具。
weapon: String，字符串。武器的名称，可以使用特殊对象获取武器信息。
count: Number，大于等于0的整数。表示弹匣中的弹药数量。
        注：如果所填数量大于弹匣所能装下弹药的数量上限，会被自动设置为满弹匣的数量，而不是无限制。

return: 无。
```

```script
例1：设置玩家手枪的弹匣中的弹药数量为10发
player setAmmo [handgunWeapon player, 10];

例2：设置玩家当前拿着武器的弹匣中的弹药数量为10发
player setAmmo [currentWeapon player, 1];

例3：设置玩家当前驾驶载具的20mm机炮当前弹匣中的弹药数量为100发
vehicle player setAmmo ["weapon_Fighter_Gun20mm_AA", 100];
```

## 七十五、*Variables* 变量操作命令

## 七十六、*Vehicle in Vehicle Transport* 载具运输命令

## [Subcategory子分类]、*Vehicle Inventory* 载具仓储命令

### 1. *setVehicleAmmo* 设置载具备弹数量

[LocalArgument ![LA](./../assets/img/LA.png)] [GlobalEffect ![GE](./../assets/img/GE.png)]

[原链接](https://community.bistudio.com/wiki/setVehicleAmmo)

设置载具的整体备弹数量（仅与系统载具类型预设的`满备弹量参照`相比，或者与脚本执行后的载具`满备弹量参照`相比）。

+ 想要设置一辆载具当前的整体备弹数量，需要一个`满备弹量参照`。在默认情况下，以一辆载具的系统预设值作为满备弹量参照；但是如果事先使用脚本命令修改了一辆载具的武器备弹情况（同一局游戏内，或是脚本自定义的载具对象），那么这辆载具的满备弹量参照就会变成脚本修改之后的值。

+ ~~载具上**每一种武器**的备弹量都是单独计算的，且每一种武器的**总共弹匣数量**、**已装载弹匣中的弹药数量**也是单独计算的（先算弹匣数量，如果弹匣数量只有1个，再算已装载弹匣中的弹药数量）~~。//TODO 20210119 暂时还未发现确切的规律，官方文档下面已经有一些玩家使用意见，后续需要完善，下面的举例2同理
+ 仅与满载弹量相比计算，而不会在上一次的修改结果基础上继续计算。

举例：

1. 例如F/A181默认装载了20mm机炮450发（只有一个弹匣），那么这个450发就是F/A181 20mm机炮的默认满备弹量参照。这时使用setVehicleAmmo命令修改备弹量，参照数量就是450，取1就是450、取0.5就是225、取0.1就是45。
2. ~~如果游戏中使用例如addMagazines等命令给F/A181 20mm机炮弹匣数量修改到10个，那么这架181此时有两个满备弹量参照，其一**总共有10个弹匣**（包括已装载的一个弹匣）、其二**每个弹匣满弹药数量为450发**。          这时如果使用setVehicleAmmo命令修改备弹量，例如取值0.5，首先会计算**总共弹匣数量**（即参照数量为10），取0.5就是总共弹匣数量变成5，又因为弹匣数量大于1，所以不计算已装载弹匣中的弹药数量，最终结果就是一个5个弹匣，其中一个已装载，且已装载的弹匣中是满弹药450发。          如果使用setVehicleAmmo且取值0.1，首先计算**总共弹匣数量**（参照数量10），取0.1为总共1个弹匣，继续计算**已装载弹匣中的弹药数量**，取0.1为弹药数量45发，最终结果就是只有1个弹匣且这个弹匣已装载，其中只有45发弹药。~~

```script
vehicleName setVehicleAmmo value;

vehicleName: Object，载具对象。
value: Number，[0,1]区间的数字，可以是整数或小数。数字越小，备弹量越少，数字越大，备弹量越多。
        备选值：0，空载弹；1，满载弹；其他[0,1]区间小数；

return: 无。
```

```script
例1：设置玩家当前驾驶的载具为满备弹量
vehicle player setVehicleAmmo 1;

例2：设置玩家当前驾驶的载具载弹量为满备弹量参照的一半
vehicle player setVehicleAmmo 0.5;

例3：设置玩家当前驾驶的载具为空备弹量
vehicle player setVehicleAmmo 0;
```




## 七十七、*Vehicle Loadout* 载具外部装备命令（装甲、外挂等）

## 七十八、*Waypoints* 路径点命令

## 七十九、*Weapon Pool* 武器池命令（操作一个预先设定的武器集合）

## 八十、*Weapons* 武器、供弹命令

## 八十一、*Zeus (Curator)* 宙斯命令
