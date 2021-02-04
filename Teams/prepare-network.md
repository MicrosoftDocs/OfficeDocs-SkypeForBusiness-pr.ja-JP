---
title: Teams 用に組織のネットワークを準備する
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: jastark, kojika
audience: admin
description: ネットワーク要件、ネットワークの最適化、帯域幅要件など、組織のネットワークを Microsoft Teams 用に準備する方法について説明します。
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
ms.openlocfilehash: 9212c096323eb57754e0a8a47b61649bec42de87
ms.sourcegitcommit: 5c33ca450a3215b9bf3c5da8bb3c9ef1a715a1a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2021
ms.locfileid: "50099574"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a>Microsoft Teams 用に組織のネットワークを準備する 

## <a name="network-requirements"></a>ネットワーク要件

[Microsoft 365 または Office 365](https://docs.microsoft.com/Office365/Enterprise/assessing-network-connectivity)用にネットワークを既に最適化している場合は、Microsoft Teams の準備が整っている可能性があります。 いずれにしても、特に、リモート ワーカーをサポートするために最初の Microsoft 365 または Office 365 ワークロードとしてTeams をすばやく展開する場合は、Teams のロールアウトを開始する前に、次の点を確認してください。

1.  すべての場所にインターネットアクセス権がありますか (Microsoft 365 または Office 365 に接続できます)。 少なくとも、通常の Web トラフィックに加えて、Teams のメディアに対して、すべての場所に対して次の情報を開いている必要があります。

    |  |  |
    |---------|---------|
    |ポート     |UDP ポート <strong>3478</strong> ~ <strong>3481</strong>        |
    |[IP アドレス](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) |<strong>13.107.64.0/18、52.112.0.0/14、</strong><strong>および 52.120.0.0/14</strong> <strong></strong>         |

    > [!IMPORTANT]
    > Skype for Business (オンプレミスまたはオンライン) とフェデレーションする必要がある場合は、追加の DNS レコードを構成する必要があります。
    >
    >|CNAME レコード/ホスト名  |TTL  |ポイント先のアドレスまたは値  |
    >|---------|---------|---------|
    >|sip     |    3600     |    sipdir.online.lync.com     |
    >|lyncdiscover     |   3600      |    webdir.online.lync.com     |
    
2.  Microsoft 365 または Office 365 の確認済みドメイン (contoso.com など) がある場合
    
    - 組織で Microsoft 365 または Office 365 が展開されていない場合は、「使用を開始する」を [参照してください](https://docs.microsoft.com/microsoft-365/admin/admin-overview/get-started-with-office-365)。
    - 組織で Microsoft 365 または Office 365 の確認済みドメインが追加または構成されていない場合は、ドメインに関する FAQ を [参照してください](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)。

3.  組織で Exchange Online と SharePoint Online を展開していますか?
    
    - 組織に Exchange Online がインストールされていない場合は、「Exchange と Microsoft Teams のやり取り方法について理解する」を [参照してください](exchange-teams-interact.md)。
    - 組織に SharePoint Online がインストールされていない場合は [、「SharePoint Online](sharepoint-onedrive-interact.md)と OneDrive for Business が Microsoft Teams とやり取りする方法について理解する」を参照してください。

これらのネットワーク要件を満たしていることを確認したら、Teams を展開する準備 [が整う可能性があります](How-to-roll-out-teams.md)。 大規模な多国籍企業の場合、またはネットワークに制限がある場合は、Teams 用にネットワークを評価して最適化する方法について説明します。

> [!IMPORTANT]
> **教育機関の場合**: 組織が教育機関で学生情報システム (SIS) を使用している場合は [、Teams](https://docs.microsoft.com/schooldatasync/) を展開する前に School Data Sync を展開します。
>  
> オンプレミス **の Skype for Business Server** の実行: 組織でオンプレミスの Skype for Business Server (または Lync Server) を実行している場合は、オンプレミス ディレクトリを Microsoft 365 または Office 365 と同期するように Azure AD [Connect](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-azure-ad-connect)を構成する必要があります。

### <a name="best-practice-monitor-your-network-using-cqd-and-call-analytics"></a>ベスト プラクティス: CQD と通話分析を使用してネットワークを監視する 

通話品質 [ダッシュボード (CQD)](turning-on-and-using-call-quality-dashboard.md) を使用して、Teams での通話と会議の品質に関する洞察を得ることができます。 CQD は、品質、信頼性、ユーザー エクスペリエンスを常に把握することで、ネットワークの最適化に役立ちます。 CQD は、全体的なパターンが明らかになる可能性がある組織全体の集計テレメトリを調えます。これにより、問題を特定し、修復を計画することができます。 さらに、CQD には、全体的な品質、信頼性、ユーザー エクスペリエンスに関する洞察を提供する豊富なメトリック レポートが提供されます。 

通話分析を使用 [して、個々の](set-up-call-analytics.md) ユーザーの通話や会議の問題を調査します。

## <a name="network-optimization"></a>ネットワークの最適化

次のタスクはオプションであり、Teams を展開する場合は必須ではありません。特に小規模企業で、Microsoft 365 または Office 365 を展開している場合です。 このガイダンスを使用して、ネットワークと Teams のパフォーマンスを最適化するか、ネットワークに制限がある場合に使用します。

次の場合は、さらにネットワークの最適化を行う必要がある場合があります。

  - Teams の実行速度が遅い (帯域幅が不足している可能性がある)
  - 通話がドロップし続ける (ファイアウォールまたはプロキシブロックが原因である可能性がある)
  - 呼び出しが静的で切り取り、または音声がロボットのように聞こえる (ジッターやパケット損失の可能性がある)

ネットワークの最適化の詳細な説明 (ネットワーク障害の特定と修正のガイダンスなど) については [、Microsoft 365 および Office 365 ネットワーク](https://aka.ms/pnc)接続の原則を参照してください。

<table>
<thead>
<tr class="header">
<th><strong>ネットワーク最適化タスク</strong></th>
<th><strong>詳細</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>ネットワーク プランナー</td>
<td><p>組織の物理的な場所における帯域幅の計算やネットワーク要件など、ネットワークの評価に関するヘルプについては、Teams 管理センター<a href="https://docs.microsoft.com/microsoftteams/network-planner"></a>のネットワーク プランナー ツールを<a href="https://admin.teams.microsoft.com">参照してください</a>。 ネットワークの詳細と Teams の使用状況を提示すると、Network Planner は、組織の物理的な場所で Teams とクラウドの音声を展開するためのネットワーク要件を計算します。</p>
<p>シナリオ例については、「ネットワーク プランナーの使用 - シナリオ <a href="https://docs.microsoft.com/microsoftteams/tutorial-network-planner-example">例」を参照してください</a>。</p></td>
</tr>
<tr class="even">
<td>Teams のアドバイザー</td>
<td><a href="https://docs.microsoft.com/microsoftteams/use-advisor-teams-roll-out">Teams のアドバイザーは、Teams</a> 管理センター <a href="https://admin.teams.microsoft.com">の一部です</a>。 Microsoft 365 または Office 365 の環境を評価し、Teams を正常に展開する前に更新または変更する必要がある最も一般的な構成を特定します。</td>
</tr>
<tr class="odd">
<td>外部の名前解決</td>
<td>Teams クライアントを実行しているすべてのコンピューターが外部 DNS クエリを解決して、Microsoft 365 または Office 365 によって提供されるサービスを検出し、ファイアウォールがアクセスを妨げているのではないか確認してください。 ファイアウォール ポートの構成については <a href="https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges">、Microsoft 365 と 365</a>の URL Office IP 範囲を参照してください。</td>
</tr>
<tr class="odd">
<td>セッションの永続性を維持する</td>
<td>ファイアウォールで、UDP のマップされたネットワーク アドレス変換 (NAT) アドレスまたはポートが変更されていないことを確認します。</td>
</tr><tr class="odd">
<td>NAT プールのサイズを検証する</td>
<td>ユーザー接続に必要なネットワーク アドレス変換 (NAT) プール のサイズを検証します。 複数のユーザーやデバイスがネットワーク アドレス変換 (NAT) またはポート アドレス変換 <a href="https://docs.microsoft.com/office365/enterprise/nat-support-with-office-365">(PAT)</a>を使用して Microsoft 365 または Office 365 にアクセスする場合は、パブリックにラウト可能な各 IP アドレスの背後に隠れているデバイスがサポートされている数を超えないようにする必要があります。 ポートが使い果たされるのを防ぐために、適切なパブリック IP アドレスが NAT プールに割り当てられている必要があります。 ポートの使い果たされ、内部ユーザーやデバイスが Microsoft 365 または Office 365 サービスに接続できない可能性があります。</td>
</tr>
<tr class="even">
<td>Microsoft データ センターへのルーティング</td>
<td><a href="https://docs.microsoft.com/office365/enterprise/client-connectivity">Microsoft データ センターへの最も効率的なルーティングを実装します</a>。 ローカルまたは地域の出口ポイントを使用して、可能な限り効率的に Microsoft ネットワークに接続できる場所を特定します。</td>
</tr>
<tr class="odd">
<td>侵入検出と防止のガイダンス</td>
<td>環境に、送信接続<a href="https://docs.microsoft.com/azure/network-watcher/network-watcher-intrusion-detection-open-source-tools"></a>用のセキュリティ層の追加のために展開された侵入検出または防止システム (IDS/IPS) がある場合は、すべての Microsoft 365 または Office 365 URL を許可してください。</td>
</tr>
<tr class="even">
<td>分割トンネル VPN を構成する</td>
<td><p>仮想プライベート ネットワーク (VPN) をバイパスする Teams トラフィックの代替パス (一般に分割トンネル <a href="https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-routing">VPN) を提供することをお勧めします</a>。 分割トンネリングとは、Microsoft 365 または Office 365 のトラフィックが VPN を経由するのではなく、Microsoft 365 または Office 365 に直接送信されるという意味です。 VPN をバイパスすると、Teams の品質にプラスの影響を与え、VPN デバイスや組織のネットワークからの負荷が軽減されます。 分割トンネル VPN を実装するには、VPN ベンダーとご利用ください。</p>
<p>その他の理由として、VPN をバイパスすることをお勧めします。
<ul>
<li><p>VPN は通常、リアルタイム メディアをサポートするように設計または構成されていません。</p></li> 
<li><p>一部の VPN は UDP をサポートしていない場合があります (これは Teams に必要です)。</p></li> 
<li><p>また、VPN は、既に暗号化されているメディア トラフィックの上に、暗号化の層を追加します。</p></li> 
<li><p>VPN デバイスを介した髪の毛のピン留めトラフィックが原因で、Teams への接続が効率的ではない可能性があります。</p></li></td>
</tr>
<tr class="odd">
<td>QoS の実装</td>
<td><a href="https://docs.microsoft.com/microsoftteams/qos-in-teams">サービスの品質 (QoS) を使用して</a> 、パケットの優先順位付けを構成します。 これにより、Teams の通話品質が向上し、通話品質を監視およびトラブルシューティングできます。 QoS は、管理対象ネットワークのすべてのセグメントに実装する必要があります。 ネットワークが帯域幅に対して十分にプロビジョニングされている場合でも、QoS は、予定のないネットワーク イベントが発生した場合のリスク軽減を提供します。 QoS では、音声トラフィックが優先順位付けされ、これらの不必要なイベントが品質に悪影響を及ぼしません。</td>
</tr>
<tr class="even">
<td>WiFi を最適化する</td>
<td><p>VPN と同様に、WiFi ネットワークは必ずしもリアルタイム メディアをサポートするように設計または構成されているとは限りません。 Teams をサポートするための WiFi ネットワークの計画または最適化は、高品質の展開に関する重要な考慮事項です。 次の要因を考慮してください。</p>
<ul>
<li><p>メディア トラフィックが WiFi ネットワークよりも適切に優先順位付けされるのを確認するには、QoS または WiFi マルチメディア (WMM) を実装します。</p></li>
<li><p>WiFi バンドとアクセス ポイントの配置を計画して最適化します。 アクセス ポイントの配置に応じて、2.4 GHz 帯で十分なエクスペリエンスが提供される可能性がありますが、アクセス ポイントは、多くの場合にその帯域で動作するその他のコンシューマー デバイスによって影響を受けます。 5 GHz の範囲は、密な範囲が原因でリアルタイム メディアに適していますが、十分なカバレッジを得るには、より多くのアクセス ポイントが必要です。 エンドポイントも、その帯をサポートしており、それらの帯を利用できるように構成されている必要があります。</p></li>
<li><p>デュアルバンド WiFi ネットワークを使用している場合は、バンド 運営の実装を検討してください。 <em>バンド 運営は</em> 、WiFi ベンダーが 5 GHz の範囲を使用するデュアルバンド クライアントに影響を与える手法です。</p></li>
<li><p>同じチャネルのアクセス ポイントが近すぎると、信号の重複が発生し、意図せず競合し、ユーザーのエクスペリエンスが悪い結果になります。 互いに隣り合っているアクセス ポイントが、重複しないチャネル上に表示されます。</p></li>
</ul>
<p>各無線ベンダーは、その無線ソリューションを展開する場合の推奨事項をそれぞれ持っています。 具体的なガイダンスについては、WiFi ベンダーに問い合わせください。</p></td>
</tr>
</tbody>
</table>

## <a name="bandwidth-requirements"></a>帯域幅要件

Teams は、ネットワークの状態に関係なく、最高のオーディオ、ビデオ、コンテンツ共有エクスペリエンスを提供するように設計されています。 つまり、帯域幅が十分でない場合、Teams はオーディオ品質をビデオ品質よりも優先します。

帯域幅が制限されていない場合、Teams は最大 1080p のビデオ解像度、ビデオの場合は最大 30fps、コンテンツの場合は 15fps、忠実度の高いオーディオなど、メディア品質を最適化します。 

[!INCLUDE [bandwidth-requirements](includes/bandwidth-requirements.md)]


## <a name="related-topics"></a>関連項目

[Microsoft 365 および Office 365 ネットワーク接続の原則](https://aka.ms/pnc)

[世界中のエンドポイント: Skype for Business Online と Teams](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

[Teams のプロキシ サーバー](proxy-servers-for-skype-for-business-online.md)

[Teams のメディア: 会議が単純な理由](https://aka.ms/teams-media)

[Teams のメディア: メディア フローの詳細](https://aka.ms/teams-media-flows)

[Teams での ID モデルと認証](identify-models-authentication.md)

[Teams の展開方法](How-to-roll-out-teams.md)

[Teams のトラブルシューティング](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
