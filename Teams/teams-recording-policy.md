---
title: 会議をTeamsするポリシー ベースの記録の概要&説明
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
description: 会議のTeamsのポリシーベースの記録について&します。
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
ms.openlocfilehash: 18e7b02a52a0ddc7c380ed3fb4c5879b45fe18dc
ms.sourcegitcommit: b878c57b8e822913b7aac8c105f476bc4ebfcd7d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2022
ms.locfileid: "63761931"
---
# <a name="introduction-to-teams-policy-based-recording-for-callings--meetings"></a>会議のTeamsに対するポリシー ベースの記録の概要&説明

ポリシー ベースの記録を使用すると、通話と会議に Microsoft Teams を採用する組織は、関連する企業または規制ポリシーの要求に応じて、通話とオンライン会議を自動的に記録して保持する必要がある場合に、管理ポリシーを使用して指定できます。

Teamsは、Teams 通信を構成、管理、記録、保存、分析するためのエンド to エンド ソリューションを提供するために必要なプラットフォーム機能、ユーザー エクスペリエンス、管理インターフェイスなど、サード パーティ製の記録ソリューションの統合をサポートするために強化されました。 機能強化には、通信プラットフォーム API と記録用のイベントが含まれます。次の機能が提供されます。

- デバイス間およびオーディオ、ビデオ、画面共有、チャットでサポートされているすべてのエンドポイントにわたるシームレスで高品質のメディア キャプチャ。

- ユーザーとサポートされている呼び出しTeamsエンドポイント (Teams、Teams Mobile、Skype for Business PSTN) 間の対話キャプチャのサポート

- コンプライアンス記録用の新しい管理ポリシー (既存の通話および会議ツールTeamsポリシーとの統合を含む)

コンプライアンス記録は、Microsoft 365 A3/A5/E3/E5/Business プレミアム および Office 365 A3/A5/E3/E5 ユーザーで有効にできます。 

コンプライアンス記録ソリューションの統合機能は、コンプライアンス記録およびセキュリティ セッションの Ignite 2019 [でもMicrosoft Teamsされました](https://myignite.microsoft.com/archives/IG19-VCE40)。

## <a name="teams-interaction-recording-overview"></a>Teams記録の概要

対話記録の使用例は、画像に示すように、便利、機能、組織、および法律上のインターセプトの 4 つの主要な記録機能カテゴリに効果的に分けることができます。

> [!div class="mx-imgBorder"]
> ![操作の記録の理由と理由を示すスクリーンショット。](media/recording-taxonomy.png "画像には、記録カテゴリが表示されます。")

各カテゴリには、レコーディングの開始方法、記録の記録方法、記録の保存場所、通知を受け取るユーザー、アクセス権を制御するユーザー、保持の処理方法に関するさまざまな要件が含まれます。

| 種類                   | 利便性 (通常のTeams記録) | 組織 - 規制対象 (コンプライアンス記録) |
| ---------------------- | ------------------ | --------------- |
| イニシエーター              | ユーザー               | 管理者 (システム)  |
| Target                 | 通話/会議ごとに | ユーザーごと        |
| Storage所有者          | ユーザー               | コンプライアンス      |
| 通知が必要ですか? | はい                | はい             |
| アクセス所有者           | ユーザー               | コンプライアンス      |
| アイテム保持ポリシー      | 省略可能           | はい             |

Teamsは、会議やライブ [イベントの便利](./cloud-recording.md)で機能的な記録のためのさまざまな機能を提供します。 組織の記録とは、通話や会議に Teams を採用する組織が、関連する企業または規制ポリシーの要求に応じて、通話とオンライン会議を自動的に記録および保持するために、管理ポリシーを使用して自動的に記録およびキャプチャする必要がある場合に、それを可能に意味します。 このポリシーの下のユーザーは、Teams とのデジタル対話が記録されているが、記録を無効にできないので、対話が完了すると記録にアクセスできないという認識を受け取る必要があります。 記録は、電子情報開示、法的保持、その他の企業保有の使用に関するコンプライアンス担当者および法務担当者が利用できる組織のアーカイブの一部になります。

## <a name="example-user-needs"></a>ユーザーニーズの例

<table>
<thead>
<tr class="header">
<th>ペルシャ</th>
<th>ニーズ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>記録されたユーザー</td>
<td><ul>
<li><p>記録が進行中のときに通知を受け取る。</p></li>
<li><p>ポリシーやレコーダーのエラーが呼び出し動作の変更を引き起こしている場合は、通知を受け取る必要があります。</p></li>
</ul></td>
</tr>
<tr class="even">
<td>コミュニケーション管理者</td>
<td><ul>
<li><p>ユーザー/エンドポイントに記録ポリシーを適用/適用する理由と方法Teams理解します。</p></li>
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

> [!div class="mx-imgBorder"]
> ![チームのカスタム アプリ設定を示すスクリーンショット。](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "画像は、会議または通話がTeams受信した場合のフローを示しています。")

> [!NOTE]
> このソリューションは、ポリシー ベースのコンプライアンス記録を有効にするように特別に設計Teams。 このソリューションのその他の使用はサポートされません。

## <a name="recorder"></a>レコーダー

コンプライアンス記録ソリューションのコア コンポーネントは、レコーダーです。
レコーダーは、Microsoft の通信プラットフォームを使用し、[Microsoft](/graph/cloud-communications-concept-overview) Graph にアプリケーションとして登録するスケーラブルな Azure ベースのサービス (ボット) として構築されています。 この記録機能は、通話や会議Teamsプラットフォーム [API](/graph/api/resources/communications-api-overview) との直接やり取りを提供し、メディア インジェストのエンドポイントを提供します。

ボット [の構成、](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot) アプリ インスタンスの作成、コンプライアンス ポリシーの割り当て方法を示すサンプル コンプライアンス 記録アプリケーションを使用できます。 このサンプルには、着信通話ルーティングの処理、録音状態の変更、記録[](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244)されているユーザーの削除[](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138)など、特定の対話を記録するための API の使用状況の例も[示されています](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126)。
Graph API の詳細については、[updateRecordingStatus](/graph/api/call-updaterecordingstatus?tabs=http) と incomingContext に関するページ[を参照してください](/graph/api/resources/incomingcontext)。

レコーダー サービスの正確な実装はパートナーによって異なりますが、Teams からレコーダーへの待機時間を短縮するために、デプロイの高可用性と地理的分散を実現するために、複数のレコーダーをサポートするように設計する必要があります。 さらに、回復性と冗長性を念頭に置いてレコーダー自体を設計する必要があります。

パートナーは、コンプライアンス記録統合のすべての要件がサポートされるのを確認するために、認定のためのソリューションを提出する前に、Microsoft Graph 通信 API および SDK の最小必須リリース バージョンを Microsoft と確認する必要があります。

コンプライアンス記録シナリオの基本である 2 つの具体的な要件は次のとおりです。

- レコーダー ボットを Azure にデプロイする必要があります

- レコーダー ボットは、Azure の仮想マシンWindows実行する必要があります。

Azure および Windows VM の要件は Teams Bot コンポーネントにのみ適用されます。つまり、パートナーは、コンプライアンス記録に関する関連するパフォーマンス要件と機能要件を満たしている場合に、選択したプラットフォームの残りの部分を実装できます。

## <a name="compliance-recording-policy-assignment-and-provisioning"></a>コンプライアンス記録ポリシーの割り当てとプロビジョニング

IT 管理者は、コンプライアンス記録ポリシーを作成して割り当てると、どのユーザーを記録し、どのレコーダーを各ユーザーに使用されるかを決定できます。 記録者は、通信操作が行われたときに、これらのポリシーの構成に基づいて会話に参加するために自動的に招待されます。 コンプライアンス記録ポリシーは [Microsoft PowerShell](./teams-powershell-overview.md) を使用して管理され、テナント、ユーザー単位、およびセキュリティ グループ レベルで組織ごとに適用できます。 会議ポリシー、通話ポリシー、[グループ ポリシーに](./meeting-policies-overview.md)関する Microsoft Docs [の詳細を](./teams-calling-policy.md)[確認できます](./assign-policies-users-and-groups.md#assign-a-policy-to-a-group)。

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

   [「Set-CsTeamsComplianceRecordingPolicy」を参照してください](/powershell/module/skype/set-csteamscompliancerecordingpolicy)。

3. コンプライアンス記録ポリシーをユーザーに割り当てる。

   ```powershell
   PS C:\> Grant-CsTeamsComplianceRecordingPolicy -Identity testuser@contoso.onmicrosoft.com -PolicyName TestComplianceRecordingPolicy
   ```

   [Grant-CsTeamsComplianceRecordingPolicy に関するページを参照してください](/powershell/module/skype/grant-csteamscompliancerecordingpolicy)。

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

> [!NOTE]
> コンプライアンス記録は、電話会議モードの通話キューではサポートされていません。 転送モードの呼び出しキューを使用してください。
> ユーザーがインターネットの停止を経験し、SBA を使用して PSTN 通話を発信および受信している場合、コンプライアンス記録は機能しません。

## <a name="compliance-recording-for-teams-certification-programs"></a>認定プログラムのTeams記録

公開されている API を公開することで、パートナーは CCaaS ソリューションを開発して Teams と統合できるほか、microsoft ソリューションから期待される品質、互換性、信頼性を提供するために、参加している各パートナーのソリューションがテストおよび検証されたという保証を顧客に提供するために、Microsoft Teams 認定プログラムのコンプライアンス記録を開発しました。  

次のパートナーは、ソリューションの認定を受Microsoft Teams。<br/><br/>

|パートナー|ソリューションの Web サイト |
|:--|:--|
|ASC テクノロジ |[https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html](https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html) |
|AudioCodes |[https://online.audiocodes.com/smarttap-360-live-for-microsoft-teams](https://online.audiocodes.com/smarttap-360-live-for-microsoft-teams) |
|CallCabinet |[https://www.callcabinet.com/compliance-microsoft-teams-call-recording](https://www.callcabinet.com/compliance-microsoft-teams-call-recording ) |
|ダバー |[https://www.dubber.net/call-recording/](https://www.dubber.net/call-recording/) |
|Insightful テクノロジ |[https://insightfultechnology.com/teams/](https://insightfultechnology.com/teams/) |
|NICE |[https://www.niceactimize.com/compliance/ms-teams-recording.html](https://www.niceactimize.com/compliance/ms-teams-recording.html) |
|Numonix |[https://numonix.cloud](https://numonix.cloud)    |
|Oak Innovation |[https://www.oakinnovate.com/clarify](https://www.oakinnovate.com/clarify) |
|赤いボックス |[https://www.redboxvoice.com/compliance-recording-for-microsoft-teams](https://www.redboxvoice.com/compliance-recording-for-microsoft-teams)  |
|Theta Lake |[https://thetalake.com/integrations/microsoft/](https://thetalake.com/integrations/microsoft/) |
|Verint |[https://www.verba.com/solutions/microsoft-teams-recording](https://www.verba.com/solutions/microsoft-teams-recording) |
|Oak Innovation |[https://www.oakinnovate.com/clarify](https://www.oakinnovate.com/clarify) |

<br/>
次のパートナーは、ソリューションを認定するプロセスをMicrosoft Teams。<br/><br/>

|パートナー|ソリューションの Web サイト |
|:--|:--|
|Landis Technologies |[https://landistechnologies.com/](https://landistechnologies.com/) |
|Luware |[https://luware.com/en/solution/microsoft-teams-recording/](https://luware.com/en/solution/microsoft-teams-recording/) |


このリストは、パートナーが参加して認定条件を満たしたときに更新されます。

## <a name="next-steps"></a>次の手順

認定プログラムへの参加を希望しているベンダーの場合は、認定プログラムにメールを [Teamscategorypartner@microsoft.com](mailto:Teamscategorypartner@microsoft.com)。
