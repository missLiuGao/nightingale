<p align="center">
  <a href="https://github.com/ccfos/nightingale">
    <img src="doc/img/Nightingale_L_V.png" alt="nightingale - cloud native monitoring" width="100" /></a>
</p>
<p align="center">
  <b>开源告警管理专家 一体化的可观测平台</b>
</p>

<p align="center">
<a href="https://flashcat.cloud/docs/">
  <img alt="Docs" src="https://img.shields.io/badge/docs-get%20started-brightgreen"/></a>
<a href="https://hub.docker.com/u/flashcatcloud">
  <img alt="Docker pulls" src="https://img.shields.io/docker/pulls/flashcatcloud/nightingale"/></a>
<a href="https://github.com/ccfos/nightingale/graphs/contributors">
  <img alt="GitHub contributors" src="https://img.shields.io/github/contributors-anon/ccfos/nightingale"/></a>
<img alt="GitHub Repo stars" src="https://img.shields.io/github/stars/ccfos/nightingale">
<img alt="GitHub forks" src="https://img.shields.io/github/forks/ccfos/nightingale">
<br/><img alt="GitHub Repo issues" src="https://img.shields.io/github/issues/ccfos/nightingale">
<img alt="GitHub Repo issues closed" src="https://img.shields.io/github/issues-closed/ccfos/nightingale">
<img alt="GitHub latest release" src="https://img.shields.io/github/v/release/ccfos/nightingale"/>
<img alt="License" src="https://img.shields.io/badge/license-Apache--2.0-blue"/>
<a href="https://n9e-talk.slack.com/">
  <img alt="GitHub contributors" src="https://img.shields.io/badge/join%20slack-%23n9e-brightgreen.svg"/></a>
</p>



[English](./README_en.md) | [中文](./README.md)

## 夜莺 Nightingale 是什么

> 夜莺 Nightingale 是什么，解决什么问题？以大家都很熟悉的 Grafana 做个类比，Grafana 擅长对接各种各样的数据源，然后提供灵活、强大、好看的可视化面板。夜莺则擅长对接各种多样的数据源，提供灵活、强大、高效的监控告警管理能力。从发展路径和定位来说，夜莺和 Grafana 很像，可以总结为一句话：可视化就用 Grafana，监控告警就找夜莺。
>
> 在可视化领域，Grafana 是毫无争议的领导者，Grafana 在影响力、装机量、用户群、开发者数量等各个维度的数字上，相比夜莺都是追赶的榜样。巨无霸往往都是从一个切入点打开局面的，Grafana Labs 有了在可视化领域 Grafana 这个王牌，逐步扩展到整个可观测性方向，比如 Logging 维度有 Loki，Tracing 维度有 Tempo，Profiling 维度有收购来的 Pyroscope，On-call 维度有同样是收购来的 Grafana-OnCall 项目，还有时序数据库 Mimir、eBPF 采集器 Beyla、OpenTelemetry 采集器 Alloy、前端监控 SDK Faro，最终构成了一个完整的可观测性工具矩阵，但整个飞轮都是从 Grafana 项目开始转动起来的。
>
>夜莺，则是从监控告警这个切入点打开局面，也逐步横向做了相应扩展，比如夜莺也自研了可视化面板，如果你想有一个 all-in-one 的监控告警+可视化的工具，那么用夜莺也是正确的选择；比如 OnCall 方向，夜莺可以和 [Flashduty SaaS](https://flashcat.cloud/product/flashcat-duty/) 服务无缝的集成；在采集器方向，夜莺有配套的 [Categraf](https://flashcat.cloud/product/categraf)，可以一个采集器中管理所有的 exporter，并同时支持指标和日志的采集，极大减轻工程师维护的采集器数量和工作量（这个点太痛了，你可能也遇到过业务团队吐槽采集器数量比业务应用进程数量还多的窘况吧）。

夜莺 Nightingale 作为一款开源云原生监控工具，最初由滴滴开发和开源，并于 2022 年 5 月 11 日，捐赠予中国计算机学会开源发展委员会（CCF ODC），为 CCF ODC 成立后接受捐赠的第一个开源项目。在 GitHub 上有超过 10000 颗星，是广受关注和使用的开源监控工具。夜莺的核心研发团队，也是 Open-Falcon 项目原核心研发人员，从 2014 年（Open-Falcon 是 2014 年开源）算起来，也有 10 年了，只为把监控做到极致。


## 快速开始
- 👉 [文档中心](https://flashcat.cloud/docs/) | [下载中心](https://flashcat.cloud/download/nightingale/)
- ❤️ [报告 Bug](https://github.com/ccfos/nightingale/issues/new?assignees=&labels=&projects=&template=question.yml)
- ℹ️ 为了提供更快速的访问体验，上述文档和下载站点托管于 [FlashcatCloud](https://flashcat.cloud)
- 💡 前后端代码分离，前端代码仓库：[https://github.com/n9e/fe](https://github.com/n9e/fe)

## 功能特点

- 对接多种时序库，实现统一监控告警管理：支持对接的时序库包括 Prometheus、VictoriaMetrics、Thanos、Mimir、M3DB、TDengine 等。
- 对接日志库，实现针对日志的监控告警：支持对接的日志库包括 ElasticSearch、Loki 等。
- 专业告警能力：内置支持多种告警规则，可以扩展支持常见通知媒介，支持告警屏蔽/抑制/订阅/自愈、告警事件管理。
- 高性能可视化引擎：支持多种图表样式，内置众多 Dashboard 模版，也可导入 Grafana 模版，开箱即用，开源协议商业友好。
- 支持常见采集器：支持 [Categraf](https://flashcat.cloud/product/categraf)、Telegraf、Grafana-agent、Datadog-agent、各种 Exporter 作为采集器，没有什么数据是不能监控的。
- 👀无缝搭配 [Flashduty](https://flashcat.cloud/product/flashcat-duty/)：实现告警聚合收敛、认领、升级、排班、IM集成，确保告警处理不遗漏，减少打扰，高效协同。


## 截图演示


你可以在页面的右上角，切换语言和主题，目前我们支持英语、简体中文、繁体中文。

![语言切换](doc/img/readme/n9e-switch-i18n.png)

即时查询，类似 Prometheus 内置的查询分析页面，做 ad-hoc 查询，夜莺做了一些 UI 优化，同时提供了一些内置 promql 指标，让不太了解 promql 的用户也可以快速查询。

![即时查询](doc/img/readme/20240513103305.png)

当然，也可以直接通过指标视图查看，有了指标视图，即时查询基本可以不用了，或者只有高端玩家使用即时查询，普通用户直接通过指标视图查询即可。

![指标视图](doc/img/readme/20240513103530.png)

夜莺内置了常用仪表盘，可以直接导入使用。也可以导入 Grafana 仪表盘，不过只能兼容 Grafana 基本图表，如果已经习惯了 Grafana 建议继续使用 Grafana 看图，把夜莺作为一个告警引擎使用。

![内置仪表盘](doc/img/readme/20240513103628.png)

除了内置的仪表盘，也内置了很多告警规则，开箱即用。

![内置告警规则](doc/img/readme/20240513103825.png)



## 产品架构

社区使用夜莺最多的场景就是使用夜莺做告警引擎，对接多套时序库，统一告警规则管理。绘图仍然使用 Grafana 居多。作为一个告警引擎，夜莺的产品架构如下：

![产品架构](doc/img/readme/20240221152601.png)

对于个别边缘机房，如果和中心夜莺服务端网络链路不好，希望提升告警可用性，我们也提供边缘机房告警引擎下沉部署模式，这个模式下，即便网络割裂，告警功能也不受影响。

![边缘部署模式](doc/img/readme/20240222102119.png)


## 交流渠道
- 报告Bug，优先推荐提交[夜莺GitHub Issue](https://github.com/ccfos/nightingale/issues/new?assignees=&labels=kind%2Fbug&projects=&template=bug_report.yml)
- 关注[这个公众号](https://gitlink.org.cn/UlricQin)了解更多夜莺动态和知识
- 加我微信：`picobyte`（我已关闭好友验证）拉入微信群，备注：`夜莺互助群`

## 广受关注
[![Stargazers over time](https://api.star-history.com/svg?repos=ccfos/nightingale&type=Date)](https://star-history.com/#ccfos/nightingale&Date)

## 社区共建
- ❇️ 请阅读浏览[夜莺开源项目和社区治理架构草案](./doc/community-governance.md)，真诚欢迎每一位用户、开发者、公司以及组织，使用夜莺监控、积极反馈 Bug、提交功能需求、分享最佳实践，共建专业、活跃的夜莺开源社区。
- ❤️ 夜莺贡献者
<a href="https://github.com/ccfos/nightingale/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=ccfos/nightingale" />
</a>

## License
- [Apache License V2.0](https://github.com/didi/nightingale/blob/main/LICENSE)
