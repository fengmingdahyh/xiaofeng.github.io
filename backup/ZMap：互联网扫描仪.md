### ZMap：互联网扫描仪

- **性能特点**：ZMap 能在45分钟内扫描整个公共IPv4地址空间的单个端口。使用10gigE连接和netmap或PF_RING，扫描时间可缩短至5分钟。
- **兼容性**：ZMap 可在 GNU/Linux、Mac OS 和 BSD 上运行。
- **探测模块**：已实现TCP SYN扫描、ICMP、DNS查询、UPnP、BACNET探测模块，同时支持大量UDP探测。
- **复杂扫描**：对于更复杂的扫描，如横幅抓取或TLS握手，可使用ZMap的姊妹项目ZGrab 2。

### 使用 ZMap

- **入门指南**：ZMap 提供了详细的分步指南，帮助新手快速上手。
- **文档资源**：所有选项和高级功能文档可在GitHub Wiki中找到。
- **社区支持**：如有疑问，可查看常见问题解答或在Github讨论中提问。

### 安装 ZMap

- **最新版本**：ZMap 4.1.0-RC2添加了对扫描多个端口的支持。
- **安装命令**：
  - BlackArch：`sudo pacman -Syu yay && sudo yay -S zmap`
  - Kali/Parrot/Debian系列：`sudo apt update && sudo apt install zmap`
  - CentOS/RedHat系列：`sudo yum install -y zmap`

### 架构与性能

- **发送/接收解耦**：ZMap 设计为无状态，发送和接收线程独立运作，极大提高性能。
- **提高扫描精度**：可通过调整扫描速率和增加探测次数来提高扫描精度。

### 许可和版权

- **版权所有**：2023年密歇根大学董事会。
- **许可证**：根据Apache许可证2.0版获得许可。[http://www.apache.org/licenses/LICENSE-2.0](http://www.apache.org/licenses/LICENSE-2.0) 获取许可证副本（注：由于网络原因，链接解析可能未成功，建议检查链接合法性并适当重试）。

### 入门指南

- **安装验证**：运行`zmap --version`检查是否正确安装。
- **扫描速率警告**：ZMap 无拥塞控制，建议根据网络条件调整扫描速率。
- **线程警告**：建议使用不超过8个发送线程以避免性能下降。

### 运行您的第一次扫描

- **基本命令**：`sudo zmap -p 80 -r 128 171.67.70.0/23`，向子网中的所有IP发送TCP SYN数据包。

### 输出与性能

- **输出文件**：使用`--output-file`标志指定输出文件位置。
- **性能影响因素**：讨论了影响ZMap性能的各种因素，包括发送/接收解耦和提高发送性能。

希望这些信息对您有所帮助！
