# Crowd sourcing platform (front-end)


## 开发规范(来自yjx的记录)

1. dev从master拉取，dev和master都只能被merge，不要push进去
2. 不要merge进master除非是迅速改bug，可以拉取一个分支并且merge进去，正确的做法是merge进dev，确定dev没有问题才能merge dev => master
3. 一定维护master的稳定性，不稳定测试和开发在dev上进行，保证演示不出bug
4. 每一个commit后面#加上issue

## 故障速查

1. 确保当前正在访问的页面不是cached的页面（disable cache/无痕模式）
2. 检查报错信息正误

## Hints

- 前端master已开启分支保护 请使用merge向主分支提交信息
- 可将todo分成gitlab上的issue（然后可以assign给自己表示认领这个任务，当然assign别人也可行），可以开PR时引用该issue

### 调试

- sep容器管理里面可以看log
- 输出调试：`console.log(...)`
- 由于CORS问题，前端反向代理是必须的。每次build完用nginx反代太耗时间，但nuxt似乎不大支持rewrites功能，在考虑用middleware实现或找现成轮子。

## TODO-List

- [ ] Basis
    - [x] **实现nuxt反向代理**
    - [ ] nuxi typecheck
    - [x] eslint
    - [x] sonarqube
    - [ ] async函数使用 （待参考小作业）
    - [x] master dev 双部署
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
    - [x] CSS选型 ~~ChatWJS or UI组件库~~ Element ui plus
    - [x] 不同管理人员的登录界面？


## 实现架构

现有架构见gitlab

### users/

#### login/
#### register/

### tasks/

#### [id]/

##### modify
##### upload

#### Establish

