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
- m365-frontline
- tier2
- highpri
description: チーム テンプレートと、Microsoft Teams 管理センターでチーム テンプレートを管理する方法について説明します。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- chat-teams-channels-revamp
appliesto:
- Microsoft Teams
ms.openlocfilehash: 063f84ffc0b34c99ff937c4a5496d5df3be2ddf5
ms.sourcegitcommit: 387141880842c93ecf4a936aaa26342a3f996259
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2023
ms.locfileid: "69778987"
---
# <a name="get-started-with-team-templates-in-the-teams-admin-center"></a>Teams 管理センターで Teams テンプレートの使用を開始する

**カスタム テンプレートを作成する機能は、EDU のお客様にはまだサポートされていません。**

> [!NOTE]
> - プライベート チャネルと共有チャネルは現在、チーム テンプレートではサポートされていません。 プライベートおよび共有チャネルの作成は、テンプレート定義には含まれません。
>
> - GCC 環境のチーム テンプレートでは、秘密度ラベルはサポートされていません。 [テンプレートからチームを作成する] フローの秘密度ラベル オプションは、チームには適用されません。

## <a name="overview"></a>概要

Microsoft Teams のチーム テンプレートは、ビジネス ニーズまたはプロジェクトを中心に設計されたチームの構造の定義です。 管理者は、テンプレートを使用して、組織全体で一貫性のあるチームを簡単にデプロイできます。 テンプレートを使用すると、ユーザーは定義済みの設定、チャネル、アプリを使用して、豊富なコラボレーション スペースをすばやく作成できます。

チーム テンプレートは、Microsoft Teams 管理センターまたは PowerShell を使用して管理できます。 用意されている事前構築済みのテンプレートを使用できます。また、 [独自のカスタム テンプレートを作成](#create-your-own-team-templates)することもできます。 [また、テンプレート ポリシーを適用して、](#apply-team-template-policies)Teams のユーザーが使用できるテンプレートを制御することもできます。

この記事では、Teams 管理センターでのチーム テンプレートの操作の概要について説明します。 テンプレートでサポートされているプロパティ、用意されている事前構築済みのテンプレート、テンプレートサイズの制限、テンプレートの作成と管理方法などについて説明します。

> [!NOTE]
> ユーザーは、 [Teams アプリの事前構築済みまたはカスタム チーム テンプレートからチームを作成](https://support.microsoft.com/office/create-a-team-from-a-template-a90c30f3-9940-4897-ab5b-988e69e4cd9c) できます。 開発者は、Microsoft Graph を使用して、事前に構築されたチーム テンプレートまたはカスタム チーム テンプレートからチームをプログラムで作成することもできます。 詳細については、「 [Microsoft Graph を使用したチーム テンプレートの](get-started-with-teams-templates.md)概要」を参照してください。

## <a name="team-template-capabilities"></a>チーム テンプレートの機能

チームのほとんどのプロパティは、チーム テンプレートによって含まれ、サポートされています。 ただし、現在サポートされていないプロパティと機能がいくつかあります。 含まれている内容と、チーム テンプレートに含まれていない内容の概要を次に示します。

| **チーム テンプレートでサポートされるチーム プロパティ** | **チーム テンプレートでまだサポートされていないチーム プロパティ** |
| ------------------------------------------------ | -------------------------------------------------------- |
| テンプレートの種類 | チーム メンバーシップ |
| チーム名 | チーム画像 |
| チームの説明 | チャネル設定 |
| チームの可視性 (パブリックまたはプライベート) | コネクタ |
| チーム設定 (メンバー、ゲスト、@ メンションなど) | ファイルとコンテンツ |
| Autofavorite チャネル | |
| インストールされたアプリ | |
| ピン留めされたタブ | |

> [!NOTE]
> Microsoft Teams の今後のリリースではさらにテンプレート機能を追加する予定なので、サポートされているプロパティに関する最新の情報を確認してください。

## <a name="pre-built-team-templates-in-the-teams-admin-center"></a>Teams 管理センターの事前構築済みチーム テンプレート

Teams 管理センターで使用できる事前構築済みのチーム テンプレートを次に示します。 事前構築済みのテンプレートは、特定の業界向けに作成したテンプレートです。 これらのテンプレートを表示するには、Teams 管理センターの左側のナビゲーションで、[**Teams チーム** >  テンプレート] に移動 **します**。

事前構築済みのテンプレートを複製することはできますが、編集することはできません。 事前構築済みテンプレートのプロパティを変更する場合は、既存のテンプレートから新しいテンプレートを作成し、必要なプロパティを追加または削除できます。 一部のテンプレートの特定のプロパティは変更できないことに注意してください。

> [!NOTE]
> アスタリスク (*) は、テンプレートが *Microsoft 365 接続テンプレート* であることを示します。 ユーザーがテンプレートを使用してチームを作成すると、接続された SharePoint テンプレートがサイトとチームに適用されます。 ページ、リスト、Power Platform の統合などの SharePoint コンポーネントは自動的に追加され、チームの [全般] チャネルにタブとしてピン留めされます。 ユーザーは、Teams 内から直接これらのページとリストを編集できます。
>
> SharePoint テンプレートの詳細については、「 [SharePoint サイト テンプレートの適用とカスタマイズ](https://support.microsoft.com/office/apply-and-customize-sharepoint-site-templates-39382463-0e45-4d1b-be27-0e96aeec8398#ID0EDBJ=Team_site_templates)」を参照してください。

>[!div class="mx-tdBreakAll"]
>| テンプレートの種類 | TemplateId | このテンプレートに含まれるプロパティ |
>| ------------------ | -------------- | ----------------------------------------------------- |
>|プロジェクトの管理* |`com.microsoft.teams.template.ManageAProject`| チャネル: <ul><li>全般</li> <li>お知らせ</li> <li>リソース</li> <li>計画</li></ul> アプリ:<ul><li>承認</li><li>情報</li><li>リスト<ul><li>プロジェクト トラッカー</li><li>イシュー トラッカー</li></ul></li><li>マイルス トーン</li><li>OneNote</li><li>Power Automate</li><li>SharePoint ページ<ul><li>当社のサイト</li></ul></li><li>Planner と To Do によるタスク</li><li>Wiki</li></ul> |
|イベントの管理*|`com.microsoft.teams.template.ManageAnEvent` | チャネル: <ul><li>全般</li> <li>お知らせ</li> <li>予算</li> <li>コンテンツ</li><li>物流</li> <li>計画</li> <li> マーケティングと PR</li></ul> アプリ:<ul><li>承認</li><li>情報</li> <li>従業員のアイデア</li><li>リスト<ul><li>コンテンツ スケジューラ</li></ul></li><li>マイルス トーン</li> <li>OneNote</li> <li>Power Automate</li> <li>SharePoint ページ<ul><li>当社のサイト</li><li>イベントについて</li></ul><li>Planner と To Do によるタスク</li><li>Wiki</li> |
|従業員のオンボード*|`com.microsoft.teams.template.OnboardEmployees` | チャネル: <ul><li>全般</li> <li>お知らせ</li> <li>従業員チャット</li> <li>トレーニング</li></ul>アプリ:<ul><li>情報</li><li>従業員のアイデア</li><li>リスト<ul><li>オンボード チェックリスト</li></ul></li><li>マイルス トーン</li><li>Power Automate</li> <li>SharePoint ページ<ul><li>はじめに</li><li>トレーニング</li></ul><li>Planner と To Do によるタスク</li><li>Viva エンゲージ</li><li>Wiki</li></ul>|
|Office 365を採用する |`com.microsoft.teams.template.AdoptOffice365`|  チャネル: <ul><li>全般</li> <li>お知らせ</li> <li>チャンピオンズ コーナー</li> <li>チーム フォーム</li><li>カレンダー</li></ul> アプリ: <ul><li>情報</li>  <li>チャネルカレンダー</li> <li>マイルス トーン</li><li>Wiki</li></ul>|
|ヘルプ デスクの整理*| `com.microsoft.teams.template.OrganizeHelpDesk`|チャネル:<ul><li>全般</li><li>お知らせ</li><li>よくあるご質問 (FAQ)</li></ul>アプリ:<ul><li>Issue Reporting</li><li>リスト<ul><li>デバイス</li><li>チケット</li></ul></li><li>OneNote</li><li>Power Automate</li><li>SharePoint ページ<ul><li>当社のサイト</li><li>よく寄せられる質問</li></ul></li><li>Planner と To Do によるタスク</li><li>Wiki</li></ul> |
|インシデント対応| `com.microsoft.teams.template.CoordinateIncidentResponse`|チャネル: <ul><li>全般<li>お知らせ</li><li>物流</li><li>計画</li><li>回復</li><li>緊急</li></ul> アプリ: <ul><li>承認</li><li>情報</li><li>Excel</li><li>検査</li><li>マイルス トーン</li> <li>OneNote</li> <li>Power Automate</li> <li>SharePoint</li><li>Planner と To Do によるタスク</li><li>Wiki</li></ul>|
|危機通信* |`com.microsoft.teams.template.CollaborateOnAGlobalCrisisOrEvent`| チャネル: <ul><li>全般<li>お知らせ</li><li>エグゼクティブ更新プログラム</li><li>計画</li><li>物流</li></ul>アプリ: <ul><li>承認</li><li>Issue Reporting</li><li>リスト<ul><li>コンテンツ スケジューラ</li><li>プロジェクト計画</li></ul></li><li>OneNote</li><li>Power Automate</li><li>SharePoint ページ<ul><li>当社のサイト</li><li>最新の更新プログラム</li></ul><li>Planner と To Do によるタスク</li>|
|ストアの管理*| `com.microsoft.teams.template.retailStore` |チャネル: <ul><li>全般<li>Shift ハンドオフ</li><li>ストアの準備</li><li>学習</li></ul> アプリ: <ul><li>承認</li><li>検査</li><li>リスト<ul><li>インベントリ一覧</li></ul></li><li>SharePoint ページ<ul><li>当社の店舗</li></ul></li><li>Shifts</li><li>Planner と To Do によるタスク</li><li>Wiki</li></ul>|
|銀行支店| `com.microsoft.teams.template.CollaborateWithinABankBranch`|チャネル: <ul><li>全般<li>お知らせ</li><li>ハドル</li><li>顧客会議</li><li>承認要求 </li><li>指導</li><li>スキル開発</li><li>ローン処理</li><li>顧客からの苦情</li><li>称賛</li><li>楽しいもの</li><li>コンプライアンス</li></ul>アプリ:<ul><li>承認</li><li>情報</li><li>チャネルカレンダー</li><li>従業員のアイデア</li><li>Issue Reporting</li><li>称賛</li><li>Shifts</li><li>Wiki</li></ul>|
|患者ケア| `com.microsoft.teams.template.healthcareWard`| チャネル:<ul><li>全般</li><li>お知らせ</li><li>ハドル</li><li>ラウンド</li><li>人員配置</li><li>トレーニング</li></ul> アプリ: <ul><li>承認</li><li>情報</li><li>検査</li><li>リスト</li><li>Shifts</li><li>Planner と To Do によるタスク</li><li>Wiki</li></ul>|
|病院| `com.microsoft.teams.template.healthcareHospital` |チャネル <ul><li>全般</li><li>お知らせ</li><li>コンプライアンス</li><li>親権</li><li>人事</li><li>薬局</li></ul> アプリ: <ul><li>承認</li><li>情報</li><li>従業員のアイデア</li><li>検査</li><li>リスト</li><li>Shifts</li><li>Planner と To Do によるタスク</li><li>Wiki</li></ul>|
|品質と安全性 |`com.microsoft.teams.template.QualitySafety`|チャネル: <ul><li>全般</li><li>リーダーシップ</li><li>メンテナンス</li><li>生産ライン 1</li><li>生産ライン 2</li><li>生産ライン 3</li><li>健康と安全</li><li>トレーニング</li><li>楽しいもの</li></ul> アプリ: <ul><li>承認</li><li>検査</li><li>Issue Reporting</li><li>Shifts</li> <li>Planner と To Do によるタスク</li> <li>Wiki</li> </ul>|
|マネージャー向け小売*| `com.microsoft.teams.template.retailManagerCollaboration` |チャネル: <ul><li>全般<li>操作</li><li>学習</li></ul> アプリ: <ul><li>承認</li><li>検査</li><li>SharePoint ページ<ul><li>当社の店舗</li></ul></li><li>Planner と To Do によるタスク</li><li>Wiki</li></ul>|
|ボランティアの管理| `com.microsoft.teams.template.ManageVolunteers` |チャネル: <ul><li>全般<li>お知らせ</li><li>レポート</li><li>ボランティアの管理</li><li>エンゲージメントの機会</li><li>ボランティア オンボーディング</li></ul> アプリ: <ul><li>OneNote</li><li>Power Apps</li><li>Power BI</li><li>SharePoint</li><li>Planner と To Do によるタスク</li><li>Web サイト</li><li>YouTube</li></ul>|
|現場でのコラボレーション| `com.microsoft.teams.template.Frontline` |チャネル: <ul><li>全般<li>お知らせ</li><li>Shift ハンドオフ</li><li>操作</li><li>学習</li></ul> アプリ: <ul><li>承認</li><li>Issue Reporting</li><li>リスト</li><li>称賛</li><li>Shifts</li><li>Planner と To Do によるタスク</li></ul>|

### <a name="team-templates-by-category-and-industry"></a>カテゴリ別および業界別のチーム テンプレート

業界で事前構築済みのテンプレートを使用する方法の詳細については、次を参照してください。

- [一般的なチーム テンプレート](general-teams-templates-in-the-admin-console.md)
- [財務チーム テンプレート](financial-teams-templates-in-the-admin-console.md)
- [政府機関チーム テンプレート](government-teams-templates-in-the-admin-console.md)
- [医療チーム テンプレート](expand-teams-across-your-org/healthcare/healthcare-templates-admin-console.md)
- [製造チーム テンプレート](manufacturing-teams-templates-in-the-admin-console.md)
- [非営利団体チーム テンプレート](team-templates-nonprofit.md)
- [リテール チーム テンプレート](get-started-with-retail-teams-templates.md)

## <a name="team-template-size-limits"></a>チーム テンプレートのサイズ制限

テンプレートは、特定の数のチャネル、タブ、アプリに制限されます。

 > [!Note]
 > テンプレートから作成した後、チャネル、タブ、アプリをさらにチームに追加できます。

|機能 | 制限|
|-|-|
|テンプレートあたりのチャネル数 | 15 |
|テンプレート内のチャネルごとのタブ | 20 |
|テンプレートごとのアプリ | 50|

詳細については、「 [Teams の制限と仕様](limits-specifications-teams.md)」を参照してください。

## <a name="manage-team-templates"></a>チーム テンプレートを管理する

### <a name="manage-team-templates-in-the-teams-admin-center"></a>Teams 管理センターでチーム テンプレートを管理する

#### <a name="view-team-templates"></a>チーム テンプレートを表示する

チーム テンプレートを表示するには、Teams 管理センターの左側のナビゲーションで、[**Teams チーム** >  テンプレート] に移動 **します**。 テンプレートを選択すると、そのテンプレートに含まれるチャネルやアプリなど、詳細が表示されます。

#### <a name="create-your-own-team-templates"></a>独自のチーム テンプレートを作成する

独自のカスタム テンプレートは、最初から作成することも、既存のチームから作成することも、既存のテンプレートから作成することもできます。 詳細については、次を参照してください。

- [カスタム チーム テンプレートを作成する](create-a-team-template.md)
- [既存のチームからテンプレートを作成する](create-template-from-existing-team.md)
- [既存のチーム テンプレートからチーム テンプレートを作成する](create-template-from-existing-template.md)

#### <a name="apply-team-template-policies"></a>チーム テンプレート ポリシーを適用する

チームを作成するために Teams に表示されるテンプレートを制御するには、テンプレート ポリシー [を](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b)設定し、組織内のユーザーとグループに割り当てることができます。 詳細については、「 [Teams 管理センターでチーム テンプレートを管理する」を](templates-policies.md)参照してください。

### <a name="manage-team-templates-using-powershell"></a>PowerShell を使用してチーム テンプレートを管理する

PowerShell でテンプレートを管理するには、次のコマンドレットを使用します。

- [Get-CsTeamTemplate](/powershell/module/teams/get-csteamtemplate)
- [Get-CsTeamTemplateList](/powershell/module/teams/get-csteamtemplatelist)
- [New-CsTeamTemplate](/powershell/module/teams/new-csteamtemplate)
- [Remove-CsTeamTemplate](/powershell/module/teams/remove-csteamtemplate)
- [Update-CsTeamTemplate](/powershell/module/teams/update-csteamtemplate)

## <a name="related-articles"></a>関連記事

- [テンプレートからチームを作成する](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b)
- [Microsoft Graph を使用して、チーム テンプレートの使用を開始する](get-started-with-teams-templates.md)
- [チームを複製する](/graph/api/team-clone)
- [Teams と SharePoint の統合の概要](/sharepoint/teams-connected-sites)
