---
title: 管理センターで Teams テンプレートを使用する
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
description: Teams テンプレートを使用して、プレインストールされているテンプレートを使用して、さまざまなトピックのチャネルを含むコラボレーション スペースを作成する方法について説明します。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7ad35b874f3f11a7e71d61c63cb90a1945c7cc85
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662652"
---
# <a name="get-started-with-teams-templates-in-the-admin-center"></a>管理センターで Teams テンプレートの使用を開始する

**EDU ユーザー向けカスタム テンプレートはまだサポートされていません。**

> [!NOTE]
> 現在、Teams テンプレートはプライベート チャネルの作成をサポートしています。 プライベート チャネルの作成は、テンプレート定義には含まれません。

Teams テンプレートは、ビジネス の必要性やプロジェクトを中心に設計された、チームの構造の事前に構築された定義です。 あらかじめ作成されたテンプレートを使用するか、独自のテンプレートを作成します。 Teams テンプレートを使用すると、さまざまなトピックのチャネルを含む豊富なコラボレーション スペースをすばやく作成し、ミッション クリティカルなコンテンツとサービスを取り込むアプリをプレインストールできます。 Teams テンプレートには定義済みのチーム構造があり、組織全体で一貫したチームを簡単に作成できます。 現時点では、Teams のテンプレートから、または Microsoft Graph を使用してチーム [を作成できます](get-started-with-teams-templates.md)。

この記事では、テンプレートで定義できるプロパティ、基本テンプレートの種類、およびいくつかのサンプル要求を使用してテンプレートからチームを作成する方法について説明します。

この記事は、組織全体で複数のチームを計画、展開、管理する責任がある場合に役立ちます。

## <a name="teams-template-capabilities"></a>Teams テンプレートの機能

チーム内のほとんどのプロパティはテンプレートに含まれており、サポートされます。 ただし、現在サポートされていないプロパティと機能がいくつかある。 次の表は、Teams テンプレートに含まれるものと含まれていないものについて簡単に説明しています。

| **Teams テンプレートでサポートされるチームのプロパティ** | **Teams テンプレートでまだサポートされていないチームのプロパティ** |
| ------------------------------------------------ | -------------------------------------------------------- |
| 基本テンプレートの種類 | チーム メンバーシップ |
| チーム名 | チームの画像 |
| チームの説明 | チャネルの設定 |
| チームの公開 (パブリックまたはプライベート) | コネクタ |
| チームの設定 (メンバー、ゲスト、@ メンションなど) | ファイルとコンテンツ |
| 自動お好みチャネル | |
| インストールされているアプリ | |
| ピン留めされたタブ | |

> [!NOTE]
> Microsoft Teams の今後のリリースでさらにテンプレート機能を追加する予定なので、サポートされているプロパティに関する最新の情報を確認してください。

## <a name="what-are-base-template-types"></a>基本テンプレートの種類

基本テンプレートの種類は、Microsoft が特定の業界向けに作成した特別なテンプレートです。 これらの基本テンプレートには、多くの場合、アプリ ストアでは利用できない専用アプリが含まれている場合があります。

基本テンプレートの種類を定義したら、指定する追加のプロパティを使用して、これらの特別なテンプレートを拡張または上書きできます。 一部の基本テンプレートの種類には、上書きできないプロパティが含まれている場合があります。

> [!NOTE]
> Microsoft Teams で提供される事前に定義された基本テンプレートは複製できますが、編集はされません。

| 基本テンプレートの種類 | baseTemplateId | この基本テンプレートに含まれるプロパティ |
| ------------------ | -------------- | ----------------------------------------------------- |
| 365 をOfficeする |`com.microsoft.teams.template.AdoptOffice365`|  チャネル: <ul><li>一般</li> <li>お知らせ</li> <li>チャンピオン コーナー</li> <li>チーム フォーム</li></ul> アプリ: <ul><li>Wiki</li>  <li>カレンダー</li> |
| プロジェクトを管理する |`com.microsoft.teams.template.ManageAProject`| チャネル: <ul><li>一般</li> <li>お知らせ</li> <li>リソース</li> <li>計画</li></ul> アプリ:<ul><li>Wiki</li><li>OneNote</li><li>プランナー</li><li>リスト</li>  </ul> |
| イベントを管理する|`com.microsoft.teams.template.ManageAnEvent` | チャネル: <ul><li>一般</li> <li>お知らせ</li> <li>予算</li> <li>コンテンツ</li><li>物流</li> <li>計画</li> <li> マーケティングと PR</li></ul> アプリ:<ul><li>Wiki</li><li>Web サイト</li> <li>YouTube</li> <li>プランナー</li> <li>OneNote</li></ul> |
|従業員のオンボード|`com.microsoft.teams.template.OnboardEmployees` | チャネル: <ul><li>一般</li> <li>お知らせ</li> <li>従業員のチャット</li> <li>トレーニング</li></ul>アプリ:<ul><li>Wiki</li><li>コミュニティ</li><li>プランナー</li></ul>|
|ヘルプ デスクを整理する| `com.microsoft.teams.template.OrganizeHelpDesk`|チャネル:<ul><li>一般</li><li>お知らせ</li><li>FAQ</li></ul>アプリ:<ul><li>Wiki</li><li>OneNote</li><li>プランナー </li><li>称賛</li></ul> |
| 患者の治療で共同作業を行う| `healthcareWard`| チャネル:<ul><li>一般</li><li>お知らせ</li><li>Huddles</li><li>丸め</li><li>スタッフ</li><li>トレーニング</li></ul> アプリ: <ul><li>Wiki</li><li>リスト  </li></ul>|
| グローバルクライシスまたはイベントで共同作業する |`com.microsoft.teams.template.CollaborateOnAGlobalCrisisOrEvent`| チャネル: <ul><li>一般<li>お知らせ</li><li>世界のニュース</li><li>ビジネス継続性</li><li>リモートでの作業</li><li>内部通信</li><li>外部通信</li><li>承認要求</li><li>顧客からの苦情</li><li>クード</li><li>エグゼクティブ更新</li></ul>アプリ: <ul><li>称賛</li><li>Wiki</li><li>Web サイト</li><li>プランナー</li></ul>|
|銀行の支店内で共同作業を行う| `com.microsoft.teams.template.CollaborateWithinABankBranch`|チャネル: <ul><li>一般<li>お知らせ</li><li>Huddles</li><li>顧客会議</li><li>承認要求 </li><li>コーチ</li><li>スキル開発</li><li>ローン処理</li><li>顧客からの苦情</li><li>クード</li><li>楽しい情報</li><li>コンプライアンス</li></ul>アプリ:<ul><li>称賛 </li></ul>|
|インシデントの対応を調整する| `com.microsoft.teams.template.CoordinateIncidentResponse`|チャネル: <ul><li>一般<li>お知らせ</li><li>物流</li><li>計画</li><li>回復</li><li>緊急</li></ul> アプリ: <ul><li>Wiki</li><li>Excel</li><li>OneNote</li><li>SharePoint</li><li>プランナー</li></ul>|
|病院| `healthcareHospital` |チャネル: <ul><li>一般</li><li>お知らせ</li><li>コンプライアンス</li><li>Custodial</li><li>人事</li><li>[分数]</li></ul> アプリ: <ul><li>Wiki</li><li>リスト  </li></ul>|
|ストアを整理する| `retailStore` |チャネル: <ul><li>一般<li>Shift の手渡し</li><li>学習</li></ul> アプリ: <ul><li>Wiki</li><li>プランナー</li></ul>|
|品質と安全性 |`com.microsoft.teams.template.QualitySafety`|チャネル: <ul><li>一般<li>お知らせ</li><li>行 1</li><li>行 2</li><li>行 3</li><li>安全性</li><li>トレーニング</li><li>メンテナンス</li><li>楽しい情報</li></ul> アプリ: <ul><li>Wiki</li><li>プランナー</li></ul>|
|リテール - マネージャーの共同作業| `retailManagerCollaboration` |チャネル: <ul><li>一般<li>操作</li><li>学習</li></ul> アプリ: <ul><li>Wiki</li><li>プランナー</li></ul>|
||||

テンプレートカテゴリの詳細については、次のカテゴリを参照してください。

- [財務テンプレート](financial-teams-templates-in-the-admin-console.md)
- [一般的なテンプレート](general-teams-templates-in-the-admin-console.md)
- [政府機関のテンプレート](government-teams-templates-in-the-admin-console.md)
- [医療テンプレート](expand-teams-across-your-org/healthcare/healthcare-templates-admin-console.md)
- [製造テンプレート](manufacturing-teams-templates-in-the-admin-console.md)
- [小売用テンプレート](retail-teams-templates-in-the-admin-console.md)

## <a name="template-size-limits"></a>テンプレートのサイズ制限

テンプレートは、チャネル、タブ、アプリの特定の数に制限されます。

 > [!Note]
 > テンプレートから作成したチャネル、タブ、アプリをチームに追加できます。

|機能 | 制限|
|-|-|
|テンプレートごとのチャネル | 15 |
|テンプレートのチャネルごとのタブ | 20 |
|テンプレートごとのアプリ | 50|
|||

詳細 [については、「Teams の制限と](limits-specifications-teams.md) 仕様」を参照してください。

## <a name="related-topics"></a>関連項目

- [カスタム チーム テンプレートを作成する](create-a-team-template.md)
- [既存のチーム テンプレートからチーム テンプレートを作成する](create-template-from-existing-template.md)
- [既存のチームからテンプレートを作成する](create-template-from-existing-team.md)
