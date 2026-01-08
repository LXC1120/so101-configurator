# 舵机配置工具（Web Serial）

这是一个**纯静态网页**，使用 **Web Serial API** 直接在浏览器里通过串口配置舵机（无需安装 Python/软件）。

## 使用要求

- **桌面版** Chrome / Edge
- 站点必须是 **HTTPS**（或 `http://localhost`）
- 舵机必须**外接电源**（例如 6V+），USB 串口不供电
- 串口线序：**TX ↔ RX 交叉**，且 **GND 必须共地**
- 建议一次只连接 **1 个舵机**（广播写入会影响所有连接的舵机）

## 快速部署（GitHub Pages）

1. 新建一个公开仓库（Public），例如 `servo-id-configurator`
2. 上传 `index.html` 到仓库根目录
3. 仓库 Settings → Pages：
   - Source: Deploy from a branch
   - Branch: `main` / `(root)`
4. 打开 GitHub 提供的 HTTPS 链接即可使用

## 本地测试（可选）

Web Serial 需要安全上下文，本地可用：

```bash
python -m http.server 8000
```

然后用 Chrome 打开：

- http://localhost:8000

## 免责声明

本工具会向广播地址（0xFE）写入参数。若同时连接多个舵机，可能导致多个舵机被同时改写。
请确保一次只接一台舵机，并确保供电与线序正确。

---

生成时间：2026-01-08
