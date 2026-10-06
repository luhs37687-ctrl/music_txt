# music_txt

手机 App（MIT App Inventor）在线曲谱下载用的曲谱仓库。

---

## 一、曲谱文件格式

```
音高Hz,时长ms;音高Hz,时长ms;...
```

- `;` 分隔不同音符
- `,` 分隔 **音高(Hz)** 和 **时长(ms)**
- App 通过蓝牙发送时会加前缀 `SONG,`、结尾 `\n`

**示例（小星星开头）：**
```
262,500;262,500;392,500;392,500;440,500;440,500;392,1000
```

---

## 二、曲目索引 `songs.txt`

**格式：`显示名,文件名`（文件名不含 .txt），一行一首。**

```
生日快乐,happy_birthday
小星星,twinkle
两只老虎,two_tigers
欢乐颂,ode_to_joy
玛丽有只小羊羔,mary_lamb
小蜜蜂,bee
```

App 先下载 `songs.txt` → 解析出曲目列表 → 用户选一首 → 拼 URL 下载对应文件。

---

## 三、曲目清单

| 显示名 | 文件名 | 说明 |
|---|---|---|
| 生日快乐 | `happy_birthday.txt` | C大调 BPM=120 |
| 小星星 | `twinkle.txt` | C大调 BPM=120 |
| 两只老虎 | `two_tigers.txt` | C大调 BPM=120 |
| 欢乐颂 | `ode_to_joy.txt` | C大调 BPM=120 |
| 玛丽有只小羊羔 | `mary_lamb.txt` | C大调 BPM=120 |
| 小蜜蜂 | `bee.txt` | C大调 BPM=120 |

---

## 四、URL 规则

```
索引：  https://raw.githubusercontent.com/luhs37687-ctrl/music_txt/main/songs.txt
曲谱：  https://raw.githubusercontent.com/luhs37687-ctrl/music_txt/main/<文件名>.txt
```

例如：
```
https://raw.githubusercontent.com/luhs37687-ctrl/music_txt/main/twinkle.txt
```

---

## 五、音高对照（C大调）

| 音名 | Hz | 简谱 |
|---|---|---|
| C4 | 262 | 1 |
| D4 | 294 | 2 |
| E4 | 330 | 3 |
| F4 | 349 | 4 |
| G4 | 392 | 5 |
| A4 | 440 | 6 |
| B4 | 494 | 7 |
| C5 | 523 | 1̇ |
| D5 | 587 | 2̇ |
| E5 | 659 | 3̇ |
| F5 | 698 | 4̇ |
| G5 | 784 | 5̇ |

---

## 六、加新曲子的步骤

1. 按格式新建 `<文件名>.txt`（**文件名用英文/拼音**，避免 URL 编码问题）
2. 在 `songs.txt` 里加一行 `显示名,文件名`
3. 提交推送 —— **App 不用改**
