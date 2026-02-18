# ShiningBall 极梦 Demo 视频 Prompts（三场景）

面向极梦平台（C Dance / C Dream）生成三条产品 Demo 视频，重点体现：**交互感**（手机/OpenClaw 指令）、**音乐场景**（音响与节奏）、**灯光场景**（一体机顶环灯追光、变色、呼吸）、**OpenClaw + 硬件能力**（本地、自主、智能一体机）。

**产品形态**：参考 Apple HomePod / 小米智能音箱，为一台**桌面智能一体机**——矮圆柱、织物/磨砂机身、**顶部环形 RGB 灯带** + **小圆屏**、**摄像头**、**内置音响**，可整体 **Pan-Tilt 灵活转动** 实现追光，**灯光可打在场景/人/锚点位置**，带科技感与屏幕感。详见 PROJECT_DOC Part 1.5。

---

## 生成流程（三步骤，按顺序）

| 步骤 | 文件 | 产出 | 说明 |
|------|------|------|------|
| **1** | `01_产品图_风格锚点.md` | **产品风格锚点图** | 用该文件中的「必出：主锚点图」生成产品图，保存（如 `shiningball_product_anchor.png`）。后续所有步骤都依赖此图保证设备外观一致。 |
| **2** | `02_视频风格锚点_首帧.md` | **各场景视频风格锚点图** | 上传产品锚点图后，分别生成场景一 D1+D2、场景二 P1+P2、场景三 A1+A2 的首帧图，保存为各场景的「视频风格锚点」。 |
| **3** | 本文件 `极梦_三场景_demo视频_prompts.md` | **三条 Demo 视频** | 生成视频时：**上传产品锚点图 + 该场景视频风格锚点图（首帧）**，再按镜号使用下方对应场景的 D1–D7 / P1–P7 / A1–A6 prompt 生成片段或整段。 |

**重要**：步骤 2 和 3 中都必须带入**产品锚点图**，这样视频里的设备形象才会与产品图一致。

---

---

## 0. 统一风格锁与负面词

### STYLE LOCK（建议每条 prompt 末尾都带上）

```
Cinematic product film, premium smart home aesthetic, Apple and Xiaomi-like product design,
one compact smart speaker device as hero: short cylinder shape, fabric mesh or frosted body, 
top ring RGB light with small circular display screen in center, small camera on rim for tracking, built-in speaker,
can sit on desk or on pan-tilt base for flexible rotation, light from device can spotlight scene or person or anchor point,
soft room lighting mixed with colored glow from the device top ring,
realistic human silhouette or back view (no full face close-up for privacy),
clean modern room interior, 16:9, no logos no watermark,
smooth motion, film grain subtle, high-end lifestyle vibe with tech and screen presence,
graphite white and dark gray surfaces with purple, amber, cyan accent from the ring light
```

### 负面词 NEGATIVE（每条可追加）

```
no distorted hands, no extra fingers, no messy cables, no cluttered room, 
no readable phone screen text, no brand logos, no low-res, no artifacts, 
no deformed body, no harsh lighting, no cartoon style, no watermark
```

---

# 场景一：一人蹦迪（推荐用 C Dance）

**本场景生成视频时请带入**：产品锚点图（来自 `01_产品图_风格锚点.md`）+ 本场景视频风格锚点图（D1、D2，来自 `02_视频风格锚点_首帧.md`）。

**叙事**：发 Discord 指令 → 一体机呼吸灯亮 → 放电子乐顶环紫红闪爆 → 人走到中央一体机转头追光 → 随节奏跳舞灯光跟随 → 累了灯光自动变暖黄慢呼吸。

| 镜号 | 镜头类型 | 叙事要点 | 时长建议 |
|------|----------|----------|----------|
| D1 | Wide | 房间全景 + 一体机待机 | 2–3s |
| D2 | Close | 手机发「蹦迪模式」+ 一体机由暗到呼吸灯 + 小屏 | 3s |
| D3 | Medium | 内置音响出电子乐 + 顶环紫红闪烁与节拍同步 | 4s |
| D4 | Medium | 人走到中央，一体机云台扭头把光打在人身上 | 3s |
| D5 | Wide | 人随音乐跳舞，一体机左右跟随，灯光闪爆 | 5s |
| D6 | Medium | 动作变慢，顶环灯光自动切暖黄慢呼吸 | 3s |
| D7 | Hero | 一体机 + 人影 + 暖光收束 | 2s |

### D1（Wide）开场：房间与一体机待机

**极梦用：**

```
Wide shot of a modern minimalist room at night, a single compact smart speaker device on the shelf—short cylinder, fabric mesh body, top ring light dim or off, small circular screen faint, small camera on rim—soft ambient room light, person silhouette in the background near the door, calm and ready, cinematic 16:9. 
STYLE LOCK. NEGATIVE.
```

### D2（Close）交互：手机发指令 + 一体机亮起

**极梦用：**

```
Close-up of a smartphone in hand, screen shows a chat interface with one sent message bubble (blurred, no readable text), 
thumb just tapped send, in the background the smart speaker device top ring starts glowing with a soft breathing amber pulse, small screen shows a minimal mode icon, intimate moment of human commanding the device, shallow DOF. STYLE LOCK. NEGATIVE.
```

### D3（Medium）音乐 + 灯光节奏同步

**极梦用：**

```
Medium shot: the same smart speaker device is playing music from its built-in speaker, subtle sound waves or bass vibe in the air, 
the top ring light explodes into purple and red strobe flashing in perfect sync with the beat, 
room filled with dynamic colored light from the device, person silhouette starting to move, high energy. STYLE LOCK. NEGATIVE.
```

### D4（Medium）追光：一体机转头打在人身上

**极梦用：**

```
Medium shot: person standing in the center of the room, the smart speaker device on pan-tilt base has turned to face them (flexible rotation),
top ring casting one strong beam of colored light (purple or magenta) illuminating the person from the front—light from device onto person,
like a mini spotlight tracking the user, fabric cylinder body visible, camera on rim, cinematic. STYLE LOCK. NEGATIVE.
```

### D5（Wide）跳舞 + 灯光跟随

**极梦用：**

```
Wide shot: person dancing freely in the middle of the room, the smart speaker on pan-tilt base smoothly panning left and right following the person (flexible rotation),
top ring light always on the dancer, light from device spotlighting the person, colors shifting purple-red-electric blue with the music rhythm from the device, 
room feels like a private club, dynamic and immersive. STYLE LOCK. NEGATIVE.
```

### D6（Medium）疲劳检测：灯光变柔和

**极梦用：**

```
Medium shot: same person now moving slowly, tired, the device top ring light shifts from intense purple-red strobe to warm amber and soft yellow,
slow breathing pulse, small screen dim, calm and cozy, as if the system understood the user is winding down. STYLE LOCK. NEGATIVE.
```

### D7（Hero）收束：一体机与人同框

**极梦用：**

```
Hero product shot: the compact smart speaker (fabric cylinder, top ring, small screen, camera) in foreground glowing warm amber, 
person silhouette relaxed in the background, room lit by the device only, 
premium lifestyle vibe, 16:9, cinematic end frame. STYLE LOCK. NEGATIVE.
```

---

# 场景二：独奏练习（推荐用 C Dream）

**本场景生成视频时请带入**：产品锚点图（来自 `01_产品图_风格锚点.md`）+ 本场景视频风格锚点图（P1、P2，来自 `02_视频风格锚点_首帧.md`）。

**叙事**：Telegram 发「演奏模式 民谣」→ 一体机暖色脉动 → 坐姿弹吉他一体机锁定打光 → 激情段落灯光变亮冷白 → 轻柔段落暖橙 → 手机录视频观感升级。

| 镜号 | 镜头类型 | 叙事要点 | 时长建议 |
|------|----------|----------|----------|
| P1 | Wide | 下午房间 + 一体机 + 吉他 | 2s |
| P2 | Close | 手机发「演奏模式」+ 一体机暖色呼吸 + 小屏 | 3s |
| P3 | Medium | 坐姿弹吉他，一体机光束稳定打在人身上 | 4s |
| P4 | Close | 弹到激情段，顶环灯变亮、冷白色 | 3s |
| P5 | Medium | 指弹轻柔段，灯光回到暖橙色 | 3s |
| P6 | Close | 手机竖屏录视频，画面里是人与动态灯光 | 3s |
| P7 | Hero | 一体机 + 吉他 + 暖光收束 | 2s |

### P1（Wide）开场：下午演奏环境

**极梦用：**

```
Wide shot of a cozy room in afternoon daylight, acoustic guitar on stand, 
compact smart speaker (fabric cylinder, top ring, small screen, camera) on a side table, soft natural light mixed with a hint of warm tone from the device, 
empty chair in frame, calm and inviting. STYLE LOCK. NEGATIVE.
```

### P2（Close）交互：发演奏模式

**极梦用：**

```
Close-up of hand holding phone, Telegram chat with one sent message (blurred), 
in background the smart speaker top ring switches to warm orange and amber, slow breathing pulse, small screen shows a gentle icon, 
“演奏模式” feeling, warm and creative. STYLE LOCK. NEGATIVE.
```

### P3（Medium）追光锁定演奏者

**极梦用：**

```
Medium shot: person sitting on chair playing acoustic guitar, the smart speaker on pan-tilt base aimed at the musician (flexible rotation, light from device onto person), 
top ring casting steady beam of warm light on upper body and guitar, no jitter, like a small stage light, 
peaceful and focused. STYLE LOCK. NEGATIVE.
```

### P4（Close）激情段落：灯光变亮冷白

**极梦用：**

```
Close-up: guitar strumming harder, the device top ring brightens and color shifts to cool white and light blue, 
room feels more intense, built-in speaker and light in sync with the playing energy. STYLE LOCK. NEGATIVE.
```

### P5（Medium）轻柔段落：暖橙回归

**极梦用：**

```
Medium shot: fingerstyle gentle playing, the top ring dims slightly and returns to warm orange and soft amber, 
smooth transition, no sudden jump, calm and professional. STYLE LOCK. NEGATIVE.
```

### P6（Close）录视频：人与动态灯光

**极梦用：**

```
Close-up: smartphone in portrait mode recording, screen shows a preview of the musician with dynamic lighting from the smart speaker in the frame (light from device spotlighting the musician), 
premium “studio-like” look, subtle motion. STYLE LOCK. NEGATIVE.
```

### P7（Hero）收束

**极梦用：**

```
Hero shot: compact smart speaker (fabric cylinder, top ring, small screen, camera) glowing warm amber, acoustic guitar in frame, 
person silhouette, afternoon mood, premium product + lifestyle, 16:9. STYLE LOCK. NEGATIVE.
```

---

# 场景三：日常氛围灯（推荐用 C Dream）

**本场景生成视频时请带入**：产品锚点图（来自 `01_产品图_风格锚点.md`）+ 本场景视频风格锚点图（A1、A2，来自 `02_视频风格锚点_首帧.md`）。

**叙事**：无指令，全天自适应。早上坐桌前一体机中性白光 → 下午站起来活动灯光变暖 → 晚上放音乐自动音乐同步 → 深夜人离开一体机自动熄灭。

| 镜号 | 镜头类型 | 叙事要点 | 时长建议 |
|------|----------|----------|----------|
| A1 | Wide | 早上房间，人坐桌前，一体机柔和白光 | 3s |
| A2 | Medium | 下午人站起活动，顶环灯渐变为暖色 | 3s |
| A3 | Medium | 晚上内置音响放歌，顶环自动随音乐变色 | 4s |
| A4 | Close | 一体机特写：顶环从节奏彩色变为缓慢呼吸，小屏微亮 | 2s |
| A5 | Wide | 深夜空房间，一体机缓缓熄灭 | 3s |
| A6 | Hero | 一体机 + 时钟/窗景，强调「零操作」 | 2s |

### A1（Wide）早上：人在即亮，中性白光

**极梦用：**

```
Wide shot: morning, person sitting at desk working on laptop, 
the compact smart speaker (fabric cylinder, top ring, small screen) emits soft neutral white light from its ring,
small screen faint, like a gentle desk companion, clean and productive. STYLE LOCK. NEGATIVE.
```

### A2（Medium）下午：人动灯暖

**极梦用：**

```
Medium shot: person standing up from desk, stretching, 
the device top ring light gradually shifts from white to warm amber and soft yellow, 
smooth transition, as if the room knows the user is taking a break. STYLE LOCK. NEGATIVE.
```

### A3（Medium）晚上：音乐同步自动开启

**极梦用：**

```
Medium shot: evening, soft room light, music playing from the smart speaker built-in speaker, 
the top ring automatically starts syncing with the music—gentle color changes and soft pulse, 
no one touching phone or switch, “lights just get it”. STYLE LOCK. NEGATIVE.
```

### A4（Close）一体机特写：节奏到呼吸

**极梦用：**

```
Close-up of the smart speaker (fabric cylinder, top ring, small circular screen, camera),
ring colors shifting from music-sync mode to a slow breathing fade, small screen dim,
smooth and hypnotic, premium product detail. STYLE LOCK. NEGATIVE.
```

### A5（Wide）深夜：人走灯灭

**极梦用：**

```
Wide shot: empty room at night, the smart speaker top ring slowly dims and turns off, small screen goes dark, 
only faint ambient light left, calm and autonomous, “no one home, light knows”. STYLE LOCK. NEGATIVE.
```

### A6（Hero）收束：零操作一天

**极梦用：**

```
Hero shot: the compact smart speaker (fabric cylinder, top ring, small screen, camera) in a clean room, window with soft night view, 
minimal tagline vibe (no text), “all day, no touch”, premium smart home, 16:9. STYLE LOCK. NEGATIVE.
```

---

# 极梦平台使用建议

| 场景 | 推荐模型 | 说明 |
|------|----------|------|
| 一人蹦迪 | **C Dance** | 节奏感强、闪切多，适合音乐+灯光同步与追光动感 |
| 独奏练习 | **C Dream** | 氛围柔和、过渡顺，适合暖色与冷白渐变 |
| 日常氛围 | **C Dream** | 安静、时间流逝感，适合「无操作」叙事 |

- **统一风格**：三条片都用同一套 STYLE LOCK + NEGATIVE，便于剪成系列或混剪。
- **成片节奏**：每条约 18–25 秒可只保留核心 4–5 镜；若要 1–2 分钟，可每镜拉长或加重复节奏镜头。
- **交互与硬件**：D2/P2 强调「手机发指令」，D3/P3/A3 强调「一体机+音乐+小屏」，D4/D5/P3 强调「追光」，A1/A2/A5 强调「自动、零操作」，便于体现 OpenClaw + 硬件能力。

---

**步骤 3 提醒**：生成每条视频时，在极梦中**先上传产品锚点图 + 该场景视频风格锚点图（首帧）**，再使用本文件该场景的 D1–D7 / P1–P7 / A1–A6 的「极梦用」prompt，这样产品形象与画面风格会与锚点一致。

> *Turn your room into a stage. One ball. Zero cloud. All you.*  
> 三条 Demo 对应 PROJECT_DOC 场景一 / 二 / 三；流程见本文件顶部「生成流程（三步骤）」。
