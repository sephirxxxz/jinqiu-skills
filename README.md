# jinqiu-skills

锦秋基金内容工作的 agent skills，按 [Agent Skills](https://agentskills.io/specification) 标准组织，pi 可直接加载。

## 包含

### `jinqiu-copywriting`

撰写、修改和审核锦秋基金小红书文案：发布标题、正文、话题标签、逐页上图文字。

- 只负责文字，不含字体、排版、封面制作、图片生成、Canva 操作和发布。
- 文案确认后停止，不自动进入出图。
- 含现行写作规范（篇幅、事实、语言）和 5 份往期案例。

## 安装

把 skill 目录复制到 agent 的 skills 目录。以 pi 为例：

```bash
cp -r jinqiu-copywriting ~/.pi/agent/skills/
```

Windows：

```powershell
Copy-Item -Recurse jinqiu-copywriting "$env:USERPROFILE\.pi\agent\skills\"
```

安装后新开一个会话即可通过描述自动加载，或手动调用 `/skill:jinqiu-copywriting`。

## 结构

```
jinqiu-copywriting/
├── SKILL.md                     入口：任务边界、工作步骤、完成标准
└── references/
    ├── writing-rules.md         现行写作规范（会变的部分放这里）
    └── examples.md              往期案例；末尾的模式是历史归纳，不是规范
```

`SKILL.md` 只在任务匹配时加载；`references/` 不自动进上下文，由 `SKILL.md` 指定读取。

## 来源

写作规范整理自锦秋图文项目的工作规范，案例来自账号已发布内容。历史案例只用于参考表达，不作为当期事实来源。

## License

[MIT](LICENSE)
