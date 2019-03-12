---
title: 小売のチーム テンプレートを使い始める
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/11/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: phecda louie
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
localization_priority: Normal
search.appverid: MET150
description: 小売業者のニーズを満たすように設計チームの構造を作成するチーム テンプレートを使用する方法について説明します。
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4ee9ecf1a6db549a002c72f7eeea1e0a383ae966
ms.sourcegitcommit: 70d4d02a3cc894f2f197aeea459ac079cde63877
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/11/2019
ms.locfileid: "30543016"
---
# <a name="get-started-with-teams-templates-in-retail"></a>小売のチーム テンプレートを使い始める 

チーム テンプレートでは、迅速にすることし、設定、チャネル、およびプリインストールされているアプリケーションの定義済みのテンプレートを提供することで簡単にチームを作成します。

チーム テンプレートでは、小売業者のニーズに沿って設計されているチームの構造体の定義が作成済みがされます。 チーム テンプレートを使用すると、小売業者に対しても正常に機能し、組織全体に展開チームの種類を簡単に作成します。 組織のニーズに合わせたチームを作成するチーム テンプレートを拡張することもできます。

この資料では、チーム テンプレートとどのように使用をお勧めするを紹介します。

この資料は、計画、展開、および小売組織全体で複数のチームの管理を担当する場合のです。

チームの詳細についてテンプレート一般を参照してください[チーム テンプレートを使用して開始](get-started-with-teams-templates.md)します。

## <a name="store-template"></a>ストアのテンプレート

ストアのテンプレートは、チームは、個々 の小売店舗の場所を表すための作成に最適です。 ストアのテンプレートを使用すると、組織内の小売店舗ごとのチームを作成できます。

| 基本テンプレートの種類 | baseTemplateId | この基本テンプレートに用意されているプロパティ |
| ------------------ | -------------- | ----------------------------------------------------- |
| 小売- <br>ストア | `https://graph.microsoft.com/beta/teamsTemplates/`<br>`retailStore`| チャネル <ul><li>ハンドオフにシフトします。\*</li><li>学習\*</li></ul>\*自動お気に入りチャンネル<br><br>チーム プロパティ <ul><li>チームの可視性がパブリックに設定</li></ul> <br>メンバーのアクセス許可 <ul><li>チャネルの作成、更新または削除をことはできません。 </li><li>アプリケーションの追加と削除できません。 </li><li>作成/更新/削除タブをことはできません。</li><li>コネクタの作成/更新/削除をことはできません。</li><ul>|
||||

組織のストアのテンプレートをカスタマイズする方法をお勧めします。

- 組織部門各店舗内である場合は、各部門用のチャネルを追加します。 これは、部門のコミュニケーションやコラボレーションを容易になります。

- 組織が、内部の web サイト (SharePoint サイトなど) の場合は、チームの適切なチャネルでのタブとしてそれらの固定を検討してください。 手順については、[チーム テンプレートを使用](get-started-with-teams-templates.md)する参照してください。

## <a name="manager-collaboration-template"></a>マネージャー コラボレーション テンプレート

マネージャー コラボレーション テンプレートは、別販売店に沿って設計されているチーム テンプレートのいずれかが必要です。 マネージャーの共同作業のテンプレートは、一連の管理者は、複数の店舗や地域、その他のチームの作成に最適です。などの組織に領域がある場合は、カリフォルニア地域のマネージャーの共同作業チームを作成し、その地域の地域マネージャーと同様に、その領域内のすべてのストア マネージャーが含まれます。

| 基本テンプレートの種類 | baseTemplateId | この基本テンプレートに用意されているプロパティ |
| ------------------ | -------------- | ----------------------------------------------------- |
| 小売- <br>ストア | `https://graph.microsoft.com/beta/teamsTemplates/`<br>`retailManagerCollaboration`| チャネル <ul><li>運用\*</li><li>学習\*</li></ul>\*自動お気に入りチャンネル<br><br>チーム プロパティ <ul><li>チームの可視性が Private に設定</li></ul> <br>メンバーのアクセス許可 <ul><li>チャネルの作成、更新または削除ができます。 </li><li>アプリケーションの追加と削除できます。 </li><li>作成/更新/削除タブをことができます。</li><li>コネクタの作成/更新/削除をことができます。</li><ul>|
||||

組織のマネージャーの共同作業のテンプレートをカスタマイズする方法をお勧めします。

- 組織の内部 web サイト (SharePoint サイトなど)、マネージャーに関連する場合、チームの適切なチャネルでのタブとしてそれらの固定を検討してください (のマニュアルを参照してください[ここでは](get-started-with-teams-templates.md))。