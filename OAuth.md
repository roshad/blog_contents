---
title: OAuth
date created: 260208
date modified: 260208
---
- IDP (Identity Provider)，中文通常翻译为 “身份提供商” 或 “认证提供商”
- RP (Relying Party) —— 依赖方（或叫 SP - Service Provider）
- OAuth= Open Authentication
- OAuth被视为“Identity as a Service” (IDaaS)，即 “身份即服务”
### OAuth登录时返回什么？
授权IDP登录后，RP通常会拿到这几样东西：
- **ID Token (身份令牌)**：这个最关键。它是一个 **JWT（JSON Web Token）**，你可以把它看成一张“电子身份证”。
    - **里面有啥**：这个 Token 看起来是一串乱码，但平台解开它后，里面直接写着你的**姓名、邮箱、头像 URL、唯一用户 ID**。
    - **作用**：平台通过它就知道“你是谁”，从而直接帮你建立账号。
- **Access Token (访问令牌)**：这就是我之前说的“房卡”。
    - **作用**：如果那个平台还想读取你的谷歌网盘或者日历，它就得拿着这个 Token 去找谷歌要数据。
- **Refresh Token (刷新令牌)**：
    - **作用**：Access Token 通常几十分钟就过期了。有了这个“刷新令牌”，平台可以在你没操作的时候，偷偷去谷歌那换一个新的 Access Token，保证你不用天天重复点登录。