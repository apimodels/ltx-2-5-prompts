# LTX 2.5 提示词：Civitai、fal.ai 和 X 上收集的 89 条真实提示词

[English](README.md) · 简体中文 · [在 apimodels.app 上看带成片的版本](https://apimodels.app/zh/ltx-2-5-prompts) · [在 GitHub Pages 上搜索、一键复制](https://apimodels.github.io/ltx-2-5-prompts/)

本仓库收录 89 条 LTX-2.5 视频提示词，来自 35 位作者和网站在 Civitai（63 条）、fal.ai（22 条）和 X（4 条）上公开发布的内容，每条都逐字全文收录、署名作者，并附原帖链接。

说明：这个合集由 [apimodels.app](https://apimodels.app) 整理，我在这个 API 平台工作。apimodels.app 是多模型 API 平台，也提供 [LTX 2.5 Fast](https://apimodels.app/zh/models/ltx-2.5-fast) 和 [LTX 2.5 Pro](https://apimodels.app/zh/models/ltx-2.5-pro) 的 API；这里不少提示词是作者用开源权重在本地跑的，区别见下面「[用 API 跑这些提示词](#用-api-跑这些提示词)」。带成片、可以直接播放的在线版在 [apimodels.app 的 LTX 2.5 提示词库](https://apimodels.app/zh/ltx-2-5-prompts)。

## 目录

- [对白与人声](#对白与人声)（17）
- [电影感](#电影感)（40）
- [人像与角色](#人像与角色)（10）
- [自然与风景](#自然与风景)（6）
- [风格化与动画](#风格化与动画)（6）
- [奇幻与变身](#奇幻与变身)（10）
- [这些提示词是怎么写的](#这些提示词是怎么写的)
- [用 API 跑这些提示词](#用-api-跑这些提示词)
- [怎么收集的](#怎么收集的)
- [出处、版权与许可](#出处版权与许可)

每条提示词在 [prompts/](prompts) 下有单独一页，写明作者、原帖、从哪里发现的、提示词的语言和长度，以及成片链接。全部 89 条也在 [data/prompts.json](data/prompts.json)，[index.html](index.html) 是可以搜索、筛选、一键复制的浏览页。

## 这些提示词是怎么写的

- **一个镜头写成一段话,按发生顺序写**：本库 fal.ai 的那些示例,每条都是从头到尾描述一个机位:景别和主体、发生了什么、镜头怎么动、光线,最后才是镜头焦段。大意是「缓慢推近擂台上的拳击手,顶光穿过烟雾打在肩上,50mm、f/2」。一串关键词堆在一起,模型拿不到先后顺序。
- **把声音写进去,反正每条都会出声**：LTX-2.5 的声音和画面一起生成,我们的 API 也没有静音选项,所以要不要声音不由你,怎么响可以由你。台词放进引号、写明是谁说的,再写环境音和最关键的那一下声音。本库有几条 Civitai 提示词把两个人的对话一句一句写好,每个人开口前先交代嗓音。
- **动作长度要对得上 API 的时长档**：Fast 的文生和图生是 6 到 20 秒、只能取偶数秒,1440p 或 48 / 50 fps 时只有 6、8、10 秒;Pro 只有 6、8、10 秒。本地工作流常用帧数定长度,除以帧率就知道原帖要的是几秒,再挑最接近的一档。API 不会看提示词自己定长度,要自己传 duration。
- **传了首帧,就写动作,别再描述画面**：图生视频里,主体、场景和构图已经由那张图定死了,提示词就专心写什么在动:谁转身、镜头怎么走、听到什么。成片会保持图片的比例;带首帧又传 aspect_ratio,会直接返回 400。
- **音频生视频:音轨说了算,提示词负责选角**：LTX 2.5 Fast 收到 audio_url 后,会把这段音频原样当成片的声音,再按它生成画面。提示词写清楚画面里是谁、怎么动、怎么取景就够了,比如我们文档里的例子:明亮的演播室里,一位年轻主持人对着镜头讲话,手势自然,中景。长度默认跟着音频走,也可以自己设 duration。Pro 不收音频。
- **API 收不了的东西,先删掉**：本地 LTX-2.5 工作流里可以挂负面提示词、LoRA 触发词、额外的引导图或尾帧。我们的请求只收提示词、一张首帧、一段音频和生成参数,别的都不收:尾帧、参考图、视频输入会返回 400。也没有负面提示词这个字段,原帖写在负面提示词里的东西,不挪进正文就等于没了。
- **画面文字和很乱的物理,别指望一次成**：Lightricks 自己的提示词指南也说了,画面里的文字和混乱的物理运动目前还不稳定。如果一个镜头靠一块看得清的招牌,或者一堆东西互相撞,做好多跑几次的准备,文字也可以剪辑时再加。

## 对白与人声

| # | 提示词 | 作者 | 原帖 | 字符 | 成片 |
| --- | --- | --- | --- | --- | --- |
| LTX009 | [日籍模特英语口音自述](prompts/dialogue-voice/LTX009.md) | [gs816uo79](https://civitai.com/user/gs816uo79) | [Civitai](https://civitai.com/images/140143867) | 195 | [视频](https://image.civitai.com/xG1nkqKTMzGDvpLrqFT7WA/85e50c79-49c2-4483-b0d3-902400377107/original=true/85e50c79-49c2-4483-b0d3-902400377107.mp4) |
| LTX012 | [科幻咖啡馆里的吐槽](prompts/dialogue-voice/LTX012.md) | [broadsly](https://civitai.com/user/broadsly) | [Civitai](https://civitai.com/images/143036789) | 425 | [视频](https://image.civitai.com/xG1nkqKTMzGDvpLrqFT7WA/7f2ad28b-19a6-4a29-853a-0b927fa2fa44/original=true/7f2ad28b-19a6-4a29-853a-0b927fa2fa44.mp4) |
| LTX013 | [阴天户外采访](prompts/dialogue-voice/LTX013.md) | [aaawilly136879](https://civitai.com/user/aaawilly136879) | [Civitai](https://civitai.com/images/139477098) | 1609 | [视频](https://image.civitai.com/xG1nkqKTMzGDvpLrqFT7WA/e77e11ff-ffc1-45b4-91e5-3fe48f9118f1/original=true/e77e11ff-ffc1-45b4-91e5-3fe48f9118f1.mp4) |
| LTX020 | [表格恍惚惊见鹅](prompts/dialogue-voice/LTX020.md) | [broadsly](https://civitai.com/user/broadsly) | [Civitai](https://civitai.com/images/142832974) | 260 | [视频](https://image.civitai.com/xG1nkqKTMzGDvpLrqFT7WA/a29b103c-7e77-4cdf-8b34-7c698eda294a/original=true/a29b103c-7e77-4cdf-8b34-7c698eda294a.mp4) |
| LTX024 | [商店退货婚纱](prompts/dialogue-voice/LTX024.md) | [broadsly](https://civitai.com/user/broadsly) | [Civitai](https://civitai.com/images/142902123) | 292 | [视频](https://image.civitai.com/xG1nkqKTMzGDvpLrqFT7WA/e7b3566e-9d83-4508-a2d0-c38a8f4f732e/original=true/e7b3566e-9d83-4508-a2d0-c38a8f4f732e.mp4) |
| LTX033 | [工地女子受访谈家族](prompts/dialogue-voice/LTX033.md) | [broadsly](https://civitai.com/user/broadsly) | [Civitai](https://civitai.com/images/142902135) | 365 | [视频](https://image.civitai.com/xG1nkqKTMzGDvpLrqFT7WA/170130a6-5602-428f-98a4-d787e94bc8ad/original=true/170130a6-5602-428f-98a4-d787e94bc8ad.mp4) |
| LTX034 | [侦探分析冷静嫌疑人](prompts/dialogue-voice/LTX034.md) | [broadsly](https://civitai.com/user/broadsly) | [Civitai](https://civitai.com/images/142902128) | 336 | [视频](https://image.civitai.com/xG1nkqKTMzGDvpLrqFT7WA/67ffe61e-e036-4310-bf1b-7022e0e602ab/original=true/67ffe61e-e036-4310-bf1b-7022e0e602ab.mp4) |
| LTX035 | [新西兰女子求职面试](prompts/dialogue-voice/LTX035.md) | [broadsly](https://civitai.com/user/broadsly) | [Civitai](https://civitai.com/images/142902122) | 391 | [视频](https://image.civitai.com/xG1nkqKTMzGDvpLrqFT7WA/6be22554-6be2-4eaa-a9c2-08c722dae0c4/original=true/6be22554-6be2-4eaa-a9c2-08c722dae0c4.mp4) |
| LTX039 | [渔女谈论水中鱼](prompts/dialogue-voice/LTX039.md) | [broadsly](https://civitai.com/user/broadsly) | [Civitai](https://civitai.com/images/142902141) | 320 | [视频](https://image.civitai.com/xG1nkqKTMzGDvpLrqFT7WA/b421b89f-d2ed-4268-84ba-f1321e78b8ab/original=true/b421b89f-d2ed-4268-84ba-f1321e78b8ab.mp4) |
| LTX040 | [机长广播飞行趣事](prompts/dialogue-voice/LTX040.md) | [broadsly](https://civitai.com/user/broadsly) | [Civitai](https://civitai.com/images/142902156) | 348 | [视频](https://image.civitai.com/xG1nkqKTMzGDvpLrqFT7WA/71860c0b-e747-46c7-8c32-676cddc0b392/original=true/71860c0b-e747-46c7-8c32-676cddc0b392.mp4) |
| LTX043 | [两个哥布林守卫闲聊](prompts/dialogue-voice/LTX043.md) | [sawbladex818](https://civitai.com/user/sawbladex818) | [Civitai](https://civitai.com/images/148894077) | 113 | [视频](https://image.civitai.com/xG1nkqKTMzGDvpLrqFT7WA/75c2ac6a-f69b-4016-bf20-e2973f4f6712/original=true/75c2ac6a-f69b-4016-bf20-e2973f4f6712.mp4) |
| LTX051 | [咖啡馆经理冷面受访](prompts/dialogue-voice/LTX051.md) | [broadsly](https://civitai.com/user/broadsly) | [Civitai](https://civitai.com/images/142902124) | 285 | [视频](https://image.civitai.com/xG1nkqKTMzGDvpLrqFT7WA/3bfd0ab2-704e-40dd-b544-8354833a0947/original=true/3bfd0ab2-704e-40dd-b544-8354833a0947.mp4) |
| LTX055 | [阿姆斯特丹夜色自拍](prompts/dialogue-voice/LTX055.md) | [dutchit288](https://civitai.com/user/dutchit288) | [Civitai](https://civitai.com/images/142218936) | 2014 | [视频](https://image.civitai.com/xG1nkqKTMzGDvpLrqFT7WA/396ef7bd-5d0e-4b35-a736-a0deb33aa57f/original=true/396ef7bd-5d0e-4b35-a736-a0deb33aa57f.mp4) |
| LTX061 | [爱尔兰女子对镜说话](prompts/dialogue-voice/LTX061.md) | [gs816uo79](https://civitai.com/user/gs816uo79) | [Civitai](https://civitai.com/images/142163643) | 391 | [视频](https://image.civitai.com/xG1nkqKTMzGDvpLrqFT7WA/2d6c22ea-7748-4c5a-b466-2603d6d83126/original=true/2d6c22ea-7748-4c5a-b466-2603d6d83126.mp4) |
| LTX083 | [1974年维也纳旅馆对峙](prompts/dialogue-voice/LTX083.md) | [fal.ai](https://fal.ai) | [fal.ai](https://fal.ai/learn/tools/how-to-use-ltx-2-5) | 854 | [视频](https://v3b.fal.media/files/b/0aa6bb8f/xsVKo43UMEmDBM9mE5QJi_A%20slow%20push-in%20down%20a%20narrow%20Venetian%20calle%20at%20night%20during%20carnival%2C%20a%20masked%20crowd%20pressing%20past%20the%20lens%20in%20both%20directions.mp4) |
| LTX087 | [女律师的结案陈词](prompts/dialogue-voice/LTX087.md) | [fal.ai](https://fal.ai) | [fal.ai](https://fal.ai/learn/tools/how-to-use-ltx-2-5) | 307 | [视频](https://v3b.fal.media/files/b/0aa6bb8e/BqpQymedkuDRooNPQfj_U_A%20flamenco%20dancer%20alone%20in%20a%20bare%20whitewashed%20room.mp4) |
| LTX089 | [昆虫龙开口说话](prompts/dialogue-voice/LTX089.md) | [sawbladex818](https://civitai.com/user/sawbladex818) | [Civitai](https://civitai.com/images/147756765) | 68 | [视频](https://image.civitai.com/xG1nkqKTMzGDvpLrqFT7WA/e3acd845-d7ee-40cc-92a4-6295e652d16e/original=true/e3acd845-d7ee-40cc-92a4-6295e652d16e.mp4) |

## 电影感

| # | 提示词 | 作者 | 原帖 | 字符 | 成片 |
| --- | --- | --- | --- | --- | --- |
| LTX001 | [女子凝视远处故障屏幕](prompts/cinematic/LTX001.md) | [@ivanfioravanti](https://x.com/ivanfioravanti) | [X](https://x.com/ivanfioravanti/status/2087292914539839918) | 447 | [视频](https://video.twimg.com/amplify_video/2087290011821457410/vid/avc1/1280x704/7mqXBnfM82BFGvKy.mp4?tag=29) |
| LTX002 | [巧克力浇淋奶油与蓝莓](prompts/cinematic/LTX002.md) | [hichuicomfy](https://civitai.com/user/hichuicomfy) | [Civitai](https://civitai.com/images/139677582) | 344 | [视频](https://image.civitai.com/xG1nkqKTMzGDvpLrqFT7WA/83a34478-6e7a-4d08-a8cd-269f772b8424/original=true/83a34478-6e7a-4d08-a8cd-269f772b8424.mp4) |
| LTX006 | [白色小团子收到信件](prompts/cinematic/LTX006.md) | [@Stellakjbk](https://x.com/Stellakjbk) | [X](https://x.com/Stellakjbk/status/2088303811454538201) | 7387 | [视频](https://video.twimg.com/amplify_video/2088297974237396992/vid/avc1/2538x1440/b5hpQlkxPG66BLJY.mp4?tag=29) |
| LTX007 | [超市购物车狂飙场面](prompts/cinematic/LTX007.md) | [EbenezerDanglewood](https://civitai.com/user/EbenezerDanglewood) | [Civitai](https://civitai.com/images/139942480) | 245 | [视频](https://image.civitai.com/xG1nkqKTMzGDvpLrqFT7WA/987229cb-ced8-4207-afa3-54733dcfa690/original=true/987229cb-ced8-4207-afa3-54733dcfa690.mp4) |
| LTX008 | [霓虹都市阳台上的粉章鱼](prompts/cinematic/LTX008.md) | [WickedGargoyleProductions](https://civitai.com/user/WickedGargoyleProductions) | [Civitai](https://civitai.com/images/148076128) | 534 | [视频](https://image.civitai.com/xG1nkqKTMzGDvpLrqFT7WA/31315429-9efa-4a05-aaf5-d67266fcbd2a/original=true/31315429-9efa-4a05-aaf5-d67266fcbd2a.mp4) |
| LTX010 | [女子歌唱身后火箭升空](prompts/cinematic/LTX010.md) | [samlowgan598](https://civitai.com/user/samlowgan598) | [Civitai](https://civitai.com/images/139513594) | 112 | [视频](https://image.civitai.com/xG1nkqKTMzGDvpLrqFT7WA/5846e5d6-1998-4b08-a360-dfad091e3bbb/original=true/5846e5d6-1998-4b08-a360-dfad091e3bbb.mp4) |
| LTX015 | [沙漠女战士环绕镜头](prompts/cinematic/LTX015.md) | [MrSoles](https://civitai.com/user/MrSoles) | [Civitai](https://civitai.com/images/146566794) | 977 | [视频](https://image.civitai.com/xG1nkqKTMzGDvpLrqFT7WA/8d496ed4-fbc2-4fcb-a555-5f5f5d402e94/original=true/8d496ed4-fbc2-4fcb-a555-5f5f5d402e94.mp4) |
| LTX016 | [厨房南瓜交接场景](prompts/cinematic/LTX016.md) | [@SattyEth](https://x.com/SattyEth) | [X](https://x.com/SattyEth/status/2114764887205220684) | 3295 | [视频](https://video.twimg.com/ext_tw_video/2114764866544128000/pu/vid/avc1/720x720/kdvZVRoSDPXxsJeL.mp4?tag=12) |
| LTX018 | [水晶王座女战士](prompts/cinematic/LTX018.md) | [MrSoles](https://civitai.com/user/MrSoles) | [Civitai](https://civitai.com/images/146476668) | 919 | [视频](https://image.civitai.com/xG1nkqKTMzGDvpLrqFT7WA/c43d7640-14da-4d57-bc10-34d8bc4b168a/original=true/c43d7640-14da-4d57-bc10-34d8bc4b168a.mp4) |
| LTX026 | [黑洞前的渺小身影](prompts/cinematic/LTX026.md) | [ANGI1019](https://civitai.com/user/ANGI1019) | [Civitai](https://civitai.com/images/148283516) | 671 | [视频](https://image.civitai.com/xG1nkqKTMzGDvpLrqFT7WA/bdf8a641-c743-47b9-8772-d2f2d2b9515b/original=true/bdf8a641-c743-47b9-8772-d2f2d2b9515b.mp4) |
| LTX027 | [精灵法师开启森林传送门](prompts/cinematic/LTX027.md) | [imaginaryArt](https://civitai.com/user/imaginaryArt) | [Civitai](https://civitai.com/images/147014005) | 1510 | [视频](https://image.civitai.com/xG1nkqKTMzGDvpLrqFT7WA/1dd4ae09-d5de-4095-a45a-799b8e5cb863/original=true/1dd4ae09-d5de-4095-a45a-799b8e5cb863.mp4) |
| LTX031 | [码头海军女兵特写](prompts/cinematic/LTX031.md) | [witalpro665](https://civitai.com/user/witalpro665) | [Civitai](https://civitai.com/images/147645766) | 372 | [视频](https://image.civitai.com/xG1nkqKTMzGDvpLrqFT7WA/11eb2a7a-4ba7-43b6-ae85-ff71208870bc/original=true/11eb2a7a-4ba7-43b6-ae85-ff71208870bc.mp4) |
| LTX036 | [屋顶飞跃城市间隙](prompts/cinematic/LTX036.md) | [MisterMR](https://civitai.com/user/MisterMR) | [Civitai](https://civitai.com/images/139583895) | 1687 | [视频](https://image.civitai.com/xG1nkqKTMzGDvpLrqFT7WA/9728158b-1f93-4863-8ac0-e6792726a607/original=true/9728158b-1f93-4863-8ac0-e6792726a607.mp4) |
| LTX041 | [古桥上的猫巫师](prompts/cinematic/LTX041.md) | [msandy54400837](https://civitai.com/user/msandy54400837) | [Civitai](https://civitai.com/images/149534482) | 3772 | [视频](https://image.civitai.com/xG1nkqKTMzGDvpLrqFT7WA/c3a8e579-5815-4419-8ed1-9c65079de712/original=true/c3a8e579-5815-4419-8ed1-9c65079de712.mp4) |
| LTX044 | [动漫女子藏身墙角](prompts/cinematic/LTX044.md) | [WickedGargoyleProductions](https://civitai.com/user/WickedGargoyleProductions) | [Civitai](https://civitai.com/images/144450772) | 2748 | [视频](https://image.civitai.com/xG1nkqKTMzGDvpLrqFT7WA/9c9ff3f7-309b-4d5f-ad3c-9a91aab24d47/original=true/9c9ff3f7-309b-4d5f-ad3c-9a91aab24d47.mp4) |
| LTX046 | [阳光下花园小径漫步](prompts/cinematic/LTX046.md) | [dutchit288](https://civitai.com/user/dutchit288) | [Civitai](https://civitai.com/images/141774734) | 1781 | [视频](https://image.civitai.com/xG1nkqKTMzGDvpLrqFT7WA/e89b0be8-e5eb-4de9-8a75-3eec9539368c/original=true/e89b0be8-e5eb-4de9-8a75-3eec9539368c.mp4) |
| LTX049 | [精灵飘过薄雾森林](prompts/cinematic/LTX049.md) | [@SShahHashmi](https://x.com/SShahHashmi) | [X](https://x.com/SShahHashmi/status/2121939395037335934) | 822 | [视频](https://video.twimg.com/amplify_video/2121939315026513920/vid/avc1/832x1088/KKzg8Bk9bsYsIFRw.mp4?tag=29) |
| LTX053 | [天堂到地狱镜头之旅](prompts/cinematic/LTX053.md) | [msavitt623](https://civitai.com/user/msavitt623) | [Civitai](https://civitai.com/images/142954577) | 543 | [视频](https://image.civitai.com/xG1nkqKTMzGDvpLrqFT7WA/0bb7565f-67dd-4222-ace6-1cd992359ea0/original=true/0bb7565f-67dd-4222-ace6-1cd992359ea0.mp4) |
| LTX054 | [外星UFO机库检修](prompts/cinematic/LTX054.md) | [peterjoyce874](https://civitai.com/user/peterjoyce874) | [Civitai](https://civitai.com/images/142632419) | 660 | [视频](https://image.civitai.com/xG1nkqKTMzGDvpLrqFT7WA/2c890cf6-ff02-4ead-b5ac-d66b91b91050/original=true/2c890cf6-ff02-4ead-b5ac-d66b91b91050.mp4) |
| LTX058 | [超现实水族箱内部](prompts/cinematic/LTX058.md) | [msavitt623](https://civitai.com/user/msavitt623) | [Civitai](https://civitai.com/images/147116339) | 1501 | [视频](https://image.civitai.com/xG1nkqKTMzGDvpLrqFT7WA/94144966-b191-4386-b347-5cd27e71d3be/original=true/94144966-b191-4386-b347-5cd27e71d3be.mp4) |
| LTX059 | [球场抛球的女子](prompts/cinematic/LTX059.md) | [msavitt623](https://civitai.com/user/msavitt623) | [Civitai](https://civitai.com/images/143255443) | 1598 | [视频](https://image.civitai.com/xG1nkqKTMzGDvpLrqFT7WA/87cab0cc-d73f-4ff6-9de9-7cc0124d4c6b/original=true/87cab0cc-d73f-4ff6-9de9-7cc0124d4c6b.mp4) |
| LTX060 | [破旧办公室休息室](prompts/cinematic/LTX060.md) | [msavitt623](https://civitai.com/user/msavitt623) | [Civitai](https://civitai.com/images/142955514) | 1143 | [视频](https://image.civitai.com/xG1nkqKTMzGDvpLrqFT7WA/a6f3080a-5101-4ac7-b4e7-2634616c276a/original=true/a6f3080a-5101-4ac7-b4e7-2634616c276a.mp4) |
| LTX062 | [1950年代镜像门惊悚](prompts/cinematic/LTX062.md) | [JayKowzer](https://civitai.com/user/JayKowzer) | [Civitai](https://civitai.com/images/141640850) | 1249 | [视频](https://image.civitai.com/xG1nkqKTMzGDvpLrqFT7WA/dda4952a-21e1-45df-896b-1d67a8948c13/original=true/dda4952a-21e1-45df-896b-1d67a8948c13.mp4) |
| LTX064 | [女子推动沉重衣柜](prompts/cinematic/LTX064.md) | [WickedGargoyleProductions](https://civitai.com/user/WickedGargoyleProductions) | [Civitai](https://civitai.com/images/147240348) | 654 | [视频](https://image.civitai.com/xG1nkqKTMzGDvpLrqFT7WA/3d8bfff7-5ec7-4172-83e6-d70a54d54ada/original=true/3d8bfff7-5ec7-4172-83e6-d70a54d54ada.mp4) |
| LTX065 | [崖边俯瞰夜城的男人](prompts/cinematic/LTX065.md) | [Servph](https://civitai.com/user/Servph) | [Civitai](https://civitai.com/images/145708552) | 205 | [视频](https://image.civitai.com/xG1nkqKTMzGDvpLrqFT7WA/a803ccff-3365-43b9-9db8-84de76273e5b/original=true/a803ccff-3365-43b9-9db8-84de76273e5b.mp4) |
| LTX067 | [黑暗拳台独站的拳手](prompts/cinematic/LTX067.md) | [fal.ai](https://fal.ai) | [fal.ai](https://fal.ai/ltx-2.5) | 339 | [视频](https://ir7z8qsacw4tk54b.public.blob.vercel-storage.com/ltx-2.5/example-1.mp4) |
| LTX068 | [泳池漂浮鸭双视角](prompts/cinematic/LTX068.md) | [fal.ai](https://fal.ai) | [fal.ai](https://fal.ai/ltx-2.5) | 332 | [视频](https://ir7z8qsacw4tk54b.public.blob.vercel-storage.com/ltx-2.5/example-2.mp4) |
| LTX069 | [秋林中跳舞的老夫妻](prompts/cinematic/LTX069.md) | [fal.ai](https://fal.ai) | [fal.ai](https://fal.ai/ltx-2.5) | 295 | [视频](https://ir7z8qsacw4tk54b.public.blob.vercel-storage.com/ltx-2.5/example-3.mp4) |
| LTX071 | [铸造厂浇铸钢水飞溅](prompts/cinematic/LTX071.md) | [fal.ai](https://fal.ai) | [fal.ai](https://fal.ai/ltx-2.5) | 320 | [视频](https://ir7z8qsacw4tk54b.public.blob.vercel-storage.com/ltx-2.5/example-5.mp4) |
| LTX072 | [泥地摩托越野过弯](prompts/cinematic/LTX072.md) | [fal.ai](https://fal.ai) | [fal.ai](https://fal.ai/ltx-2.5) | 280 | [视频](https://ir7z8qsacw4tk54b.public.blob.vercel-storage.com/ltx-2.5/example-6.mp4) |
| LTX074 | [玻璃门后的七十年代男子](prompts/cinematic/LTX074.md) | [fal.ai](https://fal.ai) | [fal.ai](https://fal.ai/ltx-2.5) | 307 | [视频](https://ir7z8qsacw4tk54b.public.blob.vercel-storage.com/ltx-2.5/example-8.mp4) |
| LTX076 | [夕阳下跳跃的马赛武士](prompts/cinematic/LTX076.md) | [fal.ai](https://fal.ai) | [fal.ai](https://fal.ai/models/lightricks/ltx-2.5/image-to-video/pro) | 348 | [视频](https://v3b.fal.media/files/b/0a90dd31/VUCTD0YYJIp_K4qQkkneL_wMVDWNRn.mp4) |
| LTX077 | [雨夜酒吧窗上的霓虹倒影](prompts/cinematic/LTX077.md) | [fal.ai](https://fal.ai) | [fal.ai](https://fal.ai/learn/devs/seedance-2-5-vs-ltx-2-5-pro) | 2122 | [视频](https://v3b.fal.media/files/b/0aa6daf3/K9P8gf6PK8Bp4grceahpe_A%20dolly%20past%20a%20bar%20window%20in%20the%20rain%20-%20seedance%202.5.mp4) |
| LTX079 | [短跑运动员起跑冲刺](prompts/cinematic/LTX079.md) | [fal.ai](https://fal.ai) | [fal.ai](https://fal.ai/learn/devs/seedance-2-5-vs-ltx-2-5-pro) | 1061 | [视频](https://v3b.fal.media/files/b/0aa6daf6/WagUXp5YkqlGXkjAdLFB6_Out%20of%20the%20blocks%20-%20seedance%202.5.mp4) |
| LTX080 | [雨夜赛道上的原型赛车](prompts/cinematic/LTX080.md) | [fal.ai](https://fal.ai) | [fal.ai](https://fal.ai/learn/tools/how-to-use-ltx-2-5) | 808 | [视频](https://v3b.fal.media/files/b/0aa6bb8e/AeIJ_50dvVbFRjWaWlT7e_A%20long%20lens%20tracks%20a%20lone%20endurance%20prototype%20through%20a%20rain-soaked%20forest%20section%20of%20a%20night%20race.mp4) |
| LTX081 | [黄昏庭院与香水瓶](prompts/cinematic/LTX081.md) | [fal.ai](https://fal.ai) | [fal.ai](https://fal.ai/learn/tools/how-to-use-ltx-2-5) | 1145 | [视频](https://v3b.fal.media/files/b/0aa6bb8e/AeIJ_50dvVbFRjWaWlT7e_A%20long%20lens%20tracks%20a%20lone%20endurance%20prototype%20through%20a%20rain-soaked%20forest%20section%20of%20a%20night%20race.mp4) |
| LTX082 | [威尼斯狂欢节夜行人群](prompts/cinematic/LTX082.md) | [fal.ai](https://fal.ai) | [fal.ai](https://fal.ai/learn/tools/how-to-use-ltx-2-5) | 779 | [视频](https://v3b.fal.media/files/b/0aa6bb90/hqXSeSpWwtyaGJlQNiL0I_A%20wide%20shot%20establishes%20the%20courtyard%20of%20a%20Marrakech%20riad%20at%20dusk%2C%20zellige%20tile%20underfoot%2C%20tall%20silk%20curtains%20lifting.mp4) |
| LTX084 | [威士忌倒入冰块特写](prompts/cinematic/LTX084.md) | [fal.ai](https://fal.ai) | [fal.ai](https://fal.ai/learn/tools/how-to-use-ltx-2-5) | 550 | [视频](https://v3b.fal.media/files/b/0aa6bb90/3n5nu-HVlU5_3IWyNUFnA_A%20stream%20of%20amber%20spirit%20pours%20into%20the%20rocks%20glass%20from%20off%20frame%20right%20and%20rises%20to%20two%20thirds%2C%20the%20surface%20settling%20as%20it%20fills%20and%20the%20caustics%20on%20the%20walnut%20shifting%20with%20it.mp4) |
| LTX086 | [弗拉明戈舞者独舞长镜头](prompts/cinematic/LTX086.md) | [fal.ai](https://fal.ai) | [fal.ai](https://fal.ai/learn/tools/how-to-use-ltx-2-5) | 539 | [视频](https://v3b.fal.media/files/b/0aa6bb91/hMAdj_rq7daSg_Qroq6tI_One%20continuous%20transformation%20from%20the%20empty%20room%20to%20the%20full%20ballroom.mp4) |
| LTX088 | [电动摩托影棚旋转展示](prompts/cinematic/LTX088.md) | [fal.ai](https://fal.ai) | [fal.ai](https://fal.ai/learn/tools/how-to-use-ltx-2-5) | 727 | [视频](https://v3b.fal.media/files/b/0aa6bb90/L5dXzsCZAQ8L18OtmHj2g_A%20woman%20in%20her%20forties%20in%20a%20charcoal%20suit%20stands%20at%20the%20lectern%20of%20a%20wood-panelled%20courtroom.mp4) |

## 人像与角色

| # | 提示词 | 作者 | 原帖 | 字符 | 成片 |
| --- | --- | --- | --- | --- | --- |
| LTX004 | [京都街头的战斗修女](prompts/portrait-character/LTX004.md) | [promt228842](https://civitai.com/user/promt228842) | [Civitai](https://civitai.com/images/141203497) | 1004 | [视频](https://image.civitai.com/xG1nkqKTMzGDvpLrqFT7WA/b337cc9d-6155-49ae-9e56-a8cca76a1754/original=true/b337cc9d-6155-49ae-9e56-a8cca76a1754.mp4) |
| LTX019 | [街头采访特写](prompts/portrait-character/LTX019.md) | [clueless\_engineer](https://civitai.com/user/clueless_engineer) | [Civitai](https://civitai.com/images/139450857) | 3976 | [视频](https://image.civitai.com/xG1nkqKTMzGDvpLrqFT7WA/a4220be2-a36f-4ca3-861e-5c84d49fb969/original=true/a4220be2-a36f-4ca3-861e-5c84d49fb969.mp4) |
| LTX028 | [紧张女子环顾尘埃](prompts/portrait-character/LTX028.md) | [WickedGargoyleProductions](https://civitai.com/user/WickedGargoyleProductions) | [Civitai](https://civitai.com/images/144453460) | 569 | [视频](https://image.civitai.com/xG1nkqKTMzGDvpLrqFT7WA/5dbf08cb-db2d-42c9-8ce6-0ede7899ad9c/original=true/5dbf08cb-db2d-42c9-8ce6-0ede7899ad9c.mp4) |
| LTX037 | [夜晚天桥边的女子](prompts/portrait-character/LTX037.md) | [theminionschickenleg](https://civitai.com/user/theminionschickenleg) | [Civitai](https://civitai.com/images/146500948) | 1436 | [视频](https://image.civitai.com/xG1nkqKTMzGDvpLrqFT7WA/dbcbae86-b98b-44f4-8cf0-2a7395707a29/original=true/dbcbae86-b98b-44f4-8cf0-2a7395707a29.mp4) |
| LTX042 | [谷仓旁嚼口香糖的哥特女孩](prompts/portrait-character/LTX042.md) | [HlKlK0M0Rl](https://civitai.com/user/HlKlK0M0Rl) | [Civitai](https://civitai.com/images/148965442) | 440 | [视频](https://image.civitai.com/xG1nkqKTMzGDvpLrqFT7WA/b1c844b4-c7f2-446e-9736-4bfb725f31f1/original=true/b1c844b4-c7f2-446e-9736-4bfb725f31f1.mp4) |
| LTX050 | [章鱼头外星人走廊说唱](prompts/portrait-character/LTX050.md) | [WickedGargoyleProductions](https://civitai.com/user/WickedGargoyleProductions) | [Civitai](https://civitai.com/images/148131430) | 852 | [视频](https://image.civitai.com/xG1nkqKTMzGDvpLrqFT7WA/a97b5841-68fc-45ff-999d-97219eed9171/original=true/a97b5841-68fc-45ff-999d-97219eed9171.mp4) |
| LTX056 | [夜晚秘书喝咖啡](prompts/portrait-character/LTX056.md) | [Pergy25](https://civitai.com/user/Pergy25) | [Civitai](https://civitai.com/images/139502982) | 662 | [视频](https://image.civitai.com/xG1nkqKTMzGDvpLrqFT7WA/c6181881-923e-4e15-8f76-3fcb70453caf/original=true/c6181881-923e-4e15-8f76-3fcb70453caf.mp4) |
| LTX070 | [少年面颊贴车窗玻璃](prompts/portrait-character/LTX070.md) | [fal.ai](https://fal.ai) | [fal.ai](https://fal.ai/ltx-2.5) | 306 | [视频](https://ir7z8qsacw4tk54b.public.blob.vercel-storage.com/ltx-2.5/example-4.mp4) |
| LTX073 | [林中阳光下的眼镜女子](prompts/portrait-character/LTX073.md) | [fal.ai](https://fal.ai) | [fal.ai](https://fal.ai/ltx-2.5) | 304 | [视频](https://ir7z8qsacw4tk54b.public.blob.vercel-storage.com/ltx-2.5/example-7.mp4) |
| LTX075 | [红纱后的印度新娘](prompts/portrait-character/LTX075.md) | [fal.ai](https://fal.ai) | [fal.ai](https://fal.ai/models/lightricks/ltx-2.5/text-to-video/pro) | 411 | [视频](https://v3b.fal.media/files/b/0a90dd3a/EG257tf7j9UfVc-jHF8lI_0MWboc13.mp4) |

## 自然与风景

| # | 提示词 | 作者 | 原帖 | 字符 | 成片 |
| --- | --- | --- | --- | --- | --- |
| LTX003 | [秋日瀑布与林间木屋](prompts/nature-landscape/LTX003.md) | [Esteban099009](https://civitai.com/user/Esteban099009) | [Civitai](https://civitai.com/images/140615724) | 350 | [视频](https://image.civitai.com/xG1nkqKTMzGDvpLrqFT7WA/6df500a7-e4b7-4aae-aa18-af451221120e/original=true/6df500a7-e4b7-4aae-aa18-af451221120e.mp4) |
| LTX014 | [日落雪山风景](prompts/nature-landscape/LTX014.md) | [Esteban099009](https://civitai.com/user/Esteban099009) | [Civitai](https://civitai.com/images/141223871) | 102 | [视频](https://image.civitai.com/xG1nkqKTMzGDvpLrqFT7WA/1203dd70-668f-4a7a-b727-118027ac8c89/original=true/1203dd70-668f-4a7a-b727-118027ac8c89.mp4) |
| LTX025 | [异星巨石水池](prompts/nature-landscape/LTX025.md) | [J032](https://civitai.com/user/J032) | [Civitai](https://civitai.com/images/149521478) | 1931 | [视频](https://image.civitai.com/xG1nkqKTMzGDvpLrqFT7WA/16f156dc-665c-4b76-a8cb-ed24e759aa5c/original=true/16f156dc-665c-4b76-a8cb-ed24e759aa5c.mp4) |
| LTX045 | [VHS火山山谷风景](prompts/nature-landscape/LTX045.md) | [msavitt623](https://civitai.com/user/msavitt623) | [Civitai](https://civitai.com/images/142851851) | 2503 | [视频](https://image.civitai.com/xG1nkqKTMzGDvpLrqFT7WA/6edbf74c-2d2e-4815-8191-0ab35a907a4b/original=true/6edbf74c-2d2e-4815-8191-0ab35a907a4b.mp4) |
| LTX052 | [立体派秋日木屋风景](prompts/nature-landscape/LTX052.md) | [msavitt623](https://civitai.com/user/msavitt623) | [Civitai](https://civitai.com/images/142956311) | 1478 | [视频](https://image.civitai.com/xG1nkqKTMzGDvpLrqFT7WA/f0fc8425-184e-4c04-95a0-cd474d517f95/original=true/f0fc8425-184e-4c04-95a0-cd474d517f95.mp4) |
| LTX063 | [佛蒙特雪湖日落](prompts/nature-landscape/LTX063.md) | [Franklin\_Sports](https://civitai.com/user/Franklin_Sports) | [Civitai](https://civitai.com/images/149481689) | 113 | [视频](https://image.civitai.com/xG1nkqKTMzGDvpLrqFT7WA/9fee7324-ce39-4b17-a296-1487605528c1/original=true/9fee7324-ce39-4b17-a296-1487605528c1.mp4) |

## 风格化与动画

| # | 提示词 | 作者 | 原帖 | 字符 | 成片 |
| --- | --- | --- | --- | --- | --- |
| LTX017 | [电梯卡通小品动画](prompts/stylized-animation/LTX017.md) | [Azimondious](https://civitai.com/user/Azimondious) | [Civitai](https://civitai.com/images/143826941) | 1113 | [视频](https://image.civitai.com/xG1nkqKTMzGDvpLrqFT7WA/19c504ee-b676-4962-99bb-be12eedddedc/original=true/19c504ee-b676-4962-99bb-be12eedddedc.mp4) |
| LTX022 | [码头海军女兵](prompts/stylized-animation/LTX022.md) | [witalpro665](https://civitai.com/user/witalpro665) | [Civitai](https://civitai.com/images/147819770) | 522 | [视频](https://image.civitai.com/xG1nkqKTMzGDvpLrqFT7WA/2f487722-1aa4-4e1d-8986-f7a1f6935f90/original=true/2f487722-1aa4-4e1d-8986-f7a1f6935f90.mp4) |
| LTX029 | [平面动画情侣拥抱](prompts/stylized-animation/LTX029.md) | [Le\_Grand\_Duc](https://civitai.com/user/Le_Grand_Duc) | [Civitai](https://civitai.com/images/142315799) | 252 | [视频](https://image.civitai.com/xG1nkqKTMzGDvpLrqFT7WA/1bfe005f-dde0-455d-a39a-011f4d427ce4/original=true/1bfe005f-dde0-455d-a39a-011f4d427ce4.mp4) |
| LTX032 | [暗黑动画霓虹小巷](prompts/stylized-animation/LTX032.md) | [WickedGargoyleProductions](https://civitai.com/user/WickedGargoyleProductions) | [Civitai](https://civitai.com/images/144450516) | 2707 | [视频](https://image.civitai.com/xG1nkqKTMzGDvpLrqFT7WA/8eeac939-6b33-4c8d-a1f3-1b4072ccd35a/original=true/8eeac939-6b33-4c8d-a1f3-1b4072ccd35a.mp4) |
| LTX066 | [全息霓虹音乐工作室](prompts/stylized-animation/LTX066.md) | [msavitt623](https://civitai.com/user/msavitt623) | [Civitai](https://civitai.com/images/142657779) | 1495 | [视频](https://image.civitai.com/xG1nkqKTMzGDvpLrqFT7WA/9dbe7e4a-60bb-446c-8b87-f1768f34ccf3/original=true/9dbe7e4a-60bb-446c-8b87-f1768f34ccf3.mp4) |
| LTX078 | [飞艇舱内的獾与鹤](prompts/stylized-animation/LTX078.md) | [fal.ai](https://fal.ai) | [fal.ai](https://fal.ai/learn/devs/seedance-2-5-vs-ltx-2-5-pro) | 2525 | [视频](https://v3b.fal.media/files/b/0aa6daf2/aAp7n06LKExr61sMqKvuZ_A%20dolly%20past%20a%20bar%20window%20in%20the%20rain%20-%20ltx%202.5%20pro.mp4) |

## 奇幻与变身

| # | 提示词 | 作者 | 原帖 | 字符 | 成片 |
| --- | --- | --- | --- | --- | --- |
| LTX005 | [女子变身绿眼尖牙恶魔](prompts/fantasy-transformation/LTX005.md) | [bcrm](https://civitai.com/user/bcrm) | [Civitai](https://civitai.com/images/140625014) | 95 | [视频](https://image.civitai.com/xG1nkqKTMzGDvpLrqFT7WA/e5992f87-232e-4218-8f35-fc6979da7060/original=true/e5992f87-232e-4218-8f35-fc6979da7060.mp4) |
| LTX011 | [女子缓缓变成恶魔](prompts/fantasy-transformation/LTX011.md) | [bcrm](https://civitai.com/user/bcrm) | [Civitai](https://civitai.com/images/140627565) | 90 | [视频](https://image.civitai.com/xG1nkqKTMzGDvpLrqFT7WA/5373c614-ec43-40bd-84b5-84e0dfd41d72/original=true/5373c614-ec43-40bd-84b5-84e0dfd41d72.mp4) |
| LTX021 | [女子变身紫眼尖牙恶魔](prompts/fantasy-transformation/LTX021.md) | [bcrm](https://civitai.com/user/bcrm) | [Civitai](https://civitai.com/images/141689966) | 96 | [视频](https://image.civitai.com/xG1nkqKTMzGDvpLrqFT7WA/6d6f49de-acba-4179-8c64-f2401cf6c179/original=true/6d6f49de-acba-4179-8c64-f2401cf6c179.mp4) |
| LTX023 | [女子变身黄眼尖牙恶魔](prompts/fantasy-transformation/LTX023.md) | [bcrm](https://civitai.com/user/bcrm) | [Civitai](https://civitai.com/images/141689122) | 96 | [视频](https://image.civitai.com/xG1nkqKTMzGDvpLrqFT7WA/faeeb703-8fc4-4013-a3c4-b3a572705dbb/original=true/faeeb703-8fc4-4013-a3c4-b3a572705dbb.mp4) |
| LTX030 | [女子变身红眼尖牙恶魔](prompts/fantasy-transformation/LTX030.md) | [bcrm](https://civitai.com/user/bcrm) | [Civitai](https://civitai.com/images/141689017) | 93 | [视频](https://image.civitai.com/xG1nkqKTMzGDvpLrqFT7WA/6effc9fd-e891-4e13-930d-6eadd7b259bb/original=true/6effc9fd-e891-4e13-930d-6eadd7b259bb.mp4) |
| LTX038 | [女子变身蓝眼尖牙恶魔](prompts/fantasy-transformation/LTX038.md) | [bcrm](https://civitai.com/user/bcrm) | [Civitai](https://civitai.com/images/141689191) | 94 | [视频](https://image.civitai.com/xG1nkqKTMzGDvpLrqFT7WA/98fe3cd8-d856-40f7-a44a-f976c6070d26/original=true/98fe3cd8-d856-40f7-a44a-f976c6070d26.mp4) |
| LTX047 | [女子变身橙眼尖牙恶魔](prompts/fantasy-transformation/LTX047.md) | [bcrm](https://civitai.com/user/bcrm) | [Civitai](https://civitai.com/images/141689692) | 96 | [视频](https://image.civitai.com/xG1nkqKTMzGDvpLrqFT7WA/6a60f378-62ce-4f0a-8f20-5fe34ebee562/original=true/6a60f378-62ce-4f0a-8f20-5fe34ebee562.mp4) |
| LTX048 | [女子变身青绿眼尖牙恶魔](prompts/fantasy-transformation/LTX048.md) | [bcrm](https://civitai.com/user/bcrm) | [Civitai](https://civitai.com/images/141691290) | 94 | [视频](https://image.civitai.com/xG1nkqKTMzGDvpLrqFT7WA/13dcaf15-e565-4a92-a85b-04c9874ca92f/original=true/13dcaf15-e565-4a92-a85b-04c9874ca92f.mp4) |
| LTX057 | [英雄连续变身](prompts/fantasy-transformation/LTX057.md) | [msavitt623](https://civitai.com/user/msavitt623) | [Civitai](https://civitai.com/images/147438107) | 808 | [视频](https://image.civitai.com/xG1nkqKTMzGDvpLrqFT7WA/c392aea5-7a76-4029-9bd5-6398d6a208d8/original=true/c392aea5-7a76-4029-9bd5-6398d6a208d8.mp4) |
| LTX085 | [空房间变身华丽舞厅](prompts/fantasy-transformation/LTX085.md) | [fal.ai](https://fal.ai) | [fal.ai](https://fal.ai/learn/tools/how-to-use-ltx-2-5) | 653 | [视频](https://v3b.fal.media/files/b/0aa6bb90/3n5nu-HVlU5_3IWyNUFnA_A%20stream%20of%20amber%20spirit%20pours%20into%20the%20rocks%20glass%20from%20off%20frame%20right%20and%20rises%20to%20two%20thirds%2C%20the%20surface%20settling%20as%20it%20fills%20and%20the%20caustics%20on%20the%20walnut%20shifting%20with%20it.mp4) |

## 用 API 跑这些提示词

这里的大部分提示词不是在我们的 API 上跑的：Civitai 上很多条是作者在自己电脑上用 LTX-2.5 开源权重、在 ComfyUI 工作流里跑的，同一段文字放到 API 上，出来的效果可能不一样。apimodels.app 上的 LTX-2.5 分两档，用同一个端点（[API 文档](https://apimodels.app/zh/docs/ltx-2-5)）：

- [LTX 2.5 Fast](https://apimodels.app/zh/models/ltx-2.5-fast)（`ltx-2.5-fast`）可以只给提示词，也可以再加一张首帧图（`image_url`）或一段音频（`audio_url`），输出 720p、1080p 或 1440p，24、25、48 或 50 fps。文生和图生是 6 到 20 秒、只能取偶数秒；1440p 或 48 / 50 fps 时只有 6、8、10 秒。
- [LTX 2.5 Pro](https://apimodels.app/zh/models/ltx-2.5-pro)（`ltx-2.5-pro`）是 Lightricks 定位给成片用的一档，只做文生和首帧图生，720p 或 1080p，6、8、10 秒三档，不收音频。
- 提示词最长 5000 字符。没有 4K、尾帧、参考图和视频输入，也没有负面提示词字段：原帖写在负面提示词里的东西，不挪进正文就等于没了。传了首帧又传 `aspect_ratio`，会直接返回 400。
- 每条视频的声音都和画面一起生成，没有静音选项。用 Fast 时，传进去的 `audio_url` 会原样当成片的声音，画面按它来生成。
- Fast：720p 每秒 $0.081、1080p 每秒 $0.117、1440p 每秒 $0.171，720p 6 秒 $0.486，1080p 10 秒 $1.17，1080p 20 秒 $2.34。Pro：720p 每秒 $0.108、1080p 每秒 $0.153，1080p 10 秒 $1.53。两档都比 Lightricks 官方 API 价低 10%；Fast 的音频生视频按成片长度计到 0.01 秒；失败不扣费。
- 本地跑的时候，作者可能用了 dev 或蒸馏版权重、自己调的采样参数、负面提示词或额外的引导图，这些都不在提示词文字里，搬不过来。想接近原帖里的成片，在 Fast 或 Pro 上要多试几次。
- 本库有 1 条超过 5000 字符，要先删短；最长的一条 7387 字符。
- 如果你自己在本地跑开源权重，它用的是 Lightricks 的 LTX-2.x Community License，有自己的条件，商用前先读一遍。

```bash
curl -X POST https://api.apimodels.app/v1/video/generations \
  -H "Authorization: Bearer YOUR_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "model": "ltx-2.5-fast",
    "prompt": "Style: high-resolution food photography - close-up - The chocolate is poured over the whipped cream and berries. The chocolate flows slowly, creating rich, glossy streaks across the white cream and the blue blueberry, the deep brown contrasting with the vibrant fruit. A soft, rich sound of chocolate dripping and settling accompanies the pour.",
    "resolution": "1080p",
    "fps": 24,
    "duration": 10,
    "aspect_ratio": "16:9"
  }'
# Fast、1080p、10 秒：$1.17。返回里有 taskId，轮询到 state 为 "completed"：
curl "https://api.apimodels.app/v1/video/generations?task_id=TASK_ID" \
  -H "Authorization: Bearer YOUR_API_KEY"
```

示例里的提示词是本库的 LTX002，作者 hichuicomfy，原样引用。

## 怎么收集的

提示词来自三类出处。Civitai 上的条目，取归在 LTX-2.5 下的视频帖子公开的生成信息里的提示词，只收生成信息里没有挂 LoRA 或其他附加模型的。fal.ai 上的条目照它的 LTX-2.5 页面原文收录：[模型页](https://fal.ai/ltx-2.5)、Pro 的文生视频和图生视频页，以及两篇 fal.ai 指南（[LTX-2.5 怎么用](https://fal.ai/learn/tools/how-to-use-ltx-2-5)、[Seedance 2.5 vs LTX-2.5 Pro](https://fal.ai/learn/devs/seedance-2-5-vs-ltx-2-5-pro)）。X 上的帖子是搜出来的，只收帖子或同一串回复里提到 LTX 的；提示词取原帖正文，或作者在原帖下自己的回复。

没收的：没有公开提示词的帖子、不是可用提示词的帖子（广告、教程、新闻、多模型对比、闲聊、残缺片段）、推广、夹着大量评论的提示词、色情内容（按关键词、Civitai 自己的分级和审核三道筛）、涉及未成年人的内容、真人肖像、血腥画面、不到 25 个字符的提示词，以及重复项。X 上提示词前面的「Prompt:」之类的标签、结尾的话题标签和 t.co 媒体链接不算提示词正文；提示词本身一个字没改。标题和分类是我们起的，编号顺序与 apimodels.app 上的提示词库一致。

## 出处、版权与许可

- **每条提示词的版权归作者**，视频和图片也归各自的作者。每条都写明作者、附原帖链接，媒体只链接到它原本所在的地方，没有任何文件拷进本仓库。
- **全文收录**：每条提示词都按原帖或原页面逐字全文收录。商用前请先看原帖。
- **我们自己写的内容**（写法说明、标题、分类表、数据文件和浏览页）按 [CC BY 4.0](LICENSE) 许可，引用请注明 apimodels.app 并附链接。
- 如果你是其中某条提示词的作者，想删除或更正署名，请开一个 issue，我们会尽快处理。
