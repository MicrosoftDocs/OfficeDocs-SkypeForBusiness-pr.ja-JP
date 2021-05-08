---
title: 会議をTeamsする場合のポリシーベースの記録の&概要
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
description: 会議のTeamsのポリシーベースの記録について&する
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
# <a name="introduction-to-teams-policy-based-recording-for-callings--meetings"></a>会議のTeamsに対するポリシーベースの記録の&概要

ポリシー ベースの記録を使用すると、通話と会議に Microsoft Teams を採用する組織は、関連する企業または規制ポリシーの要求に応じて、通話とオンライン会議を自動的に記録して保持する必要がある場合に、管理ポリシーを使用して指定できます。

Teamsは、Teams 通信を構成、管理、記録、保存、分析するためのエンド to エンド ソリューションを提供するために必要なプラットフォーム機能、ユーザー エクスペリエンス、管理インターフェイスなど、サード パーティ製の記録ソリューションの統合をサポートするために強化されました。 機能強化には、通信プラットフォーム API と記録用のイベントが含まれます。次の機能が提供されます。

- デバイス間およびオーディオ、ビデオ、画面共有、チャットでサポートされているすべてのエンドポイントで、シームレスで高品質のメディア キャプチャ。

- ユーザーとサポートされている呼び出しTeamsエンドポイント (Teams、Teams Mobile、Skype for Business PSTN) 間の対話キャプチャのサポート

- コンプライアンス記録用の新しい管理ポリシー (既存の通話および会議ツールTeamsポリシーとの統合を含む)

コンプライアンス記録は、Microsoft 365 A3/A5/E3/E5/Business プレミアム および Office 365 A3/A5/E3/E5 ユーザーで有効にできます。 

コンプライアンス記録ソリューションの統合機能は、コンプライアンス記録セッションの Ignite 2019 [<span class="underline">Microsoft Teamsされました</span>](https://myignite.microsoft.com/archives/IG19-VCE40)。

## <a name="teams-interaction-recording-overview"></a>Teams記録の概要

対話記録の使用例は、画像に示すように、便利、機能、組織、および法律上のインターセプトの 4 つの主要な記録機能カテゴリに効果的に分けることができます。

![操作の記録の理由と理由を示すスクリーンショット。](media/recording-taxonomy.png "画像には、記録カテゴリが表示されます。")

各カテゴリには、レコーディングの開始方法、記録の記録方法、記録の保存場所、通知を受け取るユーザー、アクセス権を制御するユーザー、保持の処理方法に関するさまざまな要件が含まれます。

| 種類                   | 利便性 (通常のTeams記録) | 組織 - 規制対象 (コンプライアンス記録) |
| ---------------------- | ------------------ | --------------- |
| イニシエーター              | ユーザー               | 管理者 (システム)  |
| Target                 | 通話/会議ごとに | ユーザーごと        |
| Storage所有者          | ユーザー               | コンプライアンス      |
| 通知が必要ですか? | はい                | はい             |
| アクセス所有者           | ユーザー               | コンプライアンス      |
| アイテム保持ポリシー      | 省略可能           | はい             |

Teamsは、会議やライブ イベントに[<span class="underline">便利</span>](./cloud-recording.md)で機能的な記録を行うさまざまな機能を提供します。 組織記録とは、関連する企業または規制ポリシーで必要に応じて、通話とオンライン会議を自動的に記録して保持する必要がある場合に、管理ポリシーを使用して、通話と会議に Teams を導入する組織が自動的に記録およびキャプチャを行う必要がある場合に有効にするためのものです。 このポリシーの下のユーザーは、Teams とのデジタル対話が記録されているが、記録を無効にできないので、対話が完了すると記録にアクセスできないという認識を受け取る。 記録は、電子情報開示、法的保持、その他の企業保有の使用に関するコンプライアンス担当者および法務担当者が利用できる組織のアーカイブの一部になります。

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
<li><p>記録が進行中のときに通知を受け取る。</p></li>
<li><p>ポリシーやレコーダーのエラーが呼び出し動作の変更を引き起こしている場合は、通知を受け取る。</p></li>
</ul></td>
</tr>
<tr class="even">
<td>コミュニケーション管理者</td>
<td><ul>
<li><p>ユーザー/エンドポイントに記録ポリシーを適用/適用する理由Teams理解します。</p></li>
<li><p>組織のTeams記録ポリシーを構成および管理します。</p></li>
<li><p>通話や会議の記録に関連する問題Teamsトラブルシューティングを行います。</p></li>
<li><p>使用状況、品質、信頼性に関する運用分析で内部コンプライアンス責任者をサポートします。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td>コンプライアンス責任者</td>
<td><ul>
<li><p>適切な地域Teamsコンプライアンス義務を満たすために必要な方法で、すべての情報通信を収集します。</p></li>
<li><p>コミュニケーション関連のメタデータまたは対話コンテンツに基づいて対話を検索します。 一般的な例を次に示します。</p>
<ul>
<li><p><strong>メタデータ</strong> - 参加者、時間、方向、ダイヤルされた番号、発信元番号、カスタム ビジネス データ</p></li>
<li><p><strong>コンテンツ</strong> – 文字起こし、センチメント、音声、関連する対話</p></li>
</ul></li>
<li><p>収集される通信を監視する機能など、収集された通信を分析して操作します。</p></li>
<li><p>収集された通信のセキュリティを確保し、すべての段階で改ざんを防ぐ。</p></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="solution-architecture-overview"></a>ソリューション アーキテクチャの概要

コンプライアンス記録ソリューションは、次の図Teamsと統合されています。

![チームのカスタム アプリ設定を示すスクリーンショット](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "画像は、会議または通話がTeams受信した場合のフローを示しています。")

## <a name="recorder"></a>レコーダー

コンプライアンス記録ソリューションのコア コンポーネントは、レコーダーです。
レコーダーは、Microsoft の通信プラットフォームを活用し[<span class="underline">、Microsoft</span>](/graph/cloud-communications-concept-overview) Graph にアプリケーションとして登録するスケーラブルな Azure ベースのサービス (ボット) として構築されています。 レコーダーは、通話や会議の通信プラットフォーム API Teams直接やり[<span class="underline"></span>](/graph/api/resources/communications-api-overview?view=graph-rest-1.0)取りし、メディア インジェストのエンドポイントを提供します。

ボット [<span class="underline">の構成、アプリ</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot) インスタンスの作成、コンプライアンス ポリシーの割り当て方法を示すサンプル コンプライアンス 記録アプリケーションを使用できます。 このサンプルには、着信通話ルーティングの処理、録音状態の変更、記録[<span class="underline"></span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244)されているユーザーの削除[<span class="underline"></span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138)など、特定の対話を記録するための API 使用法の例も[<span class="underline">示されています</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126)。
Graph API の詳細については[<span class="underline">、updateRecordingStatus</span>](/graph/api/call-updaterecordingstatus?tabs=http&view=graph-rest-1.0)と incomingContext に関するページ[<span class="underline">を参照してください</span>](/graph/api/resources/incomingcontext?view=graph-rest-1.0)。

レコーダー サービスの正確な実装はパートナーによって異なりますが、Teams からレコーダーへの待機時間を短縮するために、デプロイの高可用性と地理的分散を実現するために、複数のレコーダーをサポートするように設計する必要があります。 さらに、回復性と冗長性を念頭に置いてレコーダー自体を設計する必要があります。

パートナーは、コンプライアンス記録統合のすべての要件がサポートされるのを確認するために、認定のためのソリューションを提出する前に、Microsoft Graph 通信 API と SDK の最小必須リリース バージョンを確認する必要があります。

コンプライアンス記録シナリオの基本である 2 つの具体的な要件は次のとおりです。

- レコーダー ボットを Azure にデプロイする必要があります

- レコーダー ボットは、Azure 内の Windows VM 上で実行する必要があります

Azure および Windows VM の要件は Teams Bot コンポーネントにのみ適用されます。つまり、パートナーは、コンプライアンス記録に関する関連するパフォーマンス要件と機能要件を満たしている場合に、選択したプラットフォームの残りの部分を実装できます。

## <a name="compliance-recording-policy-assignment-and-provisioning"></a>コンプライアンス記録ポリシーの割り当てとプロビジョニング

IT 管理者は、コンプライアンス記録ポリシーを作成して割り当てると、どのユーザーを記録し、どのレコーダーを各ユーザーに使用されるかを決定できます。 記録者は、通信操作が行われたときに、これらのポリシーの構成に基づいて会話に参加するために自動的に招待されます。 コンプライアンス記録ポリシーは [<span class="underline">Microsoft PowerShell</span>](./teams-powershell-overview.md) を使用して管理され、テナント、ユーザー単位、およびセキュリティ グループ レベルで組織ごとに適用できます。 会議ポリシー、通話ポリシー、グループ[<span class="underline">ポリシーに</span>](./meeting-policies-in-teams.md)関する[<span class="underline"></span>](./teams-calling-policy.md)Microsoft Docs の詳細[<span class="underline">については、 を参照してください</span>](./assign-policies.md#assign-a-policy-to-a-group)。

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

通知のサポートは、クライアント エクスペリエンスのTeams使用して有効になります。 エクスペリエンスには、視覚的またはオーディオを使用できます。

**Teams クライアント - 視覚的な通知**
- デスクトップ/Web
- モバイル (iOS/Android)
- Teams電話
- Teamsルーム

**その他のエンドポイント - 音声に関する通知**
- SIP 電話
- Skype for Business
- 電話会議
- PSTN 発信者

## <a name="compliance-recording-for-teams-certification-programs"></a>認定プログラムのTeams記録

公開されている API を公開することで、パートナーは CCaaS ソリューションを開発して Teams と統合できるほか、microsoft ソリューションから期待される品質、互換性、信頼性を提供するために、参加している各パートナーのソリューションがテストおよび検証されたという保証を顧客に提供するために、Microsoft Teams 認定プログラムのコンプライアンス記録を開発しました。  

次のパートナーは、パートナーのソリューションを認定Microsoft Teams。

|パートナー|ソリューションの Web サイト |
|:--|:--|
|ASC テクノロジ |[https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html](https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html) |
|AudioCodes |[https://www.audiocodes.com/solutions-products/voiceai/meetings-and-recording/smarttap-360](https://www.audiocodes.com/solutions-products/voiceai/meetings-and-recording/smarttap-360) |
|ダバー |[https://www.dubber.net/call-recording/](https://www.dubber.net/call-recording/) |
|NICE |[https://www.niceactimize.com/compliance/ms-teams-recording.html](https://www.niceactimize.com/compliance/ms-teams-recording.html) |
|Numonix |[https://numonix.cloud](https://numonix.cloud)    |

次のパートナーは、ソリューションを認定するプロセスをMicrosoft Teams。

|パートナー|ソリューションの Web サイト |
|:--|:--|
|CallCabinet |[https://www.callcabinet.com/compliance-microsoft-teams-call-recording](https://www.callcabinet.com/compliance-microsoft-teams-call-recording ) |
|Landis Technologies |[https://landistechnologies.com/](https://landistechnologies.com/) |
|Luware |[https://luware.com/en/solution/microsoft-teams-recording/](https://luware.com/en/solution/microsoft-teams-recording/) |
|Oak Innovation |[https://www.oakinnovate.com/call-recording](https://www.oakinnovate.com/call-recording) |
|赤いボックス |[https://www.redboxvoice.com/compliance-recording-for-microsoft-teams](https://www.redboxvoice.com/compliance-recording-for-microsoft-teams)  |
|Verint |[https://www.verba.com/solutions/microsoft-teams-recording](https://www.verba.com/solutions/microsoft-teams-recording) |
|Theta Lake |[https://thetalake.com/integrations/microsoft/](https://thetalake.com/integrations/microsoft/) |

このリストは、パートナーが参加して認定条件を満たしたときに更新されます。

## <a name="next-steps"></a>次の手順

認定プログラムへの参加を希望しているベンダーの場合は、 にメール<a href= "mailto:Teamscategorypartner@microsoft.com">Teamscategorypartner@microsoft.com。</a>
