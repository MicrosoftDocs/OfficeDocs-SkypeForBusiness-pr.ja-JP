---
title: 小売業の Teams テンプレートの使用を開始する
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: phecda louie
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
localization_priority: Normal
search.appverid: MET150
description: チームテンプレートを使用して、小売業者のニーズに合わせて設計されたチーム構造を作成する方法について説明します。
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1ef5647ba20b3fd9d3d4378182ea2e8b39b1487b
ms.sourcegitcommit: 332817f49ec1e6767334fdd4c2ec3f791020a26c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2019
ms.locfileid: "36767103"
---
# <a name="get-started-with-teams-templates-in-retail"></a>小売業の Teams テンプレートの使用を開始する 

Teams テンプレートを使用すると、設定、チャネル、プリインストールされているアプリに定義済みのテンプレートを提供して、チームをすばやく簡単に作成できます。

Teams のテンプレートには、小売業者のニーズに合わせて設計されたチーム構造の事前定義が含まれています。 Teams テンプレートを使用すると、小売業者に適したチームの種類をすばやく作成して、組織全体に展開することができます。 また、チームテンプレートを拡張して、特定の組織のニーズに合わせてカスタマイズされたチームを作成することもできます。

この記事では、各チームテンプレートを紹介し、その使用をお勧めする方法について説明します。

この記事は、小売組織全体で複数のチームの計画、展開、管理を担当している場合に使います。 組織に Teams サービスを既に展開していることを前提としています。 まだチームをロールアウトしていない場合は、「 [Microsoft teams をロールアウトする方法](How-to-roll-out-teams.md)」を参照してください。

チームテンプレートの詳細については、「[チームテンプレートの使用を開始](get-started-with-teams-templates.md)する」を参照してください。

## <a name="store-template"></a>ストアテンプレート

ストアテンプレートは、個々の小売店の場所を表すチームの作成に適しています。 ストアテンプレートを使用して、組織内の各小売店舗の場所に対してチームを作成できます。

| ベーステンプレートの種類 | baseTemplateId | この基本テンプレートに含まれるプロパティ |
| ------------------ | -------------- | ----------------------------------------------------- |
| 向け <br>ストア | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')`| チャネル <ul><li>シフトシフト\*</li><li>意欲\*</li></ul>\*自動お気に入りチャネル<br><br>チームのプロパティ <ul><li>チームの表示がパブリックに設定</li></ul> <br>メンバーの権限 <ul><li>チャンネルを作成、更新、削除できません </li><li>アプリを追加または削除できません </li><li>タブの作成、更新、削除ができない</li><li>コネクタの作成、更新、削除ができない</li><ul>|
||||

組織のストアテンプレートをカスタマイズするための推奨される方法:

- 組織が各ストア内に部署を持っている場合は、部門ごとにチャネルを追加します。 これにより、部門内でのコミュニケーションとコラボレーションが容易になります。

- 組織に内部の web サイトがある場合 (SharePoint サイトなど) は、関連するチームチャネルのタブとしてピン留めすることを検討してください。 手順については、「[チームテンプレートの使用を開始](get-started-with-teams-templates.md)する」を参照してください。

## <a name="manager-collaboration-template"></a>Manager グループ作業テンプレート

マネージャーコラボレーションテンプレートは、小売業者のニーズに合わせて設計された Teams テンプレートのもう1つです。 マネージャーコラボレーションテンプレートは、ストアや地域で共同作業するためのチームを作成するのに適しています。たとえば、組織に地域がある場合は、カリフォルニア地域のマネージャーコラボレーションチームを作成し、その地域のすべてのストアマネージャーとその地域の地域マネージャーを含めることができます。

| ベーステンプレートの種類 | baseTemplateId | この基本テンプレートに含まれるプロパティ |
| ------------------ | -------------- | ----------------------------------------------------- |
| 向け <br>ストア | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')`| チャネル <ul><li>操作\*</li><li>意欲\*</li></ul>\*自動お気に入りチャネル<br><br>チームのプロパティ <ul><li>チームの表示はプライベートに設定</li></ul> <br>メンバーの権限 <ul><li>チャンネルを作成、更新、削除できます </li><li>アプリを追加/削除できる </li><li>タブを作成、更新、削除できます</li><li>コネクタを作成、更新、削除できます</li><ul>|
||||

組織のマネージャーコラボレーションテンプレートをカスタマイズするには、次の方法をお勧めします。

- 組織に、マネージャーに関連する内部の web サイト (SharePoint サイトなど) がある場合は、それらを関連チームチャネルのタブとして固定することを検討してください (手順について[は、こちら](get-started-with-teams-templates.md)のドキュメントを参照してください)。
