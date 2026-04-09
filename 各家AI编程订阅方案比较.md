---
title: 各家AI编程订阅方案比较
date created: 260213
date modified: 260213
---
# 国产 

| 厂商与方案                                                                                                                                                                                                                                                                   | 月费(人民币)                                                                     | 额度 / 限制                                                                                        |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| **DeepSeek** 无<br>                                                                                                                                                                                                                                                      | [PAYGO](https://api-docs.deepseek.com/quick_start/pricing)                  |                                                                                                |
| [**Minimax**  ](https://www.minimaxi.com/pricing)<br>(稀宇科技)                                                                                                                                                                                                             | **Starter**: ¥29 / 月  <br>**Plus**: **¥49 / 月** (推荐)  <br>**Max**: ¥119 / 月 | **Starter**: 40 Prompts / 5小时  <br>**Plus**: 100 Prompts / 5小时  <br>**Max**: 300 Prompts / 5小时 |
| [**GLM**](https://bigmodel.cn/glm-coding?utm_source=tab_card&utm_medium=official-website&utm_content=glm-coding-plan&utm_campaign=Platform_Ops&_channel_track_key=hAjWuFKb)                                                                                             | **Lite**: ¥49 / 月  <br>**Pro**: **¥149 / 月**                                | 未标注                                                                                            |
| [Kimi](https://www.kimi.com/code?track_id=b921eab9-eee9-4805-8af2-b19387ef552d)                                                                                                                                                                                         | 49起步                                                                        | ~                                                                                              |
| [火山方舟](https://www.volcengine.com/activity/codingplan)                                                                                                                                                                                                                  | 40起                                                                         | ~                                                                                              |
| [阿里云百炼](https://bailian.console.aliyun.com/cn-beijing/?spm=5176.28197619.console-base_search-panel.dtab-product_sfm.13933ae4DEdFBF&scm=20140722.S_sfm._.ID_sfm-RL_%E5%A4%A7%E6%A8%A1%E5%9E%8B-LOC_console_console-OR_ser-V_4-P0_0&tab=doc#/doc/?type=model&url=3005961) | ~                                                                           |                                                                                                |

# 海外
## Claude Code

| Tier    | Credits/5h | Credits/周           | ~/month | Opus-rate tokens        | Equivalent API cost | Price |
| ------- | ---------- | ------------------- | ------- | ----------------------- | ------------------- | ----- |
| Pro     | 0.55M (1×) | 5M (1×)             | 21.7M   | 32.5M in or 6.5M out    | $163 (8.1×)         | $20   |
| Max 5×  | 3.3M(6×)   | 41,666,700 (8.33×)  | 180.6M  | 270.9M in or 54.2M out  | $1,354 (13.5×)      | $100  |
| Max 20× | 11M(20×)   | 83,333,300 (16.67×) | 361.1M  | 541.7M in or 108.3M out | $2,708 (13.5×)      | $200  |
Max在claude code的cache read是免费的，而不是像API那样是input的0.1倍

### 避免claude code 查封的处理
opencode-anthropic-auth 做的事情 CLIProxyAPI 已經都處理了：

| 功能                           | opencode-anthropic-auth | CLIProxyAPI                                                                                      |
| ---------------------------- | ----------------------- | ------------------------------------------------------------------------------------------------ |
| OAuth 認證                     | 己處理                     | 已處理                                                                                              |
| 系統提示加 "Claude Code" 前綴       | 有                       | 有 ([cloak 模式](https://deepwiki.com/search/cloak_a6764627-4e3c-4096-9689-309b03c2a29d?mode=fast)) |
| "OpenCode" 替換為 "Claude Code" | 有                       | 有                                                                                                |
| tool name 加 mcp_ 前綴          | 有                       | 有                                                                                                |
| anthropic-beta headers       | 有                       | 有                                                                                                |

