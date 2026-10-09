# NEUTRINO — Twitter/X 发布文案

## 方案 A：单条发布（≤140 汉字以内，可直接发）

把望远镜埋进南极冰下——不是看星星，是等一个粒子穿过地球来到身旁。

我用 Three.js + 手写 GLSL 拍了部 2 分钟的中微子音乐电影《NEUTRINO》：7 幕、33 句歌词，全部卡在 129.3 BPM 上，纯代码逐帧渲染。

「以前我们用光看星空，现在用粒子看宇宙」

#中微子 #IceCube #creativecoding

---

## 方案 B：Thread 串推（主推 + 5 条）

### 主推
用代码拍了一部「中微子」音乐电影《NEUTRINO》🎬

不是 AE，不是 C4D——Three.js + 12 个手写 GLSL 着色器，在浏览器里逐帧渲染。2 分钟、7 幕、33 句歌词，全部卡在 129.3 BPM 的节拍上。

先看片，再讲它是怎么拍出来的 👇

### 2/6 故事线
剧本跟着歌词走，7 幕对应 7 个音乐段落：

I 黑洞射出一根发丝细的蓝线
II 冲入南极冰层，IceCube 在黑暗中逐颗亮起
III 穿过整个地球，从冰下上行
IV Cherenkov 光锥展开 → 探测器 1→2→5→10 级联点亮
V 回头看，箭头指向宇宙的源
VI–VII 一路拉远到宇宙，最后硬停

### 3/6 视觉铁律
给全片定了三条铁律：

· 蓝色只给中微子和 Cherenkov 光，星云尘埃一律银灰
· 黑色负空间 ≥ 60%，每帧都要说清「光从哪来」
· 主角永远是一根线，线宽按屏幕像素算，再远也是「一根线」

看到蓝，你就知道是它。

### 4/6 技术
怎么渲染的：

· 体积光线步进：吸积盘、地球分层内部、宇宙网
· 每帧 5–6 个子帧累积，做 180° 快门运动模糊
· HDR → 6 级 Bloom → ACES → 色散 → 双层胶片颗粒
· 无头 Chrome 确定性导出，ffmpeg 合成

约 3000 行 JS + GLSL，没有一张贴图。

### 5/6 科学细节
科学上不敢糊弄：

· 中微子本身不发光，蓝光只出现在核反应之后——那是带电 μ 子的 Cherenkov 辐射
· 探测器点亮顺序按光锥几何算，不随机闪
· 方向重建的箭头穿出冰层，指向耀变体 TXS 0506+056

「它很少撞上物质，所以很难被找到」

### 6/6 收尾
「以前我们用光看星空，现在用粒子看宇宙」

全片 2:06，1080p，纯代码渲染。
如果你也喜欢科学 × 影像 × 代码的混搭，这根蓝线送给你 🩵

#中微子 #IceCube #creativecoding #WebGL #threejs

---

## 方案 C：English（单条）

I made a 2-minute music film about NEUTRINOS — entirely in code.

Three.js + hand-written GLSL: volumetric ray-marching, 180° shutter motion blur, 6-stage bloom, rendered frame-by-frame in headless Chrome.

7 acts locked to 129.3 BPM. No textures, no stock — just math and physics.

"Once we catch it, we can know the shape of the universe."

#Neutrino #IceCube #creativecoding #WebGL

---

## 发布小贴士

1. **视频规格**：X 普通账号上传上限 512MB / 2:20。`out/NEUTRINO_1080p.mp4` 时长刚好，但 714MB 超重，建议 `ffmpeg -i NEUTRINO_1080p.mp4 -c:v libx264 -crf 24 -pix_fmt yuv420p NEUTRINO_x.mp4` 重压一版，或直接用 720p 版本。
2. **封面**：用 `out/act5-7_keyframes.png` 里的 Cherenkov 光锥或"宇宙新窗口"帧做封面图。
3. **钩子变体**：想突出 AI 协作角度（本项目由 Claude 生成），把主推第一句换成「我和 Claude 一起拍了一部中微子音乐电影」——这个钩子通常转发率更高。
