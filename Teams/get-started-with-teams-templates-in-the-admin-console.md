---
title: 管理Teamsテンプレートを使用する
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: aaglick
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: インストール済みのテンプレートを使用Teamsを使用して、さまざまなトピックのチャネルを含むコラボレーション スペースを作成する方法について説明します。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: c898d8b0d79eae6fb7042ab087e94a0fff5d275f
ms.sourcegitcommit: 6c1b051c4e29a74bc15cdfd0716893a25ba18719
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2021
ms.locfileid: "52207955"
---
# <a name="get-started-with-teams-templates-in-the-admin-center"></a>管理センターでTeamsテンプレートの使用を開始する

**カスタム テンプレートを作成する機能は、EDU のお客様ではまだサポートされていません。**

> [!NOTE]
> プライベート チャネルと感度ラベルは、現在、一部のテンプレートTeamsされていません。 プライベート チャネルの作成は、テンプレート定義には含まれません。 [テンプレート フローからチームを作成 **する** ] の [感度ラベル] オプションは、チームには適用されません。

Teamsテンプレートは、ビジネスの必要性やプロジェクトを中心に設計されたチームの構造を事前に構築した定義です。 事前構築済みのテンプレートを使用するか、独自のテンプレートを作成します。 Teamsテンプレートを使用すると、さまざまなトピックのチャネルを含む豊富なコラボレーション スペースをすばやく作成し、ミッション クリティカルなコンテンツとサービスを取り込むアプリをプレインストールできます。 Teamsテンプレートは、組織全体で一貫性のあるチームを簡単に作成するのに役立つ定義済みのチーム構造を提供します。 現時点では、テンプレートからチームを作成するか、または Microsoft Teams を使用[Graph。](get-started-with-teams-templates.md)

この記事では、次の機能について説明します。

- テンプレートで定義できるプロパティ。
- 基本テンプレートの種類。
- いくつかのサンプル要求を使用して、テンプレートからチームを作成する方法。

この記事は、組織全体で複数のチームを計画、デプロイ、管理する責任がある場合に役立ちます。

## <a name="teams-template-capabilities"></a>Teamsテンプレートの機能

チーム内のほとんどのプロパティは、テンプレートに含まれてサポートされています。 ただし、現在サポートされていないいくつかのプロパティと機能があります。 次の表は、テンプレートに含まれるものと、テンプレートに含まれていないものについて簡単にTeamsします。

| **新しいテンプレートでサポートされるチームTeamsプロパティ** | **チームのプロパティは、テンプレートでまだTeamsされていません** |
| ------------------------------------------------ | -------------------------------------------------------- |
| 基本テンプレートの種類 | チーム メンバーシップ |
| チーム名 | チームの画像 |
| チームの説明 | チャネル設定 |
| チームの可視性 (パブリックまたはプライベート) | コネクタ |
| チーム設定 (メンバー、ゲスト、@ メンションなど) | ファイルとコンテンツ |
| Autofavorite チャネル | |
| インストールされたアプリ | |
| ピン留めされたタブ | |

> [!NOTE]
> Microsoft Teams の将来のリリースではテンプレート機能を追加する予定なので、サポートされているプロパティに関する最新の情報を確認してください。

## <a name="what-are-base-template-types"></a>基本テンプレートの種類

基本テンプレートの種類は、Microsoft が特定の業界向けに作成した特別なテンプレートです。 これらの基本テンプレートには、多くの場合、アプリ ストアで使用できない独自のアプリが含まれている場合があります。

基本テンプレートの種類を定義したら、指定するプロパティを追加して、これらの特殊なテンプレートを拡張またはオーバーライドできます。 一部の基本テンプレートの種類には、オーバーライドできないプロパティが含まれている場合があります。

> [!NOTE]
> テンプレートで提供される定義済みのベース Microsoft Teamsは複製できますが、編集は行えない。

| 基本テンプレートの種類 | baseTemplateId | この基本テンプレートに含まれるプロパティ |
| ------------------ | -------------- | ----------------------------------------------------- |
| 導入Office 365 |`com.microsoft.teams.template.AdoptOffice365`|  チャネル <ul><li>全般</li> <li>お知らせ</li> <li>チャンピオン コーナー</li> <li>チーム フォーム</li></ul> アプリ: <ul><li>Wiki</li>  <li>カレンダー</li> |
| プロジェクトを管理する |`com.microsoft.teams.template.ManageAProject`| チャネル <ul><li>全般</li> <li>お知らせ</li> <li>リソース</li> <li>計画</li></ul> アプリ:<ul><li>Wiki</li><li>OneNote</li><li>プランナー</li><li>リスト</li>  </ul> |
| イベントを管理する|`com.microsoft.teams.template.ManageAnEvent` | チャネル <ul><li>全般</li> <li>お知らせ</li> <li>予算</li> <li>コンテンツ</li><li>物流</li> <li>計画</li> <li> マーケティングと PR</li></ul> アプリ:<ul><li>Wiki</li><li>Web サイト</li> <li>YouTube</li> <li>プランナー</li> <li>OneNote</li> <li>従業員のアイデア</li> <li>問題レポーター</li></ul> |
|従業員のオンボード|`com.microsoft.teams.template.OnboardEmployees` | チャネル <ul><li>全般</li> <li>お知らせ</li> <li>従業員チャット</li> <li>トレーニング</li></ul>アプリ:<ul><li>Wiki</li><li>コミュニティ</li><li>プランナー</li><li>従業員のアイデア</li></ul>|
|ヘルプ デスクを整理する| `com.microsoft.teams.template.OrganizeHelpDesk`|チャネル<ul><li>全般</li><li>お知らせ</li><li>よくあるご質問 (FAQ)</li></ul>アプリ:<ul><li>Wiki</li><li>OneNote</li><li>プランナー </li><li>称賛</li><li>問題レポーター</li></ul> |
| 患者のケア| `healthcareWard`| チャネル<ul><li>全般</li><li>お知らせ</li><li>ハドル</li><li>ラウンド</li><li>人員配置</li><li>トレーニング</li></ul> アプリ: <ul><li>Wiki</li><li>リスト  </li><li>承認</li></ul>|
| グローバルな危機やイベントで共同作業を行う |`com.microsoft.teams.template.CollaborateOnAGlobalCrisisOrEvent`| チャネル <ul><li>全般<li>お知らせ</li><li>世界のニュース</li><li>ビジネス継続性</li><li>リモート作業</li><li>内部 comms</li><li>外部通信</li><li>承認要求</li><li>顧客からの苦情</li><li>Kudos</li><li>エグゼクティブの更新</li></ul>アプリ: <ul><li>称賛</li><li>Wiki</li><li>Web サイト</li><li>プランナー</li><li>問題レポーター</li></ul>|
|銀行支店| `com.microsoft.teams.template.CollaborateWithinABankBranch`|チャネル <ul><li>全般<li>お知らせ</li><li>ハドル</li><li>顧客会議</li><li>承認要求 </li><li>コーチング</li><li>スキル開発</li><li>ローン処理</li><li>顧客からの苦情</li><li>Kudos</li><li>楽しい情報</li><li>コンプライアンス</li></ul>アプリ:<ul><li>称賛 </li><li>問題レポーター</li></ul>|
|インシデント対応| `com.microsoft.teams.template.CoordinateIncidentResponse`|チャネル <ul><li>全般<li>お知らせ</li><li>物流</li><li>計画</li><li>回復</li><li>緊急</li></ul> アプリ: <ul><li>Wiki</li><li>Excel</li><li>OneNote</li><li>SharePoint</li><li>プランナー</li> <li>承認</li> <li>検査</li> </ul>|
|病院| `healthcareHospital` |チャネル <ul><li>全般</li><li>お知らせ</li><li>コンプライアンス</li><li>親権</li><li>人事管理</li><li>薬局</li></ul> アプリ: <ul><li>Wiki</li><li>リスト  </li></ul>|
|店舗を整理する| `retailStore` |チャネル: <ul><li>全般<li>シフトのハンドオフ</li><li>学習</li></ul> アプリ: <ul><li>Wiki</li><li>プランナー</li></ul>|
|品質と安全性 |`com.microsoft.teams.template.QualitySafety`|チャネル <ul><li>全般<li>お知らせ</li><li>1 行目</li><li>2 行目</li><li>3 行目</li><li>安全性</li><li>トレーニング</li><li>メンテナンス</li><li>楽しい情報</li></ul> アプリ: <ul><li>Wiki</li><li>プランナー</li> <li>問題レポーター</li> <li>検査</li> </ul>|
|マネージャー向けリテール| `retailManagerCollaboration` |チャネル <ul><li>全般<li>操作</li><li>学習</li></ul> アプリ: <ul><li>Wiki</li><li>プランナー</li></ul>|
||||

テンプレート カテゴリの詳細については、次のカテゴリを参照してください。

- [財務テンプレート](financial-teams-templates-in-the-admin-console.md)
- [一般的なテンプレート](general-teams-templates-in-the-admin-console.md)
- [Government テンプレート](government-teams-templates-in-the-admin-console.md)
- [医療テンプレート](expand-teams-across-your-org/healthcare/healthcare-templates-admin-console.md)
- [製造テンプレート](manufacturing-teams-templates-in-the-admin-console.md)
- [リテール テンプレート](retail-teams-templates-in-the-admin-console.md)

## <a name="template-size-limits"></a>テンプレート サイズの制限

テンプレートは、特定の数のチャネル、タブ、アプリに制限されます。

 > [!Note]
 > テンプレートから作成したチャネル、タブ、アプリをチームに追加できます。

|機能 | 制限|
|-|-|
|テンプレートあたりのチャネル数 | 15 |
|テンプレートのチャネルごとのタブ数 | 20 |
|テンプレートあたりのアプリ数 | 50|
|||

詳細[については、「Teamsの](limits-specifications-teams.md)制限と仕様」を参照してください。

## <a name="related-topics"></a>関連項目

- [カスタム チーム テンプレートを作成する](create-a-team-template.md)
- [既存のチーム テンプレートからチーム テンプレートを作成する](create-template-from-existing-template.md)
- [既存のチームからテンプレートを作成する](create-template-from-existing-team.md)
