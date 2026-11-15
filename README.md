# Modbus 榨汁机 / MoDonald’s

查点位、读状态、留记录、导数据，打开一个软件就能做。

Windows x64 Modbus TCP 查询、批量读取与 CSV 记录工具。支持关键词和轻度模糊搜索，减少翻阅点表、手动配置和查找设备 IP 的重复操作。

## 下载 / Downloads

前往 [1.10.3 发布页](https://github.com/berwaberwa/register-juicer/releases/tag/v1.10.3)。首次使用下载 `MoDonalds.1.10.3.Windows.x64.zip`，解压后运行，内附 V1.7 中文指南。独立 EXE 用于软件内更新，`SHA256SUMS.txt` 用于检查下载完整性。

## 主要功能

- 按名称、关键词或轻度模糊词查询已收录点位；选中后自动准备适用的读取配置。
- 单点或多点选择，支持预览、增删、排序、组合保存和复用。
- 导入项目设备号映射后，按设备号查 IP，在结果旁识别设备。
- 多设备、多点位手动读取或自动刷新，每轮完成后再开始下一轮。
- 显示已确认的状态解释和按量级换算的读值，保留原单位读值供核验。
- 自动刷新期间可直接开始持续 CSV 记录，支持暂停、继续、停止、快照和当前读数导出。
- 持续记录上限：单设备最多 100 点；多设备每台最多 5 点、每轮合计最多 50 个设备与点位配对。实际采样速度取决于设备响应和网络条件。
- 支持中英文、日夜模式和沉浸阅读。个人导入内容和设置保存在本机，不自动公开或同步。

## 登录与更新

首次登录或激活需要联网。有效缓存授权可按软件显示的期限离线使用；正常关闭保留登录记忆，主动退出后需重新登录。免登录模式提供通用原始读取，受限功能需要有效授权。

更新由使用者确认。升级前结束记录并停止读取，本地个人设置继续保留。请确认所选点位适用于实际设备；不明确的定义不会被猜测为有效解释。

## English

A portable Windows x64 Modbus TCP lookup, batch reading and CSV recording tool. Search approximate register terms, prepare reusable reading lists, find device IPs through equipment mappings, refresh multiple devices, and retain test data locally. Recording supports up to 100 registers on one device, or 5 per device and 50 device/register pairs per cycle across multiple devices. Performance depends on equipment and network conditions. Initial activation requires connectivity; valid cached access supports offline use. Public documentation describes generic workflows only.
