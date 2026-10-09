# Meta Muse Connector Brief

## 1. 连接器概述 (Overview)
*   **名称**：Local Assistant Connector
*   **版本**：1.0.0
*   **描述**：一个允许 Muse AI 发送指令控制本地电脑软件（如发微信、打开应用）并进行常规信息查询的集成器。由于涉及本地端操作，需要在用户本地环境中运行轻量级执行服务。

## 2. 技术参数 (Technical Parameters)
*   **MCP 类型**：Raw API / Existing MCP (根据你的实际开发情况选择)
*   **核心端点 (Endpoint)**：`https://your-domain.com/mcp` 或 本地服务转发地址
*   **认证方式**：API Key (Bearer Token)

## 3. 工具与指令定义 (Tools & Prompts)
本连接器提供以下工具供 Muse 调用：

### 工具一：`open_local_app`
*   **描述**：打开本地已安装的软件。
*   **参数**：`app_name` (软件名称，如 "微信", "QQ", "Chrome")
*   **提示示例**：
    *   “帮我打开微信”
    *   “启动浏览器”

### 工具二：`send_message`
*   **描述**：在指定的本地聊天软件中发送消息。
*   **参数**：`contact_name` (联系人姓名), `message_content` (消息内容)
*   **提示示例**：
    *   “给张三发微信，说我晚点到”
    *   “告诉老板，我下午三点开会”
    *   “给女朋友发消息说晚安”

### 工具三：`query_system_info`
*   **描述**：查询本地或用户指定的信息。
*   **参数**：`query_type` (查询类型，如 "weather", "system_status")
*   **提示示例**：
    *   “查一下长沙现在的天气”
    *   “看看我电脑内存占用”

## 4. 审核注意事项 (Notes for Review)
*   **隐私合规**：本连接器仅在本地用户设备上执行操作，用户提示词中涉及的联系人信息仅用于本地匹配，不上传至第三方服务器。
*   **使用限制**：使用前用户必须安装并启动本地同步客户端（Local Sync Client）。


