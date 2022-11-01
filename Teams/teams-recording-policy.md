---
title: '&会議を呼び出すための Teams ポリシー ベースの記録の概要'
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
description: '&会議を呼び出すための Teams ポリシーベースの記録について説明します'
f1.keywords:
- CSH
ms.custom:
- Adopt
- seo-marvel-mar2020
ms.collection:
- Teams_ITAdmin_Adopt
- M365-collaboration
- tier3
- purview-compliance
appliesto:
- Microsoft Teams
ms.openlocfilehash: 088515e6d9d4fe9e6dc893d736f7baac1148c731
ms.sourcegitcommit: 86b9503eb0085e23176cb346767f880ea3a73e77
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2022
ms.locfileid: "68808286"
---
# <a name="introduction-to-teams-policy-based-recording-for-callings--meetings"></a>通話&会議の Teams ポリシー ベースの記録の概要

ポリシー ベースの記録を使用すると、電話やオンライン会議を自動的に記録し、関連する企業または規制ポリシーで必要に応じて後続の処理と保持のためにキャプチャする必要がある場合に、管理ポリシーを使用して、通話と会議に Microsoft Teams を採用する組織が規定できます。

Teams は、Teams 通信を構成、管理、記録、格納、分析するためのエンドツーエンド ソリューションを提供するために必要なプラットフォーム機能、ユーザー エクスペリエンス、管理インターフェイスなど、サードパーティの記録ソリューションの統合をサポートするように強化されました。 機能強化には、通信プラットフォーム API と記録用のイベントが含まれます。これには、次の機能が用意されています。

- オーディオ、ビデオ、画面共有、チャットでサポートされているすべてのエンドポイントと、デバイス間でシームレスで高品質のメディア キャプチャ。

- Teams ユーザーとサポートされている通話エンドポイント (Teams、Teams Mobile、Skype for Business、PSTN) 間の対話キャプチャのサポート

- 既存の Teams 管理通話と会議ツールとポリシーとの統合を含む、コンプライアンス記録用の新しい管理ポリシー

コンプライアンス記録は、Microsoft 365 A3/A5/E3/E5/Business Premium および Office 365 A3/A5/E3/E5 ユーザーで有効にすることができます。 

コンプライアンス記録ソリューション統合機能は、 [コンプライアンス記録と Microsoft Teams セッション](https://myignite.microsoft.com/archives/IG19-VCE40)の Ignite 2019 でも確認されました。

## <a name="teams-interaction-recording-overview"></a>Teams の対話記録の概要

対話記録のユース ケースは、画像に示すように、記録機能の 4 つの主要なカテゴリ (利便性、機能、組織、および合法的傍受) に効果的に分けることができます。

> [!div class="mx-imgBorder"]
> ![操作の内容と理由を記録しているスクリーンショット。](media/recording-taxonomy.png "画像は、記録カテゴリを示しています。")

各カテゴリには、記録の開始方法、記録内容、記録の保存場所、通知を受け取るユーザー、アクセスを制御するユーザー、保持の処理方法に関するさまざまな要件が伴います。

| 種類                   | 利便性 (通常の Teams レコーディング) | 組織 - 規制 (コンプライアンス記録) |
| ---------------------- | ------------------ | --------------- |
| イニシエーター              | ユーザー               | 管理 (システム)  |
| Target                 | 通話ごと/会議 | ユーザーごと        |
| ストレージ所有者          | ユーザー               | コンプライアンス      |
| 通知が必要ですか? | Yes                | Yes             |
| アクセス所有者           | ユーザー               | コンプライアンス      |
| アイテム保持ポリシー      | 省略可能           | Yes             |

Teams には、会議やライブ イベントの [便利](./cloud-recording.md) で機能的な記録のためのさまざまな機能が用意されています。 組織の記録とは、通話やオンライン会議を自動的に記録し、関連する企業または規制ポリシーで必要に応じて後続の処理と保持のためにキャプチャする必要がある場合に、管理ポリシーを使用して、Teams を呼び出しおよび会議に採用する組織が規定できるようにすることを意味します。 このポリシーの下のユーザーは、Teams とのデジタル対話が記録されているが、記録を無効にできず、操作が完了すると記録にアクセスできないことを認識します。 記録は、電子情報開示、訴訟ホールド、およびその他の企業リテンション期間の使用に関するコンプライアンス担当者および法務担当者が利用できる組織アーカイブの一部になります。

## <a name="example-user-needs"></a>ユーザーのニーズの例

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
<li><p>記録中に通知を受け取ります。</p></li>
<li><p>ポリシーやレコーダーのエラーによって呼び出し動作が変更されている場合に通知されます。</p></li>
</ul></td>
</tr>
<tr class="even">
<td>コミュニケーション管理者</td>
<td><ul>
<li><p>Teams ユーザー/エンドポイントに記録ポリシーを適用/適用する理由と方法について説明します。</p></li>
<li><p>組織の Teams 記録ポリシーを構成して管理します。</p></li>
<li><p>Teams の通話と会議に関する記録関連の問題を監視およびトラブルシューティングします。</p></li>
<li><p>使用、品質、信頼性に関する運用分析で内部コンプライアンス責任者をサポートします。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td>コンプライアンス責任者</td>
<td><ul>
<li><p>適切な地域の境界でコンプライアンス義務を満たすために必要な方法ですべての Teams 通信を収集します。</p></li>
<li><p>コミュニケーション関連のメタデータまたは対話コンテンツに基づいて相互作用を検索します。 一般的な例を次に示します。</p>
<ul>
<li><p><strong>メタデータ</strong> - 参加者、時刻、方向、ダイヤル番号、配信元番号、カスタム ビジネス データ</p></li>
<li><p><strong>コンテンツ</strong> – 文字起こし、センチメント、音声学、関連する相互作用</p></li>
</ul></li>
<li><p>収集された通信を分析して操作します。収集中の対話を監視する機能も含まれます。</p></li>
<li><p>収集された通信のセキュリティを確保し、すべての段階で改ざんを防ぎます。</p></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="solution-architecture-overview"></a>ソリューション アーキテクチャの概要

コンプライアンス記録ソリューションは、次の図に示すように Teams と統合されています。

> [!div class="mx-imgBorder"]
> ![チームのカスタム アプリ設定を示すスクリーンショット。](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "この画像は、Teams の会議または通話が送受信されたときのフローを示しています。")

> [!NOTE]
> このソリューションは、Teams でのポリシー ベースのコンプライアンス記録を有効にするために特別に設計されています。 このソリューションのその他の使用はサポートされません。

## <a name="recorder"></a>レコーダー

コンプライアンス記録ソリューションのコア コンポーネントは、レコーダーです。
レコーダーは、 [Microsoft の通信プラットフォームを使用](/graph/cloud-communications-concept-overview) し、Microsoft Graph にアプリケーションとして登録するスケーラブルな Azure ベースのサービス (ボット) として構築されています。 レコーダーは、Teams 呼び出しと会議 [通信プラットフォーム API との](/graph/api/resources/communications-api-overview) 直接的な対話を提供し、メディア インジェストのエンドポイントを提供します。

[サンプル コンプライアンス レコーダー アプリケーションを使用して、](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot)ボットを構成し、アプリ インスタンスを作成し、コンプライアンス ポリシーを割り当てる方法を示します。 このサンプルには、 [着信呼び出し](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244) ルーティングの処理、 [記録状態の変更](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138)、記録されているユーザーの削除など、特定 [の操作を記録](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126)するための API の使用例もあります。
特定の API に関するグラフ ドキュメントについては、 [updateRecordingStatus](/graph/api/call-updaterecordingstatus?tabs=http) と [incomingContext](/graph/api/resources/incomingcontext) に関するページを参照してください。

レコーダー サービスの正確な実装はパートナーによって異なりますが、Teams からレコーダーへの待機時間を短縮するために、デプロイの高可用性と地理的な分散を実現するために、複数のレコーダーをサポートするように設計する必要があります。 さらに、レコーダー自体が回復性と冗長性を念頭に置いて設計されることが期待されます。

パートナーは、コンプライアンス記録統合のすべての要件がサポートされていることを確認するために、認定ソリューションを提出する前に、Microsoft Graph 通信 API と SDK の最低限必要なリリース バージョンを Microsoft と確認する必要があります。

コンプライアンス記録シナリオの基礎となる 2 つの特定の要件は次のとおりです。

- レコーダー ボットは Azure にデプロイする必要があります

- レコーダー ボットは、Azure の Windows VM で実行する必要があります

Azure と Windows VM の要件は Teams Bot コンポーネントにのみ適用されます。つまり、コンプライアンス記録に関連するパフォーマンスと機能の要件を満たすことができる場合、パートナーは選択したプラットフォームの残りの部分を実装できます。

## <a name="compliance-recording-policy-assignment-and-provisioning"></a>コンプライアンス記録ポリシーの割り当てとプロビジョニング

IT 管理者は、コンプライアンス記録ポリシーを作成して割り当てることで、記録するユーザーと各ユーザーに使用するレコーダーを決定できます。 レコーダーは、通信の対話が行われるとき、これらのポリシーの構成に基づいて会話に参加するように自動的に招待されます。 コンプライアンス記録ポリシーは [Microsoft PowerShell](./teams-powershell-overview.md) を使用して管理され、各組織のテナント、ユーザーごと、およびセキュリティ グループ レベルで適用できます。 Microsoft Learn for [Meeting ポリシー](./meeting-policies-overview.md)、 [通話ポリシー](./teams-calling-policy.md) 、グループ ポリシーの詳細については、こちらをご覧  [ください](./assign-policies-users-and-groups.md#assign-a-policy-to-a-group)。

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

   [「Set-CsTeamsComplianceRecordingPolicy」を参照](/powershell/module/skype/set-csteamscompliancerecordingpolicy)してください。

3. コンプライアンス記録ポリシーをユーザーに割り当てます。

   ```powershell
   PS C:\> Grant-CsTeamsComplianceRecordingPolicy -Identity testuser@contoso.onmicrosoft.com -PolicyName TestComplianceRecordingPolicy
   ```

   [「Grant-CsTeamsComplianceRecordingPolicy」を](/powershell/module/skype/grant-csteamscompliancerecordingpolicy)参照してください。

   ```powershell
   PS C:\> Get-CsOnlineUser testuser@contoso.onmicrosoft.com | select SipAddress, TenantId, TeamsComplianceRecordingPolicy | fl

   UserPrincipalName              : testuser@contoso.onmicrosoft.com
   TenantId                       : 5b943d7c-5e14-474b-8237-5022eb8e0dc9
   TeamsComplianceRecordingPolicy : TestComplianceRecordingPolicy
   ```

## <a name="user-experiences"></a>ユーザー エクスペリエンス

通知のサポートは、Teams クライアント エクスペリエンスを使用して有効になります。 エクスペリエンスには、ビジュアルまたはオーディオを使用できます。

**Teams クライアント - 視覚的な通知**
- デスクトップ/Web
- モバイル (iOS/Android)
- Teams 電話
- Teams ルーム

**その他のエンドポイント - 音声通知**
- SIP 電話
- Skype for Business
- 電話会議 (ダイヤルイン番号の既定またはユーザーが選択した言語での音声通知)
- PSTN 発信者 (Teams ユーザーの既定の言語での音声通知)

> [!NOTE]
> コンプライアンス記録は、会議モードの通話キューではサポートされていません。 転送モードの呼び出しキューを使用してください。
> ユーザーがインターネットの停止を経験し、SBA を使用して PSTN 通話を発信および受信している場合、コンプライアンス記録は機能しません。

## <a name="compliance-recording-for-teams-certification-programs"></a>Teams 認定プログラムのコンプライアンス記録

パートナーが CCaaS ソリューションを開発して Teams と統合できるようにする公開 API を公開することに加えて、Microsoft Teams 認定プログラムのコンプライアンス記録を開発し、各参加パートナーのソリューションがテストおよび検証され、Microsoft ソリューションから期待される品質、互換性、信頼性を提供することを保証します。  

次のパートナーは、Microsoft Teams のソリューションを認定しています。<br/><br/>

|パートナー|ソリューションの Web サイト |
|:--|:--|
|ASC テクノロジ |[https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html](https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html) |
|AudioCodes |[https://online.audiocodes.com/smarttap-360-live-for-microsoft-teams](https://online.audiocodes.com/smarttap-360-live-for-microsoft-teams) |
|CallCabinet |[https://www.callcabinet.com/compliance-microsoft-teams-call-recording](https://www.callcabinet.com/compliance-microsoft-teams-call-recording ) |
|Dubber |[https://www.dubber.net/call-recording/](https://www.dubber.net/call-recording/) |
|Insightful テクノロジ |[https://insightfultechnology.com/teams/](https://insightfultechnology.com/teams/) |
|Mida Solutions |[https://www.midasolutions.com/recorder-for-teams/](https://www.midasolutions.com/recorder-for-teams/) |
|NICE Engage |[https://www.nice.com/products/workforce-engagement/call-recording/air-and-engage](https://www.nice.com/products/workforce-engagement/call-recording/air-and-engage) |
|NICE NTR |[https://www.niceactimize.com/compliance/ms-teams-recording.html](https://www.niceactimize.com/compliance/ms-teams-recording.html) |
|Numonix |[https://numonix.cloud](https://numonix.cloud)    |
|オークイノベーション |[https://www.oakinnovate.com/clarify](https://www.oakinnovate.com/clarify) |
|赤いボックス |[https://www.redboxvoice.com/compliance-recording-for-microsoft-teams](https://www.redboxvoice.com/red-box-partners/microsoft-integration/compliance-recording-for-microsoft-teams)  |
|テタ湖 |[https://thetalake.com/integrations/microsoft/](https://thetalake.com/integrations/microsoft/) |
|Verint |[https://www.verba.com/solutions/microsoft-teams-recording](https://www.verba.com/solutions/microsoft-teams-recording) |
|オークイノベーション |[https://www.oakinnovate.com/clarify](https://www.oakinnovate.com/clarify) |

<br/>
次のパートナーは、Microsoft Teams のソリューションを認定する過程にあります。<br/><br/>

|パートナー|ソリューションの Web サイト |
|:--|:--|
|GuardRec |[https://www.guardrec.com/en/teams-compliance-recording/](https://www.guardrec.com/en/teams-compliance-recording/) |
|Landis Technologies |[https://landistechnologies.com/](https://landistechnologies.com/) |
|Luware |[https://luware.com/en/solution/microsoft-teams-recording/](https://luware.com/en/solution/microsoft-teams-recording/) |
|Redwood Technologies |[https://www.contentguru.com/en-gb/solutions/needs/compliance-recording-MS-Teams/](https://www.contentguru.com/en-gb/solutions/needs/compliance-recording-MS-Teams/) |


このリストは、パートナーが参加して認定条件を満たしたときに更新されます。


## <a name="next-steps"></a>次の手順

認定プログラムに参加しようとしているベンダーの場合は、次の手順として [このフォーム](https://aka.ms/CallingPlatformIntake) に入力します。 追加のコンテキストと詳細を指定する必要がある場合は、 [Teamscategorypartner@microsoft.com](mailto:Teamscategorypartner@microsoft.com) にメールを送信します。
