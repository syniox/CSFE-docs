# Crowd sourcing platform (front-end)

## 注意事项

- 终端输入`git config --global user.name <学号> && git config --global user.email <学号>@secoder.net`让软工平台记录你写的代码
    - 或在某个git仓库目录下设置仅对该仓库生效的个人信息：`git config user.name <学号> && git config user.email <学号>@secoder.net`
- 确保仓库存在合理的`.gitignore`文件，忽略掉依赖和程序运行生成的文件，防止成为助教所说的第一周提交几十万行代码的组

## TODO-List

### 基础设施
- [ ] Basis
    - [ ] nuxi typecheck
    - [ ] eslint
- [ ] APIs
    - [ ] 需求方/发布方识别 考虑因素：
        - [ ] 前端是否分开注册，是否分开登录
        - [ ] 前端发送用户类别，让后端判断是否正确，还是后端返回用户类型？
- [ ] Pages
    - [ ] CSS选型 ChatWJS or UI组件库


## 实现架构

