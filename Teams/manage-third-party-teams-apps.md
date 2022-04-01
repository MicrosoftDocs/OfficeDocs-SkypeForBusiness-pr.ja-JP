---
title: 複数のアプリへのTeamsを管理Microsoft 365
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.reviewer: v-tbasra
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: 複数のアプリへのTeamsを管理Microsoft 365。
ms.openlocfilehash: a9a0eb67323874e725510342e1e6810dcc5c0b0d
ms.sourcegitcommit: 2388838163812eeabcbd5331aaf680b79da3ccba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/31/2022
ms.locfileid: "64593002"
---
# <a name="manage-access-to-teams-apps-across-microsoft-365"></a>複数のアプリへのTeamsを管理Microsoft 365

アプリ開発者は、Microsoft Teams で動作するアプリに加えて、Outlook および Office.com で動作するアプリを強化Teams。 エンド ユーザーは、強化後、Teams、Microsoft Outlook、Microsoft Office.com で拡張アプリを使用できます。 現時点では、対象指定リリースのエンド ユーザーだけが、これらの特定のアプリを Teams、Outlook、Office.com で表示および使用できます。 既存の管理Teams、これらのアプリへのアクセスを管理するために適用されます。 この変更に関する通知は、メッセージ センターで [確認できます](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter/:/messages/MC334280)。 Teams管理者は、特定のエンド ユーザーが拡張アプリを使用したり、Teams、Outlook、Office.com で拡張アプリへのアクセスを管理したりすることができます。 Teams管理者は、Teams管理センターを使用してアプリへのアクセスを管理します。

Outlook および Office.com で使用するために、拡張アプリでは引き続き、Teams で付与された既存のアクセス許可が使用されます。 強化 [されたアプリのアクセス許可に変更はありません](https://devblogs.microsoft.com/microsoft365dev/ignite-2021-building-apps-for-collaboration-in-a-hybrid-world/#personal-tabs)。

強化されたアプリの一覧を次に示します。

* [Mural](https://teams.microsoft.com/l/app/c738b607-88dd-4f16-aefe-6a824c65d25d?source=app-details-dialog)
* [Power BI](https://teams.microsoft.com/l/app/1c4340de-2a85-40e5-8eb0-4f295368978b?source=app-details-dialog)
* [SurveyMonkey](https://teams.microsoft.com/l/app/0fd925a0-357f-4d25-8456-b3022aaa41a9?source=app-details-dialog)
* [Zoho Projects](https://teams.microsoft.com/l/app/4a39aea9-8537-4c2f-b66d-ca364eb3b80d?source=app-details-dialog)

次の方法を使用して、Teams アプリへのエンドユーザー アクセスを制御できます。 アプリ管理者の場合は、Office管理者または管理者に連絡してTeamsアクセスを管理してください。

| アクセスを管理するためのオプション |ポータル|グローバル管理者|Teams管理者|
|--|---|---|--|
| 対象指定リリースのエンド ユーザーだけが新しいアプリにアクセスできます。 ユーザーを Standard リリースに移行します。 「 [標準リリース オプションまたは対象指定リリース オプションを設定する」を参照してください。](/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true) | Microsoft 365 管理センター | はい | いいえ |
| 特定のエンド ユーザーの新しいアプリへのアクセスを管理します。 「 [カスタムアクセス許可ポリシーを追加し、](teams-app-permission-policies.md#create-a-custom-app-permission-policy) カスタム [ポリシーをユーザーに割り当てる」を参照してください](policy-assignment-overview.md)。 | Teams管理センター | Yes | Yes |
| 組織全体のすべてのエンド ユーザーの新しいアプリへのアクセスを管理します。 「アプリ [を許可またはブロックする」を参照してください](manage-apps.md#allow-and-block-apps)。 | Teams管理センター | Yes | Yes |

> [!NOTE]
> エンド ユーザーの [アクセスを管理するには、標準](/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true) リリース オプションを使用することをお勧めします。 その他のオプションでは、エンド ユーザーのアクセス権が削除され、既存のアプリを使用Teams。

> [!NOTE]
> Outlook と Office で同じアプリの既存の市場内アドインをインストールしたユーザーは、引き続きそのアプリを使用します。 アドインはアプリにTeams、管理者Teamsアクセスを管理できない場合があります。

## <a name="see-also"></a>関連項目

* [Microsoft Teamsおよび Microsoft 365.com にプレビューで提供されるOutlook向Office アプリ](https://techcommunity.microsoft.com/t5/microsoft-365-blog/microsoft-teams-apps-designed-for-microsoft-365-coming-in/ba-p/3269538)
* [管理アカウントの管理者ロールについてMicrosoft 365](/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide&preserve-view=true)  
* [アドインOutlookについて](/office/dev/add-ins/outlook/outlook-add-ins-overview)
* [開発者がアプリを拡張Teamsアプリを複数のアプリで動作Microsoft 365](/microsoftteams/platform/m365-apps/overview)
