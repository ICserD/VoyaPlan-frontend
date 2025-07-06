# VoyaPlan-frontend

## 项目简介

VoyaPlan 项目的前端项目。VoyaPlan 是一款开源的智能旅游规划系统，致力于为用户提供一站式的旅游规划服务，涵盖 AI 个性化出行规划、游记分享等功能。

## 项目文档

- 需求文档：https://xqjxrzdxmq8.feishu.cn/wiki/VCZMwHEwQiSbTWkhowHcySKJnah?from=from_copylink
- 原型设计文档：https://www.figma.com/design/wlCm2r1bLosW5cNhx55XlT/VoyaPlan?node-id=0-1&p=f
- Api 接口文档：https://apifox.com/apidoc/shared-e537625c-ff0d-44fa-8cef-eea4b5a5047d

## 项目结构
```shell
.
├── README.md
└── VoyaPlan-front
    ├── docs
    │   └── VoyaPlan-frontend_Installation_Guide.md # 前端安装指南
    └── VoyaPlan
        ├── env.d.ts
        ├── index.html
        ├── node_modules  # 依赖包
        │   └── ......
        ├── package.json
        ├── package-lock.json
        ├── public
        │   └── favicon.ico
        ├── src  # 源代码
        │   ├── apiConfig.ts # 接口配置
        │   ├── App.vue
        │   ├── assets  # 静态资源
        │   ├── components # 组件
        │   ├── main.ts 
        │   ├── router # 路由
        │   └── views # 页面
        ├── tsconfig.app.json
        ├── tsconfig.json
        ├── tsconfig.node.json
        └── vite.config.ts
```

## 开发规范

### 基本规范

#### 代码风格
- 参见 vue 风格指南：https://v2.cn.vuejs.org/v2/style-guide

#### 提交规范
- **提交信息**：每次提交都应包含清晰、简洁的提交信息，描述该提交的内容和目的，如果是简单的功能，可以不用写详细描述

  - 提交信息格式：

    ```
    <类型>(<模块>): <简短描述>
    ```

    - 示例：

      ```
      feat(auth): add login API
      ```

  - 提交类型常见的有：

    - **feat**：新功能
    - **fix**：修复 bug
    - **docs**：文档更改
    - **style**：代码格式更改（不影响功能）
    - **refactor**：代码重构
    - **test**：增加测试
    - **chore**：其他修改（如更新构建工具等）

- **每个提交尽量只做一件事**：避免大规模的提交，要保证每个提交都能独立工作。

#### 分支管理

> 减少合并冲突的好习惯：
>
> 1. 定期去develop分支同步代码
>
> ```shell
> # 切换到主开发分支
> git checkout develop
> 
> # 拉取远程仓库最新代码
> git pull origin develop
> 
> # 切换回正在开发的分支, 假设为login界面
> git checkout feature/LoginPage
> 
> # 将主分支最新代码合并到当前开发的分支
> git merge develop
> ```
>
> 2. 定期更新自己的分支
>
> ```shell
> # 切换到当前开发分支
> git checkout feature/LoginPage
> 
> # 拉取远程主开发分支的最新代码并合并
> git merge origin/develop
> ```
>
> 

- **主分支（main/master）**：始终保持可部署的稳定版本，避免直接在该分支上进行开发。

- **开发分支（develop）**：所有新功能和 bug 修复都应提交到开发分支上，开发完成后通过 Pull Request（PR）合并到主分支。

- **功能分支**：

  每个新功能或 bug 修复应该从 `develop` 分支拉出一个新的功能分支，命名规则为：

  - **feature/<功能名称>**：用于开发新功能。
  - **bugfix/<bug描述>**：用于修复 bug。

  示例：

  ```
  feature/login-page
  bugfix/fix-header-position
  ```


- **避免直接在主分支（`main` 或 `master`）上提交**：所有开发都应该在 `develop` 分支或功能分支上进行。