# NetworkClaw — 约 136 秒英文故事视频

成片：`output/NetworkClaw-story-en.mp4`。1920×1080，24 fps，约 136.2 秒（实测时长见 `renders/verification.json`），英文合成旁白、画面内英文字幕，以及可切换的英文字幕轨。独立字幕在 `subtitles/networkclaw.en.srt`。旧版成片、源文件、音频和脚本保存在 `archive/`。

本轮只调整第 5–12 段（Coordinator、Agent、Tool、Data、Evidence 和 LLM 决策）：语速相对上一版降低 8%，段间停顿从 0.30 秒增加到 0.55 秒。总时长增加约 7.73 秒；开场、结尾及全部文案保持不变。字幕、镜头与提示图层按新时间轴重新渲染。逐段时长回归证据在 `renders/pace-verification.json`，修改前完整备份在 `archive/v8-before-middle-pace/`。

本版重点讲清 INOC 与 NetworkClaw 的集成：工程师在 INOC 看到 active alert，在初步分析基础上点击 Intelligent Analysis；INOC 自动把告警上下文传给 NetworkClaw，触发 LLM 驱动的自动根因分析，响应再流式回到 INOC 对话框，工程师可以继续追问。Network engineer 与 INOC 的位置已调整，并加入明确的告警/响应连线。

新增内容还包括 Medical Model 项目提炼的 specialist agents 和 tools、与网络 domain 团队共建的 prompt/workflow，以及 Data Management System 的独立说明：inventory、SevOne metrics、HPNA device configurations 汇入 data lake，再向工具提供实时 metrics、logs、alerts、changes、incidents。NetworkClaw 在英文字幕中保持单词连续；配音侧只将其转换为 “Network Claw” 以改善语音发音。

本轮新增两组随旁白淡入淡出的视觉提示：Specialist agent 附近显示 Cisco、Juniper、F5、Check Point 标识；Connectivity data 附近显示 Our Data Management System 以及 Metrics、Logs、Alerts、Changes、Incidents 小图标。旁白明确说明工具查询我们的 Data Management System 获取 Connectivity 实时数据。两组提示分别仅在对应讲解段落出现，进入和退出各用 650 毫秒渐变，按影片时钟计算。标识只表示用户要求展示的领域例子，不表示所有厂商已完成集成验收。修改前完整制作文件备份在 `archive/v5-before-vendor-data-cues/`。

品牌素材本地保存在 `source/assets/`，导演版 HTML 内嵌 SVG，不依赖在线加载。Cisco、F5、Juniper 素材来自 Simple Icons（`https://cdn.simpleicons.org/cisco/049FD9`、`https://cdn.simpleicons.org/f5/E4002B`、`https://cdn.simpleicons.org/junipernetworks/00856A`）；Check Point 标识来自其官网 `https://www.checkpoint.com/wp-content/themes/checkpoint-theme-v2/images/checkpoint-logo.svg`。品牌标识归各自权利人所有。数据类型图标采用系统 emoji。

本轮检查四个 SVG 均能解码，两组图层在对应段落淡入淡出、其余段落透明；结果在 `renders/cue-verification.json`。已查看 agent 和 data 段落截图，图标、节点和字幕无重叠。最终媒体解码和字幕检查见 `renders/verification.json`。

第四版明确产品归属：NetworkClaw 是 INOC 内部新颖且重要的 LLM 驱动智能体模块，而非独立系统。视频保留组件拆分以讲清职责，并在画面持续标注这一关系。放宽时长上限到 70 秒，通用英式旁白基础语速由 +3% 调为 -2%，段间停顿由 180 ms 增加到 300 ms；最终时序按 68.7 秒目标编排。保留 “a confident next step” 结尾。

入口说明：在 INOC 点击“智能分析”（英文视频中写作 Intelligent Analysis），进入 NetworkClaw 开展相关分析。第二段旁白、标题和入口指引同步呈现；该入口描述来自用户提供的信息，视频没有冒充真实 INOC 界面录屏。

发音约定：INOC 读作 “I knock”。合成语音时单独替换发音文本，画面、分镜和英文字幕仍保留 INOC 拼写。修改前的视频保存在 `archive/v4-before-inoc-pronunciation/`。

礼貌开场与收尾：开场问候 “Good morning, good afternoon, Connectivity.”，结尾保留 “a confident next step” 并加上 “Thank you.”；问候前版本保存在 `archive/before-greeting/`。

Specialist agent 说明：按用户提供的产品能力，支持交换机、路由器、负载均衡器、防火墙等专门领域，并可使用领域 prompt 与预配置工具工作流。旁白、章节标题和画面提示同步呈现。具体可用能力取决于配置，不表示已对所有设备完成真实集成验收。为保持 70 秒以内与舒缓节奏，精简了其他段落的重复表述。修改前成片保存在 `archive/before-specialist-detail/`。

第二版扩展开场和结尾：从值班时告警与分散线索讲起，强调 AI Coordinator 由 large language model（LLM）驱动，最后展开健康检查、性能分析和容量规划等可能场景。场景拓展以相应工具与权限配置为前提。采用耐心、循序渐进、解释因果的教练式讲解，保留通用英式英文声音。

## 内容与演示方式

第三版从日常运维切入：工程师检查性能，或在 Connectivity 内部智能系统 INOC 中查看告警；也可能需要了解已有 incident。没有预设紧急故障，也不再描述 INOC 主动产生告警。视频中的 INOC 使用电脑图标与 Connectivity intelligence 说明，开场不播放 INOC 向 Coordinator 发送告警的连线。

工程师向 NetworkClaw 提问；LLM 驱动的 AI Coordinator 理解目标、发现 Agent 和 Tool，安排调查。Tool 查询 Connectivity 数据，通过虚线返回数据，再将结果交给 Coordinator。Coordinator 复核并决定是否继续调查，最终向工程师提供洞察与行动建议，以 “a confident next step” 收尾。第二版完整备份在 `archive/v2/`。

旁白仍为通用英式男声 en-GB-RyanNeural，音高轻微降低 2 Hz；未仿制或克隆 Malcolm Moore 的个人声线。

视频直接使用现有 Archify HTML 的 SVG 节点、路径与真实连线 ID。制作副本调用 HTML 的 guidedViews 章节接口与 focus 接口，另外加入与旁白时序绑定的镜头、路径流动标记、标题及字幕。它是基于 HTML 的导演版演示，不是后端实际执行的录制。源仓库 HTML 未改动。推荐行动不代表自动修改生产网络。

参考视频：https://www.youtube.com/watch?v=KXPA79lWVZw

已读取参考页标题、介绍和章节：Malcolm Moore 的滑雪转弯教学。采用“具体问题 → 分步解释 → 每一步的作用 → 下一步”的教学结构。参考播放器后续报错且字幕接口未返回正文，因此没有声称完整听看或精确复刻语气。未复制参考视频画面、音频，也未克隆讲者声音。旁白使用通用 `en-GB-RyanNeural` 合成语音。

## 目录

- `output/`：可分享 MP4。
- `source/`：原 HTML/JSON 副本、英文分镜脚本、精确时序、导演版 HTML。
- `audio/`：逐段语音 MP3/WAV、合并后的旁白；voice-test 是制作时的试音。
- `subtitles/`：英文 SRT。
- `renders/`：无声画面、逐章节截图、浏览器检查及媒体验证。
- `scripts/`：配音、渲染、验证脚本。
- `tools/`：项目内 Python 依赖、FFmpeg、Playwright；保留各工具自带的许可证。
- `cache/`、`tmp/`：依赖下载缓存、浏览器配置、临时文件。

制作使用机器已有的 Python、Node 和 Google Chrome 可执行程序；新增依赖和浏览器配置在本目录。英文脚本由 edge-tts 发送给语音合成服务；不读取项目 .env，也不发送仓库源代码或实际网络数据。

## 重建

在本目录执行：

```sh
TMPDIR="$PWD/tmp" PYTHONDONTWRITEBYTECODE=1 python3 scripts/narrate.py
TMPDIR="$PWD/tmp" node scripts/render.mjs
TMPDIR="$PWD/tmp" node scripts/verify.mjs
TMPDIR="$PWD/tmp" node scripts/verify-cues.mjs
```

修改旁白后，需要将对应 `audio/NN.mp3` 移至备份目录，以便重新合成；脚本复用已有片段以避免重复请求。每次成片前可将 `output/` 的旧版本复制备份。删除本视频目录不会影响原 NetworkClaw 仓库。

验证结果见 `renders/verification.json`。浏览器检查记录每段旁白对应的章节、节点和路径；镜头检查截图在 `renders/checks/`。真人主观听审尚未完成，最终语音语感可按反馈继续迭代。
