# Hex

Hex Web Platform for opencode

**中文** | [English](#english)

---

## 中文

### 使用方法

1. 启动并打开 HEX —— 以下两种方式**二选一**：

   **方式一：本地运行**（两条命令各占一个窗口，`node server.js` 需另开一个命令窗口）

   只有 `node server.js` 必须在 HEX 项目目录（`server.js` 所在目录）下运行；`opencode serve` 没有限制，想在哪工作就在哪个目录启动：

   ```bash
   opencode serve   # 任意目录，你的工作路径
   # 另开一个命令窗口：
   cd /path/to/Hex   # 进入 server.js 所在的目录
   node server.js
   # 打开 http://localhost:3000，连接 http://localhost:4096
   ```

   **方式二：托管版**（不做方式一，直接打开 https://hex-mind.github.io/ 并连接 `http://localhost:4096`）

   OpenCode 需要为该来源开启 CORS，二选一：

   ```bash
   opencode serve --cors https://hex-mind.github.io
   ```

   或在 `~/.config/opencode/opencode.json` 中配置一次（改完重启 OpenCode）：

   ```json
   {
     "$schema": "https://opencode.ai/config.json",
     "server": {
       "cors": ["https://hex-mind.github.io"]
     }
   }
   ```

   在浏览器中打开时，HEX 优先使用 `localhost` 而非 `127.0.0.1`。

2. 以路径为中心工作

   - 使用顶栏的路径选择器（或 Files 面板）选择目录。
   - 选择路径不会创建会话。新建会话（顶栏或 ⌘/Ctrl J）也不会——它只会在当前路径上显示欢迎输入框。发送消息后，HEX 才会在该 workingDirectory 中启动会话。
   - 使用 Recent、Bookmarks 或顶栏的 `>` 展开跳转已有会话。

3. 关注 agent 动态

   - **侧边面板** — 六个标签：Recent、Files、Git、Search、Todo、Bookmarks。复杂任务中 agent 把工作拆解成步骤时会出现 Todo。活动栏还有 Open shell 和 Tips。
   - **浮动窗口** — 工具结果（shell、diff、文件查看器、web、子 agent、权限、提问）会在可移动、缩放、关闭的窗口中打开。
   - **权限** — 当 agent 想要执行操作时，内联允许或拒绝。

4. 快捷键

   | 快捷键 | 功能 |
   | --- | --- |
   | ⌘/Ctrl J | 新建会话 |
   | ⌥/Alt N | 新建会话 |
   | ⌥/Alt ↑ ↓ | 切换会话 |
   | Esc Esc | 停止 |
   | Enter | 发送（如在设置中启用则为 Ctrl+Enter） |
   | 按住 Shift（顶栏） | 在已归档会话上显示归档/删除 |

### FAQ

- **Chrome 无法让托管版访问本机服务？**

  Chrome 可能阻止 HTTPS 网站访问你电脑上的服务（仅使用托管版时需要）。打开以下任一地址：

  - `chrome://settings/content/loopbackNetwork`
  - `chrome://settings/content/localNetworkAccess`

  并允许 `https://hex-mind.github.io`。在 macOS 上还需在 系统设置 → 隐私与安全性 → 本地网络 中启用 Chrome。

- **Windows 上找不到 `opencode` 命令？**

  如果 `opencode` 命令不在 Path 上，添加其安装目录：

  ```
  E:\Users\<你的用户名>\.local\share\opencode\bin
  ```

  在受管设备上，你可能只能编辑用户级环境变量。

- **连接 `http://localhost:4096` 失败？**

  localhost 之间通常不需要 CORS。以防万一，可为加载 HEX 的来源开启 CORS：

  ```bash
  opencode serve --cors http://localhost:3000
  ```

  或在 `~/.config/opencode/opencode.json` 中配置一次（改完重启 OpenCode）：

  ```json
  {
    "$schema": "https://opencode.ai/config.json",
    "server": {
      "cors": ["http://localhost:3000"]
    }
  }
  ```

---

## English

[中文](#中文) | **English**

### User Guide

1. Start and open HEX — pick **one** of two options:

   **Option A: Run locally** (each command keeps running — open a second terminal for `node server.js`)

   Only `node server.js` must run from the HEX project directory (where `server.js` lives); `opencode serve` can run anywhere — start it in whatever directory you want to work in:

   ```bash
   opencode serve   # any directory — your working path
   # in a second terminal:
   cd /path/to/Hex   # the directory containing server.js
   node server.js
   # open http://localhost:3000 and connect to http://localhost:4096
   ```

   **Option B: Hosted** (skip Option A entirely — just open https://hex-mind.github.io/ and connect to `http://localhost:4096`)

   OpenCode must have CORS enabled for that origin — either:

   ```bash
   opencode serve --cors https://hex-mind.github.io
   ```

   Or configure it once in `~/.config/opencode/opencode.json` (restart OpenCode after changing):

   ```json
   {
     "$schema": "https://opencode.ai/config.json",
     "server": {
       "cors": ["https://hex-mind.github.io"]
     }
   }
   ```

   HEX prefers `localhost` over `127.0.0.1` when you open it in a browser.

2. Work path-first

   - Use the top-bar path picker (or Files panel) to select a directory.
   - Selecting a path does not create a session. New session (top bar or ⌘/Ctrl J) also does not create one — it shows the welcome composer on the current path. Send a message and HEX starts a session in that workingDirectory.
   - Use Recent, Bookmarks, or the `>` expansion in the top bar to jump into existing sessions.

3. Keep an eye on the agent

   - **Side panel** — six tabs: Recent, Files, Git, Search, Todo, and Bookmarks. Todo appears on complex tasks when the agent breaks work into steps. The activity bar also has Open shell and Tips.
   - **Floating windows** — tool results (shell, diffs, file viewers, web, sub-agents, permissions, questions) open in windows you can move, resize, and close.
   - **Permissions** — when the agent wants to run something, allow or deny it inline.

4. Shortcuts

   | Shortcut | Action |
   | --- | --- |
   | ⌘/Ctrl J | New session |
   | ⌥/Alt N | New session |
   | ⌥/Alt ↑ ↓ | Switch session |
   | Esc Esc | Stop |
   | Enter | Send (or Ctrl+Enter if you enabled that in Settings) |
   | Hold Shift (top bar) | Show archive/delete on archived sessions |

### FAQ

- **Chrome won't let the hosted version reach services on your computer?**

  Chrome may block hosted HTTPS sites from reaching loopback services (only needed for the hosted version). Open one of:

  - `chrome://settings/content/loopbackNetwork`
  - `chrome://settings/content/localNetworkAccess`

  and allow `https://hex-mind.github.io`. On macOS also enable Chrome under System Settings → Privacy & Security → Local Network.

- **`opencode` command not found on Windows?**

  If the `opencode` command isn't on your Path, add its install directory:

  ```
  E:\Users\<your-username>\.local\share\opencode\bin
  ```

  On managed devices you may only be able to edit user-level environment variables.

- **Can't connect to `http://localhost:4096`?**

  CORS is usually not needed between localhost origins. Just in case, enable CORS for the origin you load HEX from:

  ```bash
  opencode serve --cors http://localhost:3000
  ```

  Or configure it once in `~/.config/opencode/opencode.json` (restart OpenCode after changing):

  ```json
  {
    "$schema": "https://opencode.ai/config.json",
    "server": {
      "cors": ["http://localhost:3000"]
    }
  }
  ```
