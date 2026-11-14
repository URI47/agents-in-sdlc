---
title: "第 12 课 - 使用 GitHub Pages 部署网站"
description: "使用 GitHub Copilot 应用配置 Pages 工作流、审查拉取请求，并验证已发布的 Space Quiz。"
authors:
  - jamesmontemagno
lastUpdated: 2026-10-12
---

使用 GitHub Pages 部署 Space Quiz，让其他人也能访问该网站。Copilot 可以准备工作流并指导部署，但你仍需负责审查更改并确认网站已上线。

本课将：

- 请 Copilot 配置 GitHub Pages 部署。
- 在合并前审查工作流和拉取请求。
- 跟进部署并验证已发布的网站。

## 场景

Space Quiz 已位于 GitHub 存储库中，但用户仍需要一种简单的试用方式。使用 GitHub Pages 发布单文件网站，无需添加服务器或运行时依赖项，即可通过公共 URL 访问该网站。

## 请 Copilot 准备部署

> [!WARNING]
> 创建拉取请求可能会提交并推送代码。发送此提示前，请检查审批设置和目标存储库。如果选择了 **Approve all**，不要指望系统会再次请求确认。

在 `space-quiz` 的 Copilot 应用会话中，发送以下提示：

```plaintext
为此存储库准备 GitHub Pages 部署。创建一个 GitHub Actions 工作流，在需要时构建网站，并在更改进入默认分支后将其部署到 GitHub Pages。如果存储库中还没有 README，请添加一个，介绍此应用以及如何在本地运行它。使用这些更改创建拉取请求，并报告其链接以及所需的 Pages 设置或权限。不要合并、启用自动合并、更改 Pages 设置或部署。停止并等待我审查。
```

## 审查工作流和拉取请求

1. 确认只有在存储库原本没有 README 时才添加了 README。
2. 审查拉取请求中的更改，包括工作流的构建和部署步骤、触发条件及权限。
3. 确认工作流从默认分支部署，而不是从尚未合并的拉取请求部署。
4. 提出所需的更正并审查更新后的差异。在授权合并前，等待必需的拉取请求检查全部通过。

## 授权合并和部署

> [!WARNING]
> 以下提示授权智能体合并已审查的拉取请求、更改存储库的 Pages 设置并发布网站。只有在完成审查并确认存储库和拉取请求后，才能发送此提示。根据审批设置，这些操作可能无需再次确认即可执行。

将 `<PR_NUMBER>` 替换为已审查的拉取请求编号，然后单独发送以下提示：

```plaintext
我已审查此存储库中的拉取请求 <PR_NUMBER>，并授权合并和部署。使用 GitHub Actions 启用 GitHub Pages，只有在必需检查通过后才合并该拉取请求，并持续监控部署，直到成功。报告已上线网站的最终 URL。如果你没有启用 Pages 或合并的权限，请准确说明我需要批准或执行的操作；在网站上线前不要报告成功。
```

![三阶段示意图：已合并的 space-quiz 拉取请求；GitHub Actions 中成功运行的 Deploy website，其中包含 Build website、Upload artifact 和 Deploy to Pages 步骤；以及发布在 yourname.github.io/space-quiz/ 的 Space Quiz。](../../../_images/first-steps-app-pages-deploy.svg)

## 验证部署

1. 跟进 GitHub Actions 部署运行，直到成功。
2. 打开报告的 URL，确认 Space Quiz 可以正常加载。

如果智能体无法启用 Pages 或合并拉取请求，请按照它提供的具体说明操作。只有部署成功且网站正常加载后，才能将任务视为完成。

## 总结与后续步骤

Space Quiz 现已作为已上线的网站发布，你也亲自验证了部署，而不是只依赖智能体的报告。继续学习[第 13 课：审查与后续步骤][next-lesson]。

[next-lesson]: ../13-review/
