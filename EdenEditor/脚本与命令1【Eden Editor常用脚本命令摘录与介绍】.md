<!--
 * @Description: 
 * @Version: 
 * @Author: Ultronxr
 * @Date: 2021-01-11 21:25:36
 * @LastEditors: Ultronxr
 * @LastEditTime: 2021-01-12 18:17:59
-->

# Eden Editor编辑器常用脚本命令摘录与介绍

帮助内容请参见【参考文档和官方Wiki】文件中的 `## 脚本与命令` 二级标题内容。

需要注意的是：

+ 命令中的中括号/方括号、双引号是命令的语法规则，并不表示强调含义，随意省略或添加将会直接导致命令执行出错；
+ param、param1、param2等单词代表了命令中的“参数”，使用命令时需要把这些单词替换为实际内容；
+ 参数中如果注明了“备选值”，请尽量在备选值中选择填写，否则可能会导致命令执行出错；
+ 在描述与讲解命令时使用了很多英文单词，这里并不是不给翻译，而是这些单词是官方在代码/编辑器中定义的专有敏感词，使用原单词可以防止出现谬误；

## 一、环境与地形命令

### 控制环境效果

修改环境动物和环境声音开关效果。
详见[原链接](https://community.bistudio.com/wiki/enableEnvironment)

```script
enableEnvironment [ambientLife, ambientSound];

ambientLife: Boolean，布尔值。开/关环境动物效果。
        备选值：true/false
ambientSound: Boolean，布尔值。开/关环境声音。
        备选值：true/false

return: 无
```

```text
例：关闭环境动物和环境声音
enableEnvironment [false, false];
```

### 修改地形网格

修改地形中内容的精细复杂程度，例如远处地形的平滑程度、植被覆盖率、是否存在草皮等。
详见[原链接](https://community.bistudio.com/wiki/setTerrainGrid)

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

## 二、武器装备命令

### 全局（global）删除武器

详见[原链接](https://community.bistudio.com/wiki/removeWeaponGlobal)

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

例3：删除所有xxxxxxxxxxxx载具装备的xxxxxxxxxxxx
{
    if (typeOf _x == "O_Heli_Attack_02_black_F") then {
        _x removeWeaponGlobal "rockets_Skyfire";
    };
} forEach vehicles;
```

### 生成载具

详见[原链接](https://community.bistudio.com/wiki/createVehicle)

```script
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
```

```script
例1：

```

## 三、行为命令

### 修改损坏的载具是否能容下乘客

修改当载具受到损坏时，是否能让乘客继续停留在载具中。
对AI的行为影响：如果设置为是，AI会继续待在遭受损坏的地面载具/飞机中继续驾驶，而不是马上逃脱/跳伞；如果设置为否，AI会在载具受到损坏时马上脱离逃生。
详见[原链接](https://community.bistudio.com/wiki/allowCrewInImmobile)

```script
param1 allowCrewInImmobile param2;

param1: 只能是载具对象，如：vehicle、_vehicle等
param2: 备选值：true/false
```

```script
例1：让处于局部（local）的所有载具对象能在损坏时容纳乘客（仅限单人游戏已经开始时使用）
_vehicle allowCrewInImmobile true; 

例2：让处于局部（local）和全局（global）的所有载具对象能在损坏时容纳乘客（用于在Editor的Init时使用）
{
    _x allowCrewInImmobile true;
} forEach vehicles;
```

## 四、其他游戏性命令
