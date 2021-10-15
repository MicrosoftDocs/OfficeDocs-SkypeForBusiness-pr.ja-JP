---
title: Teams 管理センターで Teams テンプレートの使用を開始する
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: yinchang
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: チーム テンプレートと、管理センターでチーム テンプレートを管理するMicrosoft Teams説明します。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1f51c262e26613cf29a7dd2883afbf1cc6871b26
ms.sourcegitcommit: d23185cf6caeeeb055c36609e7c788a2b2e8d07d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2021
ms.locfileid: "60367519"
---
# <a name="get-started-with-team-templates-in-the-teams-admin-center"></a>Teams 管理センターで Teams テンプレートの使用を開始する

**カスタム テンプレートを作成する機能は、EDU のお客様ではまだサポートされていません。**

> [!NOTE]
> プライベート チャネルと感度ラベルは、チーム テンプレートでは現在サポートされていません。 プライベート チャネルの作成は、テンプレート定義には含まれません。 [テンプレート フローからチームを作成 **する** ] の [感度ラベル] オプションは、チームには適用されません。

## <a name="overview"></a>概要

Microsoft Teamsチーム テンプレートは、ビジネスの必要性やプロジェクトを中心に設計されたチームの構造の定義です。 管理者は、テンプレートを使用して、組織全体に一貫性のあるチームを簡単にデプロイできます。 テンプレートを使用すると、ユーザーは定義済みの設定、チャネル、アプリを使用して、豊富なコラボレーション スペースをすばやく作成できます。

チーム テンプレートは、Microsoft Teams または PowerShell を使用して管理できます。 用意されている事前構築済みのテンプレートを使用できます。また、独自のカスタム [テンプレートを作成することもできます](#create-your-own-team-templates)。 また、テンプレート[ポリシーを適用して](#apply-team-template-policies)、ユーザーが使用できるテンプレートを管理Teams。

この記事では、管理センターでチーム テンプレートを操作するTeams説明します。 テンプレートでサポートされているプロパティ、提供される事前構築済みのテンプレート、テンプレート サイズの制限、テンプレートの作成と管理の方法などについて説明します。

> [!NOTE]
> ユーザーは、[アプリ内の事前構築済](https://support.microsoft.com/office/create-a-team-from-a-template-a90c30f3-9940-4897-ab5b-988e69e4cd9c)みのチーム テンプレートまたはカスタム チーム テンプレートからTeamsできます。 開発者は、Microsoft Graph を使用して、事前に構築されたチーム テンプレートからチームを作成することもできます。 詳細については、「Microsoft Graph を使用してチーム テンプレートの[使用を開始する」を参照してください](get-started-with-teams-templates.md)。

## <a name="team-template-capabilities"></a>チーム テンプレートの機能

チーム内のほとんどのプロパティは、チーム テンプレートに含まれてサポートされます。 ただし、現在サポートされていないいくつかのプロパティと機能があります。 チーム テンプレートに含まれるものと、チーム テンプレートに含まれていない情報の概要を次に示します。

| **チーム テンプレートでサポートされるチームのプロパティ** | **チーム テンプレートでまだサポートされていないチームのプロパティ** |
| ------------------------------------------------ | -------------------------------------------------------- |
| テンプレートの種類 | チーム メンバーシップ |
| チーム名 | チームの画像 |
| チームの説明 | チャネル設定 |
| チームの可視性 (パブリックまたはプライベート) | コネクタ |
| チーム設定 (メンバー、ゲスト、@ メンションなど) | ファイルとコンテンツ |
| Autofavorite チャネル | |
| インストールされたアプリ | |
| ピン留めされたタブ | |

> [!NOTE]
> Microsoft Teams の今後のリリースでテンプレート機能を追加する予定なので、サポートされているプロパティに関する最新の情報を確認してください。

## <a name="pre-built-team-templates-in-the-teams-admin-center"></a>Teams 管理センターの事前構築済みのチーム テンプレート

管理センターで使用できる事前構築済みのチーム テンプレートをTeamsします。 事前構築済みのテンプレートは、特定の業界向けに作成したテンプレートです。 これらのテンプレートを表示するには、管理センターの左側のTeamsチーム テンプレート に移動Teams  >  **移動します**。

事前構築済みのテンプレートを複製できますが、編集は行えはありません。 事前構築済みのテンプレートのプロパティを変更する場合は、既存のテンプレートから新しいテンプレートを作成し、必要なプロパティを追加または削除できます。 一部のテンプレートの特定のプロパティを変更することはできません。

| テンプレートの種類 | TemplateId | このテンプレートに含まれるプロパティ |
| ------------------ | -------------- | ----------------------------------------------------- |
| 導入Office 365 |`com.microsoft.teams.template.AdoptOffice365`|  チャネル: <ul><li>全般</li> <li>お知らせ</li> <li>チャンピオン コーナー</li> <li>チーム フォーム</li><li>カレンダー</li></ul> アプリ: <ul><li>Wiki</li>  <li>チャネルカレンダー</li> <li>マイルストーン</li><li>情報</li></ul>|
| プロジェクトを管理する |`com.microsoft.teams.template.ManageAProject`| チャネル: <ul><li>全般</li> <li>お知らせ</li> <li>リソース</li> <li>計画</li></ul> アプリ:<ul><li>Wiki</li><li>OneNote</li><li>タスク</li><li>リスト</li><li>Power Automate</li></ul> |
| イベントを管理する|`com.microsoft.teams.template.ManageAnEvent` | チャネル: <ul><li>全般</li> <li>お知らせ</li> <li>予算</li> <li>コンテンツ</li><li>物流</li> <li>計画</li> <li> マーケティングと PR</li></ul> アプリ:<ul><li>Wiki</li><li>Web サイト</li> <li>YouTube</li> <li>タスク</li> <li>OneNote</li> <li>従業員のアイデア</li> <li>問題の報告者</li><li>Power Automate</li><li>情報</li><li>マイルストーン</li></ul> |
|従業員のオンボード|`com.microsoft.teams.template.OnboardEmployees` | チャネル: <ul><li>全般</li> <li>お知らせ</li> <li>従業員チャット</li> <li>トレーニング</li></ul>アプリ:<ul><li>Wiki</li><li>コミュニティ</li><li>タスク</li><li>従業員のアイデア</li><li>Power Automate</li><li>情報</li><li>マイルストーン</li></ul>|
|ヘルプ デスクを整理する| `com.microsoft.teams.template.OrganizeHelpDesk`|チャネル:<ul><li>全般</li><li>お知らせ</li><li>よくあるご質問 (FAQ)</li></ul>アプリ:<ul><li>Wiki</li><li>OneNote</li><li>タスク </li><li>称賛</li><li>問題の報告者</li><li>Power Automate</li><li>情報</li></ul> |
| 患者のケア| `com.microsoft.teams.template.healthcareWard`| チャネル<ul><li>全般</li><li>お知らせ</li><li>ハドル</li><li>ラウンド</li><li>人員配置</li><li>トレーニング</li></ul> アプリ: <ul><li>Wiki</li><li>リスト  </li><li>承認</li><li>情報</li><li>検査</li></ul>|
| 危機的なコミュニケーション |`com.microsoft.teams.template.CollaborateOnAGlobalCrisisOrEvent`| チャネル: <ul><li>全般<li>お知らせ</li><li>世界のニュース</li><li>内部 comms</li><li>外部通信</li><li>承認要求</li><li>顧客のエスカレーション</li><li>エグゼクティブの更新</li><li>計画</li><li>物流</li></ul>アプリ: <ul><li>Web サイト</li><li>タスク</li><li>問題の報告者</li><li>承認</li><li>情報</li><li>OneNote</li><li>Power Automate</li><li>SharePoint</li></ul>|
|銀行の支店| `com.microsoft.teams.template.CollaborateWithinABankBranch`|チャネル <ul><li>全般<li>お知らせ</li><li>ハドル</li><li>顧客との会議</li><li>承認要求 </li><li>指導</li><li>スキルの習得</li><li>融資の処理</li><li>顧客の苦情</li><li>称賛</li><li>楽しい機能</li><li>コンプライアンス</li></ul>アプリ:<ul><li>称賛 </li><li>問題の報告者</li><li>Wiki</li><li>カレンダー</li><li>承認</li><li>情報</li><li>アイデア</li></ul>|
|インシデント対応| `com.microsoft.teams.template.CoordinateIncidentResponse`|チャネル: <ul><li>全般<li>お知らせ</li><li>物流</li><li>計画</li><li>回復</li><li>緊急</li></ul> アプリ: <ul><li>Wiki</li><li>Excel</li><li>OneNote</li><li>SharePoint</li><li>タスク</li> <li>承認</li> <li>検査</li> <li>Power Automate</li><li>情報</li><li>マイルストーン</li></ul>|
|病院| `com.microsoft.teams.template.healthcareHospital` |チャネル <ul><li>全般</li><li>お知らせ</li><li>コンプライアンス</li><li>親権</li><li>人事管理</li><li>薬局</li></ul> アプリ: <ul><li>Wiki</li><li>リスト</li><li>タスク</li><li>承認</li><li>Shifts</li><li>情報</li><li>検査</li><li>アイデア</li></ul>|
|店舗を整理する| `com.microsoft.teams.template.retailStore` |チャネル: <ul><li>全般<li>シフトのハンドオフ</li><li>ストアの準備状況</li><li>学習</li></ul> アプリ: <ul><li>Wiki</li><li>タスク</li><li>Shifts</li><li>検査</li></ul>|
|マネージャー用小売業| `com.microsoft.teams.template.retailManagerCollaboration` |チャネル <ul><li>全般<li>操作</li><li>学習</li></ul> アプリ: <ul><li>Wiki</li><li>タスク</li><li>検査</li></ul>|
|品質と安全性 |`com.microsoft.teams.template.QualitySafety`|チャネル: <ul><li>全般<li>お知らせ</li><li>リーダーシップ</li><li>メンテナンス</li><li>生産ライン 1</li><li>生産ライン 2</li><li>生産ライン 3</li><li>正常性と安全性</li><li>トレーニング</li><li>楽しい機能</li></ul> アプリ: <ul><li>Wiki</li><li>タスク</li> <li>問題の報告者</li> <li>検査</li> </ul>|

### <a name="team-templates-by-category-and-industry"></a>カテゴリと業界別のチーム テンプレート

業界で事前構築されたテンプレートを使用する方法の詳細については、以下を参照してください。

- [財務チームテンプレート](financial-teams-templates-in-the-admin-console.md)
- [一般的なチーム テンプレート](general-teams-templates-in-the-admin-console.md)
- [政府機関のチーム テンプレート](government-teams-templates-in-the-admin-console.md)
- [医療チームのテンプレート](expand-teams-across-your-org/healthcare/healthcare-templates-admin-console.md)
- [製造チーム テンプレート](manufacturing-teams-templates-in-the-admin-console.md)
- [リテール チーム テンプレート](retail-teams-templates-in-the-admin-console.md)

## <a name="team-template-size-limits"></a>チーム テンプレートのサイズ制限

テンプレートは、特定の数のチャネル、タブ、アプリに制限されます。

 > [!Note]
 > テンプレートから作成したチャネル、タブ、アプリをチームに追加できます。

|機能 | 制限|
|-|-|
|テンプレートあたりのチャネル数 | 15 |
|テンプレートのチャネルごとのタブ数 | 20 |
|テンプレートあたりのアプリ数 | 50|
|||

詳細については、 の制限[と仕様に関するページをTeams。](limits-specifications-teams.md)

## <a name="manage-team-templates"></a>チーム テンプレートを管理する

### <a name="manage-team-templates-in-the-teams-admin-center"></a>Teams 管理センターでチーム テンプレートを管理する

#### <a name="view-team-templates"></a>チーム テンプレートを表示する

チーム テンプレートを表示するには、管理センターの左側のTeamsチーム テンプレート に移動Teams  >  **移動します**。 テンプレートを選択すると、含まれるチャネルやアプリなど、詳細が表示されます。

#### <a name="create-your-own-team-templates"></a>独自のチーム テンプレートを作成する

独自のカスタム テンプレートは、ゼロから作成したり、既存のチームから作成したり、既存のテンプレートから作成したりすることができます。 詳細については、次を参照してください。

- [カスタム チーム テンプレートを作成する](create-a-team-template.md)
- [既存のチームからテンプレートを作成する](create-template-from-existing-team.md)
- [既存のチーム テンプレートからチーム テンプレートを作成する](create-template-from-existing-template.md)

#### <a name="apply-team-template-policies"></a>チーム テンプレート ポリシーを適用する

チームを作成するための Teams でユーザーに表示されるテンプレートを[](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b)制御するには、テンプレート ポリシーを設定し、組織内のユーザーとグループに割り当てできます。 詳細については、「管理センターでチーム テンプレート[を管理する」Teams参照してください](templates-policies.md)。

### <a name="manage-team-templates-using-powershell"></a>PowerShell を使用してチーム テンプレートを管理する

PowerShell でテンプレートを管理するには、次のコマンドレットを使用します。

- [Get-CsTeamTemplate](/powershell/module/teams/get-csteamtemplate?view=teams-ps)
- [Get-CsTeamTemplateList](/powershell/module/teams/get-csteamtemplatelist?view=teams-ps)
- [New-CsTeamTemplate](/powershell/module/teams/new-csteamtemplate?view=teams-ps)
- [Remove-CsTeamTemplate](/powershell/module/teams/remove-csteamtemplate?view=teams-ps)
- [Update-CsTeamTemplate](/powershell/module/teams/update-csteamtemplate?view=teams-ps)

## <a name="related-articles"></a>関連記事

- [テンプレートからチームを作成する](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b)
- [Microsoft Graph を使用して、チーム テンプレートの使用を開始する](get-started-with-teams-templates.md)
- [チームを複製する](/graph/api/team-clone?view=graph-rest-1.0&tabs=http)
