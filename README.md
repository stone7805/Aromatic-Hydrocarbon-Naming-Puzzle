# 芳香烃命名接接乐

可直接发布到 GitHub Pages 的离线单文件网页游戏。首页选择单人/双人、左/右角色、各侧专属道具，以及“常用名称”或“定位命名”，然后观察苯环图，接住中央正确名称。

- 每侧 10 轮、满分 100；前三轮共 60 分。左右独立计分，答错不扣分，暂停本侧并提示重试。
- 环图显示 C₆ 苯环、1—6 位读图标记，以及连出的 CH₃、C₂H₅；环上隐含的氢未画出。环位标记用于读图，不必等同正式命名编号。
- 速度、暂停、声音、放大、线索、刷新恢复、打印练习记录均在浏览器完成；不使用外部服务。
- 范围聚焦苯和单、双、三取代的常见芳香烃，不覆盖复杂多取代命名规则。

## 发布到 GitHub Pages（无需编程）

1. 新建 GitHub 仓库（例如 `aromatic-relay-game`）。
2. 将本目录的 **`index.html`** 上传到仓库根目录；README 可一同上传，但不必上传题库或 `skill/`。
3. 打开仓库 **Settings → Pages → Build and deployment**，Source 选 **Deploy from a branch**，Branch 选 **main / (root)**，保存。
4. 等待 Pages 显示站点地址后访问；通常形如 `https://你的用户名.github.io/aromatic-relay-game/`。发布完成前不要把示例形式当作已上线链接。

也可直接双击 `index.html` 本地练习。浏览器存储的本机成绩可能因清理站点数据而丢失，不能用于正式考试成绩认证。

## 复用技能与修改题库

`skill/build-learning-relay-game/` 是上传的接接乐技能包复刻副本，保留 `SKILL.md`、设计与 QA 参考、结构校验器、生成器和页面壳。当前芳香烃作品通过 `芳香烃题库素材.json` → `生成题库.py` → `question-bank.json` → 校验器 → 生成器 → `index.html` 得到。若修改题意、位置或玩法，应更新版本号与浏览器存储键，再重新生成并复验，不应只改页面文字。

在本目录运行：

```text
python 生成题库.py
python skill/build-learning-relay-game/scripts/validate_relay_bank.py question-bank.json
python skill/build-learning-relay-game/scripts/build_relay_game.py question-bank.json index.html
```

上面最后一条会覆盖本项目的 `index.html`，但不会覆盖用户上传的工作区根目录 `index.html`。
