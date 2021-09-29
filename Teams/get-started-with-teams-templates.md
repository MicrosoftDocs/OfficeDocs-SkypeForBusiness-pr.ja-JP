---
title: Microsoft Graph を使用してチーム テンプレートの使用を開始する
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
description: Microsoft Graph でのみ使用できるチーム テンプレートについて説明します。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: e570faff4ec7138457f7cd52e101a0a3632d64d2
ms.sourcegitcommit: 6a65e318d49d8990f2b3409ff7bb2c61ea1f2525
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/29/2021
ms.locfileid: "59991116"
---
# <a name="get-started-with-team-templates-using-microsoft-graph"></a>Microsoft Graph を使用してチーム テンプレートの使用を開始する

> [!NOTE]
> チーム テンプレートは現在、プライベート チャネルの作成をサポートされていません。 プライベート チャネルの作成は、テンプレート定義には含まれません。

Microsoft Teamsチーム テンプレートは、ビジネスの必要性やプロジェクトを中心に設計されたチームの構造の定義です。 チーム テンプレートを使用すると、定義済みの設定、チャネル、アプリを使用して、豊富なコラボレーション スペースをすばやく簡単に作成できます。 チーム テンプレートは、組織全体に一貫性のあるチームをデプロイするのに役立ちます。

Microsoft Graphでは、チームに含まれている事前構築済みのチーム テンプレートをTeamsチームを作成します。 この記事では、テンプレートで定義できるプロパティと、Microsoft Graph でのみ使用できるテンプレートについて説明します。

この記事は、次の場合に使用します。

- 組織全体で複数のチームの計画、デプロイ、管理を担当する<br>
- 定義済みのチャネルとアプリを含むチームをプログラムで作成する必要のある開発者

## <a name="team-template-capabilities"></a>チーム テンプレートの機能

チーム内のほとんどのプロパティは、テンプレートに含まれてサポートされています。 ただし、現在サポートされていないいくつかのプロパティと機能があります。 チーム テンプレートに含まれるものと含まれていないものについて簡単に説明します。

| **チーム テンプレートでサポートされるチームのプロパティ** | **チーム テンプレートでまだサポートされていないチームのプロパティ** |
| ------------------------------------------------ | -------------------------------------------------------- |
| テンプレートの種類 | チーム メンバーシップ |
| チーム名 | チームの画像 |
| チームの説明 | チャネル設定 |
| チームの可視性 (パブリックまたはプライベート) | コネクタ |
| チーム設定 (メンバー、ゲスト、@ メンションなど) | ファイルとコンテンツ |
| 自動お気に入りチャネル | |
| インストールされたアプリ | |
| ピン留めされたタブ | |

> [!NOTE]
> Microsoft Teams の将来のリリースでテンプレート機能を追加する予定なので、サポートされているプロパティに関する最新の情報を確認してください。

## <a name="pre-built-templates"></a>事前構築済みのテンプレート

事前構築されたチーム テンプレートは、特定の業界向けのテンプレートです。 Microsoft Graph でのみ使用できる事前構築済みのテンプレートを次に示Graph。

| テンプレートの種類 | TemplateId | このテンプレートに含まれるプロパティ |
| ------------------ | -------------- | ----------------------------------------------------- |
| Standard | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('standard')` | 追加のアプリとプロパティはありません |
| Education -<br>クラス チーム | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('educationClass')` | アプリ:<ul><li>OneNoteクラス ノートブック ([全般] タブ **にピン留め**) </li><li>割り当てアプリ ([全般] タブ **にピン留め** )</li></ul> チームのプロパティ:<ul><li>チームの可視性が **HiddenMembership に設定** されている (オーバーライドできない)</li></ul> |
| Education -<br>スタッフ チーム | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('educationStaff')` | アプリ:<ul><li>OneNoteスタッフ ノートブック ([全般] タブ **にピン留め**)</li></ul> |
|Education -<br>PLC チーム |`https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('educationProfessionalLearningCommunity')` | アプリ:<ul><li>OneNotePLC Notebook ([全般] タブ **にピン留め**)</ul></li>|

> [!NOTE]
> Teams クライアントと Microsoft Graph で使用できる事前構築済みのテンプレートの一覧については、「Teams 管理センターでチーム テンプレートの使用を開始する」[を参照してください](get-started-with-teams-templates-in-the-admin-console.md)。

## <a name="related-articles"></a>関連記事

- [管理センターでチーム テンプレートをTeamsする](get-started-with-teams-templates-in-the-admin-console.md)
- [チームを作成](/graph/api/team-post?view=graph-rest-beta) する (プレビュー中)
- [New-Team](/powershell/module/teams/New-Team?view=teams-ps)
