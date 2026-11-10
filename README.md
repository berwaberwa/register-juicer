# 寄存器榨汁机 / Register Juicer

Windows Modbus TCP 批量只读工具。读取寄存器，并根据选中的点表显示点名、工程量、单位和状态说明。

A read-only Windows Modbus TCP tool for batch reading and protocol point interpretation.

## 下载 / Download

从 [Releases](https://github.com/berwaberwa/register-juicer/releases) 下载最新的 `Register Juicer x.y.z.exe`，放在自己有写入权限的文件夹运行。

Download the latest executable from Releases and keep it in a writable folder.

## 使用 / Use

- 多设备读取同一点位，或单设备读取多个点位。
- 可搜索中英文关键词、相关词、近似拼写及点表/PDU 地址；选中点位后再确认读取。
- 协议按“设备名 - 点表版本 - 上传日期”显示，原始点表可在软件内另存。
- 官方点位组合随软件提供；可复制后保存为自己的组合。
- 本地导入的协议和个人组合只保存在自己的电脑，不上传，也不被软件更新覆盖。
- Auto Refresh 目标间隔为 1 秒。慢的一轮结束后才开始下一轮，不叠加请求。
- 可导出 CSV，双击结果查看完整说明。
- 界面支持英文和简体中文。

Read the same point across devices or use a saved point group on a device. Search, optional one-second refresh, CSV export and English/Chinese UI are included. Personal protocols and groups stay local.

## 地址及确认状态 / Addresses and review status

Register 输入原始、从 0 起的 PDU 地址。例如点表地址 8014，输入 8013，实际请求也发送 8013。3x 读取用 FC04，4x 读取用 FC03。

App addresses are zero-based PDU addresses. The request uses the entered address unchanged.

未确认规则只保留原始值；保留点位拦截读取。未知枚举和未知状态位不会被猜成正常状态。默认点表仍需与设备型号、固件和配置核对。

Pending rules keep raw registers only. Reserved points are blocked. Unknown states remain explicit; choose the correct device and configuration.

本地协议支持单协议 JSON 或列名明确的标准 CSV/XLSX。其他布局会归档为“待映射”，不会自动猜测类型、字序或倍率。

Local import supports a single-protocol JSON or an explicit flat CSV/XLSX table. Other layouts are archived for mapping, without guessed parsing rules.

## 可选更新 / Optional updates

软件可断网使用，无需登录。启动后后台检查新版；也可手动点击“检查更新”。发现新版只提示，由使用者确认后升级，正在读取时不会中断。更新保留本地配置、协议、组合和旧版本。

Offline use never requires an update. Startup checks are non-blocking, and updates require confirmation. Settings and local data are retained.

开发验证使用离线模拟和本机模拟器，未进行现场设备验证。

Development validation uses offline mocks and a local simulator; field-device validation has not been performed.

