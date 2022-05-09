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
description: チーム テンプレートと、Microsoft Teams管理センターで管理する方法について説明します。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 832d13955287d4166a575d213c04331b7e79e1bd
ms.sourcegitcommit: fcac607fb4ad342a0936527f848e04c85f153ba5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/22/2022
ms.locfileid: "63711901"
---
# <a name="get-started-with-team-templates-in-the-teams-admin-center"></a>Teams 管理センターで Teams テンプレートの使用を開始する

**カスタム テンプレートを作成する機能は、EDU のお客様にはまだサポートされていません。**

> [!NOTE]
> - 現在、プライベート チャネルと共有チャネルはチーム テンプレートではサポートされていません。 プライベート チャネルと共有チャネルの作成は、テンプレート定義には含まれません。
>
> - 秘密度ラベルは、GCC環境のチーム テンプレートではサポートされていません。 [テンプレートからチームを作成する] フローの秘密度ラベル オプションは、チームには適用されません。

## <a name="overview"></a>概要

Microsoft Teamsのチーム テンプレートは、ビジネスニーズまたはプロジェクトを中心に設計されたチームの構造の定義です。 管理者は、テンプレートを使用して、組織全体に一貫性のあるチームを簡単にデプロイできます。 テンプレートを使用すると、ユーザーは定義済みの設定、チャネル、アプリを使用して豊富なコラボレーション 空間をすばやく作成できます。

チーム テンプレートは、Microsoft Teams管理センターまたは PowerShell を使用して管理できます。 Microsoft が提供する事前構築済みテンプレートを使用し、 [独自のカスタム テンプレートを作成](#create-your-own-team-templates)することもできます。 テンプレート ポリシーを[適用](#apply-team-template-policies)して、Teamsでユーザーが使用できるテンプレートを制御することもできます。

この記事では、Teams管理センターでチーム テンプレートを操作する概要について説明します。 テンプレートでサポートされているプロパティ、Microsoft が提供する事前構築済みテンプレート、テンプレート サイズの制限、テンプレートの作成方法と管理方法などについて説明します。

> [!NOTE]
> ユーザーは、Teams アプリ[の事前構築済みまたはカスタム のチーム テンプレートからチームを作成](https://support.microsoft.com/office/create-a-team-from-a-template-a90c30f3-9940-4897-ab5b-988e69e4cd9c)できます。 開発者は、Microsoft Graphを使用して、事前に構築されたチーム テンプレートからチームをプログラムで作成することもできます。 詳細については、[Microsoft Graphを使用したチーム テンプレートの概要](get-started-with-teams-templates.md)に関するページを参照してください。

## <a name="team-template-capabilities"></a>チーム テンプレートの機能

チーム内のほとんどのプロパティは、チーム テンプレートによって含まれ、サポートされています。 ただし、現在サポートされていないいくつかのプロパティと機能があります。 チーム テンプレートに含まれる内容と含まれていない内容の概要を次に示します。

| **チーム テンプレートでサポートされているチーム プロパティ** | **チーム テンプレートではまだサポートされていないチーム プロパティ** |
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
> 今後のMicrosoft Teamsリリースでは、テンプレート機能を追加する予定です。そのため、サポートされているプロパティに関する最新の情報を確認してください。

## <a name="pre-built-team-templates-in-the-teams-admin-center"></a>Teams管理センターの事前構築済みチーム テンプレート

Teams管理センターで使用できる事前構築済みのチーム テンプレートを次に示します。 事前構築済みテンプレートは、特定の業界向けに作成したテンプレートです。 これらのテンプレートを表示するには、Teams管理センターの左側のナビゲーションで **、Teams** >  **Team テンプレート** に移動します。

事前構築済みのテンプレートは複製できますが、編集することはできません。 事前構築済みテンプレートのプロパティを変更する場合は、既存のテンプレートから新しいテンプレートを作成し、必要なプロパティを追加または削除できます。 一部のテンプレートの特定のプロパティは変更できないことに注意してください。

| テンプレートの種類 | TemplateId | このテンプレートに含まれるプロパティ |
| ------------------ | -------------- | ----------------------------------------------------- |
| Office 365を採用する |`com.microsoft.teams.template.AdoptOffice365`|  チャネル: <ul><li>全般</li> <li>お知らせ</li> <li>チャンピオンズ コーナー</li> <li>チーム フォーム</li><li>カレンダー</li></ul> アプリ: <ul><li>Wiki</li>  <li>チャネル カレンダー</li> <li>マイルス トーン</li><li>情報</li></ul>|
| プロジェクトを管理する |`com.microsoft.teams.template.ManageAProject`| チャネル: <ul><li>全般</li> <li>お知らせ</li> <li>リソース</li> <li>計画</li></ul> アプリ:<ul><li>Wiki</li><li>OneNote</li><li>タスク</li><li>リスト</li><li>Power Automate</li></ul> |
| イベントを管理する|`com.microsoft.teams.template.ManageAnEvent` | チャネル: <ul><li>全般</li> <li>お知らせ</li> <li>予算</li> <li>コンテンツ</li><li>物流</li> <li>計画</li> <li> マーケティングと PR</li></ul> アプリ:<ul><li>Wiki</li><li>Web サイト</li> <li>YouTube</li> <li>タスク</li> <li>OneNote</li> <li>従業員のアイデア</li> <li>問題の報告者</li><li>Power Automate</li><li>情報</li><li>マイルス トーン</li></ul> |
|従業員をオンボードする|`com.microsoft.teams.template.OnboardEmployees` | チャネル: <ul><li>全般</li> <li>お知らせ</li> <li>従業員チャット</li> <li>トレーニング</li></ul>アプリ:<ul><li>Wiki</li><li>コミュニティ</li><li>タスク</li><li>従業員のアイデア</li><li>Power Automate</li><li>情報</li><li>マイルス トーン</li></ul>|
|ヘルプ デスクを整理する| `com.microsoft.teams.template.OrganizeHelpDesk`|チャネル:<ul><li>全般</li><li>お知らせ</li><li>よくあるご質問 (FAQ)</li></ul>アプリ:<ul><li>Wiki</li><li>OneNote</li><li>タスク </li><li>称賛</li><li>問題の報告者</li><li>Power Automate</li><li>情報</li></ul> |
| 患者のケア| `com.microsoft.teams.template.healthcareWard`| チャネル<ul><li>全般</li><li>お知らせ</li><li>ハドル</li><li>ラウンド</li><li>人員配置</li><li>トレーニング</li></ul> アプリ: <ul><li>Wiki</li><li>リスト  </li><li>承認</li><li>情報</li><li>検査</li></ul>|
| クライシス コミュニケーション |`com.microsoft.teams.template.CollaborateOnAGlobalCrisisOrEvent`| チャネル: <ul><li>全般<li>お知らせ</li><li>世界のニュース</li><li>内部通信</li><li>外部通信</li><li>承認要求</li><li>顧客エスカレーション</li><li>エグゼクティブ更新プログラム</li><li>計画</li><li>物流</li></ul>アプリ: <ul><li>Web サイト</li><li>タスク</li><li>問題の報告者</li><li>承認</li><li>情報</li><li>OneNote</li><li>Power Automate</li><li>SharePoint</li></ul>|
|銀行の支店| `com.microsoft.teams.template.CollaborateWithinABankBranch`|チャネル <ul><li>全般<li>お知らせ</li><li>ハドル</li><li>顧客との会議</li><li>承認要求 </li><li>指導</li><li>スキルの習得</li><li>融資の処理</li><li>顧客の苦情</li><li>称賛</li><li>楽しい機能</li><li>コンプライアンス</li></ul>アプリ:<ul><li>称賛 </li><li>問題の報告者</li><li>Wiki</li><li>カレンダー</li><li>承認</li><li>情報</li><li>アイデア</li></ul>|
|インシデント対応| `com.microsoft.teams.template.CoordinateIncidentResponse`|チャネル: <ul><li>全般<li>お知らせ</li><li>物流</li><li>計画</li><li>回復</li><li>緊急</li></ul> アプリ: <ul><li>Wiki</li><li>Excel</li><li>OneNote</li><li>SharePoint</li><li>タスク</li> <li>承認</li> <li>検査</li> <li>Power Automate</li><li>情報</li><li>マイルス トーン</li></ul>|
|病院| `com.microsoft.teams.template.healthcareHospital` |チャネル <ul><li>全般</li><li>お知らせ</li><li>コンプライアンス</li><li>親権</li><li>人事管理</li><li>薬局</li></ul> アプリ: <ul><li>Wiki</li><li>リスト</li><li>タスク</li><li>承認</li><li>Shifts</li><li>情報</li><li>検査</li><li>アイデア</li></ul>|
|店舗を整理する| `com.microsoft.teams.template.retailStore` |チャネル: <ul><li>全般<li>シフトのハンドオフ</li><li>ストアの準備状況</li><li>学習</li></ul> アプリ: <ul><li>Wiki</li><li>タスク</li><li>Shifts</li><li>検査</li></ul>|
|マネージャー用小売業| `com.microsoft.teams.template.retailManagerCollaboration` |チャネル <ul><li>全般<li>操作</li><li>学習</li></ul> アプリ: <ul><li>Wiki</li><li>タスク</li><li>検査</li></ul>|
|品質と安全性 |`com.microsoft.teams.template.QualitySafety`|チャネル: <ul><li>全般<li>お知らせ</li><li>リーダーシップ</li><li>メンテナンス</li><li>運用ライン 1</li><li>運用ライン 2</li><li>運用ライン 3</li><li>健康と安全性</li><li>トレーニング</li><li>楽しい機能</li></ul> アプリ: <ul><li>Wiki</li><li>タスク</li> <li>問題の報告者</li> <li>検査</li> </ul>|
|ボランティアの管理| `com.microsoft.teams.template.ManageVolunteers` |チャネル: <ul><li>全般<li>お知らせ</li><li>レポート</li><li>ボランティアの管理</li><li>エンゲージメントの機会</li><li>ボランティア オンボーディング</li></ul> アプリ: <ul><li>Web サイト</li><li>YouTube</li><li>Power BI</li><li>Power Apps</li><li>タスク</li><li>SharePoint</li><li>OneNote</li></ul>|
||||

### <a name="team-templates-by-category-and-industry"></a>カテゴリと業界別のチーム テンプレート

業界で事前構築済みテンプレートを使用する方法の詳細については、次を参照してください。

- [財務チーム テンプレート](financial-teams-templates-in-the-admin-console.md)
- [一般的なチーム テンプレート](general-teams-templates-in-the-admin-console.md)
- [政府機関のチーム テンプレート](government-teams-templates-in-the-admin-console.md)
- [医療チーム テンプレート](expand-teams-across-your-org/healthcare/healthcare-templates-admin-console.md)
- [製造チーム テンプレート](manufacturing-teams-templates-in-the-admin-console.md)
- [非営利団体チーム テンプレート](team-templates-nonprofit.md)
- [リテール チーム テンプレート](retail-teams-templates-in-the-admin-console.md)

## <a name="team-template-size-limits"></a>チーム テンプレートのサイズ制限

テンプレートは、特定の数のチャネル、タブ、アプリに制限されます。

 > [!Note]
 > テンプレートから作成したチャネル、タブ、アプリをチームに追加できます。

|機能 | 制限|
|-|-|
|テンプレートあたりのチャネル数 | 15 |
|テンプレート内のチャネルごとのタブ | 20 |
|テンプレートごとのアプリ | 50|
|||

詳細については、「[Teamsの制限と仕様](limits-specifications-teams.md)」を参照してください。

## <a name="manage-team-templates"></a>チーム テンプレートを管理する

### <a name="manage-team-templates-in-the-teams-admin-center"></a>Teams 管理センターでチーム テンプレートを管理する

#### <a name="view-team-templates"></a>チーム テンプレートを表示する

チーム テンプレートを表示するには、Teams管理センターの左側のナビゲーションで **、Teams** >  **Team テンプレート** に移動します。 テンプレートを選択すると、そのテンプレートに含まれるチャネルやアプリなど、詳細が表示されます。

#### <a name="create-your-own-team-templates"></a>独自のチーム テンプレートを作成する

独自のカスタム テンプレートは、最初から、既存のチームから、既存のテンプレートから作成できます。 詳細については、次を参照してください。

- [カスタム チーム テンプレートを作成する](create-a-team-template.md)
- [既存のチームからテンプレートを作成する](create-template-from-existing-team.md)
- [既存のチーム テンプレートからチーム テンプレートを作成する](create-template-from-existing-template.md)

#### <a name="apply-team-template-policies"></a>チーム テンプレート ポリシーを適用する

[チームを作成](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b)するためにユーザーがTeamsに表示するテンプレートを制御するには、テンプレート ポリシーを設定し、組織内のユーザーとグループに割り当てることができます。 詳細については、「[Teams管理センターでチーム テンプレートを管理する](templates-policies.md)」を参照してください。

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
