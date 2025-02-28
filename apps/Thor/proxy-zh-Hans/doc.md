---
layout: raw
---

## 抓包代理使用帮助

抓包代理用于对局域网中（通常是 Wi-Fi）其它同网段设备的 HTTP(S) 流量抓包分析。


### 可以抓哪些设备

所有支持 HTTP 代理设置的设备和应用，如：电脑、其它手机或平板、智能机顶盒、游戏主机、部分联网智能设备。


### 一、浏览器和系统 HTTP 代理配置

#### mac 系统 HTTP 代理设置

系统偏好设置 > 网络 > 选择你要配置的网络 > 高级 > 代理.

注：如果要抓取 HTTPS 流量，则『安全网页代理（HTTPS）』也要勾选。
 

#### Windows / IE 浏览器 HTTP 代理设置

打开 IE 浏览器 > 点击“设置”图标 > 选择“Internet 选项” > 点击”连接“选项卡，再点击”局域网设置“ > 在“局域网设置”中，勾选“为 LAN 使用代理服务器” > 填写 Thor 里给出的地址和端口 > 确定。

Microsoft Edge 浏览器需要打开 `about:flags` 进行额外配置。


#### Mozilla Firefox 浏览器 HTTP 代理设置

打开 Firefox > 右上角三横图标 > 首选项 > 常规，右侧滚动到底部找到“网络代理” > 设置 > 使用系统代理设置或为 Firefox 设置单独的代理（手动代理配置）


#### iOS 设备 HTTP 代理设置

系统设置 > 无线局域网 > 选择要配置的 Wi-FI 右边的感叹号 > HTTP 代理 > 手动 > 填入 Thor 中的监听地址

抓包结束后，需要关闭此处的 HTTP 代理设置，否则手机网络不通。


#### Android 设备 HTTP 代理设置

部分 Android 设备没有 HTTP 代理设置入口，可以通过语音助手唤出『代理 』入口。

有的三星手机可以通过**长按网络名称**进行代理配置。


### 二、在目标设备上安装并信任 Thor SSL CA 证书

Thor 需要 Thor SSL CA 证书，才能以 MiTM 方式解析 HTTPS 流量。
自签名 CA 证书在 Thor 本地随机生成且只会存储在本地 Keychain 中，不同设备和用户间彼此不同。

如果不需要解析 HTTPS 流量，则不用安装 Thor SSL CA 证书。


#### 如何导出 Thor SSL CA 证书

打开 Thor > 更多 > HTTPS 解析设置 > 点击证书进入详情 > 右上角分享 > 选择导出的格式（cer 或者 pem 文件皆可）> 选取导出的方式


有 Shu 的用户可以把 Thor SSL CA 证书导入 Shu，然后放到 Shu 的共享目录，打开 WiFi 共享，在待抓包的目标设备浏览器中打开 Shu 的 WiFi 共享地址，然后点击下载导入的 Thor SSL CA 证书，并安装在目标设备上。


注：要解析目标设备的 HTTPS 流量，只安装证书是不够的，一定要设置信任。


#### macOS 系统

从 Thor 中导出 "Thor SSL CA" 证书 (.cer) 到 mac。

双击或拖拽证书到钥匙串安装 > 在钥匙串中找到 > 显示简介 > 选择始终信任


#### Windows 系统

从 Thor 中导出 "Thor SSL CA" 证书 (.cer) 到 Windows。

双击安装 > 选择“将所有的证书放入下列存储”，再点“浏览” > 选择“受信任的根证书颁发机构”，点确定 > 下一步，完成 > 在弹出的警告对话框中点“是”


#### iOS 设备

* 系统邮箱安装：从 Thor 中导出 "Thor SSL CA" 证书 (.cer) 选择邮件发送到目标设备 > 在目标设备的系统邮箱中收件，并点击附件安装。

* 系统文件应用安装：从 Thor 中导出 "Thor SSL CA" 证书 (.cer) 并发送到目标设备 > 在目标设备中保存证书到系统文件应用，iCloud 云盘中 > 打开系统文件应用，找到云盘中的证书 > 点击安装。

	注：iOS 10 以后系统在证书安装后，是已验证状态，并非已信任，需要在『系统设置 > 通用 > 关于本机 > 证书信任设置』信任。


#### Android 设备

从 Thor 中导出 "Thor SSL CA" 证书 (.p12 或者 .pem) 到设备进行安装。


#### Mozilla Firefox 浏览器

从 Thor 中导出 "Thor SSL CA" 证书 (.cer) 到电脑。

由于 Firefox 浏览器自己有一套证书管理的系统，所以我们需要单独为 Firefox 浏览器导入证书。

打开 Firefox > 右上角三横图标 > 首选项 > 选择页面左侧的“隐私与安全” > 把右侧页面滚动到底部，点击“查看证书” > 打开证书管理器后，选择“证书机构”选项卡，点击下面的“导入”按钮导入Thor导出的证书 > 在弹出的对话框中，勾选所有信任项，然后点“确定” > 再在证书管理器中点“确定”

