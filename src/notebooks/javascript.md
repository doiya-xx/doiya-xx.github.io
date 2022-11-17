# Javascript

## Javascript

## Typescript

## nvm for windows

下载解压：压缩包版本

配置两个系统环境变量 `NVM_HOME` 和 `NVM_SYMLINK`

```
NVM_HOME: D:\nvm
NVM_SYMLINK: D:\nvm\nodejs
```

在解压目录下创建 `settings.txt`，写入

```txt
root: D:\nvm
path: D:\nvm\nodejs
arch: 64
proxy: none
node_mirror: http://npm.taobao.org/mirrors/node/
npm_mirror: https://npm.taobao.org/mirrors/npm/
```

注意 `poweshell` 必须以管理员身份启动

```shell
nvm list available
nvm install 18.12.0
nvm list
nvm use 18.12.0
```

```shell
node -v
npm -v
npm config get cache
# 全局安装包的位置，在 node_modules 目录下。
npm config get prefix
npm config set cache "D:\nvm\nodejs\node_cache"
npm config set prefix "D:\nvm\nodejs"
# npm 换源
npm config set registry https://registry.npm.taobao.org
```



## nodejs

```shell
node -v
```

## npm

```shell
# 在源目录下生成 package.json，需要输入客制化信息
npm init
# 按照默认信息生成 package.json
npm init --yes
# 安装模块，在当前目录下生成 node_modules 目录
npm install lodash
# 安装模块并将信息写入 package.json 中的生产依赖中
npm install --save lodash
# 安装模块并将信息写入 package.json 中的测试依赖中
npm install --save-dev lodash
# 全局安装模块或者命令行工具，将模块安装到nodejs的 node_modules 目录中。
npm install -g jshint
# 更新
npm update
npm update --save
npm update --save-dev
# 更新全局中的模块
npm update -g
# 寻找全局中需要更新的模块
npm update -g --depth=0
# 卸载全局中的包
npm uninstall -g jshint
```

## npx

## React.js

## Next.js

## Vue.js

