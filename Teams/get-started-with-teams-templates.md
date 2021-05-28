---
title: Microsoft Graph を使用してチーム テンプレートの使用を開始する
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: phlouie
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Microsoft Graph でチーム テンプレートを使用して、さまざまなトピックのチャネルを含むコラボレーション スペースを作成し、コンテンツとサービスを提供するアプリをプレインストールする方法について説明します。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: fdee4dc55d0922796e66ece87b535b953ecf1580
ms.sourcegitcommit: 36924dc54fe7b09607b07d7543fe7e39eb4d2483
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2021
ms.locfileid: "52684544"
---
# <a name="get-started-with-team-templates-using-microsoft-graph"></a>Microsoft Graph を使用してチーム テンプレートの使用を開始する

> [!NOTE]
> チーム テンプレートは現在、プライベート チャネルの作成をサポートされていません。 プライベート チャネルの作成は、テンプレート定義には含まれません。

チーム テンプレートは、ビジネス の必要性やプロジェクトを中心に設計されたチームの構造を事前に構築した定義です。 管理コンソール [で独自のテンプレートを作成できます](get-started-with-teams-templates-in-the-admin-console.md)。 Microsoft Graphでは、事前構築済みのテンプレート を使用します。 チーム テンプレートを使用すると、さまざまなトピックのチャネルを含む豊富なコラボレーション スペースをすばやく作成し、ミッション クリティカルなコンテンツとサービスを取り込むアプリをプレインストールできます。 チーム テンプレートは、組織全体で一貫性のあるチームを簡単に作成するのに役立つ定義済みのチーム構造を提供します。

この記事では、テンプレートで定義できるプロパティ、基本テンプレートの種類、いくつかのサンプル要求を使用してテンプレートからチームを作成する方法について説明します。

この記事は、次の場合に使用します。

- 組織全体で複数のチームの計画、デプロイ、管理を担当する<br>
- 定義済みのチャネルとアプリを含むチームをプログラムで作成する必要のある開発者

## <a name="team-template-capabilities"></a>チーム テンプレートの機能

チーム内のほとんどのプロパティは、テンプレートに含まれてサポートされています。 ただし、現在サポートされていないいくつかのプロパティと機能があります。 次の表は、チーム テンプレートに含まれているものと含まれていないものについて簡単に説明しています。

| **チーム テンプレートでサポートされるチームのプロパティ** | **チーム テンプレートでまだサポートされていないチームプロパティ** |
| ------------------------------------------------ | -------------------------------------------------------- |
| 基本テンプレートの種類 | チーム メンバーシップ |
| チーム名 | チームの画像 |
| チームの説明 | チャネル設定 |
| チームの可視性 (パブリックまたはプライベート) | コネクタ |
| チーム設定 (メンバー、ゲスト、@ メンションなど) | ファイルとコンテンツ |
| 自動お気に入りチャネル | |
| インストールされたアプリ | |
| ピン留めされたタブ | |

> [!NOTE]
> Microsoft Teams の将来のリリースではテンプレート機能を追加する予定なので、サポートされているプロパティに関する最新の情報を確認してください。

## <a name="what-are-base-template-types"></a>基本テンプレートの種類

基本テンプレートの種類は、Microsoft が特定の業界向けに作成した特別なテンプレートです。 これらの基本テンプレートには、多くの場合、ストアで使用できない独自のアプリが含まれている場合があります。 さらに、ベース テンプレートには、チーム テンプレートで個別にサポートされていないチーム プロパティが含まれる場合があります。 Microsoft Graph で[チーム テンプレートを使用する方法について説明します](get-started-with-teams-templates.md)。

基本テンプレートの種類を定義したら、指定する追加のプロパティを使用して、これらの特別なテンプレートを拡張またはオーバーライドできます。 一部の基本テンプレートの種類には、オーバーライドできないプロパティが含まれている場合があります。

既定では、基本テンプレートは Standard に **設定** されます。このテンプレートには、追加の独自のアプリや特別なプロパティは含めされません。 使用可能な基本テンプレートの種類の現在の一覧を次に示します。

| 基本テンプレートの種類 | baseTemplateId | この基本テンプレートに含まれるプロパティ |
| ------------------ | -------------- | ----------------------------------------------------- |
| Standard | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('standard')` | 追加のアプリとプロパティはありません |
| Education -<br>クラス チーム | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('educationClass')` | アプリ:<ul><li>OneNoteクラス ノートブック ([全般] タブ **にピン留め**) </li><li>割り当てアプリ ([全般] タブ **にピン留め** )</li></ul> チームのプロパティ:<ul><li>チームの可視性が **HiddenMembership に設定** されている (オーバーライドできない)</li></ul> |
| Education -<br>スタッフ チーム | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('educationStaff')` | アプリ:<ul><li>OneNoteスタッフ ノートブック ([全般] タブ **にピン留め**)</li></ul> |
|Education -<br>PLC チーム |`https://graph.microsoft.com/beta/`<br>`teamsTemplates('educationProfessionalLearningCommunity')` | アプリ:<ul><li>OneNotePLC Notebook ([全般] タブ **にピン留め**)</ul></li>|
| 小売業 -<br>店舗 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')` | チャネル<ul><li>シフトのハンドオフ</li><li>学習</li></ul>チームのプロパティ<ul><li>チームの可視性を公開に設定</li></ul>メンバーのアクセス許可<ul><li>メンバーによるチャネルの作成、更新、または削除を防止する</li><li>メンバーによるアプリの追加または削除を防止する</li><li>メンバーによるコネクタの作成、更新、または削除を防止する</li></ul> |
| 小売業 -<br>マネージャーの共同作業 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')` | チャネル<ul><li>学習</li><li>操作</li></ul>チームのプロパティ:<ul><li>チームの可視性を非公開に設定</li></ul>メンバーのアクセス許可:<ul><li>メンバーによるチャネルの作成、更新、または削除を防止する</li><li>メンバーによるアプリの追加または削除を防止する</li><li>メンバーによるコネクタの作成、更新、または削除を防止する</li></ul>|
| 医療 -<br>区 |`https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')` |チャネル <ul><li>お知らせ\*</li><li>ハドル\*</li><li>ラウンド</li><li>人員配置\*</li><li>トレーニング\*</li></ul>\*自動的にお気に入りに登録されたチャネル |
|医療 -<br>病院 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')` |チャネル<ul><li>お知らせ\*</li><li>コンプライアンス\*</li><li>カストディアル</li><li>人事</li></li><li>薬局</li></ul>\*自動お気に入りチャネル|
|||


次のテンプレートを使用して、クライアントと Microsoft Teamsの両方でチームを作成Graph。


| 基本テンプレートの種類 | baseTemplateId | この基本テンプレートに含まれるプロパティ |
| ------------------ | -------------- | ----------------------------------------------------- |
| 導入Office 365 |`com.microsoft.teams.template.`<br>`AdoptOffice365`|  チャネル <ul><li>全般</li> <li>お知らせ</li> <li>チャンピオン コーナー</li> <li>チーム フォーム</li></ul> アプリ: <ul><li>Wiki</li>  <li>カレンダー</li> |
| プロジェクトを管理する |`com.microsoft.teams.template.`<br>`ManageAProject`| チャネル <ul><li>全般</li> <li>お知らせ</li> <li>リソース</li> <li>計画</li></ul> アプリ:<ul><li>Wiki</li><li>OneNote</li></ul> |
| イベントを管理する|`com.microsoft.teams.template.`<br>`ManageAnEvent` | チャネル <ul><li>全般</li> <li>お知らせ</li> <li>予算</li> <li>コンテンツ</li><li>物流</li> <li>計画</li> <li> マーケティングと PR</li></ul> アプリ:<ul><li>Wiki</li><li>Web サイト</li> <li>YouTube</li> <li>プランナー</li> <li>OneNote</li></ul> |
|従業員のオンボード|`com.microsoft.teams.template.`<br>`OnboardEmployees` | チャネル <ul><li>全般</li> <li>お知らせ</li> <li>従業員チャット</li> <li>トレーニング</li></ul>アプリ:<ul><li>Wiki</li><li>コミュニティ</li></ul>|
|ヘルプ デスクを整理する| `com.microsoft.teams.template.`<br>`OrganizeHelpDesk`|チャネル<ul><li>全般</li><li>お知らせ</li><li>よくあるご質問 (FAQ)</li></ul>アプリ:<ul><li>Wiki</li><li>OneNote</li></ul> |
| 患者の治療で共同作業を行う| `healthcareWard `| チャネル<ul><li>全般</li><li>お知らせ</li><li>ハドル</li><li>ラウンド</li><li>人員配置</li><li>トレーニング</li></ul> アプリ: <ul><li>Wiki</li>|
| グローバルな危機やイベントで共同作業を行う |`com.microsoft.teams.template.`<br>`CollaborateOnAGlobalCrisisOrEvent`| チャネル <ul><li>全般<li>お知らせ</li><li>世界のニュース</li><li>ビジネス継続性</li><li>リモート作業</li><li>内部 comms</li><li>外部通信</li><li>顧客からの苦情</li><li>Kudos</li><li>エグゼクティブの更新</li></ul>アプリ: <ul><li>称賛</li><li>Wiki</li><li>Web サイト</li></ul>|
|銀行支店内で共同作業を行う| `com.microsoft.teams.template.`<br>`CollaborateWithinABankBranch `|チャネル <ul><li>全般<li>お知らせ</li><li>ハドル</li><li>顧客会議</li><li>コーチング</li><li>スキル開発</li><li>ローン処理</li><li>顧客からの苦情</li><li>Kudos</li><li>楽しい情報</li><li>コンプライアンス</li></ul>|
|インシデント対応を調整する| `com.microsoft.teams.template.`<br>`CoordinateIncidentResponse`|チャネル <ul><li>全般<li>お知らせ</li><li>物流</li><li>計画</li><li>回復</li><li>緊急</li></ul> アプリ: <ul><li>Wiki</li><li>Excel</li><li>OneNote</li><li>SharePoint</li><li>プランナー</li></ul>|
|病院| `healthcareHospita`l |チャネル <ul><li>全般<li>お知らせ</li><li>コンプライアンス</li><li>親権</li><li>人事管理</li><li>薬局</li></ul> アプリ: <ul><li>Wiki</li></ul>|
|店舗を整理する| `retailStore` |チャネル: <ul><li>全般<li>シフトのハンドオフ</li><li>学習</li></ul> アプリ: <ul><li>Wiki</li></ul>|
|品質と安全性 |`com.microsoft.teams.`<br>`template.QualitySafety`|チャネル <ul><li>全般<li>お知らせ</li><li>1 行目</li><li>2 行目</li><li>3 行目</li><li>安全性</li><li>トレーニング</li><li>メンテナンス</li><li>楽しい情報</li></ul> アプリ: <ul><li>Wiki</li></ul>|
|小売業 - マネージャー コラボレーション| `retailManagerCollaboration` |チャネル: <ul><li>全般<li>操作</li><li>学習</li></ul> アプリ: <ul><li>Wiki</li></ul>|
||||

詳細 [については、「管理センターでチーム テンプレートの使用を開始する」](get-started-with-teams-templates-in-the-admin-console.md) を参照してください。

## <a name="related-topics"></a>関連項目

- [管理コンソールでチーム テンプレートの使用を開始する](get-started-with-teams-templates-in-the-admin-console.md)
- [チームを作成](/graph/api/team-post?view=graph-rest-beta) する (プレビュー中)
- [New-Team](/powershell/module/teams/New-Team?view=teams-ps)
- [Microsoft Teams の管理者トレーニング](itadmin-readiness.md)