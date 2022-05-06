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
description: Microsoft Graphでのみ使用できるチーム テンプレートについて説明します。
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
# <a name="get-started-with-team-templates-using-microsoft-graph"></a>Microsoft Graph を使用して、チーム テンプレートの使用を開始する

> [!NOTE]
> チーム テンプレートは現在、プライベート チャネルの作成をサポートしていません。 プライベート チャネルの作成は、テンプレート定義には含まれません。

Microsoft Teamsのチーム テンプレートは、ビジネスニーズまたはプロジェクトを中心に設計されたチームの構造の定義です。 チーム テンプレートを使用すると、定義済みの設定、チャネル、アプリを使用して、豊富なコラボレーション スペースをすばやく簡単に作成できます。 チーム テンプレートは、組織全体に一貫性のあるチームを展開するのに役立ちます。

Microsoft Graphでは、Teamsに含まれる事前構築済みのチーム テンプレートを使用してチームを作成します。 この記事では、テンプレートで定義できるプロパティと、Microsoft Graphでのみ使用できるテンプレートについて説明します。

この記事は、次の場合に適しています。

- 組織全体の複数のチームの計画、展開、管理を担当する<br>
- 定義済みのチャネルとアプリを含むチームをプログラムで作成したい開発者

## <a name="team-template-capabilities"></a>チーム テンプレートの機能

チーム内のほとんどのプロパティは、テンプレートによって含まれ、サポートされています。 ただし、現在サポートされていないいくつかのプロパティと機能があります。 チーム テンプレートに含まれる内容と含まれていない内容の簡単な概要を次に示します。

| **チーム テンプレートでサポートされているチーム プロパティ** | **チーム テンプレートではまだサポートされていないチーム プロパティ** |
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
> 今後のMicrosoft Teamsリリースでは、テンプレート機能を追加する予定です。そのため、サポートされているプロパティに関する最新の情報を確認してください。

## <a name="pre-built-templates"></a>事前構築済みテンプレート

事前構築済みのチーム テンプレートは、特定の業界向けに作成したテンプレートです。 Microsoft Graphでのみ使用できる事前構築済みテンプレートを次に示します。

| テンプレートの種類 | TemplateId | このテンプレートに含まれるプロパティ |
| ------------------ | -------------- | ----------------------------------------------------- |
| Standard | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('standard')` | 追加のアプリとプロパティはありません |
| 教育機関 -<br>クラス チーム | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('educationClass')` | アプリ:<ul><li>OneNote クラス ノートブック ([**全般**] タブにピン留め) </li><li>割り当てアプリ ([ **全般** ] タブにピン留め)</li></ul> チームのプロパティ:<ul><li>チームの可視性が **HiddenMembership** に設定されている (オーバーライドできません)</li></ul> |
| 教育機関 -<br>スタッフ チーム | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('educationStaff')` | アプリ:<ul><li>OneNote Staff Notebook (**[全般**] タブにピン留め)</li></ul> |
|教育機関 -<br>PLC チーム |`https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('educationProfessionalLearningCommunity')` | アプリ:<ul><li>ONENOTE PLC Notebook (**[全般**] タブにピン留め)</ul></li>|

> [!NOTE]
> Teams クライアントと Microsoft Graphで使用できる事前構築済みテンプレートの一覧については、[Teams管理センターのチーム テンプレートを使用した概要を](get-started-with-teams-templates-in-the-admin-console.md)参照してください。

## <a name="related-articles"></a>関連記事

- [Teams 管理センターで Teams テンプレートの使用を開始する](get-started-with-teams-templates-in-the-admin-console.md)
- [チームを作成する](/graph/api/team-post?view=graph-rest-beta) (プレビュー段階)
- [New-Team](/powershell/module/teams/New-Team?view=teams-ps)
