# nonebot_plugin_statistical

## 介绍

  基于 run_postprocessor 实现的功能调用统计以及可视化，且可为插件设置别名和显示白名单， 
  <br>  
  已实现动态命令增删改查别名或手动修改文件后重载，以及动态命令增删查白名单，在白名单中的插件不会再可视化中显示。

## 注

    1.在linux中可能需要中文字体，不然会出现中文乱码，找到matplotlib的数据目录后在font目录下放入SIMHEI.ttf文件，
                后删除 ~/.cache/matplotlib文件
    2.所有的cmd(别名)不得重复
    3.尽量通过命令来修改数据
    4.模块中的cmd[0]为图表上显示的名称
      例如："ddd": {
              "cmd": [
                  "滴滴滴",
                  "花花花"
              ]
            }
      则 滴滴滴 为图表上显示该功能的名称，该项可以通过命令'提升统计cmd [cmd]'来更改，示例：提升统计cmd 花花花，
                          说明：将 花花花 提升到cmd[0]的位置，图表中将以 花花花 显示该模块而不是滴滴滴
    5.关于修改文件，只可以修改 plugin2cmd.json 文件，另外2个文件是基于这个文件生成的，可以修改文件中的 'white_list' 以及模块的cmd，
              修改完毕后通过命令 '重载统计数据' 来重新生成文件
  
  
## 使用方法

### 命令总汇

  * 功能调用统计，日功能调用统计，周功能调用统计，月功能调用统计，我的功能调用统计，我的日功能调用统计，我的周功能调用统计，我的月功能调用统计
  * 重载统计数据
  * 添加统计cmd
  * 删除统计cmd
  * 显示统计cmd
  * 提升统计cmd
  * 添加统计展示白名单
  * 删除统计展示白名单
  * 显示统计展示白名单
 
#### 【注1】：开头带 ‘我的’ 皆为个人的统计，反之为群聊的统计
#### 【注2】：以下参数[cmd]只需要是模块cmd列表中的一个即可，不需要是cmd[0]

| 命令                        |    参数     |             说明                      | 示例 |  
| ----------------------     | :--------:  | :----------------------------:  | :------:
| 功能调用统计/我的功能调用统计 |   无   |   以柱状图的方式展示从开始统计开始到现在的全部数据            |     无    
| 日功能调用统计/我的日功能调用统计  |   无  |    以柱状图的方式展示今日功能调用数据             |    无      
| 周功能调用统计/我的周功能调用统计     |   [plugin_cmd] |         当未有参数时，以柱状图展示一周内的功能调用<br>当有参数时，以折线图的方式展示该功能一周内的调用情况  |     周功能调用统计<br>周功能调用统计色图     
| 月功能调用统计/我的月功能调用统计 |   [plugin_cmd]    |  同上            |   同上        
| 重载统计数据                |         无           |    用于手动修改 plugin2cmd.json 文件后重载         |  无
| 添加统计cmd                |         [cmd] [new_cmd]  |    为模块新增cmd(别名)，通过参数[cmd]查找到所在模块后添加[new_cmd]       |      添加统计cmd 色图 涩图
| 删除统计cmd     |         [cmd]            |   删除模块的cmd(别名)        |   删除统计cmd 色图
| 显示统计cmd      |          [cmd]           |   展示该模块的所有cmd(别名)，通过参数[cmd]查找到该模块        |  显示统计 色图
| 提升统计cmd     |    [cmd]             |  提升参数[cmd]所在模块的cmd列表中位置至cmd[0]，cmd[0]位置用于在图表上显示  | 提升统计cmd 色图
|添加统计展示白名单|     [cmd]           | 将某模块不在图表上展示，通过参数[cmd]来添加对应模块        | 添加统计展示白名单 色图
|删除统计展示白名单|     [cmd]           | 将某模块从白名单中删除，通过参数[cmd]来添加对应模块        | 删除统计展示白名单 色图
|显示统计展示白名单| 无 | 显示当前的统计展示白名单    |     显示统计展示白名单


