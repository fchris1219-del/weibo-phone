# 同层微博

酒馆正则 `<weiboapp>...</weiboapp>` 的远程 UI。入口为 `weibo.html`，GitHub Pages 地址为：

`https://fchris1219-del.github.io/weibo-phone/weibo.html`

## 与酱微博脚本版的关系

- UI、生成协议、微博预设、模板、档位、NPC、ID 池、热梗、世界书、上下文与柏宝书适配与脚本版同步。
- 同层版保留当前消息楼层适配：启动时读取当前 `<weiboapp>`，互动后延迟调用 `setChatMessages` 写回同一楼层。
- `chatMetadata.jiang_weibo_oneframe_v2` 仍是聊天内按档位保存的主存；当前档位同时序列化到本楼层，兼容旧同层微博的恢复方式。
- `extension_settings.jiang_weibo_oneframe_v2` 保存全局模板、角色模板和 API 配置；Token 不回显。
- 旧版 `[微博]`、`[评论]`、`<msg>/<chat:>`、旧 `<dm>/<thread:>`、`wb_lore` 与世界书快照均可继续读取。

同一份前端也可由酒馆助手启动器加载；只有检测到当前楼层接口时才开启楼层写回，悬浮脚本模式不会向正文楼层写入微博记录。
