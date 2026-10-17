# AI 每日情報：執行規範

每天的排程任務會照這份檔案執行。想調整內容、方向或格式，直接改這份檔案就好，下一次排程就會套用。

## 通用原則

- 全部使用**繁體中文**撰寫。
- **一律上網查最新資訊**（WebSearch / WebFetch），不可用訓練記憶或舊暫存資料充數；每條消息都要附**真實來源 URL 與日期**。
- 比較類內容**優先參考社群資料**（Reddit r/LocalLLaMA、r/StableDiffusion、r/AMD、r/ROCm、r/ClaudeAI、r/OpenAI、r/ChatGPTCoding、Hacker News、X、GitHub issues、YouTube 實測）。
- 查不到就寫「本日無重大更新」，不確定就標「待確認」，**絕不捏造**。
- 開始前先讀最近 1–3 份 `reports/` 與 `simulation/evolution-log.md`，避免重複報舊聞，並延續昨天的推演。

## 產出檔案

1. `reports/YYYY-MM-DD.md`：當日完整日報（格式見下）。
2. `models/rx9070xt-latest.md`：RX 9070 XT 可用模型的**現行總表**（整份覆寫為最新狀態，表頭寫最後更新日期）。
3. `simulation/evolution-log.md`：推演演進紀錄（**只追加不刪除**，在最上方加當日條目）。
4. `README.md` 的「最新日報」連結與歷史清單更新。

## 日報格式（reports/YYYY-MM-DD.md）

```
# AI 每日情報 YYYY-MM-DD

## 今日三大重點（TL;DR）

## 一、OpenAI / Anthropic 最新消息
### OpenAI
- **[日期] 標題**：重點摘要（來源）
### Anthropic
- …
### 社群反應

## 二、AMD RX 9070 XT（16GB）本地模型動態
### 本日新進／更新的模型（與昨日總表的差異）
### 軟體環境更新（ROCm / llama.cpp / Ollama / LM Studio / ComfyUI）
### 各分類首選（摘要，完整表見 models/rx9070xt-latest.md）

## 三、Codex × Claude Code 創作應用推演（第 N 輪）
### 本輪依據的新資訊
### 遊戲製作
### 漫畫產生
### 動畫製作
### 對上一輪的檢討
- ✅ 保留（實測／社群證實有效）
- ⚠️ 修正（有更好的做法）
- ❌ 淘汰（不適合、成本過高或已過時）
- ➕ 新增（新功能帶來的新玩法）
### 下一輪要觀察／驗證的項目

## 來源
```

## 模型分類（models/rx9070xt-latest.md）

硬體前提：AMD Radeon RX 9070 XT，RDNA4（gfx1201），16GB GDDR6。每類列 3–6 個，含參數量、建議量化、16GB 能否完整載入、社群實測速度、優缺點、發布日期，並標出「首選」。

- 通用大型語言模型（對話／推理）
- 程式碼模型
- 劇本／小說／角色扮演／創意寫作（標註中文能力）
- 圖片生成
- 圖片編輯／角色一致性（漫畫用 LoRA、ControlNet、IP-Adapter 類）
- 影片／動畫生成
- 語音 TTS／語音克隆／STT
- 音樂／音效生成
- 視覺語言多模態（VLM）
- 3D 生成
- Embedding／RAG
- 軟體環境建議（Windows / Linux 推薦組合與已知坑）

## 推演規則（第三部分）

- 每輪都以上一輪 `simulation/evolution-log.md` 的結論為基礎，搭配當日新資訊重新推演。
- 每個應用要寫：**做法（具體工作流程／指令／工具串接）**、**適合誰用 Codex、誰用 Claude Code**、**預期效益**、**風險與限制**。
- 可以把本地模型（第二部分）納入管線，例如 Claude Code 驅動 ComfyUI 產漫畫格、Codex 寫 Godot 腳本。
- 檢討分 ✅⚠️❌➕ 四類，每項附理由；同一想法連續 3 輪都沒有新證據支持就降級或淘汰。
