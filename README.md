# TestFrameOnAllPlatform

---

[![standard-readme compliant](https://img.shields.io/badge/readme%20style-standard-brightgreen.svg?style=flat-square)](https://github.com/RichardLitt/standard-readme)

[TOC]

## Install
安装python3.8.2，并配置path环境变量

Python官网：https://www.python.org/


本工具基于python3.8.2开发，需要安装以下第三方插件：

```
直接通过requirements.txt安装
pip install -r requirements.txt
或者通过下列指令安装：
pip install pytest
pip install allure-pytest
pip install requests
pip install selenium
pip install pyyaml
pip install pyodbc
pip install jsonschema
pip install deepdiff
```

此外，还需要安装allure，具体安装步骤可以参考下面文档
https://www.cnblogs.com/wsy1103/p/10530397.html

性能测试框架工具：
https://locust.io

JsonSchema相关内容参考：
```
通过json串自动生成schema: 
https://jsonschema.net/
https://www.liquid-technologies.com/online-json-to-schema-converter
jasonchema的相关介绍:
https://json-schema.org/understanding-json-schema/index.html
浏览器运行exe下载可以参考：
https://npm.taobao.org/mirrors/chromedriver/
```





## File Structure

```
.\pytest.ini	#基础pytest参数
.\autoUtils     #测试使用的工具类
.\autoConfig	#测试使用的配置信息
.\testCases\apiTestCases\test_xxx.py    #接口测试用例
.\testCases\uiTestCases\test_xxx.py     #UI测试用例
.\testCases\performanceTestCases\test_xxx.py    #性能测试用例
.\testCases\testData                            #测试数据（根据环境命名，每个环境下面对应api和ui,性能测试用例）
.\autoReports\xxx                               #测试结果，用于生成报告
```

## Usage

在pytest.ini文件中进行pytest参数的配置，然后运行下面命令

```
$ python -m pytest --environment dash11testing -m illegalinputtest 按照pytest.ini配置项进行选择运行对应的case。环境是dash11testing环境，指定运行反向用例
$ python -m pytest .\tests\test_api.py	#运行tests下test_api.py脚本

# 运行完成后，在cmd中使用下面命令生成allure测试结果
$ allure serve .\report\	
这里还有一种方式生成allure测试结果
$ allure generate .\reoport\ -o .\report\xml\ --clean
$ allure open .\report\xml\
```

## Maintenances
Nash

