---
title: チームテンプレートを使用して新しいチームを作成する
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
description: プレインストールされているテンプレートを使用して、さまざまなトピックのチャネルでコラボレーションスペースを作成するために Teams テンプレートを使用する方法について説明します。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: e65fd33ed47b54d220925353bdb350557fc81bcb
ms.sourcegitcommit: 45064a0020a1231e17967c74f082106c68213ea0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/30/2020
ms.locfileid: "48308190"
---
# <a name="get-started-with-teams-templates-in-the-admin-console"></a>管理コンソールで Teams のテンプレートを使ってみる

[!INCLUDE [preview-feature](includes/preview-feature.md)]

**カスタムテンプレートは、EDU のユーザーに対してまだサポートされていません。**

> [!NOTE]
> Teams テンプレートは、現在、プライベートチャネルの作成をサポートしていません。 プライベートチャネルの作成は、テンプレートの定義に含まれていません。

Teams テンプレートは、ビジネスニーズまたはプロジェクトに合わせて設計された、チームの構造の事前定義済みの定義です。 既成のテンプレートを使用するか、独自のテンプレートを作成します。 Teams テンプレートを使用すると、さまざまなトピックのチャネルと豊富なコラボレーションスペースをすばやく作成できます。アプリをプレインストールすることで、ミッションクリティカルなコンテンツやサービスを活用できます。 Teams テンプレートには、組織全体で一貫したチームを簡単に作成できる定義済みのチーム構造が用意されています。 現在、Teams または [Microsoft Graph](get-started-with-teams-templates.md)を使用してテンプレートからチームを作成できます。

この記事では、テンプレートで定義できるプロパティ、基本テンプレートの種類について説明し、いくつかのサンプル要求を使用して、テンプレートからチームを作成する方法について説明します。

この記事は、組織全体の複数のチームの計画、展開、管理を担当している場合に適しています。

## <a name="teams-template-capabilities"></a>Teams のテンプレート機能

チーム内のほとんどのプロパティは、テンプレートに含まれており、サポートされています。 ただし、現在サポートされていないプロパティと機能はいくつかあります。 次の表では、チームテンプレートに含まれる内容と含まれていない機能の概要を簡単に説明します。

| **Teams テンプレートでサポートされているチームプロパティ** | **Teams テンプレートでまだサポートされていないチームプロパティ** |
| ------------------------------------------------ | -------------------------------------------------------- |
| ベーステンプレートの種類 | チーム メンバーシップ |
| チーム名 | チームの画像 |
| チームの説明 | チャンネル設定 |
| チームの表示 (公開または非公開) | コネクタ |
| チーム設定 (member、guest、@ メンションなど) | ファイルとコンテンツ |
| 自動お気に入りチャネル | |
| インストール済みのアプリ | |
| 固定されたタブ | |

> [!NOTE]
> Microsoft Teams の将来のリリースでテンプレート機能を追加するため、サポートされているプロパティに関する最新情報を確認してください。

## <a name="what-are-base-template-types"></a>ベーステンプレートの種類とは

ベーステンプレートの種類は、Microsoft が特定の業界向けに作成した特別なテンプレートです。 これらの基本テンプレートには、多くの場合、アプリストアでは使用できない独自のアプリが含まれています。

ベーステンプレートの種類が定義されると、これらの特殊なテンプレートを追加または上書きして、追加のプロパティを指定することができます。 一部の基本テンプレートの種類には、オーバーライドできないプロパティが含まれています。

> [!NOTE]
> Microsoft Teams で提供される事前定義された基本テンプレートは、複製はできますが、編集はできません。

| ベーステンプレートの種類 | baseTemplateId | この基本テンプレートに含まれるプロパティ |
| ------------------ |----|----------------------------------------------------- |
| Office 365 を導入する |`com.microsoft.teams.template.AdoptOffice365`|  チャネル <ul><li>一般</li> <li>お知らせ</li> <li>チャンピオンのコーナー</li> <li>チームフォーム</li></ul> アプリ <ul><li>ウィキ</li>  <li>カレンダー</li> |
| プロジェクトを管理する |`com.microsoft.teams.template.ManageAProject`| チャネル <ul><li>一般</li> <li>お知らせ</li> <li>参照</li> <li>計画</li></ul> アプリ<ul><li>ウィキ</li><li>OneNote</li></ul> |
| イベントを管理する|`com.microsoft.teams.template.ManageAnEvent` | チャネル <ul><li>一般</li> <li>お知らせ</li> <li>予算</li> <li>コンテンツ</li><li>物流</li> <li>計画</li> <li> マーケティングと PR</li></ul> アプリ<ul><li>ウィキ</li><li>当</li> <li>YouTube</li> <li>プランナー</li> <li>OneNote</li></ul> |
|オンボード従業員|`com.microsoft.teams.template.OnboardEmployees` | チャネル <ul><li>一般</li> <li>お知らせ</li> <li>従業員チャット</li> <li>トレーニング</li></ul>アプリ<ul><li>ウィキ</li><li>お気に入り</li></ul>|
|ヘルプデスクを整理する| `com.microsoft.teams.template.OrganizeHelpDesk`|チャネル<ul><li>一般</li><li>お知らせ</li><li>FAQ</li></ul>アプリ<ul><li>ウィキ</li><li>OneNote</li></ul> |
| 治療での共同作業| `healthcareWard `| チャネル<ul><li>一般</li><li>お知らせ</li><li>Huddles</li><li>切り下げ</li><li>割り当てる</li><li>トレーニング</li></ul> アプリ <ul><li>ウィキ</li>|
| グローバルな危機またはイベントでの共同作業 |`com.microsoft.teams.template.CollaborateOnAGlobalCrisisOrEvent`| チャネル <ul><li>一般<li>お知らせ</li><li>世界中のニュース</li><li>ビジネス継続性</li><li>リモート作業</li><li>内部通信</li><li>外部通信</li><li>顧客の苦情</li><li>称賛</li><li>エグゼクティブ更新プログラム</li></ul>アプリ <ul><li>称賛</li><li>ウィキ</li><li>当</li></ul>|
|銀行支店内での共同作業| `com.microsoft.teams.template.CollaborateWithinABankBranch `|チャネル <ul><li>一般<li>お知らせ</li><li>Huddles</li><li>顧客の会議</li><li>コーチング</li><li>スキルの開発</li><li>ローン処理</li><li>顧客の苦情</li><li>称賛</li><li>楽しい機能</li><li>コンプライアンス</li></ul>|
|インシデント応答の調整| `com.microsoft.teams.template.CoordinateIncidentResponse`|チャネル <ul><li>一般<li>お知らせ</li><li>物流</li><li>計画</li><li>Recovery</li><li>度</li></ul> アプリ <ul><li>ウィキ</li><li>Excel</li><li>OneNote</li><li>SharePoint</li><li>プランナー</li></ul>|
|病院| `healthcareHospita`プレーン |チャネル <ul><li>一般<li>お知らせ</li><li>コンプライアンス</li><li>Custodial</li><li>人事</li><li>薬</li></ul> アプリ <ul><li>ウィキ</li></ul>|
|ストアを整理する| `retailStore` |チャネル <ul><li>一般<li>シフトハンド</li><li>意欲</li></ul> アプリ <ul><li>ウィキ</li></ul>|
|品質と安全性 |`com.microsoft.teams.template.QualitySafety`|チャネル <ul><li>一般<li>お知らせ</li><li>行1</li><li>2行目</li><li>行3</li><li>安全</li><li>トレーニング</li><li>メンテナンス</li><li>楽しい機能</li></ul> アプリ <ul><li>ウィキ</li></ul>|
|小売課長のコラボレーション| `retailManagerCollaboration` |チャネル <ul><li>一般<li>操作</li><li>意欲</li></ul> アプリ <ul><li>ウィキ</li></ul>|
||||

テンプレートカテゴリの詳細については、次のカテゴリを参照してください。

- [財務テンプレート](financial-teams-templates-in-the-admin-console.md)
- [一般的なテンプレート](general-teams-templates-in-the-admin-console.md)
- [行政機関向けテンプレート](government-teams-templates-in-the-admin-console.md)
- [医療用テンプレート](expand-teams-across-your-org/healthcare/healthcare-templates-admin-console.md)
- [製造テンプレート](manufacturing-teams-templates-in-the-admin-console.md)
- [小売用テンプレート](retail-teams-templates-in-the-admin-console.md)

## <a name="template-size-limits"></a>テンプレートサイズの制限

テンプレートは、特定の数のチャネル、タブ、アプリに制限されます。

 > [!Note]
 > テンプレートから作成された後で、チームにチャネル、タブ、アプリを追加することができます。

|機能 | 抑制|
|-|-|
|テンプレートあたりのチャネル数 | マート |
|テンプレートのチャネルごとのタブ | 超える |
|テンプレートあたりのアプリ数 | 50|
|||

詳細については [、「Teams の制限と仕様](limits-specifications-teams.md) 」を参照してください。

## <a name="related-topics"></a>関連項目

- [カスタムチームテンプレートを作成する](create-a-team-template.md)
- [既存のチームテンプレートからチームテンプレートを作成する](create-template-from-existing-template.md)
- [既存のチームからテンプレートを作成する](create-template-from-existing-team.md)
