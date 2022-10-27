---
title: Microsoft 365 全体で Teams アプリへのアクセスを管理する
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-apps
audience: Admin
ms.date: 10/24/2022
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: high
search.appverid: MET150
description: Microsoft 365 全体で Teams アプリへのアクセスを管理する方法について説明します。
ms.openlocfilehash: 01aee1ebd59b52f05db36303d60358b86b95cf84
ms.sourcegitcommit: c2d8c7f779f4f938f8355632ecfbfc9147b53bb2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2022
ms.locfileid: "68738803"
---
# <a name="manage-access-to-teams-apps-across-microsoft-365"></a>Microsoft 365 全体で Teams アプリへのアクセスを管理する

アプリ開発者は、Teams で動作するアプリに加えて、Outlook と Office.com で動作するように Microsoft Teams アプリを強化できます。 エンド ユーザーは、強化後に Microsoft Outlook と Microsoft Office.com の Teams で強化されたアプリを使用できます。 現時点では、Teams、Outlook、Office.com でこれらの特定のアプリを表示および使用できるのは、 [対象リリース](/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true) のエンド ユーザーのみです。 この変更に関する通知は、[メッセージ センター](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter/:/messages/MC334280)で入手できます。

## <a name="manage-users-access-to-the-enhanced-apps"></a>拡張アプリへのユーザーのアクセスを管理する

既存の Teams 管理者エクスペリエンスは、これらのアプリへのアクセスを管理するために適用されます。 Teams 管理者は、Teams 管理センターを使用してアプリへのアクセスを管理します。 Teams 管理者は、特定のエンド ユーザーが強化されたアプリを使用したり、Teams、Outlook、Office.com で強化されたアプリへのアクセスを管理したりすることができます。

Outlook と Office.com で使用する場合、強化されたアプリでは、Teams で付与された既存のアクセス許可が引き続き使用されます。 拡張アプリのアクセス許可に変更はありません。 Outlook と Office で同じアプリの既存の市場内アドインをインストールしたユーザーは、引き続きそのアプリを使用します。 アドインは Teams アプリではなく、Teams 管理者はアクセスを管理できません。

Office Apps 管理者は、グローバル管理者または Teams 管理者に連絡して、拡張アプリのアクセスを管理できます。 詳細については、「 [Microsoft 365 の管理者ロール](/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide&preserve-view=true)」を参照してください。

エンド ユーザー アクセスは、次の方法で制御できます。

| アクセスを管理するオプション |ポータル|グローバル管理者|Teams 管理者|
|--|---|---|--|
| 対象指定リリースのエンド ユーザーのみが新しいアプリにアクセスできます。 ユーザーを標準リリースに移動します。 「[標準または対象指定リリース オプションを設定する](/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true)」をご覧ください | Microsoft 365 管理センター | Yes | いいえ |
| 特定のエンド ユーザーの新しいアプリへのアクセスを管理します。 「[カスタム アクセス許可ポリシーを追加する](teams-app-permission-policies.md#create-an-app-permission-policy)」と「[カスタム ポリシーをユーザーに割り当てる](policy-assignment-overview.md)」を参照してください。 | Teams 管理センター | Yes | Yes |
| 組織全体のすべてのエンド ユーザーの新しいアプリへのアクセスを管理します。 [「アプリの許可または禁止](manage-apps.md#allow-and-block-apps)」をご覧ください。 | Teams 管理センター | Yes | Yes |

> [!NOTE]
> [標準リリース オプション](/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true)を使用して、エンド ユーザー アクセスを管理することをお勧めします。 その他のオプションでは、エンド ユーザー アクセスが削除され、Teams で既存のアプリを使用できなくなります。

## <a name="list-of-enhanced-apps"></a>拡張アプリの一覧

強化されたアプリの一覧を次に示します。

* [Adobe Acrobat Sign](https://teams.microsoft.com/l/app/0f56a9d1-f502-40f9-a9e8-816d7adbb68b?source=app-details-dialog)
* [より大きな頭脳 eLearning](https://teams.microsoft.com/l/app/12345514-afee-abcd-acde-c5b34109abcd?source=app-details-dialog)
* [Bookings](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=app-details-dialog)
* [e2e-assure](https://teams.microsoft.com/l/app/8bdf3437-e038-4a93-abdc-00461630f6c3?source=app-details-dialog)
* [ESi-Tik](https://teams.microsoft.com/l/app/fe9627db-f23e-42b1-b454-d4d1ca5af33e?source=app-details-dialog)
* [レンズ](https://teams.microsoft.com/l/app/cfaeb687-adc7-4e36-a847-39bb35bfb631?source=app-details-dialog)
* [monday.com](https://teams.microsoft.com/l/app/eab2d3ce-6d6a-4415-abc4-5f40a8317b1f)
* [Mural](https://teams.microsoft.com/l/app/c738b607-88dd-4f16-aefe-6a824c65d25d)
* [マイ ステッカー](https://teams.microsoft.com/l/app/46fae4d0-faf5-11e9-80f3-53ad33b77bce?source=app-details-dialog)
* [PDF ツール](https://teams.microsoft.com/l/app/ca4b5141-5c46-47bc-a05e-2733d9bd69aa?source=app-details-dialog)
* [Power BI](https://teams.microsoft.com/l/app/1c4340de-2a85-40e5-8eb0-4f295368978b)
* [Priority Matrix](https://teams.microsoft.com/l/app/5be2b320-a5b7-4221-893c-dee506e4e365?source=app-details-dialog)
* [Jira 用スマート接続](https://teams.microsoft.com/l/app/6402de97-ce33-4386-bf28-b37e9e139c09?source=app-details-dialog)
* [間もなくスケジュールを設定する](https://teams.microsoft.com/l/app/bf280b0d-b87d-4158-9f2a-70b63674cd27?source=app-details-dialog)
* [合理化](https://teams.microsoft.com/l/app/aa6e7fb6-34ac-4947-9c13-3565c66e368b?source=app-details-dialog)
* [SurveyMonkey](https://teams.microsoft.com/l/app/0fd925a0-357f-4d25-8456-b3022aaa41a9)
* [文字起こしアシスタント TNA2](https://teams.microsoft.com/l/app/32c31ccd-b878-470e-9259-98c079ae5528?source=app-details-dialog)
* [ウンビコ](https://teams.microsoft.com/l/app/23fc1de6-dda0-4043-9ebb-a555e845843d?source=app-details-dialog)
* [ワルド](https://teams.microsoft.com/l/app/1d041f16-ab49-4627-bfda-6b60ad2cab6a?source=app-details-dialog)
* [YouTube](https://teams.microsoft.com/l/app/com.microsoft.teamspace.tab.youtube)
* [Zoho Projects](https://teams.microsoft.com/l/app/4a39aea9-8537-4c2f-b66d-ca364eb3b80d)

## <a name="related-articles"></a>関連記事

* [Microsoft 365 用に設計されたMicrosoft Teams アプリは、Outlook と Office.com のプレビュー版で提供されます](https://techcommunity.microsoft.com/t5/microsoft-365-blog/microsoft-teams-apps-designed-for-microsoft-365-coming-in/ba-p/3269538)
* [Microsoft 365 の管理者ロールを理解する](/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide&preserve-view=true)  
* [Outlook アドインについて](/office/dev/add-ins/outlook/outlook-add-ins-overview)
* [開発者が Microsoft 365 全体で作業できるように Teams アプリを拡張する方法](/microsoftteams/platform/m365-apps/overview)
