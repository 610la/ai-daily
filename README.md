# AI 日报 · ai.shuyu.me

每日自动更新的 AI 行业日报（大模型 / 产品 / 论文 / 投融资 / 政策）。

## 结构

- `index.html` — 网站静态壳，打开时通过 JS 拉取 `data/latest.json` 渲染
- `data/YYYY-MM-DD.json` — 每日日报数据（归档）
- `data/latest.json` — 当日日报数据（网站实际读取的接口）

## 每日更新

每天只需更新 `data/` 下的 JSON 并推送到仓库，Cloudflare Pages 会自动重新部署：

```bash
python3 ~/workspace/ai-daily/publish.py --news ~/workspace/ai-daily/news/2026-09-26.json
```

`publish.py` 会把日报 JSON 复制为 `data/<日期>.json` 并同步到 `data/latest.json`，然后 commit + push。
