# aliddns
Scripts for AliDDNS

# 来源
本想着自己写脚本的，结果搜到了这个 https://github.com/chenhw2/luci-app-aliddns

脚本来源于 https://github.com/chenhw2/luci-app-aliddns/blob/master/files/root/usr/sbin/aliddns

对其做了删减，去除了加域名和删域名的相关部分

# 如何用

安装依赖： `opkg install curl openssl-util`
下载文件：`wget https://raw.githubusercontent.com/hanxi/aliddns/master/aliddns`

把 `aliddns` 文件放到 `/usr/bin/` 目录下

修改 `/usr/bin/aliddns` ，填写配置
```
ak_id='AccessKeyId'
ak_sec='Access Key Secret'
main_dm='hanxi.info'
sub_dm='www'
```

配置 `crontab` ，比如：

每10分钟检测一次.

```
*/10 * * * * /usr/bin/aliddns >/dev/null 2>&1
```
