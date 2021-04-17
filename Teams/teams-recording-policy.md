---
title: 会議への通話用の Teams ポリシーベースの記録&概要
author: cabailey
ms.author: cabailey
manager: laurawi
ms.date: 05/11/2020
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: abybee
localization_priority: Normal
search.appverid: MET150
description: 会議への通話用の Teams ポリシーベースの記録&する
f1.keywords:
- CSH
ms.custom:
- Adopt
- seo-marvel-mar2020
ms.collection:
- Teams_ITAdmin_Adopt
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d5721f13a569ee240c33f2bf4262eb84966065d6
ms.sourcegitcommit: 4e1f5d99c1d0612dc5b50f850280983867ff53d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2021
ms.locfileid: "51874463"
---
# <a name="introduction-to-teams-policy-based-recording-for-callings--meetings"></a>会議の通話に対する Teams ポリシーベースの記録&概要

ポリシーベースの記録を使用すると、通話および会議に Microsoft Teams を採用する組織は、関連する企業ポリシーまたは規制ポリシーの必要に応じて、通話とオンライン会議を自動的に記録して保持するために、管理ポリシーを使用して、その後の処理と保持のために自動的に記録およびキャプチャする必要がある場合に、管理ポリシーを使用して規定することができます。

Teams は、Teams の通信を構成、管理、記録、保存、分析するためのエンドツーエンド ソリューションを提供するために必要なプラットフォームの機能、ユーザー エクスペリエンス、管理インターフェイスなど、サードパーティのレコーディング ソリューションの統合をサポートするために強化されました。 強化された機能には、通信プラットフォーム API と記録のためのイベントが含まれます。次の機能が提供されます。

- デバイス間でのシームレスで高品質なメディア キャプチャと、オーディオ、ビデオ、画面共有、チャットでサポートされるすべてのエンドポイント。

- Teams ユーザーとサポートされる通話エンドポイント (Teams、Teams Mobile、Skype for Business、PSTN) 間の対話キャプチャのサポート

- 既存の Teams 管理通話ツールおよび会議ツールとポリシーとの統合を含む、コンプライアンス記録用の新しい管理ポリシー

コンプライアンス記録は、Microsoft 365 A3/A5/E3/E5/Business Premium および Office 365 A3/A5/E3/E5 ユーザーで有効にできます。 

コンプライアンス記録ソリューション統合機能は、コンプライアンス記録と Microsoft Teams セッションの Ignite 2019 [<span class="underline">でも確認されました</span>](https://myignite.microsoft.com/archives/IG19-VCE40)。

## <a name="teams-interaction-recording-overview"></a>Teams の対話記録の概要

操作記録の使用例は、画像に示すように、記録機能の主な 4 つのカテゴリ (便利、機能、組織、および合法な切片) に実質的に分けることができます。

![操作が何と理由を記録したのかを示すスクリーンショット。](media/recording-taxonomy.png "画像は記録カテゴリを示しています。")

各カテゴリには、レコーディングの開始方法、記録の記録方法、レコーディングの保存場所、通知を受け取るユーザー、アクセスを制御するユーザー、保持の処理方法に関するさまざまな要件が含まれます。

| 種類                   | 利便性 (通常の Teams レコーディング) | 組織 - 規制 (コンプライアンス記録) |
| ---------------------- | ------------------ | --------------- |
| [開始側]              | ユーザー               | 管理者 (システム)  |
| Target                 | 1 回の通話/会議 | ユーザーごと        |
| ストレージ所有者          | ユーザー               | コンプライアンス      |
| 通知が必要ですか? | はい                | はい             |
| Access の所有者           | ユーザー               | コンプライアンス      |
| アイテム保持ポリシー      | 省略可能           | はい             |

Teams は、会議やライブ イベント [<span class="underline">に便利</span>](./cloud-recording.md) で機能的に記録するさまざまな機能を提供します。 組織の記録とは、通話と会議に Teams を採用する組織が、関連する企業ポリシーまたは規制ポリシーの必要に応じて、通話とオンライン会議を自動的に記録および取得して、その後の処理と保持のために管理ポリシーを使用して示す機能を有効に意味します。 このポリシーの下のユーザーは、Teams とのデジタル対話が記録されているが、記録を無効にできないので、操作が完了すると記録にアクセスできないという認識を受け取る。 記録は、電子情報開示、法的保持、その他の企業保持の使用に関するコンプライアンス担当者や法務担当者が利用できる組織のアーカイブの一部になります。

## <a name="example-user-needs"></a>ユーザーニーズの例

<table>
<thead>
<tr class="header">
<th><strong>ペルシャ</strong></th>
<th><strong>ニーズ</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>記録されたユーザー</td>
<td><ul>
<li><p>記録中に通知を受け取る。</p></li>
<li><p>ポリシーまたは記録エラーが呼び出し動作の変更を引き起こしている場合は、通知を受け取る。</p></li>
</ul></td>
</tr>
<tr class="even">
<td>コミュニケーション管理者</td>
<td><ul>
<li><p>記録ポリシーを Teams ユーザー/エンドポイントに適用/適用する理由と方法を理解します。</p></li>
<li><p>組織の Teams 記録ポリシーを構成および管理します。</p></li>
<li><p>Teams の通話と会議に関する記録関連の問題を監視およびトラブルシューティングします。</p></li>
<li><p>使用、品質、信頼性に関する運用分析を行う内部法令遵守責任者をサポートします。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td>法令遵守責任者</td>
<td><ul>
<li><p>適切な地域の境界でコンプライアンス義務を満たすために必要な方法で、すべての Teams 通信を収集します。</p></li>
<li><p>コミュニケーション関連のメタデータまたは対話コンテンツに基づいて対話を検索します。 一般的な例を次に示します。</p>
<ul>
<li><p><strong>メタデータ</strong> - 参加者、時刻、方向、ダイヤルされた番号、発信元番号、カスタム ビジネス データ</p></li>
<li><p><strong>コンテンツ</strong> – トランスクリプション、感情、ルク、関連する相互作用</p></li>
</ul></li>
<li><p>収集される対話を監視する機能など、収集された通信を分析および操作します。</p></li>
<li><p>収集された通信のセキュリティを確保し、すべての段階で改ざんを防ぐ。</p></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="solution-architecture-overview"></a>ソリューション アーキテクチャの概要

コンプライアンス記録ソリューションは、次の図に示すように Teams と統合されています。

![チームのカスタム アプリの設定を示すスクリーンショット](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "画像は、Teams 会議または通話が送信および受信された場合のフローを示しています。")

## <a name="recorder"></a>Recorder

コンプライアンス記録ソリューションの主要コンポーネントは、レコーダーです。
記録者は、Microsoft の通信プラットフォームを利用し [<span class="underline">、Microsoft</span>](/graph/cloud-communications-concept-overview) Graph でアプリケーションとして登録するスケーラブル Azure ベースのサービス (ボット) として構築されています。 記録者は、Teams の呼び出しおよび会議コミュニケーション プラットフォーム [<span class="underline">API</span>](/graph/api/resources/communications-api-overview?view=graph-rest-1.0) と直接やり取りし、メディアインジェストのエンドポイントを提供します。

ボット [<span class="underline">の構成方法、</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot) アプリ インスタンスの作成方法、コンプライアンス ポリシーの割り当て方法を示すサンプル コンプライアンス 記録アプリケーションを利用できます。 このサンプルには、着信通話ルーティングの処理、記録状態の変更、記録[<span class="underline"></span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244)されているユーザーの削除[<span class="underline"></span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138)など、特定の対話を記録するための API の使用状況の例も[<span class="underline">示します</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126)。
[<span class="underline">UpdateRecordingStatus</span>](/graph/api/call-updaterecordingstatus?tabs=http&view=graph-rest-1.0)と incomingContext については、特定の API に関する Graph ドキュメントを[<span class="underline">参照してください</span>](/graph/api/resources/incomingcontext?view=graph-rest-1.0)。

レコーダー サービスの正確な実装はパートナーによって異なりますが、Teams からレコーダーへの遅延を減らすために、展開の高可用性と地理的分布を実現するために、複数のレコーダーをサポートするように設計する必要があります。 さらに、レコーダー自体は回復性と冗長性を念頭に置いて設計する必要があります。

パートナーは、コンプライアンス記録統合のすべての要件を確実にサポートするために、認定のためのソリューションを提出する前に、Microsoft との Microsoft Graph 通信 API と SDK の最小必須リリース バージョンを確認する必要があります。

コンプライアンス記録シナリオの基本である 2 つの特定の要件は次のとおりです。

- レコーダー ボットは Azure に展開する必要があります

- レコーダー ボットは Azure の Windows VM で実行する必要があります

Azure と Windows VM の要件は Teams Bot コンポーネントにのみ適用されます。つまり、パートナーは、コンプライアンス記録に関する関連するパフォーマンスと機能の要件を満たしている場合に、選択したプラットフォームの残りの部分を実装できます。

## <a name="compliance-recording-policy-assignment-and-provisioning"></a>コンプライアンス記録ポリシーの割り当てとプロビジョニング

IT 管理者は、コンプライアンス記録ポリシーを作成して割り当て、記録するユーザーと、各ユーザーに使用する記録者を決定できます。 記録者は、通信操作が行われたときに、これらのポリシーの構成に基づいて会話に参加するために自動的に招待されます。 コンプライアンス記録ポリシーは [<span class="underline">Microsoft PowerShell</span>](./teams-powershell-overview.md) を使用して管理され、組織ごとにテナント、ユーザー単位、セキュリティ グループ レベルで適用できます。 会議ポリシー、通話ポリシー、グループ ポリシー[<span class="underline"></span>](./meeting-policies-in-teams.md)に関する Microsoft Docs[<span class="underline">の詳細については</span>](./teams-calling-policy.md)、以下を[<span class="underline">参照してください</span>](./assign-policies.md#assign-a-policy-to-a-group)。

1. テナントにアプリケーション インスタンスを作成します。

   ```powershell
   PS C:\> New-CsOnlineApplicationInstance -UserPrincipalName cr.instance@contoso.onmicrosoft.com -DisplayName ComplianceRecordingBotInstance -ApplicationId fcc88ff5-a42d-49cf-b3d8-f2e1f609d511

   RunspaceId        : 4c13efa6-77bc-42db-b5bf-bdd62cdfc5df
   ObjectId          : 5069aae5-c451-4983-9e57-9455ced220b7
   TenantId          : 5b943d7c-5e14-474b-8237-5022eb8e0dc9
   UserPrincipalName : cr.instance@contoso.onmicrosoft.com
   ApplicationId     : fcc88ff5-a42d-49cf-b3d8-f2e1f609d511
   DisplayName       : ComplianceRecordingBotInstance
   PhoneNumber       :
   ```

   ```powershell
   PS C:\> Sync-CsOnlineApplicationInstance -ObjectId 5069aae5-c451-4983-9e57-9455ced220b7
   ```

2. コンプライアンス記録ポリシーを作成します。

   ```powershell
   PS C:\> New-CsTeamsComplianceRecordingPolicy -Identity TestComplianceRecordingPolicy -Enabled $true -Description "Test policy created by tenant admin"

   Identity                        : Global
   ComplianceRecordingApplications : {}
   Enabled                         : True
   WarnUserOnRemoval               : True
   Description                     : Test policy created by tenant admin
   ```

   ```powershell
   PS C:\> Set-CsTeamsComplianceRecordingPolicy -Identity TestComplianceRecordingPolicy `
   -ComplianceRecordingApplications @(New-CsTeamsComplianceRecordingApplication -Id 5069aae5-c451-4983-9e57-9455ced220b7 -Parent TestComplianceRecordingPolicy)
   ```

   [<span class="underline">Set-CsTeamsComplianceRecordingPolicy</span>](/powershell/module/skype/set-csteamscompliancerecordingpolicy?view=skype-ps)

3. コンプライアンス記録ポリシーをユーザーに割り当てる。

   ```powershell
   PS C:\> Grant-CsTeamsComplianceRecordingPolicy -Identity testuser@contoso.onmicrosoft.com -PolicyName TestComplianceRecordingPolicy
   ```

   [<span class="underline">Grant-CsTeamsComplianceRecordingPolicy</span>](/powershell/module/skype/grant-csteamscompliancerecordingpolicy?view=skype-ps)

   ```powershell
   PS C:\> Get-CsOnlineUser testuser@contoso.onmicrosoft.com | select SipAddress, TenantId, TeamsComplianceRecordingPolicy | fl

   UserPrincipalName              : testuser@contoso.onmicrosoft.com
   TenantId                       : 5b943d7c-5e14-474b-8237-5022eb8e0dc9
   TeamsComplianceRecordingPolicy : TestComplianceRecordingPolicy
   ```

## <a name="user-experiences"></a>ユーザー エクスペリエンス

通知のサポートは、Teams クライアントエクスペリエンスを使用して有効になります。 エクスペリエンスには、視覚的またはオーディオを使用できます。

**Teams クライアント - 視覚的な通知**
- デスクトップ/Web
- モバイル (iOS/Android)
- Teams の電話
- Teams のルーム

**その他のエンドポイント - 音声に関する通知**
- SIP 電話機
- Skype for Business
- 電話会議
- PSTN 発信者

## <a name="compliance-recording-for-teams-certification-programs"></a>Teams 認定プログラムのコンプライアンス記録

公開されている API を公開することで、パートナーは CCaaS ソリューションを Teams と開発して統合できるだけでなく、Microsoft Teams 認定プログラムのコンプライアンス記録を開発し、参加している各パートナーのソリューションがテストされ、Microsoft ソリューションから期待される品質、互換性、信頼性を提供することを保証する保証を顧客に提供しています。  

次のパートナーは、Microsoft Teams のソリューションを認定しています。

|パートナー|ソリューションの Web サイト |
|:--|:--|
|ASC テクノロジ |[https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html](https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html) |
|AudioCodes |[https://www.audiocodes.com/solutions-products/voiceai/meetings-and-recording/smarttap-360](https://www.audiocodes.com/solutions-products/voiceai/meetings-and-recording/smarttap-360) |
|Dubber |[https://www.dubber.net/call-recording/](https://www.dubber.net/call-recording/) |
|NICE |[https://www.niceactimize.com/compliance/ms-teams-recording.html](https://www.niceactimize.com/compliance/ms-teams-recording.html) |
|Numonix |[https://numonix.cloud](https://numonix.cloud)    |

次のパートナーは、Microsoft Teams のソリューションを認定中です。

|パートナー|ソリューションの Web サイト |
|:--|:--|
|CallCabinet |[https://www.callcabinet.com/compliance-microsoft-teams-call-recording](https://www.callcabinet.com/compliance-microsoft-teams-call-recording ) |
|Landis Technologies |[https://landistechnologies.com/](https://landistechnologies.com/) |
|Luware |[https://luware.com/en/solution/microsoft-teams-recording/](https://luware.com/en/solution/microsoft-teams-recording/) |
|オーナの革新 |[https://www.oakinnovate.com/call-recording](https://www.oakinnovate.com/call-recording) |
|赤いボックス |[https://www.redboxvoice.com/compliance-recording-for-microsoft-teams](https://www.redboxvoice.com/compliance-recording-for-microsoft-teams)  |
|Verint |[https://www.verba.com/solutions/microsoft-teams-recording](https://www.verba.com/solutions/microsoft-teams-recording) |
|Theta Lake |[https://thetalake.com/integrations/microsoft/](https://thetalake.com/integrations/microsoft/) |

このリストは、パートナーが参加して認定条件を満たしたときに更新されます。

## <a name="next-steps"></a>次の手順

認定プログラムへの参加を希望しているベンダーの場合は、認定プログラムに<a href= "mailto:Teamscategorypartner@microsoft.com">Teamscategorypartner@microsoft.com。</a>
