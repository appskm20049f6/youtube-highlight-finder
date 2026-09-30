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

## 執行條件

這是 Codex 工作流程指引，不是獨立剪輯程式，也不內建下載或轉錄引擎。執行環境需要可用的影音下載工具（例如 yt-dlp）、FFmpeg／ffprobe，以及可用的原語言字幕或語音辨識工具。Skill 會先檢查工具；無法下載或轉錄時會報告具體原因，不會假造檔案。下載模型或使用付費服務依當次授權處理。

精華依字幕挑选，未驗證畫面效果；字幕時間碼需依可用工具抽查。實際數量依內容品質調整，不為湊數加入無價值片段。

## Skill 原文

[SKILL.md](skills/youtube-highlight-finder/SKILL.md)
