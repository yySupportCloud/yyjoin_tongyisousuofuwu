# 更新rsyslog配置文件

打开rsyslog配置文件，它通常在 /etc/rsyslog.d 目录下

vim /etc/rsyslog.conf  
将下列内容粘贴在这个配置文件中  

    $MaxMessageSize 64k
    $InputFileName FILEPATH
    $InputFileTag APPNAME
    $InputFileStateFile stat_APPNAME
    $InputFileSeverity info
    $InputFilePersistStateInterval 20000
    $RepeatedMsgReduction off
    $InputRunFileMonitor

    $InputFilePollInterval 3
    $template yycloudFormat_APPNAME,"%timestamp:::date-rfc3339% %HOSTNAME%  [TOKEN@32473 tag=\"TAG\"] %syslogtag% %msg%\n"

    if $programname == 'APPNAME' then @@YYCLOUDHOST:PORT; yycloudFormat_APPNAME
    if $programname == 'APPNAME' then ~

*	TOKEN: 使用“数据设置--用户标识”页面中的用户标识符替换它。示例：ba1f2511fc30423bdbb183fe33f3dd0f
*	FILEPATH: 需要上传的日志文件的绝对路径，必须包含日志文件名。示例：/var/log/nginx/access.log
*	TAG: 标签，标识日志的扩展信息，可定义多个标识，这里替换为您自行定义的标签，可用来定义日志分组，这将帮助您有效划分日志，缩小搜索范围。示例：  rizhiyi_search
*	YYCLOUDHOST:PORT：用于指定接收日志的服务器域名或者主机名。
