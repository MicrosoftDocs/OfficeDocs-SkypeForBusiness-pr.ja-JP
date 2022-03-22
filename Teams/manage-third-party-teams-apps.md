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
ms.openlocfilehash: 3fe95852fe88f64539ffa562d64619c1300b083b
ms.sourcegitcommit: abe942c294ed5fca70efdf039d38d611b9c21fe9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/18/2022
ms.locfileid: "63689155"
---
# <a name="manage-access-to-teams-apps-across-microsoft-365"></a>複数のアプリへのTeamsを管理Microsoft 365

アプリ開発者は、Outlook および Office.com で動作する Microsoft Teams アプリに加えて、Teams で動作するアプリを更新できます。 エンド ユーザーは、更新後に microsoft Outlook および Microsoft Office.com の Teams で更新されたアプリを使用できます。 現時点では、対象指定リリースのエンド ユーザーだけが、これらの特定のアプリを Teams、Outlook、Office.com で表示および使用できます。 既存の管理Teams、これらのアプリへのアクセスを管理するために適用されます。 この変更に関する通知は、メッセージ センターで [確認できます](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter/:/messages/MC334280)。 Teams 管理者は、特定のエンド ユーザーが更新されたアプリを使用したり、Teams、Outlook、Office.com で更新されたアプリへのアクセスを管理したりすることができます。 Teams管理者は、Teams管理センターを使用してアプリへのアクセスを管理します。

Outlook および Office.com で使用するために、更新されたアプリは引き続き、Teams で付与された既存のアクセス許可を使用します。 更新 [されたアプリのアクセス許可に変更はありません](https://devblogs.microsoft.com/microsoft365dev/ignite-2021-building-apps-for-collaboration-in-a-hybrid-world/#personal-tabs)。

次の方法を使用して、Teams アプリへのエンドユーザー アクセスを制御できます。 アプリ管理者の場合は、Office管理者または管理者に連絡してTeamsアクセスを管理してください。

| アクセスを管理するためのオプション |ポータル|グローバル管理者|Teams管理者|
|--|---|---|--|
| 対象指定リリースのエンド ユーザーだけが新しいアプリにアクセスできます。 ユーザーを Standard リリースに移行します。 「 [標準リリース オプションまたは対象指定リリース オプションを設定する」を参照してください。](/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true) | Microsoft 365 管理センター | はい | いいえ |
| 特定のエンド ユーザーの新しいアプリへのアクセスを管理します。 「 [カスタムアクセス許可ポリシーを追加し、](teams-app-permission-policies.md#create-a-custom-app-permission-policy) カスタム [ポリシーをユーザーに割り当てる」を参照してください](policy-assignment-overview.md)。 | Teams管理センター | はい | はい |
| 組織全体のすべてのエンド ユーザーの新しいアプリへのアクセスを管理します。 「アプリ [を許可またはブロックする」を参照してください](manage-apps.md#allow-and-block-apps)。 | Teams管理センター | はい | はい |

> [!NOTE]
> エンド ユーザーの [アクセスを管理するには、標準](/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true) リリース オプションを使用することをお勧めします。 その他のオプションでは、エンド ユーザーのアクセス権が削除され、既存のアプリを使用Teams。

> [!NOTE]
> Outlook と Office で同じアプリの既存の市場内アドインをインストールしたユーザーは、引き続きそのアプリを使用します。 アドインはアプリにTeams、管理者Teamsアクセスを管理できない場合があります。

## <a name="see-also"></a>関連項目

* [管理アカウントの管理者ロールについてMicrosoft 365](/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide&preserve-view=true)  
* [アドインOutlookについて](/office/dev/add-ins/outlook/outlook-add-ins-overview)
* [開発者がアプリを拡張Teamsアプリを複数のアプリで動作Microsoft 365](/microsoftteams/platform/m365-apps/overview)
