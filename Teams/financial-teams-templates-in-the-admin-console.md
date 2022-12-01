---
title: 財務チーム テンプレートを使用する
author: lanachin
ms.author: v-lanachin
manager: samanro
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: yinchang
ms.collection:
- M365-collaboration
ms.localizationpriority: high
search.appverid: MET150
description: 金融サービス組織のチームを迅速かつ簡単に作成するために、Teams 管理センターや Microsoft Graph で財務チーム テンプレートを管理および使用する方法を説明します。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
- chat-teams-channels-revamp
appliesto:
- Microsoft Teams
ms.openlocfilehash: 096bab4289d5ac9e81c63f83cd73efd41d98e7be
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198691"
---
# <a name="use-financial-team-templates"></a>財務チーム テンプレートを使用する

Microsoft Teams のチーム テンプレートでは、設定、チャネル、事前にインストールされたアプリの定義済みチーム構造を使用することで、チームをすばやく簡単に作成できます。

金融サービス組織の場合、チーム テンプレートは特に強力で、組織全体に一貫したチームを迅速に展開するのに役立ちます。 テンプレートは、スタッフが Teams を効果的に使用する方法を理解するのにも役立ちます。

Teams には、金融サービス組織向けに設計されたテンプレートがあります。 これらの事前構築済みのテンプレートを使用して、スタッフがコミュニケーションや共同作業を行うチームを迅速に作成できます。 この記事では、これらの各テンプレートを紹介し、それらの使用方法を推奨します。

チーム テンプレートの管理方法と作業方法は、管理者か開発者かによって異なります。

|以下の場合: | 次に、以下の場合: |
| ---- | --------- |
| 管理者または IT 担当者 |[Manage team templates in the Teams admin center](#manage-team-templates-in-the-teams-admin-center). View team templates and apply templates policies to control which templates your staff can use in Teams for creating teams. |
| 開発者 | [Microsoft Graph を使用](#use-team-templates-with-microsoft-graph)して、チーム テンプレートでチームを作成します。 |

## <a name="manage-team-templates-in-the-teams-admin-center"></a>Teams 管理センターでチーム テンプレートを管理する

管理者として、Microsoft Teams 管理センターでチーム テンプレートを管理できます。 こちらで、各テンプレートに関する詳細を表示できます。 [テンプレート ポリシーを作成してスタッフに割り当て](templates-policies.md)、[チームの作成](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b)のために Teams でスタッフが表示できるテンプレートを制御することもできます。

一般的なチーム テンプレートの詳細については、「[Teams 管理センターでチーム テンプレートの使用を開始する](get-started-with-teams-templates-in-the-admin-console.md)」をご参照ください。

現在、金融サービス組織向けに事前構築済みの次のチーム テンプレートを提供しています。 表示するには、Teams 管理センターの左側のナビゲーションで、**[Teams]**、 > **[チーム テンプレート]** の順に移動します。

### <a name="collaborate-within-a-bank-branch"></a>銀行支店内での共同作業

打ち合わせ、顧客との会議、住宅ローンでの共同作業などの業務プロセスにおいて、銀行支店の従業員による共同作業を一元化し、お知らせや称賛によって全従業員と絶えず意思疎通を図ります。

| テンプレートの種類 |TemplateId| このテンプレートに含まれるプロパティ |
| ------------------ |--|----------------------------------------------------- |
|銀行の支店| `CollaborateWithinABankBranch`|チャネル <ul><li>全般<li>お知らせ</li><li>ハドル</li><li>顧客との会議</li><li>承認要求 </li><li>指導</li><li>スキルの習得</li><li>融資の処理</li><li>顧客の苦情</li><li>称賛</li><li>楽しい機能</li><li>コンプライアンス</li></ul>アプリ:<ul><li>称賛 </li><li>問題の報告者</li><li>Wiki</li><li>カレンダー</li><li>承認</li><li>情報</li><li>アイデア</li></ul>|
||||

## <a name="use-team-templates-with-microsoft-graph"></a>Microsoft Graph で Teams テンプレートを使用する

Developers can use Microsoft Graph to create teams from pre-built team templates. To learn more about using team templates with Microsoft Graph, see [Get started with team templates using Microsoft Graph](get-started-with-teams-templates.md), [Microsoft Teams API overview](/graph/teams-concept-overview?view=graph-rest-1.0&preserve-view=true), and [teamsTemplate resource type](/graph/api/resources/teamstemplate?view=graph-rest-1.0&preserve-view=true).

### <a name="bank-branch"></a>銀行の支店

打ち合わせ、顧客との会議、住宅ローンでの共同作業などの業務プロセスにおいて、銀行支店の従業員による共同作業を一元化し、お知らせや称賛によって全従業員と絶えず意思疎通を図ります。

| テンプレートの種類 |TemplateId| テンプレート チャネル |
| ------------------ |--|----------------------------------------------------- |
|銀行の支店|`https://graph.microsoft.com/beta/teamsTemplates('CollaborateWithinABankBranch')`|全般<br>お知らせ<br>ハドル<br>顧客との会議<br>承認要求<br>指導<br>スキルの習得<br>融資の処理<br>顧客の苦情<br>称賛<br>楽しい機能<br>コンプライアンス|
||||

> [!NOTE]
> 金融サービス組織に適用されるその他のチーム テンプレートについては、「[Microsoft Graph で作成した中小企業向けチーム テンプレート](smb-templates.md)」を参照してください。

## <a name="related-articles"></a>関連記事

- [Teams 管理センターで Teams テンプレートの使用を開始する](get-started-with-teams-templates-in-the-admin-console.md)
- [テンプレートからチームを作成する](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b)
- [Microsoft Graph を使用して、チーム テンプレートの使用を開始する](get-started-with-teams-templates.md)