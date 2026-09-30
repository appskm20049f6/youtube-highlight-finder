# YouTube Highlight Finder

Codex Skill：下載 YouTube 影片、擷取語音、產生含時間碼的 SRT 字幕，再挑選每支影片 5～10 個精華片段。提供標題、開始／結束時間、原文、推薦理由與 YouTube 時間連結，不實際剪片。

## 安裝

在 Codex 貼上這段指令：

```text
請使用 skill-installer 安裝 https://github.com/appskm20049f6/youtube-highlight-finder/tree/main/skills/youtube-highlight-finder
```

安裝完成後，在下一個回合使用：

```text
使用 $youtube-highlight-finder 分析這支影片：https://www.youtube.com/watch?v=影片ID
```

也可以指定「找 8 段、每段約 60 秒、適合初學者」。

## 交付內容

- 原始影片與 WAV 語音檔。
- UTF-8 SRT 字幕，保留原影片時間軸。
- Markdown 與 CSV 精華清單，預設 5～10 段。

## 必要下載與工具準備

完整影片、從影片擷取的 WAV、原語言 SRT、Markdown 和 CSV 都是完成條件。未成功取得影音時不得自行改為字幕摘要後宣告完成。

Skill 會檢查工具路徑與版本，按安裝來源更新或補齊 yt-dlp、FFmpeg／ffprobe、JavaScript runtime（優先 Deno）與 EJS。沒有可靠原語言字幕時，補齊 Python、faster-whisper 與適合硬體的語音辨識模型。相關官方來源與檢查命令已寫入 SKILL.md。

403、429、缺少影音格式或合併失敗會按原因診斷；三次有依據的修復仍失敗則回報阻塞，保留中間成果，不用翻譯字幕替代逐字稿。

## 執行條件

這是 Codex 工作流程指引，不是獨立剪輯程式，也不內建下載或轉錄引擎。執行環境需要可用的影音下載工具（例如 yt-dlp）、FFmpeg／ffprobe，以及可用的原語言字幕或語音辨識工具。Skill 會先檢查工具；無法下載或轉錄時會報告具體原因，不會假造檔案。下載模型或使用付費服務依當次授權處理。

精華依字幕挑選，未驗證畫面效果；字幕時間碼需依可用工具抽查。實際數量依內容品質調整，不為湊數加入無價值片段。

## Skill 原文

[SKILL.md](skills/youtube-highlight-finder/SKILL.md)
