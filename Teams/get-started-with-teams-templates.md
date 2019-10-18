---
title: Teams のテンプレートの使用を開始する
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 01/25/2019
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: phlouie
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: チームテンプレートを使用して、定義済みのチャネルでチームを作成する方法について説明します。
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: d5832ccce69c9863e364f94c6e850f8d938ac162
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2019
ms.locfileid: "37569566"
---
# <a name="get-started-with-teams-templates"></a>Teams のテンプレートの使用を開始する 

Teams テンプレートは、ビジネスニーズまたはプロジェクトに合わせて設計された、チームの構造の事前定義済みの定義です。 チームテンプレートを使用して、さまざまなトピックのチャネルと豊富なコラボレーションスペースをすばやく作成したり、アプリをプレインストールしてミッションクリティカルなコンテンツやサービスを活用したりすることができます。 Teams テンプレートには、組織全体で一貫したチームを簡単に作成できる定義済みのチーム構造が用意されています。 

この記事では、テンプレートで定義できるプロパティ、基本テンプレートの種類について説明します。また、いくつかのサンプル要求を使って、テンプレートからチームを作成する方法についても説明します。
 
この記事は、次のような場合に適しています。

- 組織全体の複数のチームの計画、展開、管理を担当します。<br>
- 事前に定義されたチャネルとアプリを使って、プログラムを使用してチームを作成する開発者 

## <a name="teams-template-capabilities"></a>Teams のテンプレート機能

チーム内のほとんどのプロパティは、テンプレートに含まれており、サポートされています。 ただし、現在サポートされていないプロパティと機能はいくつかあります。 次の表では、チームテンプレートに含まれる内容と含まれていない機能の概要を簡単に説明します。

| **Teams テンプレートでサポートされているチームプロパティ** | **Teams テンプレートでまだサポートされていないチームプロパティ** |
| ------------------------------------------------ | -------------------------------------------------------- |
| ベーステンプレートの種類 | チームメンバーシップ |
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

ベーステンプレートの種類は、Microsoft が特定の業界向けに作成した特別なテンプレートです。 多くの場合、これらのベーステンプレートには、チームテンプレートではまだサポートされていないストアとチームのプロパティでは使用できない独自のアプリが含まれています。

ベーステンプレートの種類が定義されると、これらの特殊なテンプレートを追加または上書きして、追加のプロパティを指定することができます。 ただし、一部の基本テンプレートの種類には、オーバーライドできないプロパティが含まれています。 

既定では、基本テンプレートは [**標準**] に設定されています。これには、追加の固有のアプリや特別なプロパティは含まれていません。 次に示すのは、使用可能な基本テンプレートの種類の一覧です。

| ベーステンプレートの種類 | baseTemplateId | この基本テンプレートに含まれるプロパティ |
| ------------------ | -------------- | ----------------------------------------------------- |
| Standard | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('standard')` | 追加のアプリとプロパティはありません |
| Education<br>クラスチーム | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('educationClass')` | アプリ<ul><li>OneNote Class Notebook ( **[全般**] タブに固定されています) </li><li>課題アプリ ( **[全般**] タブに固定されています)</li></ul> チームのプロパティ:<ul><li>チームの表示が**HiddenMembership**に設定されている (上書きできない)</li></ul> |
| Education<br>スタッフチーム | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('educationStaff')` | アプリ<ul><li>OneNote スタッフノートブック ( **[全般**] タブに固定されています)</li></ul> |
|Education<br>PLC チーム |`https://graph.microsoft.com/beta/`<br>`teamsTemplates('educationProfessionalLearningCommunity')` | アプリ<ul><li>OneNote PLC ノートブック ( **[全般**] タブに固定されています)</ul></li>|
| 向け<br>ストア | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')` | チャネル<ul><li>シフトハンド</li><li>意欲</li></ul>チームのプロパティ<ul><li>チームの表示がパブリックに設定</li></ul>メンバーの権限<ul><li>メンバーがチャネルを作成、更新、または削除できないようにする</li><li>メンバーがアプリを追加または削除できないようにする</li><li>メンバーがコネクタを作成、更新、または削除できないようにする</li></ul> |
| 向け<br>上司との共同作業 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')` | チャネル<ul><li>シフトハンド</li><li>意欲</li></ul>チームのプロパティ:<ul><li>チームの表示はプライベートに設定</li></ul>メンバーの権限:<ul><li>メンバーがチャネルを作成、更新、または削除できないようにする</li><li>メンバーがアプリを追加または削除できないようにする</li><li>メンバーがコネクタを作成、更新、または削除できないようにする</li></ul>|
| ヘルス<br>ワード |`https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')` |チャネル <ul><li>お知らせ\*</li><li>Huddles\*</li><li>切り下げ</li><li>割り当てる\*</li><li>トレーニング\*</li></ul>\*自動お気に入りチャネル |
|ヘルス<br>所在 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')` |チャネル<ul><li>お知らせ\*</li><li>コン\*</li><li>Custodial</li><li>人事</li></li><li>薬</li></ul>\*自動お気に入りチャネル|
|||

> [!NOTE]
> Microsoft Teams の将来のリリースでは、より基本的なテンプレートの種類を追加するため、サポートされているプロパティについて、最新の情報を確認してください。


## <a name="related-topics"></a>関連項目

- [チームを作成する](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)(プレビュー中)
- [新規-チーム](https://docs.microsoft.com/powershell/module/teams/New-Team?view=teams-ps)
- [Microsoft Teams の管理者トレーニング](itadmin-readiness.md)
- [小売店向けテンプレートでTeamsを始めましょう](get-started-with-retail-teams-templates.md)
- [医療関係組織向けテンプレートでTeamsを始めましょう](expand-teams-across-your-org/healthcare/healthcare-templates.md)
