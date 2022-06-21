---
title: Microsoft 365間でTeams アプリへのアクセスを管理する
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
description: Microsoft 365全体でTeams アプリへのアクセスを管理する方法について説明します。
ms.openlocfilehash: 34587bd02f9fddb73bce8e159b9df317b3bc619a
ms.sourcegitcommit: 9946c6c1faa78617ccd7bdf115457090ebce5619
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/21/2022
ms.locfileid: "66190602"
---
# <a name="manage-access-to-teams-apps-across-microsoft-365"></a>Microsoft 365間でTeams アプリへのアクセスを管理する

アプリ開発者は、Teamsで動作するアプリに加えて、OutlookおよびOffice.com で動作するようにMicrosoft Teams アプリを強化できます。 エンド ユーザーは、強化後、microsoft Outlook および Microsoft Office.com のTeamsで強化されたアプリを使用できます。 現時点では、対象となるリリースのエンド ユーザーのみが、Teams、Outlook、Office.com でこれらの特定のアプリを表示して使用できます。 既存のTeams管理者エクスペリエンスは、これらのアプリへのアクセスを管理するために適用されます。 この変更に関する通知は、 [メッセージ センター](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter/:/messages/MC334280)で入手できます。 Teams管理者は、特定のエンド ユーザーが強化されたアプリを使用したり、Teams、Outlook、Office.com で強化されたアプリへのアクセスを管理したりできます。 Teams管理者は、Teams管理センターを使用してアプリへのアクセスを管理します。

OutlookおよびOffice.com で使用するために、強化されたアプリでは、Teamsで付与された既存のアクセス許可が引き続き使用されます。 [強化されたアプリのアクセス許可に変更はありません](https://devblogs.microsoft.com/microsoft365dev/ignite-2021-building-apps-for-collaboration-in-a-hybrid-world/#personal-tabs)。

強化されたアプリの一覧を次に示します。

* [monday.com](https://teams.microsoft.com/l/app/eab2d3ce-6d6a-4415-abc4-5f40a8317b1f)
* [壁画](https://teams.microsoft.com/l/app/c738b607-88dd-4f16-aefe-6a824c65d25d)
* [Power BI](https://teams.microsoft.com/l/app/1c4340de-2a85-40e5-8eb0-4f295368978b)
* [SurveyMonkey](https://teams.microsoft.com/l/app/0fd925a0-357f-4d25-8456-b3022aaa41a9)
* [Zoho Projects](https://teams.microsoft.com/l/app/4a39aea9-8537-4c2f-b66d-ca364eb3b80d)
* [YouTube](https://teams.microsoft.com/l/app/com.microsoft.teamspace.tab.youtube)

次の方法を使用して、Teams アプリへのエンド ユーザー アクセスを制御できます。 Office アプリ管理者の場合は、グローバル管理者またはTeams管理者に問い合わせて、アプリへのアクセスを管理します。

| アクセスを管理するオプション |ポータル|グローバル管理者|Teams管理者|
|--|---|---|--|
| ターゲット リリースのエンド ユーザーのみが新しいアプリにアクセスできます。 ユーザーを Standard リリースに移動します。 [「Standard または Targeted リリース オプションを設定する」を](/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true)参照してください。 | Microsoft 365 管理センター | はい | いいえ |
| 特定のエンド ユーザーの新しいアプリへのアクセスを管理します。 [「カスタムアクセス許可ポリシーを追加し、カスタム ポリシー](teams-app-permission-policies.md#create-a-custom-app-permission-policy)[をユーザーに割り当てる」を参照してください](policy-assignment-overview.md)。 | Teams 管理センター | はい | はい |
| 組織全体のすべてのエンド ユーザーの新しいアプリへのアクセスを管理します。 [「アプリを許可またはブロックする](manage-apps.md#allow-and-block-apps)」を参照してください。 | Teams 管理センター | はい | はい |

> [!NOTE]
> [Standard リリース オプションを](/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true)使用して、エンド ユーザー アクセスを管理することをお勧めします。 その他のオプションでは、エンド ユーザー アクセスが削除され、Teamsで既存のアプリを使用できなくなります。

> [!NOTE]
> 同じアプリの既存の市場内アドインをOutlookおよびOfficeにインストールしたユーザーは、引き続きそのアプリを使用します。 アドインはアプリTeamsされておらず、Teams管理者はアクセスを管理できません。

## <a name="see-also"></a>関連項目

* [OutlookとOffice.com へのプレビュー Microsoft 365向けに設計されたMicrosoft Teams アプリ](https://techcommunity.microsoft.com/t5/microsoft-365-blog/microsoft-teams-apps-designed-for-microsoft-365-coming-in/ba-p/3269538)
* [Microsoft 365の管理者ロールを理解する](/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide&preserve-view=true)  
* [アドインOutlookについて](/office/dev/add-ins/outlook/outlook-add-ins-overview)
* [開発者がTeams アプリをMicrosoft 365間で動作するように拡張する方法](/microsoftteams/platform/m365-apps/overview)
