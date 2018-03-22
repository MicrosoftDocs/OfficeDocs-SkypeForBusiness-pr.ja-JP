---
title: マイクロソフトのチームのサービス管理のガイドの計画
author: rmw2890
ms.author: MyAdvisor
manager: lehewe
ms.date: 03/16/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: サービス、ネットワーク、およびエンドポイントの状態と動作を定義して品質の支持者の役割を管理することにより、質の高いチームのユーザー エクスペリエンスを提供します。
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: cccd06cd9bd5ee458497fbb41db56955bb9a5ee9
ms.sourcegitcommit: d70e5a5e7d05a2226c1d011895fb12187d73fad0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2018
---
# <a name="plan-for-service-management-and-quality"></a>サービスの管理と品質の計画

このドキュメントは、マイクロソフトのチームを Envision フェーズです。
 
## <a name="introduction"></a>はじめに

このコンテンツを提供し、高品質のマイクロソフト チーム配置を維持するために必要な要件の概要を紹介します。 Envision フェーズの最初のパイロットまたは運用展開の前に、サービスの管理と品質の計画での展開を成功させることを確認することができます。

ガイダンスは、次のセクションに分かれています。

-   まず、ユーザーの操作性と品質を支持する主要なコンポーネントの概要です。 これには、マイクロソフトのチームに契約時の前に重点領域が強調表示されます。

-   2 つ目は、最初のユーザーのパイロットまたは生産の展開の前に、マイクロソフトのチームを管理するために、サポート モデルを計画するためガイダンスを指定します。 このセクションでは、品質のチームの配置を維持するために定期的に実行する必要のあるタスクについて説明します。 さらに、このセクションでは紹介を詳しく理解し、これらのタスクを任せていますを使用します。

-   3 番目に、特定のガイダンスは、マイクロソフトのチームをサポートするために計画、ネットワークおよび組織内のエンドポイントを持つことができます。

-   最後に、次の手順は、関連するコンテンツへの参照で集計されます。

## <a name="key-components-that-affect-user-experience"></a>ユーザー エクスペリエンスに影響を与える主要なコンポーネント

ユーザー エクスペリエンスに影響を与える主要なコンポーネントは、このセクションで確認されます。 主要なコンポーネントを確認するには、前に、組織のビジネス目標を実現するための重要性と操作性を理解することが重要です。 最初にユーザー エクスペリエンスを定義する方法を確認してみましょう。

### <a name="user-experience-defined"></a>ユーザー エクスペリエンスの定義

マイクロソフトのチームを展開し、ビジネス ・ プロセスのワークフローを強化するために通信を組み込む場合は、ビジネス目標を実現できます。 品質ドライブの導入と使用法: かどうか、組織が、人を喜びとしている高品質のサービスを提供し、個人やチームの信頼を獲得でき、新しい革新的な方法のサービスを使用してビジネス上の利点を促進するを検索します。

チームとユーザーの経験は、これの中核となる、人の感情と、サービスに対する姿勢です。 ユーザー エクスペリエンスをどのようなを提供しますか。 チームを使用する方法を理解し、例外的な通話の音質が発生していると、場所に関係なく確実に接続できることを日常のワークフローへの組み込みのユーザーの範囲です。 ユーザーの操作性が本質的に非常に広範ですこのドキュメントでは、組織内で制御可能な要素にのみ焦点を当てます。

優れたユーザー エクスペリエンスを提供するきわめて重要な配置に固有の要件がある-特にとクラウドの音声を使用して機能チームにします。 リアルタイム トラフィックの優先順位の指定を必要に応じてその他のコミュニケーションとコラボレーションの投資で第一級市民として、マイクロソフトのチームを扱うことが重要です。 次のセクションでは、ユーザー エクスペリエンスに影響を与える主要なコンポーネントの概要を示します。 それ以上のセクションではガイダンスが提供されますを展開し、品質を構成する主要なコンポーネントを管理する計画を開始する方法について。

### <a name="key-components-of-quality"></a>品質の主要なコンポーネント

組織またはパートナーのサポート チームの配置の Envision フェーズ中に、次の 3 つの主要コンポーネントの計画を開始する必要があります: 管理、ネットワーク、およびエンドポイントにサービスを提供します。 3 つすべての領域の組み合わせは、ユーザー エクスペリエンスの質に不可欠です。

![品質、およびサービスの管理がすべての 3 つのコンポーネントに重なっている 3 つのコンポーネントを説明する図。](media/envision-planning-for-service-management-and-quality-complete-guide-image1.png)

#### <a name="service-management"></a>サービスの管理

サービスの管理は、責任の範囲の 2 つのカテゴリに分類できます。

-   **マイクロソフトの責任**です。 マイクロソフトでは、インフラストラクチャ ・ コンポーネントを Office 365 サービスを構成する必要があります。 マイクロソフトは、信頼性と高品質の経験を持つチームに接続するユーザーのいずれかが提供されることを確実にお客様に責任を負う。

-   **お客様の責任**です。 組織は、Office 365 サービス、ネットワークの設置、およびユーザーのエンドポイントのさまざまな側面を管理する責任者です。 たとえば、Office 365 には、新しい IP アドレスを追加するユーザーの中断を回避するのには新しいエンドポイントへの通信を許可する適切なファイアウォールを更新する必要があります。

計画サービスの管理の詳細については、[サービスの管理の計画](https://docs.microsoft.com/MicrosoftTeams/envision-planning-for-service-management-and-quality-complete-guide#Plan-for-service-management)を参照してください。

#### <a name="network"></a>ネットワーク 

ほとんどの組織でネットワークが最初に設計されていますデータや、データ センターに存在するアプリケーションへのアクセスを提供します。 Office 365 のようなクラウド ベースのアプリケーションでは、チームが必要とする新しいアクセスとデータ ・ フローをサポートするためにこれらのネットワークへの変更が必要です。 チームのユーザーを有効するには、組織で、前に、評価し、現在のネットワークを最適化する必要があります。 これは、クラウドのボイス機能を利用する際に非常に重要です。

従来のネットワークでは、ユーザーがチームにアクセスするのには組織の境界ネットワークを通過する必要があります。 多くの組織では、プロキシ サーバー、ファイアウォール、およびブロック、影響を及ぼすこと、またはネットワーク トラフィック用に最適化されていないパスを提供する Vpn などのセキュリティ ベースのデバイスがあります。

さらに、コアの内部ネットワークを最適化したり、リアルタイム メディアを含め、チームの作業負荷をサポートするための十分な能力と品質を提供する適切なサイズにする必要があります。 帯域幅の計画、改善計画を使用することができ、ネットワークを確実に最適化は、Office 365 に高品質かつ効率的なパスを提供します。

ネットワークの計画に関する詳細なガイダンスは、[ネットワークの構成を計画する](https://docs.microsoft.com/MicrosoftTeams/envision-planning-for-service-management-and-quality-complete-guide#Plan-for-network-quality)を参照してください。

#### <a name="endpoints"></a>エンドポイント

マイクロソフト チームは、さまざまなエンドポイントをサポートしています。 電話のタブレット Pc からは、ほぼすべてのデバイスからのチームをどこにでもアクセスできます。

最良のエクスペリエンスをユーザーに提供可能であれば、する必要があります Envision フェーズ中にこれらの重要な側面を検討してください: エンドポイントでは、チームのハードウェアとソフトウェアの要件を達成しますか? 構成され、Wi-fi ネットワークをサポートするエンドポイントを最適化しますか。 音声通話を送受信するデバイスを使用するか。 これらのデバイスは、チームに対して最適化を行うのでしょうか。

エンドポイントの計画に関する詳細なガイダンスは、[エンドポイントの品質評価の計画](https://docs.microsoft.com/MicrosoftTeams/envision-planning-for-service-management-and-quality-complete-guide#Plan-for-endpoint-quality)を参照してください。

## <a name="plan-for-service-management"></a>サービスの管理の計画

サービスの管理は、展開およびユーザーに対して有効にされた後、マイクロソフトのチーム サービスの日常的な操作をカバーする広範なトピックです。 The Teams service encompasses Microsoft Office 365 and the infrastructure components that are deployed on-premises (for example, networking).

ほとんどの場合、サービス管理の概念はほとんどの組織にとって新しい概念ではありません。 おそらく既に実装しているプロセスと既存のサービスに関連付けられているタスクです。 とはいえ、何がある場所を計画するときサービスの管理の現在、将来的にマイクロソフトのチームをサポートするためを追加することができます可能性があります。

サービスの管理には、すべてのアクティビティが含まれますのプロセスが関与するエンド ツー エンドのマイクロソフトのチームを管理します。 前述のとおり、いくつかのコンポーネント サービス管理の — インフラストラクチャ ・ コンポーネントを Office 365 サービス自体を構成する: マイクロソフトの責任では、顧客は、チームのさまざまな側面を管理するには、そのユーザーに責任を負うが、ネットワーク、およびエンドポイントを提供します。 ドキュメントのこのセクションで、サービス管理の観点からお客様の責任に焦点を当てます。

![Qualilty、およびサービスの管理がすべての 3 つのコンポーネントに重なっている 3 つのコンポーネントを説明する図。 With a focus on Service Mangement.](media/envision-planning-for-service-management-and-quality-complete-guide-image2.png)

### <a name="introduction-to-the-operations-guide"></a>Introduction to the Operations Guide 

**What**, **Who**, and **How** are three important questions that need to be answered when it comes to service management.

You can use the Operations Guide [Link to Operations Guide] to help you address all three of these questions. The guide provides a list of activities to be performed on a daily, weekly, monthly, and as-needed basis. These activities and tasks are critical for maintaining a high-quality Teams deployment. 展開を成功させるための Envision フェーズの早い段階で実行する必要がある計画の重要な側面は、サービス管理の特定のアクティビティを実行するために担当者を決定します。 After you’ve figured out the tasks and activities, they need to be understood and followed by the groups or individuals that you assign to them. The Operations Guide provides knowledge and guidance for how to perform each of the tasks, and/or references to outside content.

### <a name="operational-role-mapping"></a>Operational role mapping

Planning for service management early is a critical milestone, because the operations phase begins when the first pilot users are enabled. The project team must review and agree on the tasks and activities required, identify the team that’s responsible for each operational task, and then get a commitment and sign-off from each respective team.

サインオフが完了した後、担当チームが開始する必要がありますし、これらの役割と責任に任せています。 This might include training and readiness, updating the staffing model, or ensuring that external partners are ready to deliver.

Envision のフェーズの早い段階で運用上の役割のマッピングには、パイロット、および操作をランプの中に、運用タスクを起動してすべての準備ができている、展開を開始した後かどうかを確認するすべてのチームが有効にします。

The Operations Guide provides a list of common tasks mapped to typical roles that should be valid in most scenarios. You need to customize these responsibilities to work for your organization.

### <a name="the-quality-champion-role"></a>The Quality Champion role

A group or individual needs to be accountable for quality in all organizations. This is the most important role in service management. The Quality Champion is a customer role that's assigned to a person or group who is passionate about their users' experience. This role requires the skills to identify trends in the environment and the sponsorship to work with other teams to drive remediation. The best candidate for the Quality Champion is typically the customer service owner, who—depending on the organization’s size and complexity—could be any person or group who is passionate about user experience.

The Quality Champion leverages existing tools and documented processes, such as the Call Quality Dashboard (CQD) and the Quality Experience Review Guide, to monitor user experience, identify quality trends, and drive remediation where needed. The Quality Champion works with the respective teams to drive remediation actions, reporting to a steering committee on their progress and open issues.

The tasks and activities associated with the role have been documented in the Operations Guide. This role should be assigned early in the Envision phase. A key step in operationalizing the role of Quality Champion is gaining the knowledge required for the role and ensuring the prerequisites are in place to deliver on the tasks. A key task for this role is running a regular Quality Experience Review.

### <a name="introduction-to-the-quality-experience-review-guide"></a>Introduction to the Quality Experience Review Guide

The Quality Experience Review Guide has a set of activities that assess and provide remediation guidance in key areas that have the greatest impact for improving user experience as shown in the figure below.

![A diagram that indicates the key areas that are examined during a quality experience review.](media/envision-planning-for-service-management-and-quality-complete-guide-image3.png)

By continually assessing and remediating the areas described in this document, you can reduce their potential to negatively affect user experience. Most user-experience problems encountered in a deployment can be grouped into the following categories:

-   Incomplete firewall or proxy configuration

-   Poor Wi-Fi coverage

-   Insufficient bandwidth

-   VPN

-   最適化されていない、または組み込みのオーディオ デバイスの使用

-   問題のあるサブネットまたはネットワーク デバイス

品質のエクスペリエンス評価ガイドで提供されるガイダンスを報告し、説明したとおりで、オーディオを採用し、影響を最大化に重点を置いた各領域を調査する主要なツールとして呼び出す品質ダッシュ ボード (救難) オンラインを使用して重点的に説明します。 Any optimizations made to the network to improve the audio experience will also directly translate to improvements in video and desktop sharing.

We highly recommend that you nominate the Quality Champion early on. After being nominated, they should start to familiarize themselves with the content in the Quality Experience Review Guide.

The Quality Experience Review Guide can be found [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/quality-of-experience-review-guide.docx?raw=true).

## <a name="plan-for-network-quality"></a>ネットワークの品質管理の計画 

Planning for network quality will be the focus for the following section.

![Diagram describing the 3 components of quality, and how service management overlaps all 3 components. With a focus on Network.](media/envision-planning-for-service-management-and-quality-complete-guide-image4.png)

As previously mentioned, planning for network quality prior to onboarding to Microsoft Teams is critical. For further guidance for network readiness, see [Prepare your organization's network for Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/prepare-network).

In most organizations, networks can comprise both managed and unmanaged networks.

Managed networks are components of the network infrastructure that an organization has direct control over. As a result, managed networks have a direct influence on the quality that can be provided to real-time traffic workloads.

Conversely, unmanaged networks are segments of the network that a customer has limited control, or no control, over.

Internet connections between the organization and Office 365 are networks where a customer has limited control. The networks are managed by an ISP, but organizations should be able to influence the quality of the network by upgrading their bandwidth, advocating for route optimizations, or—if all else fails—switching ISPs.

Home networks or networks in hotels or coffee shops are examples of networks where a customer has no control.

In the following sections, we will focus on the quality requirements of managed networks.

### <a name="key-network-planning-areas"></a>Key network planning areas

The following sections focus on the important areas for delivering a high-quality network.

> [!NOTE]
> Many networks evolve over time due to upgrades, expansion, or other business requirements. Ensure that you have operational processes in place to maintain these areas as part of your service management planning.

#### <a name="bandwidth"></a>Bandwidth

Bandwidth planning is a critical aspect of the network readiness activity. マイクロソフトのチームの作業負荷に対して、十分な帯域幅があることを保証することが不可欠です。 適切なサイズの既存のネットワークには、何が現在準備されている、現在の使用率を理解する必要がありますと、最終的には、残りの利用可能な帯域幅。

To measure current utilization, you need to monitor the network. This measurement can then be used as the starting point for bandwidth planning. In addition, the network should be continually monitored during the deployment and after the deployment to ensure that the network is sufficiently provisioned.

> [!NOTE]
> When monitoring network utilization, it’s important to avoid using averages over the day. These averages can include non-core hours that skew the result. Averages can hide peak periods and mask an underlying problem.

The [Network Planner](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner) helps you determine and organize network requirements for your deployment in just a few simple steps. By using the tool to gather your organization's networking details and Cloud Voice usage, you can get an approximate calculation of the network requirements you’ll need for your Cloud Voice deployment, manage and export these details for reporting, and view areas for further investigation and next steps.

#### <a name="quality-of-service-qos"></a>Quality of service (QoS)

QoS should be implemented on all segments of the managed network, even networks that have been adequately provisioned for bandwidth. In the latter case, QoS acts as a risk mitigation in the event of unanticipated network load. When QoS is implemented, voice traffic will be prioritized so that these unanticipated events don’t affect quality.

QoS の実装では、出口のポイントまでのエンドポイントとエンドポイントに出口のポイントから、ネットワークの領域を含める必要があります。 これは、双方向の音声トラフィックが優先されていることを確認します。 QoS should be implemented on both wired and Wi-Fi networks.

QoS を実装する、ネットワーク上での次のガイダンスに役立つ[マイクロソフトのチームでは、品質のサービス](https://docs.microsoft.com/MicrosoftTeams/qos-in-teams)

#### <a name="proxy-servers"></a>Proxy servers

Many organizations view traffic destined for the internet as a security risk, and they mitigate this risk by monitoring and evaluating traffic at the egress points in the network. プロキシ サーバーは、この要件を満たすために展開できるデバイスのクラスです。

パケット検査や変更、ペイロードを実行する場合、プロキシ サーバーに問題が発生します。 This can lead to call setup failures, dropped calls, and poor call quality. リアルタイム メディアは、強制的にプロキシ サーバーを通過する場合は、チームでメディアのスタックは TCP で、さらに品質が低下することに失敗する強制されます。 UDP は、TCP 経由で常に優先します。

さらに、プロキシ サーバーいないが設計されているマイクロソフトのチームの作業負荷では具体的には、Office 365 の追加の負荷を処理するために、リアルタイムのメディアを含みます。

Due to the potential problems a proxy server can introduce, and these additional capacity concerns, Microsoft recommends bypassing the proxy server and making a direct connection to Office 365.

プロキシ サーバーをバイパスするための構成はベンダーによって異なりますが、一般的な方法通常では、プロキシ自動構成 (PAC) ファイルを更新します。 PAC ファイルは、プロキシを通過するトラフィックと、どのようなトラフィックをバイパスすることを説明する構成ファイルです。

Some proxy server vendors provide an automated process for ensuring the configuration is up to date. 更新された PAC ファイルをダウンロードするには、ベンダーがこの自動プロセスを提供していない場合は、 <https://aka.ms/o365proxies>。

[Skype オンライン ビジネスとチームのためのプロキシ サーバー](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/proxy-servers-for-skype-for-business-online)

#### <a name="firewalls"></a>ファイアウォール

右側のポートとプロトコルは、すべての Office 365 の ip アドレスや Url を開くことを確認は、マイクロソフトのチームにアクセスする必要があります。 高品質の展開が重要です。 Simply making a call or joining a conference call is not enough to be sure your firewall is properly configured.

ファイアウォールで TCP を開くだけの場合は、セッションが確立されますが優先のトランスポート (UDP) がネゴシエートされません。 最高のユーザー エクスペリエンスを提供するファイアウォールを開放するには、TCP と UDP の両方が必要です。

ステートフルの性質のためは、TCP は、リアルタイム メディアに適していないし、マイクロソフトのチームのフェイル バックのネットワーク トランスポートとしてのみ提供されています。 Tcp の場合、パケットの遅延や損失がある場合、パケット必要があります再送信されるまで、それらを確認しています。 これにより、メディア パケットが現在のメディア パケットのタイムリーな配信と競争する必要がなくなります。 ユーザーのチームのクライアントでは、オーディオをストレッチしようとして、ネットワークの状態により音のアーティファクトを生成することができます。 TCP のオーバーヘッドを一般に許容可能な経験はユーザー エクスペリエンスの低下にシフトことができます。 このため、UDP の状態のネットワーク トランスポートが必要です。

マイクロソフト チームのファイアウォールを実行するための完全ガイドは、 [Office 365 の Url と IP アドレスの範囲](https://aka.ms/o365ips)の記事で提供されます。

ファイアウォールが開かれた後は、クラウドのボイス機能の接続性を検証するために[Microsoft ネットワーク評価ツール](https://www.microsoft.com/en-us/download/details.aspx?id=53885)を使用できます。

> [!IMPORTANT]
> Microsoft Office 365 の ip アドレスや Url は、時間の経過と共に変更されます。 サービス管理の計画の一環として、することが重要業務プロセスが存在し、グループ[Office 365 の Url と IP アドレスの範囲](https://aka.ms/o365ips)を監視し、それに応じて更新プログラムを確認する責任を負うことを確認します。

#### <a name="local-internet-egress"></a>ローカルのインターネットの出口

多くのネットワークは、ハブを使用して、スポークのトポロジを設計されました。 このトポロジでは、インターネット トラフィック通常走査 WAN 中央データ センターにインターネットに現れた (組み入れる) 前にします。 全体的なコストの削減を目標として、ネットワーク セキュリティ デバイスを集中管理するこれは、多くの場合です。

WAN 経由のトラフィックの背面の運搬は、遅延時間を増加し、品質とユーザー エクスペリエンスに悪影響を与えるには。 マイクロソフト チームは、Microsoft の大規模なグローバル ・ ネットワーク上で稼働するために多くの場合ネットワーク ピアリングの場所、ユーザーの近くに ユーザーができるだけ早くその場所に近いと、音声用に最適化されたネットワークにローカルのインターネット ポイントから egressing でパフォーマンスを向上させる可能性があります表示されます。 一部のワークロードでは、DNS 要求を使用して、トラフィックの送受信をフロント エンド サーバーに最も近い。 このような場合、ローカル出口ポイントを使用する場合はローカルの DNS 解決とペアリングされてが重要です。

マイクロソフトのグローバル ・ ネットワークへのネットワーク パスを最適化すると、パフォーマンスが向上し、最終的に最高のエクスペリエンスをユーザーに提供されます。 詳細については、[最適な接続および Office 365 のパフォーマンス](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694)を投稿するブログを参照してください。

#### <a name="vpn"></a>VPN

Vpn は、多くの組織に貴重なサービスを提供します。 残念ながら、通常ないよう設計されています。 またはされるリアルタイムのメディアをサポートするように構成します。 いくつかの Vpn にも UDP をサポートされて可能性があります。 Vpn は、トラフィックの暗号化済みのメディア上の暗号化の追加の層も紹介します。 さらに、マイクロソフトのチーム サービスへの接続は、VPN デバイス経由のトラフィックの髪の毛の固定のための効率的なできない場合があります。 さらには想定していない容量の観点からチームを必要とする予想される負荷に対応するため。

チームのトラフィックを VPN を回避する代替パスを提供することをお勧めします。 これは通常、分割トンネル VPN として呼ばれます。 スプリット トンネリングを意味 Office 365 用には、そのトラフィックは VPN を通過しないですが、Office 365 に直接送られます。 この変更は品質に良い影響を与えるがも VPN デバイスと組織のネットワークの負荷の軽減の第 2 の利点を提供します。

スプリット トンネルを実装するには、VPN のベンダーの構成の詳細を参照してください。

#### <a name="wi-fi"></a>Wi-fi

VPN と同様、Wi-fi ネットワークは設計やリアルタイム メディアをサポートするように構成しないとは限りません。 計画、および最適化する、チームをサポートするために Wi-fi ネットワークは、品質の展開の重要な考慮事項です。

Wi-fi ネットワークを最適化するために用意されているいくつかの要因があります。

-   メディア トラフィックをすることを確認するには、QoS または Wi-fi マルチ メディア (WMM) の実装を取得する優先度は、それに応じて Wi-fi ネットワークを経由します。

-   計画と W Fi のバンドとアクセスを最適化する位置をポイントします。 2.4 GHz の範囲は、アクセス ポイントの配置によって、十分な経験を提供可能性がありますが、アクセス ポイントの範囲で動作するその他の消費者向けデバイス影響を受けることがよくあります。 5 GHz の範囲はより高密度の範囲のため、リアルタイム メディアに適していますが、十分なカバレッジを取得するより多くのアクセス ポイントが必要です。 エンドポイントは、その範囲をサポートし、それに応じてそれらの帯域を活用するように構成する必要があります。

-   デュアル バンド Wi-fi ネットワークを展開している場合は、バンドのステアリングを実装することを検討してください。 バンドのステアリングは、5 Ghz の範囲を使用するデュアル バンドのクライアントに影響を及ぼす Wi-fi ベンダーによって実装されている手法です。

-   チャネル重複 – 同じチャネルのアクセス ポイントが近すぎる信号の重なりが発生し、意図せず競合しているユーザーの不正な操作の結果として、ときにします。 互いに連続してアクセス ポイントがチャンネルが重複しないよりも上にあることを確認します。

各ワイヤレス ベンダーでは、独自のワイヤレス ソリューションを展開するための推奨事項があります。 特定のガイダンスについては、仕入先を相談することをお勧めします。

### <a name="network-readiness-assessment"></a>ネットワークの準備状況の評価

ネットワークの準備活動の一部には、ネットワークの評価が含まれています。 計画と構成が完了したら後、評価するのに役立つオンボードのユーザーの前に、ネットワークの品質の基準の理解マイクロソフトのチームに。 評価の結果も、識別し、チームのユーザーを有効にする前に修復作業を優先順位を設定できます。

ワイヤード (有線) の両方に、ネットワークの評価を実行する必要があり、すべての建物の可能な Wi-fi ネットワークがチームでのボイス機能をクラウドします。

ネットワークの評価は、マイクロソフトのパートナー、サード ・ パーティ製のツールまたは[Microsoft ネットワーク評価ツール](https://www.microsoft.com/en-us/download/details.aspx?id=53885)を使用して実行できます。 私たちも詳細に説明して準備ガイダンスの一部として Microsoft ネットワーク評価ツールを使用して評価を実行する方法について[ここでは](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_3_0_2,4_3_0_3,4_3_0_5,4_3_0_6,4_3_0_7,4_3_0_8,4_3_0_10,4_3_0_11).

## <a name="plan-for-endpoint-quality"></a>エンドポイントの品質管理の計画

次の図からわかるように、エンドポイントは、エンド ・ ユーザーに対して、高品質なエクスペリエンスを提供することの重要な基盤です。

![品質、およびサービスの管理がすべての 3 つのコンポーネントに重なっている 3 つのコンポーネントを説明する図。 端点に重点を置いた。](media/envision-planning-for-service-management-and-quality-complete-guide-image5.png)

マイクロソフトのチームの端点は、Pc、Mac、タブレット、およびモバイル デバイスを含め、多くのデバイスで実行できます。 経験の一部を含むだけでなく、そのデバイスは、ユーザーがデバイスに接続する方法などのデバイスの内蔵マイクとスピーカー、イヤー ・ バッド、または、最適化されたヘッドセットを使用します。 最適化されたヘッドセットを使用すると、全体的なユーザー エクスペリエンスを追加できます。

エンドポイントの計画では、次のガイダンスを使用すると、組織の正常な契約時のチームが発生することを確認できます。

### <a name="endpoint-capability"></a>エンドポイントの機能

計画の最初の部分は、すべての Pc を確認して、組織内の他のデバイスは、マイクロソフトのチームを実行できます。 これは、ハードウェアの要件を見るだけでなくが、他の PC が何をバック グラウンドでの理解も含まれます。 多くの組織では、侵入検知システムやデバイスの基本のパフォーマンスに影響を与えるウイルス対策ソフトウェアなど、他のソフトウェアを実行します。

マイクロソフトのチームでは、使用可能なクライアントの web、デスクトップ (Windows および Mac) とモバイル (Android、iOS、および Windows Mobile) があります。 各プラットフォームのソフトウェア要件については、[マイクロソフトのチームのクライアントを取得する](https://docs.microsoft.com/microsoftteams/get-clients)を参照してください。

### <a name="endpoint-firewalls"></a>エンドポイントのファイアウォール

クライアント側のファイアウォールでは、ユーザーの操作性に大きな影響を与えるをことができます。 クライアント側のファイアウォールは、呼び出しを確立することを防ぐだけでなく、通話の音質に影響を与えます。 [Office 365 の Url と IP アドレスの範囲](https://aka.ms/o365ips)内の情報に基づいて、クライアント ファイアウォールで適切な除外を構成します。 サード パーティ ベンダーは、除外リストを作成する方法の具体的なガイダンスがあります。

> [!NOTE]
> マイクロソフト チームは、適切なファイアウォール構成で Windows ファイアウォールを自動的に更新されます。

### <a name="wi-fi-recommendations-for-endpoints"></a>エンドポイントの Wi-fi の推奨事項

マイクロソフトのチームでリアルタイムの作業負荷をサポートするために最適化された Wi-fi ネットワークの展開の計画とは、計画の重要な必要があります。 次のセクションでは、端点を計画するときにいくつかの一般的な落とし穴を避けるために役立ついくつかの一般的なガイダンスを提供します。

#### <a name="wi-fi-drivers"></a>Wi-fi ドライバー

Wi-fi ドライバーによっては、問題が発生する可能性があります。 例として、ドライバーは、品質の低下の呼び出しの原因と、アクセス ポイント間で非常に積極的な移動の動作があります。 これは、一般的なものではありませんが、PC の Wi-fi ドライバーが更新され、展開する前にテストすることを確認することが重要です。

#### <a name="wi-fi-bands"></a>Wi-fi バンド

Wi-fi 機器は現在、2.4 GHz および 5.0 GHz で使用されているバンドの主に 2 種類あります。 組織では、両方のバンドを提供する場合は、5.0 GHz バンドを使用するのには、ドライバーの設定を構成してください。 このバンドはスループットの点ではるかに高密度と、2.4 GHz 帯域内で発生する障害で影響を受ける小さい。 この推奨事項では、5.0 GHz のネットワーク帯域を正しく最適化したことを前提としています。

#### <a name="wi-fi-radio-type"></a>Wi-fi 無線タイプ

新しい Wi-fi 無線の種類をサポートしているデバイスを計画します。 802.11ac を活用する場合は、Wi-fi の非常に優れたパフォーマンスを取得できます以降にアップデートを提供するデバイスです。

#### <a name="wireless-avoidance"></a>ワイヤレスの回避

組織によっては、Wi-fi を完全に回避する場合します。 場合がありますこのガイドはユーザーがワイヤード (有線) ネットワークに直接接続するには推奨事項を用意されています。 場合によっては、ネットワークのバインド順序可能性があります優先ワイヤレス接続されているコンティニュ ワイヤード (有線) 接続する PC が接続されている場合でも、その接続を使用します。 この予期しない動作を避けるためには、このシナリオを回避するのにはバインドの順序を構成します。

#### <a name="80211-power-save-protocol"></a>802.11 省電力プロトコル

組織は、ワイヤレス アクセス ポイントを使用している、または 802.11 の電源をサポートしないルーター プロトコルの保存、通話の中断や Windows のデバイスで実行されているマイクロソフトのチームでの不適切な呼び出し品質が発生する可能性があります。 ワイヤレス アクセス ポイントまたはルーターをアップグレードしない場合は、バッテリ電源で実行されているデバイス上の Windows の電源プランの設定を更新する必要があります。 次の[資料をサポート](https://support.microsoft.com/help/928152/you-may-experience-connectivity-issues-or-performance-issues-when-you)することでさらに詳細と構成のガイダンスが提供されます。

### <a name="devices-for-teams"></a>チーム用のデバイス

マイクロソフト チームは、会議や電話システムとして使用できます。 これらの機能を使用して、チームのために使用されるインタ フェース デバイスは、ユーザー エクスペリエンスの重要な役割を果たします。

組み込み PC スピーカーとマイクを使用しては、その構成を持っているユーザーに受け入れ可能な場合がありますサウンドです。 ですが、通常これらのデバイスは、ノイズの除去用に最適化されたし、周囲のノイズの任意の種類、ダウン ストリームに影響を与え他のユーザーの呼び出しにします。 これらのシナリオ用に最適化されたデバイスを活用することと、質の高い環境を実現するのに役立ちます。

各デバイスは、ユーザーのニーズを満たす必要があります。 別のペルソナのヘッドセットなどのデバイスを調整し、組織内のユース ケースにする必要があります。 ペルソナとデバイスのマッピングの手順は、計画プロセスの一部として完了する必要があります。

デバイスを選択したら、それらを最終的な検証のためのパイロット テスト計画に含まれます。 試験運用で、デバイスの戦略を確実にフィードバックを収集するアンケートを活用して、最適です。

この時点でビジネス認定プログラムは、Skype で認定されているオーディオ デバイスの使用をお勧めします。 このプログラムによって認定デバイスを検索するには、[ビジネスの Skype の USB デバイスの認定](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs)ソリューション カタログを参照してください。

詳細については、「[クライアントとデバイスの準備ワーク ショップ](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_1_0_13)の使用」を参照していますください。

## <a name="client-updates"></a>クライアント用更新プログラム

マイクロソフトのチームの主な利点の 1 つは、あるクライアントが保つように自動的に。 PC と Mac 上のクライアントは、新しいビルドをチェックし、アプリケーションがアイドル状態のときに、新しいクライアントをダウンロードするバック グラウンド プロセスを使用して更新されます。 クライアントのダウンロード サイズは、約 100 MB です。

組織は、任意のコントロールまたは更新プロセスを管理するポリシー設定へのアクセスにすることはありません。 新しいビルドで発見することがある問題のリスクを軽減するには、エンドポイントの最後の既知の正常なバージョンが保持されます。 新しいビルドに問題がある場合マイクロソフト チーム サービスは以前のバージョンにエンドポイントを自動的に戻すことができます。

## <a name="next-steps-and-references"></a>次の手順を実行および参照

このテーブルには、関連するコンテンツへのリンクを持つ計画の活動の概要が含まれています。

| エリア | 詳細 | 参照 |
|-----------------------------|----------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Plan for service management | Conduct an operational role mapping exercise <br/> Signoff from accountable teams <br/> Role readiness | [運用ガイド](https://docs.microsoft.com/MicrosoftTeams/1-drive-value-operate-my-service) |
| | 品質の Champion(s) を指名します。 <br/> 品質の精鋭の準備| [救難を学習します。](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Academy?SOFTrainings=Leverage%20the%20Investigate%20Media%20Quality%20using%20CQD%20Videos) <br/> [品質体験レビュー ガイド](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/quality-of-experience-review-guide.docx?raw=true) |
| | エクスペリエンスの品質レビュー テンプレートをインストールします。 <br/> 構築ファイルをアップロードします。 | [QERLite templates](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/quality-of-experience-review-lite-templates-v-1-2.zip?raw=true) <br/> [アップロードの構築について](https://docs.microsoft.com/en-us/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard?ui=en-US&rs=en-US&ad=US#upload-building-information)|
| ネットワークの品質管理の計画 | ネットワークの計画を実行します。 | [ネットワーク プランナー](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner) |
| | QoS を実装します。 | [マイクロソフトのチームでのサービスの品質](https://docs.microsoft.com/MicrosoftTeams/qos-in-teams) |
| | プロキシ サーバーを使用しません。 | [プロキシのガイダンス](https://support.office.com/article/Managing-Office-365-endpoints-99cab9d4-ef59-4207-9f2b-3728eb46bf9a?ad=US#ID0EABAAA=2._Proxies&ID0EAEAAA=2._Proxies) |
| | スプリット トンネルの VPN を実装します。 | [VPN のスプリット トンネルのガイダンス](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_9) |
| | リアルタイム メディアの Wi-fi ネットワークを最適化します。  | サード パーティ ベンダーを参照してください。 |
| | ローカルのインターネットの出口を実装します。 | [ローカルのインターネットの出口](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694) |
| | ネットワーク接続を実装します。 <br/> ネットワーク接続を検証します。 | [Office 365 URLs and IP addresses](https://aka.ms/o365ips) |
| | | [Network Assessment Tool](https://www.microsoft.com/en-us/download/details.aspx?id=53885) |
| | Perform network assessment | [ネットワーク対応の評価](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_3_0_2,4_3_0_3,4_3_0_5,4_3_0_6,4_3_0_7,4_3_0_8,4_3_0_10,4_3_0_11) |
| エンドポイントの品質管理の計画 | Update endpoint firewalls | [Office 365 URLs and IP addresses](https://aka.ms/o365ips) |
| | Validate software requirements | [Get Clients for Microsoft Teams](https://docs.microsoft.com/microsoftteams/get-clients) |
| | Implement endpoint Wi-Fi recommendations | Consult 3rd Party Vendors |
| | デバイスをマッピングするようにペルソナを実施します。 <br/> デバイスをプロビジョニングし、パイロットに | [クライアントとデバイスの準備ワーク ショップ](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_1_0_13) <br/> [デバイス カタログ](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs) |