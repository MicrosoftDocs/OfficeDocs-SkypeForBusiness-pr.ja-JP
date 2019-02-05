---
title: Teams のテンプレートの使用を開始する
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 01/25/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: phecda louie
localization_priority: Normal
search.appverid: MET150
description: 定義済みのチャネルを持つチームを作成するチーム テンプレートを使用する方法について説明します。
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6b4e0ad44904a14d6a1296ea17080f668a3ab461
ms.sourcegitcommit: fddb1d6798e7a716ad87b0613f45a76deff6a043
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2019
ms.locfileid: "29735207"
---
# <a name="get-started-with-teams-templates"></a>Teams のテンプレートの使用を開始する 

チーム テンプレートのように設計されたビジネス ・ ニーズやプロジェクト チームの構造体の定義があらかじめ組み込まれており。 チャネルのさまざまなトピックの豊富なコラボレーション ・ スペースを簡単に作成し、ミッション ・ クリティカルなコンテンツとサービスを取得するアプリケーションをプレインストールするのには、チーム テンプレートを使用できます。 チーム テンプレートでは、組織全体で一貫性のあるチームを簡単に作成できる定義済みのチームの構造を提供します。 

この記事でテンプレートの種類は、基本テンプレートで定義可能なプロパティを説明し、いくつかのサンプル テンプレートからチームを作成する要求の使用方法。
 
ならここでするは。

- 計画、展開、および組織全体で複数のチームの管理を担当します。<br>
- 開発者はプログラムで定義済みのチャネルおよびアプリケーションとチームを作成しようとしています。 

## <a name="teams-template-capabilities"></a>チーム テンプレートの機能

チームのほとんどのプロパティが含まれているし、テンプレートでサポートされています。 いくつかのプロパティと、現在サポートされていない機能があります。 次の表は、含まれる機能とチーム テンプレートに含まれていない内容の簡単な概要を提供します。

| **チーム テンプレートでサポートされているチームのプロパティ** | **チーム テンプレートではサポートされていないチームのプロパティ** |
| ------------------------------------------------ | -------------------------------------------------------- |
| 基本テンプレートの種類 | チームのメンバーシップ |
| チーム名 | チームの画像 |
| チームの説明 | チャネルの設定 |
| チームの可視性 (パブリックまたはプライベート) | コネクタ |
| チームの設定 (たとえば、メンバー、参照投稿 @ のゲスト) | ファイルとコンテンツ |
| 自動お気に入りチャンネル | |
| インストールされているアプリケーション | |
| 固定タブ | | 

> [!NOTE]
> 複数のテンプレートの機能は、マイクロソフトのチームの今後のリリースを追加する、サポートされているプロパティには、最新の情報をチェックしてします。

## <a name="what-are-base-template-types"></a>基本テンプレートの種類を挙げてください。

基本テンプレートの種類とは、特定の業界にマイクロソフトが作成した特別なテンプレートです。 多くの場合、これらの基本テンプレートには、ストアとチーム プロパティをまだサポートされていない個別のチーム テンプレートでは利用できない独自のアプリケーションが含まれています。

基本テンプレートの種類を定義すると、拡張したり、これらの特別なテンプレートを指定するには追加のプロパティをオーバーライドできます。 ですが、いくつかの基本テンプレートの種類が含まれているプロパティをオーバーライドすることはできません。 

既定では、基本のテンプレートは、**標準的な**独自アプリケーションの追加や特別なプロパティが含まれていませんに設定されます。 次利用可能な種類の基本テンプレートの現在のリストに示します。

| 基本テンプレートの種類 | baseTemplateId | この基本テンプレートに用意されているプロパティ |
| ------------------ | -------------- | ----------------------------------------------------- |
| Standard | `https://graph.microsoft.com/beta/teamsTemplates/`<br>`standard` | なしのアプリケーションの追加とプロパティ |
| 教育-<br>クラスのチーム | `https://graph.microsoft.com/beta/teamsTemplates/`<br>`educationClass` | アプリケーション:<ul><li>OneNote クラスのノートブック ([**全般**] タブに固定されている) </li><li>割り当てのアプリケーション ([**全般**] タブに固定されている)</li></ul> チームのプロパティ:<ul><li>チームの表示/非表示に設定 (オーバーライドできない) **HiddenMembership**</li></ul> |
| 教育-<br>スタッフ チーム | `https://graph.microsoft.com/beta/teamsTemplates/`<br>`educationStaff` | アプリケーション:<ul><li>OneNote のスタッフのノートブック ([**全般**] タブに固定されている)</li></ul> |
|教育-<br>PLC チーム |`https://graph.microsoft.com/beta/teamsTemplates/`<br>`educationProfessionalLearningCommunity` | アプリケーション:<ul><li>OneNote PLC のノートブック ([**全般**] タブに固定されている)</ul></li>|
| 小売-<br>ストア | `https://graph.microsoft.com/beta/teamsTemplates/`<br>`retailStore` | チャネル:<ul><li>Shift キーをハンドオフ</li><li>学習</li></ul>チーム プロパティ<ul><li>チームの可視性がパブリックに設定</li></ul>メンバーのアクセス許可<ul><li>作成、更新、またはチャネルを削除してからメンバーを禁止します。</li><li>メンバーの追加またはアプリケーションを削除することを防ぐ</li><li>作成、更新、またはコネクタを削除してからメンバーを禁止します。</li></ul> |
| 小売-<br>マネージャーのコラボレーション | `https://graph.microsoft.com/beta/teamsTemplates/`<br>`retailManagerCollaboration` | チャネル:<ul><li>Shift キーをハンドオフ</li><li>学習</li></ul>チームのプロパティ:<ul><li>チームの可視性が Private に設定</li></ul>メンバーのアクセス許可:<ul><li>作成、更新、またはチャネルを削除してからメンバーを禁止します。</li><li>メンバーの追加またはアプリケーションを削除することを防ぐ</li><li>作成、更新、またはコネクタを削除してからメンバーを禁止します。</li></ul>|
| 医療・<br>区全体 |`https://graph.microsoft.com/beta/teamsTemplates/`<br>`healthcareWardWide` |チャネル: <ul><li>お知らせ\*</li><li>ライトを呼び出す</li><li>お楽しみツール\*</li><li>Huddles\*<li>スケジュールと患者の調査\*</li><li>トレーニングと認定 </li><li>ラウンド\*</li></ul>\*自動お気に入りチャンネル |
|医療・<br>病院全体 | `https://graph.microsoft.com/beta/teamsTemplates/`<br>`healthcareHospitalWide` |チャネル:<ul><li>お知らせ\*</li><li>コンプライアンス\*</li><li>信託</li><li>財務</li><li>お楽しみツール\*</li><li>人事管理</li><li>研究所</li><li>患者の安全性と品質の向上\*</li><li>薬剤</li></ul>\*自動お気に入りチャンネル|
|||

> [!NOTE]
> 追加されていく複数の基本テンプレート型の将来のマイクロソフトのチームのリリースに関する最新情報についてのチェックには、プロパティがサポートされているようです。


## <a name="related-topics"></a>関連トピック

- [チームの作成](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)(プレビュー) で
- [新しいチーム](https://docs.microsoft.com/powershell/module/teams/New-Team?view=teams-ps)
- [Microsoft Teams の管理者トレーニング](itadmin-readiness.md)
- [小売チーム テンプレートを使い始める](get-started-with-retail-teams-templates.md)
- [医療チーム テンプレートを使い始める](healthcare/healthcare-templates.md)