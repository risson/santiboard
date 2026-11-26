# Twikoo 前端（自托管）

- 来源：npm `twikoo@2.0.17`，`dist/twikoo.min.js`（不含腾讯云 CloudBase SDK，适配 Netlify / 自有服务器）
- 许可证：MIT（上游仓库 `twikoojs/twikoo`）
- 用途：评论抽屉在首次打开时动态注入本文件，然后调用 `window.twikoo.init({ envId, el, path, lang })`
- 为什么自托管：不依赖公网 CDN，取数走同源；只多 359KB，且只在打开评论抽屉时加载。

## 升级

```bash
cd /tmp && npm pack twikoo@<新版本>
tar -xzf twikoo-<新版本>.tgz package/dist/twikoo.min.js --strip-components=2
cp package/dist/twikoo.min.js <仓库>/dashboard/public/vendor/twikoo/twikoo.min.js
```

若改回腾讯云 CloudBase 部署，需要换用 `dist/twikoo.all.min.js`（含 TCB SDK），并在 `feedback-config.json` 里补 `region`。
