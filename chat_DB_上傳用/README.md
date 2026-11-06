# Ch6 Flask + NoSQL MongoDB 聊天室作業

| 資料夾 | 對應投影片 | 歷史紀錄存在哪 |
|---|---|---|
| `ch6_chat_jsonDB/` | 6-3 JSON 資料庫 | `chat_history/messages.json` |
| `ch6-2_chat_mongoDB/` | 6-4 本地 MongoDB | 本機 MongoDB → `chatapp.messages` |
| `ch6-3_chat_mongoDB_atlas/` | 6-5 Atlas + Render | MongoDB Atlas 雲端 → `chatapp.messages` |

## 執行（在 chat_DB 資料夾的終端機）

```bash
./start_mongodb.sh                 # 重開機後才需要（啟動本地 MongoDB）
cd ch6_chat_jsonDB && uv run python app.py          # JSON 版
cd ch6-2_chat_mongoDB && uv run python app.py       # MongoDB 版
```
打開 http://localhost:5000 ，按 Ctrl+C 停止。

## Atlas 版（要用自己的帳號）
1. 在 MongoDB Atlas 建 Free cluster、建使用者、Network Access 開 0.0.0.0/0
2. 把 `ch6-3_chat_mongoDB_atlas/.env.example` 複製成 `.env`，填入自己的連線字串
3. `cd ch6-3_chat_mongoDB_atlas && uv run python app.py` 本地測試
4. 上傳 GitHub（`.env` 已在 .gitignore，不會被上傳）
5. Render → Web Service，Start Command：`uv run python ch6-3_chat_mongoDB_atlas/app.py`，
   Environment 加 `MONGO_URI=...` 與 `PYTHON_VERSION=3.12.6`
