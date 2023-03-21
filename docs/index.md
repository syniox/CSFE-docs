# Crowd sourcing platform (front-end)

## Hints

- 前端master已开启分支保护 请使用merge向主分支提交信息
- 会将todo分成gitlab上的issue（然后可以assign给自己表示认领这个任务，当然assign别人也可行），可以开PR时引用该issue
- 终端输入`git config --global user.name <学号> && git config --global user.email <学号>@secoder.net`让软工平台记录你写的代码
    - 或许更好的方案：在某个git仓库目录下设置仅对该仓库生效的个人信息：`git config user.name <学号> && git config user.email <学号>@secoder.net`
- 确保仓库存在合理的`.gitignore`文件，忽略掉依赖和程序运行生成的文件，以免成为助教所说的第一周提交几十万行代码的组x

## TODO-List

- [ ] Basis
    - [ ] nuxi typecheck
    - [ ] eslint
- [ ] APIs
    - [ ] 需求方/发布方识别 考虑因素：
        - [x] ~~前端发送用户类别让后端判断是否正确，还是让后端返回用户类型？~~ 后端API会返回role
        - [ ] 前端是否分开注册，是否分开登录
    - [x] ~~文档中权限申请的含义？一个用户是否可以身兼数职~~ 一用户一身份，管理员审核需求方发布的内容
    - [ ] 页面鉴权问题（前端可使用auth middleware配置）后端是否需要一个接口判断该用户是否有权限访问该页面
    - [ ] 登录/注册页错误处理/显示
        - [ ] 页面可用snackbar
        - [ ] 错误信息等后端API？
        - [ ] CORS？
- [ ] Pages
    - [ ] CSS选型 ChatWJS or UI组件库
    - [ ] 不同管理人员的登录界面？


## 实现架构

