# LLAntiCheat-release
## Description

English | [简体中文](README_zh-cn.md)  
Free AntiCheat plugin for LiteLoaderBDS  
Powered by community, continuously updating  
Features from existing open source solutions will not be added unless the integration would lead to a better experience  
If you want to block Toolbox players, you can install [AntiToolbox](https://github.com/ShrBox/AntiToolbox)  
Due to the proliferation of modified versions of Toolbox, the interception rate of this solution is low, and it is technically impossible to solve it

## Features

- Anti Xray
- High Performance Ore Obfuscate
- Anti XpOrb
- Fix funnel bug
- ~~Anti illegal using command block and structure block~~(Mojang have fixed it)
- Anti KillAura
- Anti illegal enchant
- Fix debug packet modify game data
- Fix crash caused by push chest
- ~~Fix stonecutter change item data~~(Mojang have fixed it)
- ~~Add Anvil cost check(Anti fake exp)~~(Mojang have fixed it)
- Anti FakeName
- ~~Fix thorns's bug: copy item and crash server~~(Mojang have fixed it)
- Fix furnace copy item
- Fix funnel minecart copy item
- Fix furnace exp bug
- Anti AutoClick
- Anti fly and teleport(BDS built-in)
- Anti range destruction(BDS built-in)

## Installation

### Install via Lip (beta)

You should have Lip installed first. Refer to <https://github.com/LiteLDev/Lip>.

Then run the command below under the root of BDS:

```shell
lip install github.com/Tooth-Hub/LLAntiCheat
```

For a specific version, run commands like:

```shell
lip install github.com/Tooth-Hub/LLAntiCheat@1.3.0
```

### Install manually

[Download](https://github.com/LiteLDev/LLAntiCheat-release/releases)

## Addition

> Do not put this plugin into any integration package directly and redistribute it
> If you would like to make an integration package, please use Lip tooth and set this plugin as a dependency

In order to ensure the effect, please ensure that the LiteLoaderBDS has not been modified  
If necessary, you can cooperate with [LLEssentials](https://github.com/LiteLDev/LLEssentials) to hide the seed  
LLAC will change `correct-player-movement` and `server-authoritative-block-breaking` to `true` by default  
Please make the type of `server-authoritative-movement` is `"server-auth"` or `"server-auth-with-rewind"` in `server.properties`

**In order to protect proprietary software, this plugin uses other technologies to protect the binary files released by us. In case of false positives from anti-virus software, please join the (static scan) whitelist. To ensure your safety, it is recommended not to close anti-virus software or disable firewalls**

## Feedback&Feature Request

WangYneos@outlook.com

## Feedback group

LLAC dedicated QQ Group: 931871701  
QQ Groups, telegram channel and discord server of LL

## Configuration File

Version: 1.5.2  
Translation not 100% accurate

```jsonc
{
    //反矿物透视
    //Anti x-ray
    "AntiXray": {
        //开关
        //Switch
        "AntiXrayObfs": true,
        //强制透明的方块(ID)
        //Force transparent blocks(ID)
        "ForceTransparentBlocks": []
    },
    "BuiltinPunish": {
        //作弊次数到达CheatCountBan执行的命令
        //Command executed when the number of cheats reaches CheatCountBan
        "BanCommand": "ban {player}",
        "CheatCountBan": 8,
        "CheatCountKick": 4,
        "CrashAsKick": false,
        "KickMessage": "[AntiCheat] You have been kicked for {reason}"
    },
    //附魔相关内容
    //Enchant related information
    "Enchant": {
        //最大等级，超过该等级的附魔将被清除
        //Max Level for Enchantments, Enchantments that exceed this level will be removed
        "MaxLevel": 5
    },
    //原版漏洞相关修复
    //Fixes for bugs that existed in the original BDS
    "FixOriginalBugSwitch": {
        //箱子崩服
        //Fix Illegal Chest that cause Server Crash
        "ChestCrash": true,
        //修复活塞推箱子复制物品
        //Fix CopyItem Bug when the Container is pushed by the piston
        "HopperReplicate": true,
        //修复异常堆叠
        //fix illegal itemStack Stacking which may be used for Copy Items
        "IllegalStack": true
    },
    //杀戮光环
    "KillAura": {
        //攻击间隔时间(毫秒)
        //Attack interval time(ms)
        "AttackIntervalMs": 75,
        //忽略的实体
        //Actors ininored
        "CPSIgnoreActors": [
            "minecraft:boat",
            "minecraft:minecart"
        ],
        //是否检查KillAura
        "CheckKillAura": true,
        //开启假人检测
        //Enable fake player for detection
        "EnableFakePlayer": false,
        //假人移动角度
        //Fake player's move angle
        "FakePlayerMoveAngle": 18,
        //假人的名称
        //Fake player's name
        "FakePlayerName": "LLAC",
        //假人移动次数
        //Fake player's move count
        "FakePlayerUpdateCount": 60,
        //假人移动间隔时间
        //Fake player's move interval
        "FakePlayerUpdateInterval": 2,
        //每秒杀死的实体数，超过此数量会判定玩家作弊
        //The number of entities killed in seconds, more than this number will determine the player cheating
        "KillPerTenSecond": 8
    },
    //功能开关
    "Switch": {
        //  是否检测刷经验行为
        //  Whether to detect illegal Experience or Level Request
        "AntiXpHack": true,
        //  反矿透
        //  Prevent Player from Using Xray Mods to find Ores
        "AntiXray": true,
        // 是否检测玩家破坏方块
        // Whether to detect player's breaking behavior
        "BreakingDetection": true,
        //  检查附魔
        //  Check Item's Enchantment
        "CheckEnchant": true,
        //  禁用命令方块矿车
        //  Disable Minecart with CommandBlock
        "DisableCommandBlockMinecart": true,
        //  禁用NPC
        //  Disable NPC
        "DisableNPC": true,
        //  阻止非法昵称
        //  Prevent invalid name
        "InvalidName": true,
        // 是否检测玩家移动
        // Whether to detect player movement
        "MovementDetection": true,
        //  阻止玩家在服务器中更换皮肤，用于阻止Horion的Crash功能
        //  Prevent player change skin in the server, for prevent horion's crash function
        "PreventChangeSkin": true,
        //  阻止在睡觉时丢出物品
        //  Prevent player drop item while sleeping
        "PreventSleepDrop": true
    }
}
```
