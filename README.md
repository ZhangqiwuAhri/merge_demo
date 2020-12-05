吾立知OA API 端文档
开发规范
git
禁止使用 merge 操作, 所有的合并操作都只能用 rebase 来完成. 禁止强制推送. 工作流为: master<-dev<-feature

php
版本: 7.4, 遵循 psr12 的开发规范, 不符合规范的代码不予合并.

mysql
版本: 5.7.28, 所有的表字段均要加上注释, 以及表注释.
本地需要配置两套数据库, 一套用来完成开发, 一套用来做功能测试.

redis
版本: 5.0+

composer
线上禁止安装 dev 相关的扩展. 禁止使用 update 操作

# production
$ composer install --no-dev -o -vvv

# local
$ composer install -o -vvv

# 使用阿里云镜像源
$ composer config -g repo.packagist composer https://mirrors.aliyun.com/composer/
phpunit
所有的接口都必须完成功能测试. 未做功能测试以及测试失败的代码不予合并.

代码格式化
使用 php-cs-fixer 指定该项目 .php_cs 配置完成修复

$ php-cs-fixer fix --config .php_cs  /path/to/project
$ php-cs-fixer fix --config .php_cs  /path/to/project/file
