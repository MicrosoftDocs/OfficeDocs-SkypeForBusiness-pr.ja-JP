---
title: Teams 用に組織のネットワークを準備する
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: jastark, kojika
audience: admin
description: ネットワーク要件、ネットワーク最適化、帯域幅要件など、Microsoft Teams 用に組織のネットワークを準備する方法について説明します。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365initiative-deployteams
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom:
- seo-marvel-mar2020
ms.openlocfilehash: 1c84a753146899011fa34be56e0746cc0c600b31
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117755"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a>Microsoft Teams 用に組織のネットワークを準備する 

## <a name="network-requirements"></a>ネットワーク要件

既に[ネットワークを Microsoft 365 または Office 365 用に最適化](/Office365/Enterprise/assessing-network-connectivity)している場合は、Microsoft Teams の準備ができている可能性があります。 いずれの場合でも、特に **リモート ワーカー** をサポートする最初の Microsoft 365 または Office 365 ワークロードとして Teams を迅速に展開する場合は、Teams の展開を開始する前に次のことを確認してください。

1.  (Microsoft 365 または Office 365 に接続できるように) すべての場所にインターネット アクセスがありますか? 少なくとも、通常の Web トラフィックに加えて、すべての場所で、Teams のメディア用に以下を開いていることを確認してください。

    |  |  |
    |---------|---------|
    |ポート     |UDP ポート <strong>3478</strong> から <strong>3481</strong>        |
    |[IP アドレス](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) |<strong>13.107.64.0/18</strong>、<strong>52.112.0.0/14</strong>、および <strong>52.120.0.0/14</strong>         |

    > [!IMPORTANT]
    > オンプレミスまたはオンラインのいずれかで Skype for Business と連携する必要がある場合は、いくつかの追加の DNS レコードを構成する必要があります。
    >
    >|CNAME レコード / ホスト名  |TTL  |ポイント先のアドレスまたは値  |
    >|---------|---------|---------|
    >|sip     |    3600     |    sipdir.online.lync.com     |
    >|lyncdiscover     |   3600      |    webdir.online.lync.com     |
    
2.  Microsoft 365 または Office 365 の検証済みドメイン (たとえば、contoso.com) はありますか?
    
    - 組織が Microsoft 365 または Office 365 を展開していない場合は、「[概要](/microsoft-365/admin/admin-overview/get-started-with-office-365)」を参照してください。
    - 組織が Microsoft 365 または Office 365 の検証済みドメインを追加または構成していない場合は、「[ドメインに関する FAQ](/microsoft-365/admin/setup/domains-faq)」を参照してください。

3.  組織は Exchange Online と SharePoint Online を展開していますか?
    
    - 組織で Exchange Online が導入されていない場合は、「[Exchange と Microsoft Teams の連携](exchange-teams-interact.md)」をご覧ください。
    - 組織で SharePoint Online が導入されていない場合は、「[Microsoft Teams との SharePoint Online と OneDrive for Business の連携](sharepoint-onedrive-interact.md)」をご覧ください。

これらのネットワーク要件を満たしていることを確認したら、[Teams を展開する](./deploy-overview.md)準備ができている可能性があります。 大規模な多国籍企業の場合、またはネットワークに制限があることがわかっている場合は、Teams 用にネットワークを評価し最適化する方法をご確認ください。

> [!IMPORTANT]
> **教育機関の場合**: 組織が教育機関であり、学生情報システム (SIS) を使用している場合は、Teams を展開する前に [学校データ同期を展開](/schooldatasync/)します。
>  
> **オンプレミスの Skypefor Business Server の実行**: 組織でオンプレミスの Skype for Business Server (または Lync Server) を実行している場合、オンプレミスのディレクトリと Microsoft 365 または Office 365 を同期するよう [Azure AD Connect を構成](/skypeforbusiness/hybrid/configure-azure-ad-connect)する必要があります。

### <a name="best-practice-monitor-your-network-using-cqd-and-call-analytics"></a>ベスト プラクティス: CQD と通話分析を使用してネットワークを監視する 

[通話品質ダッシュボード (CQD)](turning-on-and-using-call-quality-dashboard.md) を使用して、Teams 内の通話と会議の品質に関する分析情報を取得します。 CQD は、品質、信頼性、およびユーザー エクスペリエンスを注意深く監視して、ネットワークを最適化するのに役立ちます。 CQD は、全体的なパターンが明らかになる可能性のある組織全体の集約テレメトリを調べます。これにより、問題を特定し、修復を計画できます。 さらに、CQD は、全体的な品質、信頼性、およびユーザー エクスペリエンスに関する分析情報を提供する豊富なメトリックス レポートを提供します。 

[通話分析](set-up-call-analytics.md)を使用して、個々のユーザーの通話と会議の問題を調査します。

## <a name="network-optimization"></a>ネットワークの最適化

特に、中小企業で、Microsoft 365 または Office 365 を既に展開している場合などは、次のタスクはオプションであり、Teams の展開に必要ありません。 ネットワークに制限があることがわかっている場合など、ネットワークと Teams のパフォーマンスを最適化するのに、このガイダンスを使用してください。

次の場合は、追加のネットワーク最適化を行うことをお勧めします。

  - Teams の実行速度が遅い (帯域幅が不足している可能性があります)
  - 通話が途切れ続ける (ファイアウォールまたはプロキシ ブロッカーが原因である可能性があります)
  - 通話が静的で途切れている、または音声がロボットのように聞こえる (ジッターまたはパケット損失の可能性があります)

ネットワーク障害を特定して修正するためのガイダンスを含む、ネットワーク最適化の詳細については、「[Microsoft 365 および Office 365 ネットワーク接続の原則](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)」をご確認ください。

<table>
<thead>
<tr class="header">
<th><strong>ネットワーク最適化のタスク</strong></th>
<th><strong>詳細</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>ネットワーク プランナー</td>
<td><p>組織の物理的な場所全体の帯域幅の計算やネットワーク要件など、ネットワークの評価については、<a href="https://admin.teams.microsoft.com">Teams 管理センター</a>の <a href="/microsoftteams/network-planner">ネットワーク プランナー</a> ツールを確認してください。 ネットワークの詳細と Teams の使用状況を提示すると、Network Planner は、組織の物理的な場所で Teams とクラウドの音声を展開するためのネットワーク要件を計算します。</p>
<p>シナリオの例については、「<a href="/microsoftteams/tutorial-network-planner-example">ネットワーク プランナーの使用 - シナリオの例</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td>Teams のアドバイザー</td>
<td><a href="/microsoftteams/use-advisor-teams-roll-out">Teams のアドバイザー</a>は、<a href="https://admin.teams.microsoft.com">Teams 管理センター</a>の一部です。 Microsoft 365 または Office 365 の環境を評価し、Teams を正常に展開する前に更新または変更する必要がある最も一般的な構成を特定します。</td>
</tr>
<tr class="odd">
<td>外部の名前解決</td>
<td>Teams クライアントを実行するすべてのコンピュータが外部 DNS クエリを解決して、Microsoft 365 または Office 365 によって提供されるサービスを検出できること、およびファイアウォールが接続を妨げていないことを確認してください。 ファイアウォールのポートの構成については、「<a href="/microsoftteams/office-365-urls-ip-address-ranges">Microsoft 365 および Office 365 の URL と IP 範囲</a>」をご覧ください。</td>
</tr>
<tr class="odd">
<td>セッションの永続性を維持する</td>
<td>ファイアウォールが、UDP のマップされたネットワーク アドレス変換 (NAT) アドレスまたはポートを変更しないことを確認してください。</td>
</tr><tr class="odd">
<td>NAT プール サイズの検証</td>
<td>ユーザー接続に必要なネットワーク アドレス変換 (NAT) プール サイズを検証します。 複数のユーザーまたはデバイスが<a href="/office365/enterprise/nat-support-with-office-365">ネットワーク アドレス変換 (NAT) またはポート アドレス変換 (PAT)</a> を使用して Microsoft 365 または Office 365 にアクセスする場合は、パブリック ルーティングに対応している各 IP アドレスの背後にあるデバイスが、サポートされる数値を超過していないことを確認する必要があります。 適切なパブリック IP アドレスを NAT プールに割り当ててポート枯渇を回避します。 ポート枯渇は、内部ユーザーとデバイスが Microsoft 365 または Office 365 サービスに接続できない原因になります。</td>
</tr>
<tr class="even">
<td>Microsoft データ センターへのルーティング</td>
<td><a href="/office365/enterprise/client-connectivity">Microsoft データ センターへの最も効率的なルーティングを実装します</a>。 ローカルまたは地域の出力ポイントを使用して、Microsoft ネットワークにできるだけ効率的に接続できる場所を特定します。</td>
</tr>
<tr class="odd">
<td>侵入検知/防御のガイダンス</td>
<td>送信接続の追加のセキュリティ レイヤーとして環境に<a href="/azure/network-watcher/network-watcher-intrusion-detection-open-source-tools">侵入検知</a>/防御システム (IDS/IPS) が配備されている場合は、すべての Microsoft 365 または Office 365 の URL を許可していることを確認してください。</td>
</tr>
<tr class="even">
<td>スプリット トンネル VPN の構成</td>
<td><p>一般に<a href="/windows/security/identity-protection/vpn/vpn-routing">スプリット トンネル VPN</a> と呼ばれる、仮想プライベート ネットワーク (VPN) をバイパスする Teams トラフィックの代替パスを提供することをお勧めします。 スプリット トンネリングとは、Microsoft 365 または Office 365 のトラフィックが VPN を通過せず、代わりに Microsoft 365 または Office 365 に直接送信されることを意味します。 VPN をバイパスすると、Teams の品質にプラスの影響があり、VPN デバイスと組織のネットワークからの負荷が軽減されます。 スプリット トンネル VPN を実装するには、VPN ベンダーにご相談ください。</p>
<p>VPN をバイパスすることをお勧めするその他の理由:
<ul>
<li><p>VPN は通常、リアルタイム メディアをサポートするように設計または構成されていません。</p></li> 
<li><p>一部の VPN は、UDP (Teams に必要) をサポートしていない場合もあります。</p></li> 
<li><p>また VPN は、既に暗号化されているメディア トラフィックの上に、暗号化の追加レイヤーを導入することもあります。</p></li> 
<li><p>VPN デバイスを介したヘアピン型トラフィックが原因で、Teams への接続が効率的ではない可能性があります。</p></li></td>
</tr>
<tr class="odd">
<td>QoS の実装</td>
<td><a href="/microsoftteams/qos-in-teams">サービスの品質 (QoS) を使用</a>して、パケットの優先度設定を構成します。 これにより、Teams の通話品質が向上し、通話品質の監視とトラブルシューティングに役立ちます。 QoS は、管理対象ネットワークのすべてのセグメントで実装される必要があります。 ネットワークに帯域幅が適切にプロビジョニングされているときでも、QoS は、予期しないネットワーク イベントが発生した場合のリスクを軽減します。 QoS では、音声トラフィックが優先されるため、想定外のイベントが発生しても品質に悪影響を与えません。</td>
</tr>
<tr class="even">
<td>Wi-Fi を最適化する</td>
<td><p>VPN と同様に、Wi-Fi ネットワークは必ずしもリアルタイム メディアをサポートするように設計または構成されているわけではありません。 Teams をサポートするために Wi-Fi ネットワークのための計画を立てたり、最適化を行うことは、高品質の展開を実現するための重要な考慮事項です。 計画では、次の要因を考慮します。</p>
<ul>
<li><p>Wi-Fi ネットワーク上でメディア トラフィックが適切に優先されるように QoS または Wi-Fi マルチメディア (WMM) を実装します。</p></li>
<li><p>W-Fi バンドとアクセス ポイントの配置を計画し最適化します。 アクセス ポイントの配置に応じて、2.4 GHz 帯で十分なエクスペリエンスが提供される可能性がありますが、アクセス ポイントは、多くの場合にその帯域で動作するその他のコンシューマー デバイスによって影響を受けます。 5 GHz 帯は、その密度により、リアルタイム メディアにより適していますが、十分なカバレッジを得るためにより多くのアクセス ポイントを必要とします。 エンドポイントも、その帯をサポートしており、それらの帯を利用できるように構成されている必要があります。</p></li>
<li><p>デュアル バンドの Wi-Fi ネットワークを使用している場合は、バンド ステアリングの実装を検討してください。 <em>バンド ステアリング</em>は Wi-Fi ベンダーによって実装された技術で、デュアル バンド クライアントが 5 GHz 帯を使用するように仕向けます。</p></li>
<li><p>同じチャネルのアクセス ポイントがお互いに近すぎる場合、信号のオーバーラップや意図しない競合が発生して、ユーザーのエクスペリエンスが低下する可能性があります。 お互いに隣り合っているアクセス ポイントが、オーバーラップしていないチャネル上にあることを確認します。</p></li>
</ul>
<p>各無線ベンダーは、その無線ソリューションを展開する場合の推奨事項をそれぞれ持っています。 具体的なガイダンスについては、Wi-Fi ベンダーにご相談ください。</p></td>
</tr>
</tbody>
</table>

## <a name="bandwidth-requirements"></a>帯域幅要件

Teams は、ネットワークの状態に関係なく、最高のオーディオ、ビデオ、およびコンテンツ共有エクスペリエンスを提供するように設計されています。 とはいえ、帯域幅が不十分な場合、Teams はビデオ品質よりもオーディオ品質を優先します。

帯域幅が制限されて *いない* 場合、Teams は、最大 1080p のビデオ解像度、最大 30fps のビデオと 15fps のコンテンツ、およびハイファイ オーディオなど、メディア品質を最適化します。 

[!INCLUDE [bandwidth-requirements](includes/bandwidth-requirements.md)]


## <a name="related-topics"></a>関連トピック

[Microsoft 365 および Office 365 ネットワーク接続の原則](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)

[世界のエンドポイント: Skype for Business Online および Teams ](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

[Teams 向けのプロキシ サーバー](proxy-servers-for-skype-for-business-online.md)

[Teams 内のメディア: 会議がシンプルな理由](https://aka.ms/teams-media)

[Teams 内のメディア: メディア フローを深く掘り下げる](https://aka.ms/teams-media-flows)

[Teams での ID モデルと認証](identify-models-authentication.md)

[Teams の展開方法](./deploy-overview.md)

[Teams のトラブルシューティング](/MicrosoftTeams/troubleshoot/teams)