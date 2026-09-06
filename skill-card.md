# skill-card.md

## Description:

引导用户完成北京积分落户测算：把用户事实映射到随包附带的单文件模拟器，解释结果、差距与规划建议。触发场景为“查积分、算积分、问怎么填、做未来规划或咨询积分落户”。只做本地模拟与咨询，不承诺官方结果。

## Owner

武毅（发布账户：vincent51-commits / user_4f0eeeda）

### License/Terms of Use:

MIT-0

## Use Case:

想了解北京积分落户得分、资格核查、未来年份推演或规划建议的个人用户；需要在本地离线使用、不接入真实申报系统的场景。

### Deployment Geography for Use:

China（北京积分落户口径）

## Known Risks and Mitigations:

Risk: 分数与规划基于本地模拟和参考口径，可能随政策、计算方式或分数线变化而失效。
Mitigation: 页面和 Skill 均明确标注“模拟计算、非官方、仅供参考”，并引导用户以官方审核或专业人士为准。

Risk: 表单内容会写在本机浏览器 `localStorage`，用于刷新恢复。
Mitigation: 数据仅保存在本机浏览器，不联网、不上传、不发送到服务器；用户可一键“清空填写记录”删除缓存。

Risk: 用户可能误以为结果等同于官方审核。
Mitigation: 每次输出必须包含免责声明；不代替代官方审核、专业律师或咨询人员。

## Reference(s):

- `references/口径与查询.md`：页面字段映射、官方口径、查询来源、边界与已知限制
- `references/填写校验清单.md`：填写完整性硬门槛与计算前后对账

## Skill Output:

Output Type(s): [Text, Interactive HTML]
Output Format: [结论、依据、差距、建议、填写状态与免责声明；单文件 `assets/beijing-jifen-wizard.html` 供本地使用]
Output Parameters: [N/A]
Other Properties Related to Output: [No network calls; no account or personal data collected by the skill itself]

## Skill Version(s):

v1.1.1 (source: pack version)

## Release Note:

首次公开发布：随包附带本地模拟器、官方口径与查询来源、填写校验清单；明确本地缓存边界与非官方免责声明。1.1.1 版本复核 ClawHub 安全校验，补齐 skill-card 并明确 localStorage 仅本地保存、不联网不上传。
