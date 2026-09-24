# 作業小管家：Apple + Google 登入 + RBAC

Node.js + Express + SQLite 全端版本。

## 角色
- admin：所有權限、管理帳號與角色
- teacher：建立/編輯/刪除作業、批改
- student：查看作業、提交作業
- parent：查看作業與統計

第一次登入依 `.env` 的 ADMIN_EMAILS / TEACHER_EMAILS / PARENT_EMAILS 指派初始角色，其餘預設 student。之後 admin 可在「權限管理」修改。

## 安裝
```bash
npm install
cp .env.example .env
npm start
```
Windows PowerShell 可用 `Copy-Item .env.example .env`。

Google callback：`http://localhost:3000/auth/google/callback`
Apple Return URL：`https://你的網域/auth/apple/callback`

正式環境請使用 HTTPS、強 SESSION_SECRET，並將 session、資料庫與檔案儲存改成適合正式部署的服務。
