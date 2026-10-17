# LifeHub 收件箱

一个单文件 PWA，用来在**手机上**把两样东西送进个人数据中枢（私有库
`lifehub-data`），全程不用打开电脑：

- **账单**：选一个咔皮记账导出的 `.xlsx` → 传到 `life/raw/money/`
- **日记**：打一段字 → 传到 `life/raw/diary/inbox/YYYY-MM-DD.txt`

云端 `lifehub-data` 的定时任务每小时（北京时间 07:17–23:17 的 :17）会把这两样
吃进去：账单入库 + 分类 + 重画看板 + 重新加密发布；日记转成正式日记条目。

## 打开

<https://kangrenwang11-collab.github.io/lifehub-inbox/>

安卓 Chrome 里「⋮ → 添加到主屏幕」就是一个图标。

## 设置

第一次打开要贴一个 GitHub 令牌（只存在手机浏览器 localStorage 里，只发给
`api.github.com`）：

1. 打开 <https://github.com/settings/personal-access-tokens/new>
2. Repository access → Only select repositories → 勾 `lifehub-data`
3. Permissions → Repository permissions → **Contents** = Read and write
4. Generate，把 `github_pat_…` 整段贴进页面的「设置」

## 这个仓库里有什么

只有页面本身（`index.html` / `manifest.webmanifest` / 图标）。
**不含任何个人数据**——数据全在私有库 `lifehub-data`。
