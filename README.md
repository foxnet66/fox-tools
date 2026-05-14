# Fox Tools

一个轻量的在线工具箱，当前优先解决中文简繁互换、温度转换、进制转换、长度转换、UUID 生成，后续可以继续扩展 JSON、URL、时间戳、编码转换等常用工具。

## 当前功能

- 简体转繁体
- 繁体转简体
- 自动识别转换方向
- 复制结果
- 粘贴文本
- 交换原文与结果
- 最近记录
- 摄氏、华氏、开氏、兰氏、列氏温度互转
- 二、八、十、十六、三十二进制互转
- 常用公制、英制、市制、天文长度单位互转
- 批量生成 UUID v4
- 工具导航与搜索
- 每个工具独立使用说明

## 项目特点

- 纯静态页面，无需后端
- 无构建步骤，直接打开即可使用
- 工具列表由 `toolCatalog` 注册表驱动，方便继续扩展
- 当前所有代码集中在 `index.html`，适合早期快速迭代

## 本地使用

直接用浏览器打开：

```text
index.html
```

也可以用任意静态服务器托管当前目录。

## 扩展新工具

后续新增工具时，建议按这个流程：

1. 在 `toolCatalog` 中新增工具元数据。
2. 新增一个对应的 `.tool-view` 容器。
3. 为该工具补充独立的渲染和交互逻辑。
4. 保持工具之间的数据、状态和历史记录命名独立。
5. 为 `help` 字段补充 2-4 条简单使用说明。

示例：

```js
{
  id: "json-formatter",
  name: "JSON 格式化",
  category: "开发工具",
  description: "校验、压缩、格式化",
  icon: "{}",
  status: "ready",
  help: [
    "粘贴 JSON 文本",
    "选择格式化或压缩",
    "复制处理后的结果"
  ]
}
```

对应视图 ID：

```html
<div class="tool-view" id="tool-json-formatter">
  ...
</div>
```

## 文件结构

```text
.
├── index.html
└── README.md
```

## 部署

这是静态站点，可以部署到：

- GitHub Pages
- Vercel
- Netlify
- Cloudflare Pages
- 任意 Nginx / 静态文件服务

## Roadmap

- JSON 格式化
- URL 编解码
- 时间戳转换
- Base64 编解码
- 文本去重 / 排序
- 字数统计
