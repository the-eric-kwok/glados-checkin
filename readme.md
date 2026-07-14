# Checkin

GitHub Actions 实现 [GLaDOS][glados] 自动签到

## 使用说明

1. Fork 这个仓库

1. 登录 [GLaDOS][glados] 获取 Cookie
   <img width="1174" height="661" alt="image" src="https://github.com/user-attachments/assets/3909930c-becf-4dea-9374-e681b84b771f" />

1. 添加 Cookie 到 Secret `GLADOS`

1. 启用 Actions, 每天北京时间 00:10 自动签到

## 高级功能

1. 如有多个帐号, 可以写为多行 Secret `GLADOS`, 每行写一个 Cookie

1. 如需修改时间, 可以修改文件 [run.yml](.github/workflows/run.yml#L7) 中的 `cron` 参数, 格式可参考 [crontab]

1. 如需推送通知, 可配置 Secret `NOTIFY`, 已支持:
    1. [WxPusher][wxpusher]: 格式 `wxpusher:{token}:{uid}`
    1. [PushPlus][pushplus]: 格式 `pushplus:{token}`
    1. [PushDeer][pushdeer]: 格式 `pushdeer:{token}`
    1. [bark][bark]: 格式 `bark:{token}`
    1. Console: 格式 `console:log`, 作为日志输出, 一般用于调试
    1. 如需配置多个, 可以写为多行, 每行写一个

1. 注意: Cookie 以及接口输出数据, 包含帐号敏感信息, 因此不要随意公开

<img width="1146" height="802" alt="image" src="https://github.com/user-attachments/assets/b0c6d18f-13ab-40dc-8ccf-f1d392994d5b" />

<img width="952" height="527" alt="image" src="https://github.com/user-attachments/assets/9972cb3a-d4f2-4e42-bb0c-2afc4bb1980a" />


---

[glados]: https://github.com/glados-network/GLaDOS
[crontab]: https://crontab.guru/
[pushplus]: https://www.pushplus.plus/
[wxpusher]: https://wxpusher.zjiecode.com/
[pushdeer]: https://github.com/easychen/pushdeer
[bark]: https://bark.day.app
