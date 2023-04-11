# Crowd sourcing platform (front-end)

## 需求文档

[基础文档](https://docs.qq.com/doc/DV2VGcVhLWXhVcHZt)  
[需求QA](https://docs.qq.com/doc/DZVFuRUFvWWhiUkln)

## 开发规范(来自yjx的记录)

1. dev从master拉取，dev和master都只能被merge，不要push进去
2. 不要merge进master除非是迅速改bug，可以拉取一个分支并且merge进去，正确的做法是merge进dev，确定dev没有问题才能merge dev => master
3. 一定维护master的稳定性，不稳定测试和开发在dev上进行，保证演示不出bug
4. 每一个commit后面#加上issue

## 故障速查

1. 确保当前正在访问的页面不是cached的页面（disable cache/无痕模式）
2. 检查报错信息正误

## Issues

- [ ] 前端注册用户名带'-'

## apifox补充

tasks.status:

- PENDING = 1 需求方未确认
- RECRUITING = 2 招募中
- IN PROGRESS = 3 满人了，正在标
- COMPLETED = 4 trivial

## Hints

- 前端master已开启分支保护 请使用merge向主分支提交信息
- 可将todo分成gitlab上的issue（然后可以assign给自己表示认领这个任务，当然assign别人也可行），可以开PR时引用该issue
- commit规范参考：https://www.conventionalcommits.org/en/v1.0.0/

### 调试

- sep容器管理里面可以看log
- 输出调试：`console.log(...)`
- 由于CORS问题，前端反向代理是必须的。每次build完用nginx反代太耗时间，但nuxt似乎不大支持rewrites功能，在考虑用middleware实现或找现成轮子。

## 待讨论问题

1. 关于动态路由的问题 我看到vue-router要加':'表示动态，但是nuxt有file-based routing，使用navigateTo时不必单独加':'

现在不统一之后盖起来
如果我没理解错jxgg的思路的话，我目前觉得是有三条路

- 就按现在这样，navigateTo然后route.$params.var.slice(1)拼接的时候把':'删掉（又不是不能用.jpg
- 走nuxt路线 直接上navigate不加':'
- 走vue router路线 用router.push实现跳转

2. 已完成任务是否开放“审”的按钮？改成查看？

## Highlights

- [ ] el-alert替代alert
- [ ] useFetch(vueuse) + vue Suspense进行async加载

- [x] Basis
    - [x] **实现nuxt反向代理**
    - [x] nuxi typecheck
    - [x] eslint
    - [x] sonarqube
    - [x] async函数使用 （待参考小作业）
    - [x] master dev 双部署
- [x] APIs
    - [x] 需求方/发布方识别 考虑因素：
        - [x] ~~前端发送用户类别让后端判断是否正确，还是让后端返回用户类型？~~ 后端API会返回role
        - [x] 前端是否分开注册，是否分开登录
    - [x] ~~文档中权限申请的含义？一个用户是否可以身兼数职~~ 一用户一身份，管理员审核需求方发布的内容
    - [x] 页面鉴权（前端可使用auth middleware配置）后端是否需要一个接口判断该用户是否有权限访问该页面
    - [x] 登录/注册页错误处理/显示
        - [ ] 页面UI：或可snackbar
        - [x] 错误信息等后端API？
        - [x] CORS？
- [x] Pages
    - [x] CSS选型 ~~ChatWJS or UI组件库~~ Element ui plus
    - [x] 不同管理人员的登录界面？


## 测试架构

测试框架[vitest](https://vitest.dev)，使用[nuxt-vitest](https://github.com/danielroe/nuxt-vitest)与nuxt进行整合。  
组件框架@vue/test-utils，想调试组件内逻辑必须品，使用文档[这里看](https://test-utils.vuejs.org)
E2E框架目前没有（看上去不要求x

测试库会识别仓库内所有的*.tests.(ts+js)或*.spec.(ts+js)文件，但是建议测试文件放在tests/下或者和组件在一起
示例：`~/tests/TaskPresent.spec.ts`


## 实现架构


### 代码架构

现有架构见gitlab

#### users/

##### login/
##### register/

#### tasks/

##### [id]/

###### modify
###### upload

##### Establish

