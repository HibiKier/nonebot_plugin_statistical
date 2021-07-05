# nonebot_plugin_statistical

## 介绍

  基于 run_postprocessor 实现的功能调用统计以及可视化，且可为插件设置别名和显示白名单， 
  <br>  
  已实现动态命令增删改查别名或手动修改文件后重载，以及动态命令增删查白名单，在白名单中的插件不会再可视化中显示。

## 注

  在linux中可能需要中文字体，不然会出现中文乱码  
    
  找到matplotlib的数据目录后在font目录下放入SIMHEI.ttf文件  
    
  后删除 ~/.cache/matplotlib文件
  
  
## 使用注解

### 命令总汇

  * 功能调用统计，日功能调用统计，周功能调用统计，月功能调用统计，我的功能调用统计，我的日功能调用统计，我的周功能调用统计，我的月功能调用统计
  * 重载统计数据
  * 删除统计cmd
  * 添加统计cmd
  * 显示统计cmd
  * 提升统计cmd
  * 添加统计展示白名单
  * 删除统计展示白名单
  * 显示统计展示白名单

