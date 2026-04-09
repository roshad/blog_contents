---
title: github release 的写法
date created: 260214
date modified: 260214
---
 - Git tag 随便自己命名，能匹配workflow 里写定的。
- 但项目里这3处“应用版本号”需统一成 不带 v 的三段式SemVer，例如 1.0.0：
	- Cargo.toml
	- tauri.conf.json
	- package.json
- MAJOR：有破坏性变化（旧数据不兼容、设置格式变更、行为大改）
	- 不变算是个好事
- MINOR：新增功能，且兼容旧版本
- PATCH：bug 修复、性能优化、小改动