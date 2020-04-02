---
title: Microsoft Teams 用に組織のネットワークを準備する
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: jastark, kojika
audience: admin
description: Microsoft Teams を展開する前に、チームの準備ができていることを確認するために、ネットワークの評価と準備を行います。 情報には、ネットワーク要件、帯域幅要件、ネットワーク最適化ガイダンスが含まれています。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 64bcdee7e1a4ce7f36a9089fd5231cf2a63e9d5b
ms.sourcegitcommit: f0f2fa999c1ca4a1118377c7938a247f79217609
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2020
ms.locfileid: "43109465"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a>Microsoft Teams 用に組織のネットワークを準備する 

## <a name="network-requirements"></a>ネットワーク要件

[Office 365 用にネットワークの最適化](https://docs.microsoft.com/Office365/Enterprise/assessing-network-connectivity)を既に行っている場合は、Microsoft Teams の準備ができている可能性があります。 いずれの場合も、**リモートワーカー**をサポートするために、最初の Office 365 ワークロードとして teams をすばやくロールアウトする場合は、チームのロールアウトを開始する前に次のことを確認してください。

1.  すべての場所でインターネットにアクセスできますか (Office 365 に接続できるようにします)。 少なくとも、通常の web トラフィックに加えて、Teams のメディアについては、すべての場所で次のように開いていることを確認してください。

    |  |  |
    |---------|---------|
    |ポート     |UDP ポート<strong>3478</strong> ~ <strong>3481</strong>        |
    |[IP アドレス](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) |<strong>13.107.64.0/18</strong>、 <strong>52.112.0.0/14</strong>、 <strong>52.120.0.0/14</strong>         |

    
2.  Office 365 の確認済みドメイン (たとえば、contoso.com) があるか。
    
      - 組織が Office 365 を展開していない場合は、「一般[法人向け office 365](https://docs.microsoft.com/office365/admin/admin-overview/get-started-with-office-365)の概要」を参照してください。
      - 組織で Office 365 の確認済みドメインを追加または構成していない場合は、「 [office 365 ドメインを確認](https://docs.microsoft.com/office365/admin/setup/domains-faq)する」を参照してください。

3.  組織が Exchange Online と SharePoint Online を展開していますか?
    
      - 組織に Exchange Online がインストールされていない場合は、「 [exchange と Microsoft Teams の相互作用](exchange-teams-interact.md)」を参照してください。
      - 組織に SharePoint Online がインストールされていない場合は、「 [Sharepoint online と OneDrive For business が Microsoft Teams とどのように連携するかについ](sharepoint-onedrive-interact.md)て」を参照してください。

これらのネットワーク要件を満たしていることを確認したら、チームを[ロールアウト](How-to-roll-out-teams.md)することができます。 大企業向けの企業の場合、またはネットワークの制限事項があることがわかっている場合は、「チームのネットワークを評価して最適化する方法」をご覧ください。

> [!IMPORTANT]
> **教育機関向けの**場合: 組織が教育機関であり、学生情報システム (SIS) を使用している場合は、チームをロールアウトする前に[School Data Sync を展開](https://docs.microsoft.com/schooldatasync/)してください。
>  
> **オンプレミスの skype For Business server を実行**している場合: 組織がオンプレミスの Skype For business server (または Lync server) を実行している場合、オンプレミスのディレクトリを Office 365 と同期するように[Azure AD Connect を構成](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-azure-ad-connect)する必要があります。

### <a name="best-practice-monitor-your-network-using-cqd-and-call-analytics"></a>ベストプラクティス: CQD と通話分析を使用してネットワークを監視する 

[通話品質ダッシュボード (CQD)](turning-on-and-using-call-quality-dashboard.md)を使用して、Teams での通話と会議の品質を把握します。 CQD は、品質、信頼性、ユーザーエクスペリエンスを常に把握して、ネットワークを最適化するのに役立ちます。 CQD は、全体的なパターンが明らかになる組織全体の集計テレメトリを確認します。これにより、問題を特定し、修復を計画することができます。 さらに、CQD には、品質、信頼性、ユーザーエクスペリエンス全体を把握するための、豊富な指標レポートが用意されています。 

個々のユーザーの通話と会議の問題を調査するには、[通話分析](set-up-call-analytics.md)を使用します。

## <a name="network-optimization"></a>ネットワーク最適化

次のタスクはオプションであり、チームをロールアウトする場合は必須ではありません。特に、小規模なビジネスで、Office 365 を既に展開している場合は、その必要はありません。 このガイダンスを使用して、ネットワークとチームのパフォーマンスを最適化します。また、ネットワークの制限事項があることがわかっている場合に使います。

次のような場合には、追加のネットワーク最適化を行うことができます。

  - チームの実行速度が遅い (帯域幅が十分でない可能性がある)
  - 通話が切断される (ファイアウォールまたはプロキシブロックが原因である可能性があります)
  - 通話には静的と途切れがあります。また、ロボットなどのボイスサウンド (ジッタまたはパケットロスの可能性があります)

ネットワークの障害を特定して修正するためのガイダンスなど、ネットワークの最適化の詳細については、「 [Office 365 のネットワーク接続の原則](https://aka.ms/pnc)」を参照してください。

<table>
<thead>
<tr class="header">
<th><strong>ネットワーク最適化タスク</strong></th>
<th><strong>詳細</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>ネットワークプランナー</td>
<td><p>組織の物理的な場所での帯域幅の計算やネットワーク要件など、ネットワークの評価について詳しくは、「 <a href="https://docs.microsoft.com/microsoftteams/network-planner">Network Planner</a> <a href="https://admin.teams.microsoft.com">ツール」をご覧ください。</a> ネットワークの詳細とチームの利用状況を入力すると、ネットワーク Planner によって、組織の物理的な場所でチームとクラウドボイスを展開するためのネットワーク要件が計算されます。</p>
<p>シナリオの例については、「<a href="https://docs.microsoft.com/microsoftteams/tutorial-network-planner-example">ネットワークプランナーの使用例のシナリオ</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td>チーム向けのアドバイザー</td>
<td><a href="https://docs.microsoft.com/microsoftteams/use-advisor-teams-roll-out">チームのアドバイザー</a>は<a href="https://admin.teams.microsoft.com">teams 管理センター</a>の一部です。 Office 365 環境を評価し、Teams を正常に展開する前に更新または変更する必要がある最も一般的な構成を特定します。</td>
</tr>
<tr class="odd">
<td>外部の名前解決</td>
<td>Teams クライアントを実行しているすべてのコンピューターで、Office 365 によって提供されるサービスを検出し、ファイアウォールによってアクセスが拒否されていないことを確認します。 ファイアウォールのポートを構成する方法については、「 <a href="https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges">Office 365 の URL と IP 範囲</a>」をご覧ください。</td>
</tr>
<tr class="odd">
<td>検証 (NAT) プールサイズ</td>
<td>ユーザー接続に必要なネットワークアドレス変換 (NAT) プールサイズを確認します。 複数のユーザーやデバイスが<a href="https://docs.microsoft.com/office365/enterprise/nat-support-with-office-365">ネットワークアドレス変換 (NAT) またはポートアドレス変換 (PAT)</a>を使って Office 365 にアクセスする場合、各パブリックルーティング可能な IP アドレスの背後に隠れているデバイスが、サポートされている番号を超えないようにする必要があります。 ポートの枯渇を防ぐため、適切なパブリック IP アドレスが NAT プールに割り当てられていることを確認します。 ポートの枯渇は、社内ユーザーと、Office 365 サービスに接続できないデバイスに寄与します。</td>
</tr>
<tr class="even">
<td>Microsoft データセンターへのルーティング</td>
<td><a href="https://docs.microsoft.com/office365/enterprise/client-connectivity">Microsoft データセンターへの最も効率的なルーティングを実装</a>します。 ローカルまたは地域の出口ポイントを使用して、可能な限り効率的に Microsoft ネットワークに接続できる場所を特定します。</td>
</tr>
<tr class="odd">
<td>侵入検知と予防のガイダンス</td>
<td>お客様の環境に、送信接続用のセキュリティレイヤーを追加するために展開された<a href="https://docs.microsoft.com/azure/network-watcher/network-watcher-intrusion-detection-open-source-tools">侵入検出</a>または防止システム (IDS/IPS) が展開されている場合は、すべての Office 365 url をホワイトリストしてください。</td>
</tr>
<tr class="even">
<td>分割トンネル VPN を構成する</td>
<td><p>一般に[分割トンネル VPN](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-routing)と呼ばれる仮想プライベートネットワーク (VPN) をバイパスするチームトラフィックの代替パスを指定することをお勧めします。 [トンネリングの分割とは、Office 365 のトラフィックが VPN 経由ではなく、直接 Office 365 に移動することを意味します。 VPN をバイパスすると、チームの品質にプラスの影響があり、VPN デバイスと組織のネットワークの負荷が軽減されます。 分離トンネル VPN を実装するには、VPN ベンダーと共同作業を行います。</p>
<p>VPN のバイパスが推奨されるその他の理由:
<ul>
<li><p>通常、Vpn は、リアルタイムメディアをサポートするように設計されていないか、構成されていません。</p></li> 
<li><p>一部の Vpn は、UDP をサポートしていない場合もあります (Teams に必要)。</p></li> 
<li><p>Vpn は、既に暗号化されているメディアトラフィックの上に、暗号化の追加レイヤーを導入することもあります。</p></li> 
<li><p>VPN デバイス経由でのヘアピンによるトラフィックにより、Teams への接続は効率的でない可能性があります。</p></li></td>
</tr>
<tr class="odd">
<td>QoS の実装</td>
<td><a href="https://docs.microsoft.com/microsoftteams/qos-in-teams">QoS (Quality Of Service) を使っ</a>てパケットの優先順位を設定します。 これにより、チームの通話品質が向上し、通話品質の監視とトラブルシューティングが容易になります。 QoS は、管理されたネットワークのすべてのセグメントに実装する必要があります。 ネットワークが帯域幅用に適切にプロビジョニングされている場合でも、予期しないネットワークイベントが発生した場合は、QoS によってリスクを軽減することができます。 QoS では、このような予期しないイベントが品質に悪影響を与えないように、ボイストラフィックの優先順位が付けられます。</td>
</tr>
<tr class="even">
<td>WiFi の最適化</td>
<td><p>VPN と同じように、WiFi ネットワークは、リアルタイムメディアをサポートするように設計されていないこともあります。 チームをサポートするための WiFi ネットワークを計画または最適化することは、高品質な展開を行うための重要な考慮事項です。 次のような要素を考慮してください。</p>
<ul>
<li><p>QoS または WiFi マルチメディア (WMM) を実装して、WiFi ネットワーク経由でメディアトラフィックの優先順位が適切に付けられるようにします。</p></li>
<li><p>WiFi バンドおよびアクセスポイントの配置を計画して最適化します。 アクセス ポイントの配置に応じて、2.4 GHz 帯で十分なエクスペリエンスが提供される可能性がありますが、アクセス ポイントは、多くの場合にその帯域で動作するその他のコンシューマー デバイスによって影響を受けます。 5 GHz の範囲は、高密度な範囲に基づくリアルタイムのメディアに適していますが、十分な範囲を確保するには、さらに多くのアクセスポイントが必要です。 エンドポイントも、その帯をサポートしており、それらの帯を利用できるように構成されている必要があります。</p></li>
<li><p>デュアルバンド WiFi ネットワークを使用している場合は、バンドステアリングの実装を検討してください。 <em>バンドステアリング</em>は、5 GHz のクライアントを使用するようにデュアルバンドクライアントに影響を与えるために、WiFi ベンダーによって実装された手法です。</p></li>
<li><p>同じチャネルのアクセスポイントが近すぎる場合は、信号の重複が発生し、意図せず競合する可能性があり、その結果、ユーザーにとって悪い操作が発生する可能性があります。 互いに隣接するアクセスポイントが重なっていないチャネル上にあることを確認します。</p></li>
</ul>
<p>各無線ベンダーは、その無線ソリューションを展開する場合の推奨事項をそれぞれ持っています。 具体的なガイダンスについては、WiFi ベンダーにお問い合わせください。</p></td>
</tr>
</tbody>
</table>

## <a name="bandwidth-requirements"></a>帯域幅要件

Teams は、ネットワークの状況に関係なく、最適なオーディオ、ビデオ、およびコンテンツ共有のエクスペリエンスを提供するために設計されています。 ただし、帯域幅が十分でない場合、チームはビデオ品質よりも音質の高い音質を優先します。

帯域幅が制限されて*いない*場合、チームは、最大1080p のビデオ解像度、ビデオ用および 15 fps 用の最大30fps、および高品質のオーディオを含むメディアの品質を最適化します。 

[!INCLUDE [bandwidth-requirements](includes/bandwidth-requirements.md)]


## <a name="related-topics"></a>関連項目

[Office 365 のネットワーク接続の原則](https://aka.ms/pnc)

[ワールドワイドエンドポイント: Skype for Business Online と Teams](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

[Teams のプロキシサーバー](proxy-servers-for-skype-for-business-online.md)

[Teams のメディア: 会議が簡単である理由](https://aka.ms/teams-media)

[Teams のメディア: メディアフローの詳細](https://aka.ms/teams-media-flows)

[Teams での ID モデルと認証](identify-models-authentication.md)

[Teams の展開方法](How-to-roll-out-teams.md)


