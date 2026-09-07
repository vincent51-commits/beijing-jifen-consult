# skill-card.md

## Description:

必须先打开随包附带的 HTML 可视化模拟器，再在页面上完成北京积分落户测算；AI 仅在页面旁引导填写、解释结果、差距与规划建议。触发场景为“查积分、算积分、问怎么填、做未来规划或咨询积分落户”。页面上所有的填写、计算和结果读取都以前端模拟器为主界面；只做本地模拟与咨询，不承诺官方结果。

## Owner

武毅（发布账户：vincent51-commits / user_4f0eeeda）

### License/Terms of Use:

MIT-0

## Use Case:

想通过可视化 HTML 模拟器了解北京积分落户得分、资格核查、未来年份推演或规划建议的个人用户；需要先打开本地离线页面，不接入真实申报系统。若环境无法打开本地 HTML，本 Skill 不提供纯文字计算兜底。

### Deployment Geography for Use:

China（北京积分落户口径）

## Known Risks and Mitigations:

Risk: 分数与规划基于本地模拟和参考口径，可能随政策、计算方式或分数线变化而失效。
Mitigation: 页面和 Skill 均明确标注“模拟计算、非官方、仅供参考”，并引导用户以官方审核或专业人士为准。

Risk: 表单内容会写在本机浏览器 `localStorage`，用于刷新恢复。
Mitigation: 数据仅保存在本机浏览器，不联网、不上传、不发送到服务器；用户可一键“清空填写记录”删除缓存。

Risk: 用户可能误以为结果等同于官方审核。
Mitigation: 每次输出必须包含免责声明；不代替代官方审核、专业律师或咨询人员。

Risk: 环境无法打开本地 HTML 时，用户可能得不到结果。
Mitigation: Skill 要求必须打开页面；打不开时停止并引导用户手动打开，不以纯文字模拟结果替代页面。

## Reference(s):

- `references/口径与查询.md`：页面字段映射、官方口径、查询来源、边界与已知限制
- `references/填写校验清单.md`：填写完整性硬门槛与计算前后对账

## Skill Output:

Output Type(s): [Interactive HTML, Text]
Output Format: [必须先打开单文件 `assets/beijing-jifen-wizard.html`；页面为主界面，文本仅用于填写引导、结果解释、差距与规划建议。未打开页面不输出计算结论]
Output Parameters: [N/A]
Other Properties Related to Output: [No network calls; no account or personal data collected by the skill itself]

## Skill Version(s):

v1.2.0 (source: pack version)

## Release Note:

首次公开发布：随包附带本地模拟器、官方口径与查询来源、填写校验清单；明确本地缓存边界与非官方免责声明。1.2.0 版本将 HTML 可视化工具有效为主界面：必须先打开模拟器，未打开不得输出计算结论或规划建议。
