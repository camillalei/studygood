# 广州版五年级上册英语学习 App

## 访问地址

**线上地址（任何设备可用）：**
```
https://camillalei.github.io/studygood
```

**本地开发地址（需电脑开启服务器）：**
```
http://localhost:8788
```

**局域网地址（同一 WiFi 下手机/平板可用）：**
```
http://192.168.0.105:8788
```

---

## 本地启动服务器

```bash
cd /Users/camillalei/Desktop/work/kiro/study/english
python3 -m http.server 8788 --directory app
```

---

## 更新线上内容

每次修改代码或数据后，运行以下命令同步到 GitHub Pages：

```bash
cd /Users/camillalei/Desktop/work/kiro/study/english/app
git add .
git commit -m "更新内容"
git push
```

推送后等待约 1-2 分钟，线上网站自动更新。

---

## 修改数据流程

内容数据存放在两个文件（需保持同步）：

- `app/data/content.json` — 实际编辑的数据文件
- `app/data/content.js` — 供网页加载的 JS 文件（由 json 生成）

**每次修改 content.json 后，必须运行以下命令重新生成 content.js：**

```bash
cd /Users/camillalei/Desktop/work/kiro/study/english
python3 -c "import json; data=json.load(open('app/data/content.json',encoding='utf-8')); open('app/data/content.js','w',encoding='utf-8').write('window.ENGLISH_DATA = '+json.dumps(data,ensure_ascii=False)+';')"
```

---

## 项目结构

```
english/
├── app/                        # 网页应用主目录（GitHub Pages 根目录）
│   ├── index.html              # 首页（单元选择）
│   ├── assets/
│   │   └── style.css           # 全局样式
│   ├── data/
│   │   ├── content.json        # 数据源（编辑这个）
│   │   └── content.js          # 网页加载用（自动生成）
│   └── pages/
│       ├── unit.html           # 单元详情页（单词/句型/短语/对话/课文）
│       ├── flashcard.html      # 闪卡练习
│       ├── spell.html          # 拼写测试
│       ├── dictation.html      # 听写
│       ├── sentences.html      # 句型练习
│       └── review.html         # 错题复习
├── 2026秋季广州版五上英语-资料来源网络整理.pdf
└── README.md                   # 本文档
```

---

## GitHub 仓库

- **仓库地址：** https://github.com/camillalei/studygood
- **Pages 设置：** Settings → Pages → Branch: main / (root)

### 绑定自定义域名（可选，后续操作）

1. 购买域名
2. 在域名商处添加 CNAME 记录指向 `camillalei.github.io`
3. 在 GitHub → Settings → Pages → Custom domain 填入域名
4. GitHub 自动配置 HTTPS

---

## 登录配置

登录页文件：`app/login.html`

打开 `login.html`，找到顶部 `CONFIG` 区修改账号密码（账号密码不同步到 GitHub），修改后重新推送即可。

---

## 各页面功能说明

| 页面 | 功能 |
|------|------|
| 首页 | 选择单元，查看学习进度 |
| 单词 tab | 单词列表，点击朗读，标记掌握状态 |
| 句型 tab | 句型列表，全部朗读，跳转练习/背诵 |
| 短语 tab | 短语卡片，全部朗读，跳转练习/听写 |
| 对话 tab | 聊天气泡形式，点击朗读，跟读对话 |
| 课文 tab | Get Started + Close Reading，全文朗读 |
| 闪卡练习 | 翻转卡片，左右滑动标记认识/不认识 |
| 拼写测试 | 听发音拼写单词 |
| 听写 | 听句子写短语 |
| 句型练习 | 看中文选英文句子 |
| 错题复习 | 汇总所有错题重练 |
