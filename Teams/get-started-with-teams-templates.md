---
title: Microsoft Graph を使用して、チーム テンプレートの使用を開始する
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
description: Microsoft Graph でのみ使用できるチーム テンプレートについて説明します。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4560e5845b2f9beabc8227d79bebc889c9d42c37
ms.sourcegitcommit: ff161779577ce9cc892f1b6b8861ad49ff4c3ca3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2022
ms.locfileid: "69131126"
---
# <a name="get-started-with-team-templates-using-microsoft-graph"></a>Microsoft Graph を使用して、チーム テンプレートの使用を開始する

> [!NOTE]
> 現在、チーム テンプレートではプライベート チャネルの作成はサポートされていません。 プライベート チャネルの作成は、テンプレート定義には含まれません。

Microsoft Teams のチーム テンプレートは、ビジネス ニーズまたはプロジェクトを中心に設計されたチームの構造の定義です。 チーム テンプレートを使用すると、定義済みの設定、チャネル、アプリを使用して、豊富なコラボレーション スペースをすばやく簡単に作成できます。 チーム テンプレートは、組織全体で一貫性のあるチームを展開するのに役立ちます。

Microsoft Graph では、独自の [テンプレートを作成](/graph/api/resources/teamtemplate?view=graph-rest-beta) したり、Teams に含まれている事前に構築されたチーム テンプレートを使用してチームを作成したりできます。 この記事では、テンプレートで定義できるプロパティと、Microsoft Graph でのみ使用できる事前構築済みのテンプレートについて説明します。

この記事は、次の場合に適しています。

- 組織全体で複数のチームを計画、展開、管理する責任<br>
- 定義済みのチャネルとアプリを使用してプログラムでチームを作成する開発者

## <a name="team-template-capabilities"></a>チーム テンプレートの機能

チームのほとんどのプロパティは、テンプレートによって含まれ、サポートされています。 ただし、現在サポートされていないプロパティと機能がいくつかあります。 含まれている内容と、チーム テンプレートに含まれていない内容の簡単な概要を次に示します。

| **チーム テンプレートでサポートされるチーム プロパティ** | **チーム テンプレートでまだサポートされていないチーム プロパティ** |
| ------------------------------------------------ | -------------------------------------------------------- |
| テンプレートの種類 | チーム メンバーシップ |
| チーム名 | チーム画像 |
| チームの説明 | チャネル設定 |
| チームの可視性 (パブリックまたはプライベート) | コネクタ |
| チーム設定 (メンバー、ゲスト、@ メンションなど) | ファイルとコンテンツ |
| 自動お気に入りのチャネル | |
| インストールされたアプリ | |
| ピン留めされたタブ | |

> [!NOTE]
> Microsoft Teams の今後のリリースではさらにテンプレート機能を追加する予定なので、サポートされているプロパティに関する最新の情報を確認してください。

## <a name="pre-built-templates"></a>事前構築済みのテンプレート

事前に構築されたチーム テンプレートは、特定の業界向けに作成したテンプレートです。 Microsoft Graph でのみ使用できる事前構築済みのテンプレートを次に示します。

| テンプレートの種類 | TemplateId | このテンプレートに含まれるプロパティ |
| ------------------ | -------------- | ----------------------------------------------------- |
| Standard | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('standard')` | 追加のアプリとプロパティはありません |
| 教育-<br>クラス チーム | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('educationClass')` | アプリ:<ul><li>OneNote クラス ノートブック ([ **全般** ] タブにピン留め) </li><li>割り当てアプリ ([ **全般** ] タブにピン留め)</li></ul> チームのプロパティ:<ul><li>チームの可視性が **HiddenMembership** に設定されている (オーバーライドできません)</li></ul> |
| 教育-<br>スタッフ チーム | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('educationStaff')` | アプリ:<ul><li>OneNote Staff Notebook ( **[全般** ] タブにピン留め)</li></ul> |
|教育-<br>PLC チーム |`https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('educationProfessionalLearningCommunity')` | アプリ:<ul><li>OneNote PLC Notebook ( **[全般** ] タブにピン留め)</ul></li>|

> [!NOTE]
> Teams クライアントと Microsoft Graph で使用できる事前構築済みのテンプレートの一覧については、「 [Teams 管理センターでのチーム テンプレートの概要](get-started-with-teams-templates-in-the-admin-console.md)」を参照してください。

## <a name="related-articles"></a>関連記事

- [Teams 管理センターで Teams テンプレートの使用を開始する](get-started-with-teams-templates-in-the-admin-console.md)
- [チームを作成する](/graph/api/team-post?view=graph-rest-beta) (プレビュー段階)
- [New-Team](/powershell/module/teams/New-Team?view=teams-ps)
