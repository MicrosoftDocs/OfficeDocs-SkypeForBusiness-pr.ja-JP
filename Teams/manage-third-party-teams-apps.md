---
title: Microsoft 365 全体で Teams アプリへのアクセスを管理する
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
ms.localizationpriority: high
search.appverid: MET150
description: Microsoft 365 全体で Teams アプリへのアクセスを管理する方法について説明します。
ms.openlocfilehash: 4c6f12d6895bd9c11d240f460285d2aa8cf27cb4
ms.sourcegitcommit: a64574da14969a33a77c7d979ffde452b5b3a531
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/02/2022
ms.locfileid: "67175871"
---
# <a name="manage-access-to-teams-apps-across-microsoft-365"></a>Microsoft 365 全体で Teams アプリへのアクセスを管理する

アプリ開発者は、Teams で動作するアプリに加えて、Outlook と Office.com で動作するように Microsoft Teams アプリを強化できます。 エンド ユーザーは、強化後に Microsoft Outlook と Microsoft Office.com の Teams で強化されたアプリを使用できます。 現時点では、Teams、Outlook、および Office.com でこれらの特定のアプリを表示および使用できるのは、対象指定リリースのエンド ユーザーのみです。 既存の Teams 管理者エクスペリエンスは、これらのアプリへのアクセスを管理するために適用されます。 この変更に関する通知は、[メッセージ センター](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter/:/messages/MC334280)で入手できます。 Teams 管理者は、特定のエンド ユーザーが強化されたアプリを使用したり、Teams、Outlook、Office.com で強化されたアプリへのアクセスを管理したりすることができます。 Teams 管理者は、Teams 管理センターを使用してアプリへのアクセスを管理します。

Outlook と Office.com で使用する場合、強化されたアプリでは、Teams で付与された既存のアクセス許可が引き続き使用されます。 [強化されたアプリのアクセス許可に変更はありません](https://devblogs.microsoft.com/microsoft365dev/ignite-2021-building-apps-for-collaboration-in-a-hybrid-world/#personal-tabs)。

強化されたアプリの一覧を次に示します。

* [monday.com](https://teams.microsoft.com/l/app/eab2d3ce-6d6a-4415-abc4-5f40a8317b1f)
* [Mural](https://teams.microsoft.com/l/app/c738b607-88dd-4f16-aefe-6a824c65d25d)
* [Power BI](https://teams.microsoft.com/l/app/1c4340de-2a85-40e5-8eb0-4f295368978b)
* [SurveyMonkey](https://teams.microsoft.com/l/app/0fd925a0-357f-4d25-8456-b3022aaa41a9)
* [Zoho Projects](https://teams.microsoft.com/l/app/4a39aea9-8537-4c2f-b66d-ca364eb3b80d)
* [YouTube](https://teams.microsoft.com/l/app/com.microsoft.teamspace.tab.youtube)

次の方法を使用して、Teams アプリへのエンド ユーザー アクセスを制御できます。 Office アプリ管理者である場合は、グローバル管理者または Teams 管理者に連絡して、アプリへのアクセスを管理してください。

| アクセスを管理するオプション |ポータル|グローバル管理者|Teams 管理者|
|--|---|---|--|
| 対象指定リリースのエンド ユーザーのみが新しいアプリにアクセスできます。 ユーザーを標準リリースに移動します。 「[標準または対象指定リリース オプションを設定する](/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true)」をご覧ください | Microsoft 365 管理センター | Yes | いいえ |
| 特定のエンド ユーザーの新しいアプリへのアクセスを管理します。 「[カスタム アクセス許可ポリシーを追加する](teams-app-permission-policies.md#create-a-custom-app-permission-policy)」と「[カスタム ポリシーをユーザーに割り当てる](policy-assignment-overview.md)」を参照してください。 | Teams 管理センター | Yes | Yes |
| 組織全体のすべてのエンド ユーザーの新しいアプリへのアクセスを管理します。 [「アプリの許可または禁止](manage-apps.md#allow-and-block-apps)」をご覧ください。 | Teams 管理センター | Yes | Yes |

> [!NOTE]
> [標準リリース オプション](/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true)を使用して、エンド ユーザー アクセスを管理することをお勧めします。 その他のオプションでは、エンド ユーザー アクセスが削除され、Teams で既存のアプリを使用できなくなります。

> [!NOTE]
> Outlook と Office で同じアプリの既存の市場内アドインをインストールしたユーザーは、引き続きそのアプリを使用します。 アドインは Teams アプリではなく、Teams 管理者はアクセスを管理できません。

## <a name="see-also"></a>関連項目

* [Microsoft 365 用に設計されたMicrosoft Teams アプリは、Outlook と Office.com のプレビュー版で提供されます](https://techcommunity.microsoft.com/t5/microsoft-365-blog/microsoft-teams-apps-designed-for-microsoft-365-coming-in/ba-p/3269538)
* [Microsoft 365 の管理者ロールを理解する](/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide&preserve-view=true)  
* [Outlook アドインについて](/office/dev/add-ins/outlook/outlook-add-ins-overview)
* [開発者が Microsoft 365 全体で作業できるように Teams アプリを拡張する方法](/microsoftteams/platform/m365-apps/overview)
