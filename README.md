# DeepSeek API 订阅站

售卖 DeepSeek API 订阅的静态官网，纯 HTML/CSS 单页，无需构建，可直接由 GitHub Pages 托管。

## 结构

- `index.html` — 站点全部内容（导航、特性、模型价格、订阅套餐、接入文档、FAQ、购买入口）
- `.nojekyll` — 禁用 GitHub Pages 的 Jekyll 构建，直接按静态文件发布

## 上线前需要修改的内容

1. **接口地址**：`index.html` 中的 `https://api.example.com/v1` 为占位符，替换成你实际的 API 网关地址。
2. **价格与套餐**：`#models` 表格和 `#plans` 套餐卡片中的价格、额度均为示例，按你的实际定价修改。
3. **购买方式**：目前购买按钮跳转到邮件联系（`#buy` 区块）。如接入支付链接（如发卡平台），把 `.buy-link` 各按钮的 `href` 换成对应支付页即可。
4. **联系方式**：页脚与购买区块中的邮箱。

## 本地预览

```bash
python3 -m http.server 8000
# 打开 http://localhost:8000
```
