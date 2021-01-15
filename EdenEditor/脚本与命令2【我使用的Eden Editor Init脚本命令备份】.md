<!--
 * @Description: 
 * @Version: 
 * @Author: Ultronxr
 * @Date: 2021-01-11 21:25:36
 * @LastEditors: Ultronxr
 * @LastEditTime: 2021-01-15 16:36:49
-->

# 我使用的Eden Editor Init脚本命令备份

[TOC]

## Init脚本命令在哪里

一、全局Init脚本：
进入Eden Editor后，我们就开始了对一个任务的编辑，点击菜单栏中的 `Attributes` -> `General` -> `Init` 选项，这个输入框里填写的脚本命令会在保存任务的同时记录在配置中，并会在任务游戏启动的同时预执行，避免每次进入游戏之后输入命令的麻烦。

需要注意的是，这里填写的脚本命令是执行在全局（global）的，任何只适用于局部（local）的对象和命令都不能直接填写在这里，否则会报错。

二、局部Init脚本：
直接双击一个对象（包括：人、载具、武器装备等单位），查看 `Object:Init` 选项卡，这个Init输入框中的命令会在游戏开始后，该对象生成时执行（local）。

## 全局Init脚本命令备份

复制脚本时请勿将第一行注释一起复制，否则会报错。

```script
// global init script

enableEnvironment [false, false];
setTerrainGrid 50;
{
    _x removeWeaponGlobal "weapon_AMRAAMLauncher";
    _x removeWeaponGlobal "weapon_BIM9xLauncher";
    _x allowCrewInImmobile true;
} forEach vehicles;
```

## 局部Init脚本命令备份

复制脚本时请勿将第一行注释一起复制，否则会报错。

```script
// FA181 script

vehicle player addMagazines ["240Rnd_CMFlareMagazine", 10];
vehicle player addMagazines ["magazine_Fighter01_Gun20mm_AA_x450", 20];

vehicle player addMagazines ["7Rnd_Rocket_04_HE_F", 20];
vehicle player addWeapon "Rocket_04_HE_Plane_CAS_01_F";

vehicle player addMagazines ["7Rnd_Rocket_04_AP_F", 20];
vehicle player addWeapon "Rocket_04_AP_Plane_CAS_01_F";





```
