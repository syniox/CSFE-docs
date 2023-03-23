# Crowd sourcing platform (front-end)

## Hints

- 前端master已开启分支保护 请使用merge向主分支提交信息
- 可将todo分成gitlab上的issue（然后可以assign给自己表示认领这个任务，当然assign别人也可行），可以开PR时引用该issue

### 调试

- sep容器管理里面可以看log
- 输出调试：`console.log(...)`
- 由于CORS问题，前端反向代理是必须的。每次build完用nginx反代太耗时间，但nuxt似乎不大支持rewrites功能，在考虑用middleware实现或。

## TODO-List


- [ ] Basis
    - [ ] **实现nuxt rewrites**
    - [ ] nuxi typecheck
    - [ ] eslint
    - [ ] sonarqube
- [ ] APIs
    - [x] 需求方/发布方识别 考虑因素：
        - [x] ~~前端发送用户类别让后端判断是否正确，还是让后端返回用户类型？~~ 后端API会返回role
        - [x] 前端是否分开注册，是否分开登录
    - [x] ~~文档中权限申请的含义？一个用户是否可以身兼数职~~ 一用户一身份，管理员审核需求方发布的内容
    - [ ] 页面鉴权（前端可使用auth middleware配置）后端是否需要一个接口判断该用户是否有权限访问该页面
    - [ ] 登录/注册页错误处理/显示
        - [ ] 页面UI：或可snackbar
        - [x] 错误信息等后端API？
        - [x] CORS？
- [ ] Pages
    - [ ] CSS选型 ChatWJS or UI组件库
    - [ ] 不同管理人员的登录界面？


## 实现架构

