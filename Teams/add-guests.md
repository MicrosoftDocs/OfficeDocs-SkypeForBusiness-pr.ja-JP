---
title: チームにゲストを追加する
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
search.appverid: MET150
ms.reviewer: sbhatta
f1.keywords:
- NOCSH
localization_priority: Priority
description: 管理者は、Microsoft Teams デスクトップ、Web クライアント、Azure Active Directory B2B コラボレーション ポータルなどのツールで、組織に新しいゲスト ユーザーを追加する方法について学習することができます。
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: baac3c7c7e83547672b8baeb0915081523e5bfe8
ms.sourcegitcommit: 20258b691ffc559b1656fd1e57f67f5c3a9e29e1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/15/2020
ms.locfileid: "46761283"
---
<a name="add-a-guest-to-a-team"></a>チームにゲストを追加する
=====================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Outlook、Gmail などの勤務先または通常のメール アカウントを持っているユーザーは、ゲストとして Teams に参加することができます。

管理者は、新しいゲスト ユーザーを複数の方法で組織に追加できます。
- グローバル管理者または Teams 管理者とチーム所有者は、Teams クライアントまたは Teams 管理センターでチームにゲストを追加できます。 詳細については、「[ゲストをチームに追加する](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f)」を参照してください。 ゲスト アクセスをまだ設定していない場合は、「[チームでゲストと共同で作業する](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)」の手順を実行してください。

> [!NOTE] 
> [**管理者とゲスト招待元ロールのユーザーは招待ができる**] が有効な場合には、これは適用されません。 ゲスト招待元ロールは Teams ではサポートされていないためです。

- Azure Active Directory (Azure AD) B2B コラボレーションを使用して組織にゲストを追加する。 Azure AD B2B コラボレーションを使用すると、グローバル管理者は、2,000 行以下のカンマ区切り (CSV) ファイルを B2B コラボレーション ポータルにアップロードすることで、複数の外部ユーザーを招待、承認できます。 詳細については、「[Azure Active Directory B2B コラボレーション](https://go.microsoft.com/fwlink/p/?linkid=826383)」をご覧ください。

Azure AD B2B コラボレーションを使用すると、組織は B2B ユーザーに対して条件付きアクセスと多要素認証 (MFA) ポリシーを適用できます。 これらのポリシーは、組織のフルタイムの従業員とメンバーに対して有効にするのと同じ方法で、テナント レベル、アプリ レベル、または個々のユーザー レベルで適用できます。 こうしたポリシーはリソース組織で実施します。 詳細については、「[B2B コラボレーション ユーザーの条件付きアクセス](https://go.microsoft.com/fwlink/?linkid=857454)」をご覧ください。 個別にゲスト ユーザーを拒否することはできません。

Azure AD B2B、Microsoft 365 グループまたは SharePoint Online 経由ですでに追加されたゲスト ユーザーは、すぐに利用を開始できます。 Microsoft 365 または Office 365 管理者またはチーム所有者は所有するチームにこのゲストを追加できます。 チームが Microsoft 365 グループにすでに追加されており、ゲストがそのグループに追加される場合、そのゲストはチームにアクセスできます。 Microsoft 365 グループを介してゲストを追加すると、そのゲストへの招待状メールは生成されません。そのため、チームの他のユーザーがそのゲストに通知する必要があります。

> [!NOTE]
> ゲストにも [ Microsoft 365 または Office 365 ](https://go.microsoft.com/fwlink/p/?linkid=282347) と [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) のサービスの制限が適用されます。

ゲストの追加は、Azure AD または Microsoft 365 セキュリティ センターで追跡できます。 Microsoft Teams でのゲストの追加は監査され、「Added member to group (グループにメンバーを追加しました)」という Azure AD グループ管理アクティビティとして記録されます。 詳細については、「[B2B コラボレーション ユーザーの監査およびレポート](https://go.microsoft.com/fwlink/p/?linkid=858884)」と「[ Microsoft 365 のセキュリティ センターで監査ログを検索する](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security--Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c)」をご覧ください。


## <a name="more-information"></a>詳細情報

[Microsoft Teams でゲスト アクセスを許可する](teams-dependencies.md)</br>
[Microsoft Teams へのゲスト アクセスをオンまたはオフにする](set-up-guests.md)</br>
[PowerShell を使用してチームへのゲスト アクセスを制御する](guest-access-powershell.md)
