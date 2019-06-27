---
title: チームにゲストを追加する
author: somakbhattacharyya
ms.author: sbhatta
manager: serdars
ms.date: 06/21/2019
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
ms.reviewer: sbhatta
localization_priority: Priority
description: 組織に新しいゲスト ユーザーを追加するために管理者が利用できる Microsoft Teams デスクトップ、Web クライアント、Azure Active Directory B2B コラボレーション ポータルなどのツールについて説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 67a00b87dbe3f29ce6588d4ff84302df2f07ce69
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2019
ms.locfileid: "35221635"
---
<a name="add-a-guest-to-a-team"></a>チームにゲストを追加する
=====================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Outlook、Gmail などの勤務先または通常のメール アカウントを持っているユーザーは、ゲストとして Teams に参加することができます。

管理者は、新しいゲスト ユーザーを複数の方法で組織に追加できます。
- チームの所有者であるグローバル管理者は、Microsoft Teams デスクトップまたは Web クライアントのいずれかを使用してチームにゲストを追加できます。 詳細については、「[ゲストをチームに追加する](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f)」を参照してください。
- Azure Active Directory (Azure AD) B2B コラボレーションを使用して組織にゲストを追加する。 Azure AD B2B コラボレーションを使用すると、グローバル管理者は、2,000 行以下のカンマ区切り (CSV) ファイルを B2B コラボレーション ポータルにアップロードすることで、複数の外部ユーザーを招待、承認できます。 詳細については、「[Azure Active Directory B2B コラボレーション](https://go.microsoft.com/fwlink/p/?linkid=826383)」をご覧ください。

Azure AD B2B コラボレーションを使用すると、組織は B2B ユーザーに対して条件付きアクセスと多要素認証 (MFA) ポリシーを適用できます。 これらのポリシーは、組織のフルタイムの従業員とメンバーに対して有効にするのと同じ方法で、テナント レベル、アプリ レベル、または個々のユーザー レベルで適用できます。 こうしたポリシーはリソース組織で実施します。 詳細については、「[B2B コラボレーション ユーザーの条件付きアクセス](https://go.microsoft.com/fwlink/?linkid=857454)」をご覧ください。 個別にゲスト ユーザーを拒否することはできません。

Azure AD B2B、Office 365 グループまたは SharePoint Online 経由ですでに追加されたゲスト ユーザーは、すぐに利用を開始できます。 Office 365 管理者またはチーム所有者は所有するチームにこのゲストを追加できます。 チームが Office 365 グループにすでに追加されており、ゲストがそのグループに追加される場合、そのゲストはチームにアクセスできます。 Office 365 グループを介してゲストを追加すると、そのゲストへの招待状メールは生成されません。そのため、チームの他のユーザーがそのゲストに通知する必要があります。

> [!NOTE]
> ゲストにも [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) と [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) のサービスの制限が適用されます。

ゲストの追加は、Azure AD または Office 365 セキュリティ &amp; コンプライアンス センターで追跡できます。 Microsoft Teams でのゲストの追加は監査され、「Added member to group (グループにメンバーを追加しました)」という Azure AD グループ管理アクティビティとして記録されます。 詳細については、「[B2B コラボレーション ユーザーの監査およびレポート](https://go.microsoft.com/fwlink/p/?linkid=858884)」と「[Office 365 のセキュリティ センター &amp; コンプライアンス センターで監査ログを検索する](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security--Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c)」をご覧ください。

## <a name="guest-access-vs-external-access-federation"></a>ゲスト アクセスと外部アクセス (フェデレーション)

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="more-information"></a>詳細情報

[Microsoft Teams でゲスト アクセスを許可する](teams-dependencies.md)</br>
[Microsoft Teams へのゲスト アクセスをオンまたはオフにする](set-up-guests.md)</br>
[PowerShell を使用してチームへのゲスト アクセスを制御する](guest-access-powershell.md)
