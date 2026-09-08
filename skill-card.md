# skill-card.md

## Description:

北京积分落户测算与咨询。环境支持时优先打开随包 HTML 可视化模拟器，在页面上完成填分、结果解释、差距与规划建议；环境无法打开时，由用户自行选择打开页面或使用文本引导模式。文本引导只负责填写引导、规则解释、查询指引和核对，不以聊天计算替代页面结果。触发场景为“查积分、算积分、问怎么填、做未来规划或咨询积分落户”。只做本地模拟与咨询，不承诺官方结果。

## Owner

武毅（发布账户：vincent51-commits / user_4f0eeeda）

### License/Terms of Use:

MIT-0

## Use Case:

想了解北京积分落户得分、资格核查、未来年份推演或规划建议的个人用户。可视化环境可使用本地 HTML 模拟器；无浏览器环境的 Agent 可先提供文本引导，并在用户需要最终结果时引导其自行打开页面或回传页面结果。页面不接入真实申报系统。

### Deployment Geography for Use:

China（北京积分落户口径）

## Known Risks and Mitigations:

Risk: 分数与规划基于本地模拟和参考口径，可能随政策、计算方式或分数线变化而失效。
Mitigation: 页面和 Skill 均明确标注“模拟计算、非官方、仅供参考”，并引导用户以官方审核或专业人士为准。

Risk: 表单内容会写在本机浏览器 `localStorage`，用于刷新恢复。
Mitigation: 数据仅保存在本机浏览器，不联网、不上传、不发送到服务器；用户可一键“清空填写记录”删除缓存。

Risk: 用户可能误以为结果等同于官方审核。
Mitigation: 每次输出必须包含免责声明；不代替代官方审核、专业律师或咨询人员。

Risk: 无浏览器环境无法打开 HTML，用户可能得不到可视化结果。
Mitigation: 不强制打开页面；允许用户自行打开，或使用文本引导模式。文本引导不替代页面计算，需要最终结果时仍以页面为准。

## Reference(s):

- `references/口径与查询.md`：页面字段映射、官方口径、查询来源、边界与已知限制
- `references/填写校验清单.md`：模式校验、填写完整性、计算来源与对账

## Skill Output:

Output Type(s): [Interactive HTML, Text]
Output Format: [有浏览器时以 `assets/beijing-jifen-wizard.html` 为可视化主界面；无浏览器时使用文本引导，明确标注“文本模式，非页面计算”。未取得页面计算结果时不输出最终分数或规划建议]
Output Parameters: [N/A]
Other Properties Related to Output: [No network calls; no account or personal data collected by the skill itself]

## Skill Version(s):

v1.3.0 (source: pack version)

## Release Note:

1.3.0 取消 HTML 硬门槛：改为“可视化 / 文本引导”模式选择。有浏览器能力时默认打开 HTML；无浏览器能力时由用户选择自行打开页面或使用文本引导。文本引导只做填写、规则解释和查询指引，不替代页面计算。
