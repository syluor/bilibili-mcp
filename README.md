# Bilibili MCP Server

[English](README.md) | [中文](README.zh-CN.md)

This MCP server provides functionality to search and interact with Bilibili (a Chinese video sharing platform) content including videos, subtitles, and video information.

## Features

- Search Bilibili videos by keywords
- Get video subtitles (AI-generated)
- View video information and details
- Generate AI subtitles for media files using Bcut API

## Components

### Tools

- **search_video**
  - Search videos from Bilibili
  - Input:
    - `keyword` (string): Search keyword
    - `page` (int, optional): Page number, defaults to 1
    - `page_size` (int, optional): Results per page, defaults to 20

- **get_video_subtitle**
  - Get subtitles from a Bilibili video
  - Input:
    - `bvid` (string): Bilibili video ID (BV format)

- **get_video_info**
  - Get detailed information about a Bilibili video
  - Input:
    - `bvid` (string): Bilibili video ID (BV format)

- **get_media_subtitle**
  - Get AI-generated Chinese subtitles for media files using Bcut API
  - Input:
    - `url` (string): Media file URL

## Getting started

1. Clone the repository
2. Install dependencies: `pip install -r requirements.txt`
3. Set up environment variables (get from bilibili website's cookies):
   - `sessdata`: Bilibili SESSDATA
   - `bili_jct`: Bilibili bili_jct 
   - `buvid3`: Bilibili buvid3
4. Start the server: `python server.py`

### Usage with Desktop App

To integrate this server with a desktop app, add the following to your app's server configuration:

```json
{
  "mcpServers": {
    "bilibili-mcp": {
      "command": "python",
      "args": [
        "{ABSOLUTE PATH TO FILE HERE}/server.py"
      ],
      "env": {
        "sessdata": "your-bilibili-sessdata",
        "bili_jct": "your-bilibili-bili_jct",
        "buvid3": "your-bilibili-buvid3"
      }
    }
  }
}
```

## Development

- Install dependencies: `pip install -r requirements.txt`
- Start the server: `python server.py`

## Dependencies

- [mcp](https://github.com/modelcontextprotocol/sdk): MCP SDK
- [bilibili-api-python](https://github.com/Nemo2011/bilibili-api): Bilibili API Python library
- [aiohttp](https://docs.aiohttp.org/): Asynchronous HTTP client/server framework

## Resources

- [Bilibili API Documentation](https://github.com/SocialSisterYi/bilibili-API-collect)
- [Bcut API](https://www.bilibili.com/read/cv12349604/)

## License

This project is licensed under the MIT License.