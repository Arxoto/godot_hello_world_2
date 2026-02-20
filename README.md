# Godot hello world

## 项目结构

垂直切分（按功能/领域），以下部分命名为示例，并且由于层级限制没法特别细分

todo 参考 <https://dev.epicgames.com/documentation/zh-cn/unreal-engine/gameplay-framework-in-unreal-engine>

```
project/
├── .git/                         # Git 版本库
├── .gitattributes                # Git LFS 配置（二进制文件管理）
├── .gitignore                    # Git 忽略规则
├── .gitmodules                   # Git 子模块索引
├── README.md                     # 项目说明、模块依赖关系、开发指南
│
├── .godot/                       # 编辑器缓存
├── project.godot                 # Godot 项目核心配置
│
├── docs/                         # 项目文档（设计文档、API说明）
│   └── .gdignore                   # 空文件，让 Godot 忽略此目录
│
├── addons/                       # 【插件目录】
│   ├── third_party_plugin/         # 第三方现成插件（ Plugin 是扩展编辑器功能的 Addon ）
│   ├── third_party_addon/          # 第三方现成插件（ Asset Library 下载）
│   ├── custom_addon/               # 自己开发的、计划跨项目复用的插件
│   └── some_ext/                   # GDExtension 的编译产物（包括调试阶段）
│       ├── some_ext.gdextension      # 配置文件（必须）
│       ├── bin/                      # 存放编译好的动态库
│       └── examples/                 # 演示场景（可选）
│
├── framework/                    # 【框架目录】（内容可以是 Git Submodule ）
│   ├── base_utils/                 # 基础工具库（业务无关）
│   └── some_ext/                   # GDExtension 的项目源码（严格控制版本）
│
├── modules/                      # 【垂直功能模块】（领域驱动）
│   ├── autoload/                   # 自动加载的全局单例（项目特有）
│   ├── core_utils/                 # 基础工具库（与游戏相关）
│   ├── components/                 # 细粒度、可复用的组件
│   ├── ui/                         # 全局 UI 模块
│   │   ├── hud/                      # 主 HUD
│   │   ├── menus/                    # 各种菜单
│   │   ├── notifications/            # 全局通知
│   │   └── themes/                   # 主题样式
│   ├── level/                      # 关卡模块
│   ├── factories/                  # 对象工厂
│   │   ├── xxx_data_factory          # 某某静态配置
│   │   └── xxx_random_factory        # 某某随机生成
│   ├── gameplay_features/          # 核心玩法机制
│   │   ├── combat/                   # 战斗模块
│   │   ├── inventory/                # 背包模块
│   │   └── quest/                    # 任务模块
│   └── game_features/              # 具体游戏内容
│       ├── environment/              # 集成度较高的环境
│       ├── items/                    # 可交互物品
│       ├── enemies/                  # 敌人 NPC
│       ├── friendlies/               # 友好 NPC
│       └── player/                   # 玩家
│
├── assets/                       # 【原始源文件】（可选，美术/音频源文件）
│   ├── art/                        # PSD/Krita 源文件
│   ├── audio/                      # WAV 工程文件
│   └── models/                     # BLEND 源文件
│
└── tests/                        # 测试
    ├── unit/                       # 单元测试（也可放在各个模块下面）
    ├── integration/                # 集成测试
    └── performance/                # 性能测试

```
