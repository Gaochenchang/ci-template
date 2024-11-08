# ci-template

该模版用于为项目部署 CI 测试。

当前模版进行的测试包括两个阶段：
 - pre_check: 预检查。包括代码风格检查、commit message 检查、commit branch 检查、code 拼写检查等。
 - build: 编译

## 目录结构
```
ci-template
├── .gitlab
│   └── ci
│       ├── build.yml                # 编译
│       ├── pre_check.yml            # 预检查
│       └── rules.yml                # 触发规则
├── tools
│   ├── check_copyright_config.py    # 检查版权配置
│   └── utils.sh                     # 工具脚本
├── .gitlab-ci.yml                   # CI 配置文件，用于 CI 入口文件
├── conftest.py                      # pytest 配置文件
├── README_CN.md
└── README.md
```

## 使用方法

1. 将 `ci-template` 文件夹复制到你的项目根目录下。
2. 参考右侧 `Settings` -> `CI/CD` -> `Variables` 中的变量，将其添加到您的项目中：
    - CHECK_TOOLS_PATH
    - MULTIMEDIA_DOCKER_REGISTRY
    - CHECK_FORMAT_TOOL_REPO
    - DOCKER_AUTH_CONFIG
    - GITLAB_KEY
    - GITLAB_SSH_SERVER
    - IDF_PATH
    - IDF_REPOSITORY
3. 为您的项目配置 Runner。 在右侧 `Settings` -> `CI/CD` -> `Runners` 中使能可用的 Runner。
