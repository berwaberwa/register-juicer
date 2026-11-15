# Modbus 榨汁机 / MoDonald’s

查点位、读状态、留记录、导数据，打开一个软件就能做。

Windows x64 Modbus TCP 查询与批量读取工具。使用已收录并适用的点表搜索点位，自动准备地址、功能码、数据类型、字序和倍率，减少逐点查表与手动配置。导入项目设备号映射后，可按设备号查 IP，在读数旁直接识别设备。

A Windows x64 Modbus TCP register lookup, batch reading and CSV recording tool. Embedded protocol definitions prepare register addresses and decoding settings. Project equipment mappings let you find device IPs by equipment ID and identify results directly.

## 下载 / Downloads

从 [1.10.3 发布页](https://github.com/berwaberwa/register-juicer/releases/tag/v1.10.3) 下载：

- 首次使用：`MoDonalds.1.10.3.Windows.x64.zip`，包含一个免安装 EXE 和一份 44 页高清操作指南。先解压，再运行。
- 独立程序：`Register.Juicer.1.10.3.exe`，也用于软件内更新。
- 单独手册：`Modbus.Juicer.Guide.V1.7.pdf`。
- 完整性校验：`SHA256SUMS.txt`。

Download the portable ZIP for the application and the illustrated guide. The standalone EXE supports in-app updates. Keep the application in a writable folder; existing personal settings, protocols and groups stay local.

## 查询、读取与记录 / Lookup, reading and recording

- 支持中英文关键词、近义词、轻度模糊词及地址搜索，不必逐字照抄或保持相同词序。搜索同时识别点表地址和减 1 后的地址；选择结果不会启动读取。
- 主界面搜索中，双击准备单点；多个点勾选后加入读取列表。预览支持增删、批量选择和排序，常用点位可保存为组合，下次直接调取。
- 单设备或多设备、单点或多点均可手动读取或自动刷新。先选模式，再点“读取”；每轮完成后开始下一轮，不重叠采样。
- 导入 IP 与设备号映射后，可按设备号或轻度模糊写法查找 IP。IP 项目、混合区间和离散设备可保存复用，更换 IP 保留当前点位选择。
- 按已确认的点表规则解释状态 bit；功率、电压和电流按量级自动换算单位，同时保留原单位读值、原始寄存器及详情。
- 自动刷新期间可直接开启持续 CSV 记录。文件准备好后，从新一轮完整采样开始，每台设备每轮一行；支持暂停、继续、停止与快照导出，不补录之前显示的旧值。
- 持续记录上限：单设备最多 100 点；多设备每台最多 5 点，每轮合计最多 50 个实际 IP/点位配对。例如 10 台×5 点或 50 台×1 点。普通读取与记录上限不同。
- 文件准备、记录整理和写盘在后台执行，队列有界。实际采样速度取决于设备响应、点位数量及网络条件；1 秒是刷新目标。
- “导出读数”用于保存当前显示的一批结果，可选列和中英文；持续记录用于测试过程留档。二者用途不同。
- 支持中英文、日夜模式、卡片收放与沉浸阅读，Esc 返回原布局。

Search using register names, approximate terms or addresses. Prepare single registers or reusable groups, then click **Read** to acquire data. Automatic refresh supports multiple devices and registers in non-overlapping cycles. Recording can start while refresh is running, beginning with a new complete cycle after file preparation. Limits are 100 registers for one device, or 5 per device and 50 device/register pairs per cycle for multiple devices. Raw values and source units remain available alongside interpreted states and scaled readings.

## 内置点表 / Embedded protocols

- 集中式逆变器 V1.0.22、PPC100 V1.1.3。
- LC200 V2.0.0.5：System summary Info-3x、Single PCS Info SC2500-3150-3x、Single PCS Info SC2750~3450-3x、System summary info-4x、BSC200 Info-3x、PV-SG3125HV-SG2475HV Info-3x。
- LC200 搜索范围统一为一个选项，结果中仍显示具体版本和分表。其余 LC200 分表不参与搜索。
- 可切换优化后的名称描述与原版名称描述；原表词条仍可搜索。个人协议和组合不自动上传或同步。

Choose the protocol version and configuration matching the equipment. Confirmed definitions are decoded; pending definitions retain raw values, and reserved or unsafe-to-read entries are blocked. Unknown states are never guessed to be normal. Local protocol imports support explicit JSON/CSV/XLSX formats; unsupported layouts are retained for mapping.

## 地址、登录与更新 / Addresses, sign-in and updates

手动输入填点表地址减 1。例如点表地址 8014，输入 8013。搜索选中后自动填写，不用再减。当前内置表的 3x 使用 FC04，4x 使用 FC03。

Manual entry uses the documented table address minus 1. Search selection fills the address automatically; do not subtract again.

首次账户登录或授权激活需要联网，随后按授权状态及最近成功核验后的最长 30 天离线期限使用。正常关闭保留登录记忆；主动退出登录后，下次需重新登录。免登录模式提供通用原始读取，受保护协议和解析需要有效授权。

Initial sign-in or activation requires an internet connection. Valid cached access can continue offline for up to 30 days after successful verification, subject to authorization expiry. Normal closure preserves sign-in; explicit sign-out requires signing in again. Anonymous mode provides generic raw reading.

更新由使用者确认，先结束记录并停止读取，再按提示下载、校验和重启。旧版本和本地个人配置继续保留。1.8.0 及更早版本请手动下载本版一次。

Updates are optional and retain local personal data. Users on 1.8.0 or earlier should download the current release manually once.

开发验证使用离线模拟；这些验证不代表已完成现场设备性能或全部工况验证。

Development verification uses offline simulations and does not establish field-device performance or coverage of every operating condition.
