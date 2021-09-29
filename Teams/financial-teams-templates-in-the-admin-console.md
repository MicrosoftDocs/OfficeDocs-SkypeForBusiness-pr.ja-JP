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
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9273f8519fd7aeea90ff35f49ca0d6986afa2d59
ms.sourcegitcommit: 6a65e318d49d8990f2b3409ff7bb2c61ea1f2525
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/29/2021
ms.locfileid: "59991106"
---
# <a name="use-financial-team-templates"></a>財務チーム テンプレートを使用する

Microsoft Teams のチーム テンプレートでは、設定、チャネル、事前にインストールされたアプリの定義済みチーム構造を使用することで、チームをすばやく簡単に作成できます。

金融サービス組織の場合、チーム テンプレートは特に強力で、組織全体に一貫したチームを迅速に展開するのに役立ちます。 テンプレートは、スタッフが Teams を効果的に使用する方法を理解するのにも役立ちます。

Teams には、金融サービス組織向けに設計されたテンプレートがあります。 これらの事前構築済みのテンプレートを使用して、スタッフがコミュニケーションや共同作業を行うチームを迅速に作成できます。 この記事では、これらの各テンプレートを紹介し、それらの使用方法を推奨します。

チーム テンプレートの管理方法と作業方法は、管理者か開発者かによって異なります。

|以下の場合: | 次に、以下の場合: |
| ---- | --------- |
| 管理者または IT 担当者 |[Teams 管理センターでチーム テンプレートを管理します](#manage-team-templates-in-the-teams-admin-center)。 チーム テンプレートを表示し、テンプレート ポリシーを適用して、Teams でチームの作成にスタッフが使用できるテンプレートを制御します。 |
| 開発者 | [Microsoft Graph を使用](#use-team-templates-with-microsoft-graph)して、チーム テンプレートでチームを作成します。 |

## <a name="manage-team-templates-in-the-teams-admin-center"></a>Teams 管理センターでチーム テンプレートを管理する

管理者として、Microsoft Teams 管理センターでチーム テンプレートを管理できます。 こちらで、各テンプレートに関する詳細を表示できます。 [テンプレート ポリシーを作成してスタッフに割り当て](templates-policies.md)、[チームの作成](https://support.microsoft.com/office/create-a-team-from-a-template-a90c30f3-9940-4897-ab5b-988e69e4cd9c)のために Teams でスタッフが表示できるテンプレートを制御することもできます。

一般的なチーム テンプレートの詳細については、「[Teams 管理センターでチーム テンプレートの使用を開始する](get-started-with-teams-templates-in-the-admin-console.md)」をご参照ください。

現在、金融サービス組織向けに事前構築済みの次のチーム テンプレートを提供しています。 表示するには、Teams 管理センターの左側のナビゲーションで、**[Teams]**、 > **[チーム テンプレート]** の順に移動します。

### <a name="collaborate-within-a-bank-branch"></a>銀行支店内での共同作業

打ち合わせ、顧客との会議、住宅ローンでの共同作業などの業務プロセスにおいて、銀行支店の従業員による共同作業を一元化し、お知らせや称賛によって全従業員と絶えず意思疎通を図ります。

| テンプレートの種類 |TemplateId| このテンプレートに含まれるプロパティ |
| ------------------ |--|----------------------------------------------------- |
|銀行の支店| `CollaborateWithinABankBranch`|チャネル <ul><li>全般<li>お知らせ</li><li>ハドル</li><li>顧客との会議</li><li>承認要求 </li><li>指導</li><li>スキルの習得</li><li>融資の処理</li><li>顧客の苦情</li><li>称賛</li><li>楽しい機能</li><li>コンプライアンス</li></ul>アプリ:<ul><li>称賛 </li><li>問題の報告者</li><li>Wiki</li><li>カレンダー</li><li>承認</li><li>情報</li><li>アイデア</li></ul>|
||||

## <a name="use-team-templates-with-microsoft-graph"></a>Microsoft Graph で Teams テンプレートを使用する

開発者は、Microsoft Graph を使用して、事前構築済みのチーム テンプレートでチームを作成できます。 Microsoft Graph を使用したチーム テンプレートの使用方法に関する詳細については、[Microsoft Graph を使用して、チーム テンプレートの使用を開始する](get-started-with-teams-templates.md)、[Microsoft Teams API の概要](/graph/teams-concept-overview?view=graph-rest-1.0)、[teamsTemplate リソースの種類](/graph/api/resources/teamstemplate?view=graph-rest-1.0)を参照してください。

### <a name="bank-branch"></a>銀行の支店

打ち合わせ、顧客との会議、住宅ローンでの共同作業などの業務プロセスにおいて、銀行支店の従業員による共同作業を一元化し、お知らせや称賛によって全従業員と絶えず意思疎通を図ります。

| テンプレートの種類 |TemplateId| テンプレート チャネル |
| ------------------ |--|----------------------------------------------------- |
|銀行の支店|`https://graph.microsoft.com/beta/teamsTemplates('CollaborateWithinABankBranch')`|全般<br>お知らせ<br>ハドル<br>顧客との会議<br>承認要求<br>指導<br>スキルの習得<br>融資の処理<br>顧客の苦情<br>称賛<br>楽しい機能<br>コンプライアンス|
||||

> [!NOTE]
> 金融サービス組織に適用されるその他のテンプレートについては、「[Microsoft Graph で作成した中小企業向けチーム テンプレート](smb-templates.md)」を参照してください。