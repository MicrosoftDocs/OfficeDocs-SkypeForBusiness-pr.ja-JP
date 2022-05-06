---
title: '&会議を呼び出すためのポリシーベースの記録Teamsの概要'
author: cabailey
ms.author: cabailey
manager: laurawi
ms.date: 05/11/2020
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: abybee
ms.localizationpriority: medium
search.appverid: MET150
description: '&会議を呼び出すためのポリシーベースの記録Teamsについて説明します'
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
ms.openlocfilehash: 554c2e893272ca8dfca1fde6c746e72f1b462f1e
ms.sourcegitcommit: cbdc80c302e97d18a923ef57bb5d4b6cf7676d00
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/30/2022
ms.locfileid: "64556558"
---
# <a name="introduction-to-teams-policy-based-recording-for-callings--meetings"></a>通話&会議のポリシーベースの記録Teamsの概要

ポリシーベースの記録を使用すると、通話と会議のMicrosoft Teamsを採用する組織は、関連する企業または規制ポリシーによって必要に応じて、通話とオンライン会議を自動的に記録し、その後の処理とリテンションのためにキャプチャする必要がある場合に、管理ポリシーを使用して規定することができます。

Teamsは、Teams通信を構成、管理、記録、保存、分析するためのエンド ツー エンド ソリューションを提供するために必要なプラットフォーム機能、ユーザー エクスペリエンス、管理インターフェイスなど、サード パーティのレコーディング ソリューションの統合をサポートするように強化されています。 機能強化には、次の機能を提供する、通信プラットフォーム API と記録用のイベントが含まれます。

- オーディオ、ビデオ、画面共有、チャットでサポートされているすべてのエンドポイントと、デバイス間でシームレスで高品質のメディア キャプチャを行います。

- Teams ユーザーとサポートされている通話エンドポイント間の対話キャプチャのサポート (Teams、Teams Mobile、Skype for Business、PSTN)

- 既存のTeamsの管理通話と会議のツールとポリシーとの統合を含む、コンプライアンス記録の新しい管理ポリシー

コンプライアンス記録は、Microsoft 365 A3/A5/E3/E5/Business プレミアム および Office 365 A3/A5/E3/E5 ユーザーで有効にできます。 

コンプライアンス記録ソリューション統合機能は、[コンプライアンス記録とMicrosoft Teams セッション](https://myignite.microsoft.com/archives/IG19-VCE40)の Ignite 2019 でも確認されました。

## <a name="teams-interaction-recording-overview"></a>Teams操作記録の概要

相互作用記録のユース ケースは、効果的に、記録機能の 4 つの主要なカテゴリ (便利、機能、組織、および法的傍受) に分けることができます。画像に示すように、

> [!div class="mx-imgBorder"]
> ![相互作用の記録とその理由を示すスクリーンショット。](media/recording-taxonomy.png "画像は、記録カテゴリを示しています。")

各カテゴリには、記録の開始方法、記録内容、記録の保存場所、通知を受けるユーザー、アクセスを制御するユーザー、保持の処理方法に関する要件が異なります。

| 種類                   | 便利 (通常のTeams記録) | 組織 - 規制 (コンプライアンス記録) |
| ---------------------- | ------------------ | --------------- |
| イニシエーター              | ユーザー               | 管理者 (システム)  |
| Target                 | 通話/会議ごと | ユーザーごと        |
| Storage所有者          | ユーザー               | コンプライアンス      |
| 通知が必要ですか? | Yes                | Yes             |
| アクセス所有者           | ユーザー               | コンプライアンス      |
| アイテム保持ポリシー      | 省略可能           | Yes             |

Teamsには、会議やライブ イベントの[便利](./cloud-recording.md)で機能的な記録のためのさまざまな機能が用意されています。 組織の記録とは、呼び出しと会議のTeamsを採用する組織が、関連する企業または規制のポリシーで必要に応じて、通話とオンライン会議を自動的に記録し、その後の処理とリテンションのためにキャプチャする必要がある場合に、管理ポリシーを使用して規定することを可能にすることを意味します。 このポリシーのユーザーは、Teamsとのデジタル操作が記録されていることに注意しますが、記録を無効にすることはできず、操作が完了すると記録にアクセスできなくなります。 記録は、電子情報開示、訴訟ホールド、およびその他の企業保有に使用するコンプライアンス担当者と法務担当者が利用できる組織アーカイブの一部になります。

## <a name="example-user-needs"></a>ユーザーニーズの例

<table>
<thead>
<tr class="header">
<th>ペルソナ</th>
<th>ニーズ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>記録されたユーザー</td>
<td><ul>
<li><p>記録の進行中に通知を受け取る。</p></li>
<li><p>ポリシーエラーやレコーダー エラーが原因で呼び出し動作が変更された場合に通知されます。</p></li>
</ul></td>
</tr>
<tr class="even">
<td>コミュニケーション管理者</td>
<td><ul>
<li><p>Teamsユーザー/エンドポイントに記録ポリシーを適用/適用する理由と方法について説明します。</p></li>
<li><p>組織のTeams記録ポリシーを構成して管理します。</p></li>
<li><p>Teams通話と会議に関する記録関連の問題を監視し、トラブルシューティングします。</p></li>
<li><p>使用状況、品質、信頼性に関する運用分析を使用して、内部コンプライアンス担当者をサポートします。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td>コンプライアンス責任者</td>
<td><ul>
<li><p>コンプライアンスの義務を適切な地域境界で満たすために必要な方法で、すべてのTeams通信を収集します。</p></li>
<li><p>通信関連のメタデータまたは対話コンテンツに基づいて対話を検索します。 一般的な例を次に示します。</p>
<ul>
<li><p><strong>メタデータ</strong> - 参加者、時間、方向、ダイヤル番号、配信元番号、カスタム ビジネス データ</p></li>
<li><p><strong>コンテンツ</strong> – 文字起こし、センチメント、ふりがな、関連する相互作用</p></li>
</ul></li>
<li><p>収集された通信を分析して対話します。これには、収集中の対話を監視する機能が含まれます。</p></li>
<li><p>収集された通信のセキュリティを確保し、すべての段階で改ざんを防止します。</p></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="solution-architecture-overview"></a>ソリューション アーキテクチャの概要

コンプライアンス記録ソリューションは、次の図に示すようにTeamsと統合されています。

> [!div class="mx-imgBorder"]
> ![チームのカスタム アプリ設定を示すスクリーンショット。](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "画像は、Teams会議または通話の送受信時のフローを示しています。")

> [!NOTE]
> このソリューションは、Teamsに対するポリシー ベースのコンプライアンス記録を有効にするように特別に設計されています。 このソリューションのその他の使用はサポートされません。

## <a name="recorder"></a>レコーダー

コンプライアンス記録ソリューションのコア コンポーネントはレコーダーです。
レコーダーは、[Microsoft の通信プラットフォームを使用](/graph/cloud-communications-concept-overview)し、Microsoft Graphにアプリケーションとして登録するスケーラブルな Azure ベースのサービス (ボット) として構築されます。 レコーダーは、Teams通話と会議[の通信プラットフォーム API と](/graph/api/resources/communications-api-overview)直接対話し、メディア インジェストのエンドポイントを提供します。

ボットの構成、アプリ インスタンスの作成、コンプライアンス ポリシーの割り当て方法を示す [コンプライアンス レコーダー アプリケーションのサンプルを利用できます](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot) 。 このサンプルには、 [着信通話](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244) ルーティングの処理、 [記録状態の変更](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138)、 [記録中のユーザーの削除](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126)など、特定の対話を記録するための API の使用例も含まれています。
特定の API に関するGraphドキュメントについては、[updateRecordingStatus](/graph/api/call-updaterecordingstatus?tabs=http) と [incomingContext](/graph/api/resources/incomingcontext) に関するページを参照してください。

レコーダー サービスの正確な実装はパートナーによって異なりますが、展開の高可用性と地理的分散を実現して、Teamsからレコーダーへの待機時間を短縮するために、複数のレコーダーをサポートするように設計する必要があります。 さらに、レコーダー自体は、回復性と冗長性を念頭に置いて設計されることが期待されます。

パートナーは、コンプライアンス記録統合のすべての要件が確実にサポートされるように、認定ソリューションを提出する前に、Microsoft Graph通信 API と SDK の最小必要なリリース バージョンを Microsoft と確認する必要があります。

コンプライアンス記録シナリオの基本となる 2 つの具体的な要件は次のとおりです。

- レコーダー ボットを Azure にデプロイする必要がある

- レコーダー ボットは、Azure のWindows VM で実行する必要があります

Azure および Windows VM の要件は、Teams Bot コンポーネントにのみ適用されます。つまり、パートナーは、コンプライアンス記録に関連するパフォーマンスと機能要件を満たすことができる限り、選択した残りのプラットフォームを実装できます。

## <a name="compliance-recording-policy-assignment-and-provisioning"></a>コンプライアンス記録ポリシーの割り当てとプロビジョニング

IT 管理者は、コンプライアンス記録ポリシーを作成して割り当てることで、記録するユーザーと、各ユーザーに使用するレコーダーを決定できます。 通信操作が行われると、これらのポリシーの構成に基づいて、レコーダーが自動的に会話に参加するように招待されます。 コンプライアンス記録ポリシーは [Microsoft PowerShell](./teams-powershell-overview.md) を使用して管理され、組織ごとにテナント、ユーザーごと、およびセキュリティ グループ レベルで適用できます。 [会議ポリシー](./meeting-policies-overview.md)、[通話](./teams-calling-policy.md)ポリシー、グループ ポリシーのMicrosoft Docsの詳細については、以下をご覧[ください](./assign-policies-users-and-groups.md#assign-a-policy-to-a-group)。

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

   [Set-CsTeamsComplianceRecordingPolicy を](/powershell/module/skype/set-csteamscompliancerecordingpolicy)参照してください。

3. コンプライアンス記録ポリシーをユーザーに割り当てます。

   ```powershell
   PS C:\> Grant-CsTeamsComplianceRecordingPolicy -Identity testuser@contoso.onmicrosoft.com -PolicyName TestComplianceRecordingPolicy
   ```

   [Grant-CsTeamsComplianceRecordingPolicy](/powershell/module/skype/grant-csteamscompliancerecordingpolicy) を参照してください。

   ```powershell
   PS C:\> Get-CsOnlineUser testuser@contoso.onmicrosoft.com | select SipAddress, TenantId, TeamsComplianceRecordingPolicy | fl

   UserPrincipalName              : testuser@contoso.onmicrosoft.com
   TenantId                       : 5b943d7c-5e14-474b-8237-5022eb8e0dc9
   TeamsComplianceRecordingPolicy : TestComplianceRecordingPolicy
   ```

## <a name="user-experiences"></a>ユーザー エクスペリエンス

通知のサポートは、Teamsクライアント エクスペリエンスを使用して有効になります。 エクスペリエンスには、ビジュアルまたはオーディオを使用できます。

**Teams クライアント - 視覚的な通知**
- Desktop/web
- モバイル (iOS/Android)
- Teams電話
- Teamsルーム

**その他のエンドポイント - オーディオ通知**
- SIP 電話
- Skype for Business
- 電話会議
- PSTN 発信者

> [!NOTE]
> コンプライアンス記録は、電話会議モードの通話キューではサポートされていません。 転送モードの呼び出しキューを使用してください。
> ユーザーがインターネットの停止を経験し、SBA を使用して PSTN 通話を発信および受信している場合、コンプライアンス記録は機能しません。

## <a name="compliance-recording-for-teams-certification-programs"></a>Teams認定プログラムのコンプライアンス記録

パートナーが CCaaS ソリューションをTeamsと開発および統合できるようにする公開 API を発行するだけでなく、Microsoft Teams認定プログラムのコンプライアンス記録を開発し、参加している各パートナーのソリューションがテストされ、Microsoft ソリューションから期待される品質、互換性、信頼性を提供することを顧客に保証します。  

次のパートナーは、Microsoft Teamsのソリューションを認定しています。<br/><br/>

|パートナー|ソリューションの Web サイト |
|:--|:--|
|ASC テクノロジ |[https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html](https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html) |
|AudioCodes |[https://online.audiocodes.com/smarttap-360-live-for-microsoft-teams](https://online.audiocodes.com/smarttap-360-live-for-microsoft-teams) |
|CallCabinet |[https://www.callcabinet.com/compliance-microsoft-teams-call-recording](https://www.callcabinet.com/compliance-microsoft-teams-call-recording ) |
|ダバー |[https://www.dubber.net/call-recording/](https://www.dubber.net/call-recording/) |
|Insightful Technology |[https://insightfultechnology.com/teams/](https://insightfultechnology.com/teams/) |
|NICE Engage |[https://www.nice.com/products/workforce-engagement/call-recording/air-and-engage](https://www.nice.com/products/workforce-engagement/call-recording/air-and-engage) |
|NICE NTR |[https://www.niceactimize.com/compliance/ms-teams-recording.html](https://www.niceactimize.com/compliance/ms-teams-recording.html) |
|Numonix |[https://numonix.cloud](https://numonix.cloud)    |
|Oak Innovation |[https://www.oakinnovate.com/clarify](https://www.oakinnovate.com/clarify) |
|赤いボックス |[https://www.redboxvoice.com/compliance-recording-for-microsoft-teams](https://www.redboxvoice.com/compliance-recording-for-microsoft-teams)  |
|Theta Lake |[https://thetalake.com/integrations/microsoft/](https://thetalake.com/integrations/microsoft/) |
|Verint |[https://www.verba.com/solutions/microsoft-teams-recording](https://www.verba.com/solutions/microsoft-teams-recording) |
|Oak Innovation |[https://www.oakinnovate.com/clarify](https://www.oakinnovate.com/clarify) |

<br/>
次のパートナーは、Microsoft Teamsのソリューションを認定しています。<br/><br/>

|パートナー|ソリューションの Web サイト |
|:--|:--|
|Landis Technologies |[https://landistechnologies.com/](https://landistechnologies.com/) |
|Luware |[https://luware.com/en/solution/microsoft-teams-recording/](https://luware.com/en/solution/microsoft-teams-recording/) |


このリストは、パートナーが参加して認定条件を満たしたときに更新されます。

## <a name="next-steps"></a>次のステップ

認定プログラムに参加しようとしているベンダーの場合は、 [Teamscategorypartner@microsoft.com](mailto:Teamscategorypartner@microsoft.com) にメールを送信します。
