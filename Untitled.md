| 字段                   | 中文               |
| ---------------------- | ------------------ |
| yudingGuid             | 预定guid           |
| projectGuid            | 项目guid           |
| orderType              | 预约类型           |
| kaibiaoRoomGuid        | 开标室房间标识     |
| pingbiaoRoomGuid       | 评标室房间标识     |
| zsjsRoomGuid           | 资审接收室房间标识 |
| zspsRoomGuid           | 资审评审室         |
| isFlow                 | 是否流标           |
| isFuping               | 是否复评           |
| projectName            | 项目名称           |
| pingbiaostarttime      | 评标开始时间       |
| pingbiaoendtime        | 评标结束时间       |
| kaibiaostarttime       | 开标开始时间       |
| kaibiaoendtime         | 开标结束时间       |
| realitypingbiaoendtime | 实际评标结束时间   |
| zsjsstarttime          | 资审接收开始时间   |
| zsjsendtime            | 资审接收结束时间   |
| [                      |                    |
| jianshedanwei          | 建设单位           |
| dailiname              | 代理单位           |
| biaoduanguid           | 标段标识           |
| biaoduanno             | 标段编号           |
| biaoduanname           | 标段名称           |
| ]                      |                    |







### 请求数据项

| 参数名       | 参数类型 | 参数说明       | 是否必填 | 备注                                                         |
| :----------- | -------- | -------------- | -------- | :----------------------------------------------------------- |
| Content      | 字符串   | 待广播文本     | 是       | 编码由 TextCode 字段决定                                     |
| TargetIds    | 整型数组 | 目标 ID 列表   | 是       | 广播目标，分区（或终端）                                     |
| TargetType   | 整型     | 目标类型       | 是       | 0-分组 <br />1-终端                                          |
| Time         | 字符串   | 时间           | 是       | 本条请求发生的时间点                                         |
| Playtime     | 整型     | 播放次数       | 是       | 必须大于 0                                                   |
| PlayInterval | 整型     | 播放间隔       | 否       |                                                              |
| PlayPrior    | 整型     | 播放优先级     | 是       | 0-1000                                                       |
| Volume       | 整型     | 会话音量       | 否       | 取值范围：1 – 56 不设置该参数则使用终端默 认音量。           |
| TTSName      | 字符串   | 语音引擎       | 是       | 不设置则使用服务器上设置 的参数                              |
| TextCode     | 整型     | 待广播文本编码 | 是       | 1- GBK<br /> 2- UTF-8 <br />不设置则使用服务器上设置 的参数  |
| TextSpeed    | 整型     | 待广播文本语速 | 否       | 最小值 -10，最大值 10 不设置则使用服务器上设置 的参数        |
| PromptTone   | 整型     | 提示音         | 否       | 0- 无提示音 <br />1- 系统预设提示音 1<br /> 2- 系统预设提示音 2 |

### 应答数据项

| 参数名  | 参数类型 | 参数说明        | 是否必填 | 备注 |
| ------- | -------- | --------------- | -------- | ---- |
| TTSUUID | 符串     | 文本广播任务 ID | 是       |      |

### 错误码表

| 错误码 | 说明                       |
| ------ | -------------------------- |
| 0      | 成功                       |
| 8000   | 接口未实现或者无效的接口名 |
| 8001   | JSESSIONID 无效            |
| 1000   | 参数错误，缺少必须的参数   |
| 1001   | 用户名、密码不正确         |
| 1002   | 发起呼叫终端不在线         |
| 1003   | 无效的终端 ID              |
| 1004   | 发起呼叫终端正忙           |
| 1005   | 无效的终端通话编码         |
| 1006   | 串口无效                   |
| 1007   | 串口操作超时               |
| 1008   | 串口数据错误               |