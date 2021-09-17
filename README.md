# exclude-composer-assets
Exclude bower and npm asset packages from composer operations.

# Yii 使用 AdminLTE 前端模板

AdminLTE 的 AssetBundle：
https://github.com/dmstr/yii2-adminlte-asset

# 在当前目录安装 package.json 里的前端资源

docker run -it --rm -v $PWD:/code -w /code --user $(id -u) node:8-alpine yarn install

# package.json的require中添加

"benbanfa/exclude-composer-assets": "dev-master",

"config": {
       "process-timeout": 1800,
       "fxp-asset": { <-------- 加这个
          "enabled": false
       }
    },

# 在 .yarnrc 配置中加入

--modules-folder vendor/node_modules

# Yii 中加入别名，默认是有的
全局的 config/main.php

'aliases' => [

       '@bower' => '@vendor/node_modules',

       '@npm' => '@vendor/node_modules',

],
