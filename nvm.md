# win10 nvm安装nodejs “坑”之"npm -v"

### 1、安装**[nvm-windows](https://github.com/coreybutler/nvm-windows)**

```bash
$ nvm

Running version 1.1.7.

Usage:

  nvm arch                     : Show if node is running in 32 or 64 bit mode.
  nvm install <version> [arch] : The version can be a node.js version or "latest" for the latest stable version.
                                 Optionally specify whether to install the 32 or 64 bit version (defaults to system arch).
                                 Set [arch] to "all" to install 32 AND 64 bit versions.
                                 Add --insecure to the end of this command to bypass SSL validation of the remote download server.
  nvm list [available]         : List the node.js installations. Type "available" at the end to see what can be installed. Aliased as ls.
  nvm on                       : Enable node.js version management.
  nvm off                      : Disable node.js version management.
  nvm proxy [url]              : Set a proxy to use for downloads. Leave [url] blank to see the current proxy.
                                 Set [url] to "none" to remove the proxy.
  nvm node_mirror [url]        : Set the node mirror. Defaults to https://nodejs.org/dist/. Leave [url] blank to use default url.
  nvm npm_mirror [url]         : Set the npm mirror. Defaults to https://github.com/npm/cli/archive/. Leave [url] blank to default url.
  nvm uninstall <version>      : The version must be a specific version.
  nvm use [version] [arch]     : Switch to use the specified version. Optionally specify 32/64bit architecture.
                                 nvm use <arch> will continue using the selected version, but switch to 32/64 bit mode.
  nvm root [path]              : Set the directory where nvm should store different versions of node.js.
                                 If <path> is not set, the current root will be displayed.
  nvm version                  : Displays the current running version of nvm for Windows. Aliased as v.
```

nvm下settings.txt文件添加淘宝镜像源

```
root: d:\user\01394109\nvm
path: d:\user\01394109\nvm\nodejs
node_mirror: https://npm.taobao.org/mirrors/node/
npm_mirror: https://npm.taobao.org/mirrors/npm/
```



**注意点**：路径最好不要有空格

### 2、通过nvm安装Node.js 

```bash
# nvm install [version]
nvm install 12.16.2
```

### 3、查看是否安装成功

```bash
$ node -v
v12.16.2
# 如果不能使用，先通过nvm切换一下
$ nvm use 12.16.2
Now using node v12.16.2 (64-bit)

$ npm -v
internal/modules/cjs/loader.js:983
  throw err;
  ^

Error: Cannot find module 'd:\nvm\nodejs\node_modules\npm\bin\npm-cli.js'
    at Function.Module._resolveFilename (internal/modules/cjs/loader.js:980:15)
    at Function.Module._load (internal/modules/cjs/loader.js:862:27)
    at Function.executeUserEntryPoint [as runMain] (internal/modules/run_main.js:74:12)
    at internal/main/run_main_module.js:18:47 {
  code: 'MODULE_NOT_FOUND',
  requireStack: []
}
internal/modules/cjs/loader.js:983
  throw err;
  ^

Error: Cannot find module 'd:\nvm\nodejs\node_modules\npm\bin\npm-cli.js'
[90m    at Function.Module._resolveFilename (internal/modules/cjs/loader.js:980:15)[39m
[90m    at Function.Module._load (internal/modules/cjs/loader.js:862:27)[39m
[90m    at Function.executeUserEntryPoint [as runMain] (internal/modules/run_main.js:74:12)[39m
[90m    at internal/main/run_main_module.js:18:47
[39m {
  code: [32m'MODULE_NOT_FOUND'[39m,
  requireStack: []
}
```

nvm 成功安装nodejs之后，执行命令“npm -v”出现错误提示。

原因是**8.11以上版本的node版本对应的npm都没法自动安装**

### 解决npm错误

1、登录npm官网( https://npm.taobao.org/mirrors/npm/)

2、下载手动安装对应的npm版本

2.1、进入nvm下的指定node版本目录下的node_modules

2.2、把下载的npm包解压，重命名为npm，然后复制到 node_modules目录下

2.3、把npm中bin目录下的npm和npm.cmd复制到node_modules目录同级目录下