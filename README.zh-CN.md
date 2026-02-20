 # Bilibili MCP 服务器

[English](README.md) | [中文](README.zh-CN.md)

这个MCP服务器提供了搜索和交互B站（哔哩哔哩）内容的功能，包括视频搜索、字幕获取和视频信息查询等。

## 功能特点

- 搜索B站视频
- 查询视频详细信息及获取AI生成的字幕

## 组件

### 工具

- **search_video**
  - 从B站搜索视频
  - 输入:
    - `keyword` (string): 搜索关键词
    - `page` (int, 可选): 页码，默认1
    - `page_size` (int, 可选): 每页数量，默认20

- **get_video_info**
  - 获取B站视频的详细信息及AI生成的字幕
  - 输入:
    - `bvid` (string): 视频的BV号

## 开始使用

1. 克隆仓库
2. 安装依赖: `pip install -r requirements.txt`
3. 设置环境变量（从B站官网cookie获取）:
   - `sessdata`: B站SESSDATA
   - `bili_jct`: B站bili_jct
   - `buvid3`: B站buvid3
4. 启动服务器: `python server.py`

### 与桌面应用集成

要将此服务器与桌面应用集成，请在应用的服务器配置中添加以下内容:

```json
{
  "mcpServers": {
    "bilibili-mcp": {
      "command": "python",
      "args": [
        "{绝对路径}/server.py"
      ],
      "env": {
        "sessdata": "你的B站SESSDATA",
        "bili_jct": "你的B站bili_jct",
        "buvid3": "你的B站buvid3"
      }
    }
  }
}
```

## 开发

- 安装依赖: `pip install -r requirements.txt`
- 启动服务器: `python server.py`

## 依赖项

- [mcp](https://github.com/modelcontextprotocol/sdk): MCP SDK
- [bilibili-api-python](https://github.com/Nemo2011/bilibili-api): B站API Python库
- [aiohttp](https://docs.aiohttp.org/): 异步HTTP客户端/服务器框架

## 资源

- [B站API文档](https://github.com/SocialSisterYi/bilibili-API-collect)

## 许可证

本项目采用MIT许可证。