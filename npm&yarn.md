# npm和yarn区别



**--save**简写为**-S**，安装包的版本信息会被写到package.json中的**dependencies**属性， 用于生产环境；

**--save-dev**简写为**-D**，安装包的版本信息会被写到package.json中的**devDependencies**属性，用于开发环境；

**npm install**简写**npm i**


| 说明                                                         | npm                                                          | yarn                                                         |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| **安装项目的全部依赖**                                       | **npm install**                                              | **yarn install**<br />yarn                                   |
| 初始化一个新项目                                             | npm init                                                     | yarn init                                                    |
| 安装本地包，并把安装依赖写入到package.json`'s `dependencies  | npm install <package_name> --save<br />npm install <package_name> -S | yarn add <package_name><br />yarn add [package]@[version]    |
| 安装本地包，并把安装依赖写入到package.json`'s `devDependencies | npm install <package_name> --save-dev<br />npm install <package_name> -D | yarn add [package] --dev                                     |
| 安装全局包                                                   | npm install <package_name> -g<br />npm install <package_name> --global | yarn global add <package_name>                               |
| 卸载安装包                                                   | npm uninstall <package_name><br />npm uninstall -g <package_name> | yarn remove <package_name>                                   |
| 卸载本地安装的包，并从 `package.json` 文件中删除依赖，需要在命令后添加参数 | npm uninstall <package_name> --save<br />npm uninstall <package_name> -S<br />npm uninstall <package_name> --save-dev<br />npm uninstall <package_name> -D | yarn remove <package_name><br />yarn remove <package_name> --dev |
| 更新全局安装的包                                             | 1、To update global packages, type: npm update -g <package_name><br />2、To update all global packages, type: npm update -g（npm update --global） | 1、yarn global upgrade <package_name><br />2、yarn global upgrade |
| 清除缓存                                                     | npm cache clean                                              | yarn cache clean                                             |
| 更新本地安装的包                                             | 1、在 `package.json` 文件所在的目录中执行 `npm update` 命令。 <br />2、执行 `npm outdated` 命令。不应该有任何输出。 | yarn upgrade [package]<br />                                 |
| 设置淘宝镜像                                                 | npm config set registry https://registry.npm.taobao.org      | yarn config set registry https://registry.npm.taobao.org     |
|                                                              |                                                              |                                                              |
|                                                              |                                                              |                                                              |



