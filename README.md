

# 简介

**CowAgent** 是基于大模型的超级 AI 助理，能够主动思考和任务规划、操作计算机和外部资源、创造和执行 Skills、拥有长期记忆和知识库并不断成长。支持灵活切换多种模型，能处理文本、语音、图片、文件等多模态消息，可接入微信、飞书、钉钉等平台，7\*24小时运行于个人电脑或服务器中。
核心能力如下：

- ✅ **自主任务规划**：理解复杂任务并自主规划执行，持续思考和调用工具直到完成目标
- ✅ **长期记忆**：自动将对话记忆持久化至本地，包括核心记忆、日级记忆和梦境蒸馏，支持关键词及向量检索
- ✅ **个人知识库**：自动整理结构化知识，支持通过对话管理知识库
- ✅ **技能系统**：支持从 Skill Hub 一键安装技能，或通过对话创造 Skills
- ✅ **工具系统**：内置文件读写、终端执行、浏览器操作、定时任务等工具
- ✅ **多模态消息**：支持文本、图片、语音、文件等多类型消息处理
- ✅ **多模型支持**：支持 OpenAI, Claude, Gemini, DeepSeek, MiniMax、GLM、Qwen、Kimi、Doubao 等国内外主流模型
- ✅ **多通道接入**：支持集成到微信、飞书、钉钉、企业微信、QQ、网页中使用

# 🚀 快速开始

## 一、准备

### 1. 模型 API

项目支持国内外主流厂商的模型接口，推荐使用以下模型：MiniMax-M2.7、glm-5-turbo、kimi-k2.5、qwen3.5-plus、claude-sonnet-4-6、gemini-3.1-pro-preview、gpt-5.4

### 2. 环境安装

支持 Linux、MacOS、Windows 操作系统，需安装 `Python`（3.7 \~ 3.13）。

**(1) 克隆项目代码：**

```bash
git clone https://github.com/zhayujie/CowAgent
cd CowAgent/
```

**(2) 安装核心依赖：**

```bash
pip3 install -r requirements.txt
```

**(3) 安装 Cow CLI (推荐)：**

```bash
pip3 install -e .
```

## 二、配置

复制配置模板并修改：

```bash
cp config-template.json config.json
```

配置示例：

```json
{
  "channel_type": "weixin",
  "model": "qwen-turbo",
  "dashscope_api_key": "你的API密钥",
  "agent": true,
  "agent_workspace": "~/cow",
  "agent_max_context_tokens": 50000,
  "agent_max_steps": 20
}
```

## 三、运行

### 本地运行

```bash
cow start    # 推荐
python app.py  # 或直接运行
```

运行后默认启动 web 服务，访问 `http://localhost:9899/chat` 即可使用。

### Docker 部署

```bash
docker run -d \
  --name cowagent \
  -p 9899:9899 \
  -e CHANNEL_TYPE=weixin \
  -e MODEL=qwen-turbo \
  -e DASHSCOPE_API_KEY=你的API密钥 \
  -v ./cow:/home/agent/cow \
  zhayujie/chatgpt-on-wechat
```

# 🔗 相关项目

- [Cow Skill Hub](https://github.com/zhayujie/cow-skill-hub)：开源的 AI Agent 技能广场
- [bot-on-anything](https://github.com/zhayujie/bot-on-anything)：轻量和高可扩展的大模型应用框架

# 📄 许可证

# 本项目遵循 [MIT 开源协议](/LICENSE)。
