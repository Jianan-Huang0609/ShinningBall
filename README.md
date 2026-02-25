# ShiningBall — 闪耀的灯球

**你的私人舞台追光灯｜OpenClaw × IoT 智能灯光系统（完全本地）**

- 输入：Pi Camera（人体位置/表情）+ USB 麦克风（节奏/BPM/能量）
- 输出：Pan-Tilt 云台追光 + WS2812B 灯环变色/闪烁
- 交互：Discord/Telegram 指令切换模式（Hackathon 现场演示优先 Discord）

> 完整设计文档：`PROJECT_DOC.md`

---

## Demo（必须通过的 5 条验收）

1. **灯球追人**：人在 3 米范围内移动，灯球持续对准人体中心，偏差 < 15°
2. **音乐同步**：播放 3 首不同 BPM 的歌，灯光闪烁与节拍匹配率 > 80%
3. **快慢歌变色**：快歌（>120 BPM）偏红紫系；慢歌（<90 BPM）偏蓝绿系
4. **指令控制**：Discord 发“蹦迪模式”等指令，5 秒内灯球启动响应
5. **完全离线（除消息通道）**：断网后除 Discord 外其余能力仍可运行

---

## Discord 演示（建议指令集 v0）

最少 6 条足够演示：

- `/disco`：蹦迪（高饱和、快闪）
- `/play`：演奏（暖色、柔和）
- `/ambient`：氛围（自适应白光/渐变）
- `/chill`：放松（暖黄慢呼吸）
- `/calibrate`：标定（舵机居中、角度范围校准）
- `/status`：状态（模式/FPS/BPM/温度/设备在线）

**30 秒现场脚本**：
1) 发 `/disco` → 2) 人走动灯追 → 3) 放歌灯按拍闪 → 4) 发 `/chill` 一键变柔 → 5) `/status` 展示“本地运行参数”

---

## 产品是什么（概念形态）

一台桌面智能一体机：矮圆柱、织物/磨砂机身，**顶环 RGB 灯** + **小圆屏** + **摄像头**，可放 Pan-Tilt 云台上灵活转动，灯光能打在场景/人/锚点。参考 Apple HomePod / 小米 Sound，带屏幕感与科技感。详述见 `PROJECT_DOC.md`。

---

## 硬件（推荐版：从零采购，Pi 4B 4GB + 24 灯珠）

> 详细采购/供电/接线说明见 `PROJECT_DOC.md` Part 5。

- Raspberry Pi 4B（4GB）套装（含电源/散热/≥32GB microSD）
- Pi Camera V2（CSI）
- Pan-Tilt 云台套件（2×SG90 舵机）
- WS2812B 24 灯珠灯环（5V）
- USB 麦克风（Linux 免驱优先）

**强制电气保护**：
- 独立 5V 3A 电源（给 LED/舵机）
- 330Ω 电阻（GPIO18→LED DIN 串联）
- 100μF 电容（舵机供电端防抖）
- 供电必须**共地（GND）**

---

## 目录说明（仓库内容）

| 路径 | 说明 |
|------|------|
| **PROJECT_DOC.md** | 完整项目文档：PRD、场景、交付、实施计划、硬件清单 |
| **Demo视频/** | Demo 素材目录（如你已生成/录制） |
| **Demo视频/prompts/** | 极梦生成用的 prompt 框架：产品图 → 视频首帧 → 三场景 Demo 视频 |
| **Demo视频/主体物图片/** | 极梦生成的产品风格锚点图，做视频时带入以保证形象一致 |

**prompts 使用顺序**：`01_产品图_风格锚点` → `02_视频风格锚点_首帧` → `极梦_三场景_demo视频_prompts`。具体步骤见 `Demo视频/prompts/README.md`。

---

## 快速启动（占位）

> 代码与脚本落地后补齐。

- `engine/`：Python 引擎（vision/audio/fusion/hardware）
- `openclaw-skill/`：OpenClaw 技能（Discord 指令 → 切模式/调用引擎）

---

## Troubleshooting（最常见翻车点）

- **Pi 反复重启/花屏/灯乱闪**：99% 是供电（LED/舵机不要从 Pi 取电；检查共地）
- **舵机抖动**：加电容 + 软件低通滤波 + 死区（<3° 不动）
- **MediaPipe 很慢**：降分辨率到 320×240 或 240×180；`model_complexity=0`
- **音频延迟大**：缩小 FFT 窗口（如 1024→512）
