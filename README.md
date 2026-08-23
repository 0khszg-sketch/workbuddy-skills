# WorkBuddy Skills 同步仓库

WorkBuddy 用户级技能的 **Mac / PC 双端同步仓库**。

> 说明：WorkBuddy 的技能存放在本机 `~/.workbuddy/skills/`，不随账号云端同步。
> 本仓库作为"权威源"（single source of truth），各设备从这里拉取。

## 当前技能

| 技能 | 说明 |
|---|---|
| `gouzi-coo` | 狗子 COO —— 跨项目 AI 首席运营官，全内部模型编排（总控/探索/执行/评审/研究） |

## 安装 / 更新（任一台设备）

**macOS / Linux：**

```bash
cd ~ && \
( test -d workbuddy-skills || git clone git@github.com:0khszg-sketch/workbuddy-skills.git ) && \
cd workbuddy-skills && git pull && \
mkdir -p ~/.workbuddy/skills && \
cp -R gouzi-coo ~/.workbuddy/skills/
```

**Windows (PowerShell)：**

```powershell
cd $HOME
if (-not (Test-Path workbuddy-skills)) { git clone git@github.com:0khszg-sketch/workbuddy-skills.git }
cd workbuddy-skills; git pull
New-Item -ItemType Directory -Force -Path "$HOME\.workbuddy\skills" | Out-Null
Copy-Item -Recurse -Force gouzi-coo "$HOME\.workbuddy\skills\"
```

安装后重启 WorkBuddy 会话，说"狗子启动"即可验证。

## 更新流程

1. 在任意设备上修改技能文件后，提交并推送到本仓库
2. 其他设备执行上面的"更新"命令拉取
3. 遵循原版狗子的多机纪律：**以本仓库 Git 历史对账，不同步任何凭证**
