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
- m365initiative-externalcollab
search.appverid: MET150
ms.reviewer: rafarhi
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
description: 管理者は、Microsoft Teams デスクトップ、Web クライアント、Azure Active Directory B2B コラボレーション ポータルなどのツールで、組織に新しいゲスト ユーザーを追加する方法について学習することができます。
ms.openlocfilehash: 21f8e733a87474888f2b33f8a23a063fa00b4b11
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/13/2020
ms.locfileid: "49030813"
---
# <a name="add-a-guest-to-a-team"></a>チームにゲストを追加する

Outlook、Gmail などの勤務先または通常のメール アカウントを持っているユーザーは、ゲストとして Teams に参加することができます。

管理者は、新しいゲスト ユーザーを複数の方法で組織に追加できます。

- グローバル管理者または Teams 管理者とチーム所有者は、Teams クライアントまたは Teams 管理センターでチームにゲストを追加できます。 詳細については、「[ゲストをチームに追加する](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f)」を参照してください。 ゲスト アクセスをまだ設定していない場合は、「[チームでゲストと共同で作業する](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)」の手順を実行してください。

- Azure Active Directory (Azure AD) B2B コラボレーションを使用して組織にゲストを追加する。 詳細については、「 [クイックスタート: Azure ポータルのディレクトリにゲストユーザーを追加する」](https://docs.microsoft.com/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal)をご覧ください。

管理者は、"ゲスト招待元" ロールを割り当てることで、組織内の他のユーザーにゲストを追加する権限を委任することもできます。 詳細については、「[B2B の外部コラボレーションを有効にしてゲストを招待できるユーザー管理する](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations)」を参照してください。

Azure AD B2B コラボレーションを使用すると、組織は B2B ユーザーに対して条件付きアクセスと多要素認証 (MFA) ポリシーを適用できます。 これらのポリシーは、組織のフルタイムの従業員とメンバーに対して有効にするのと同じ方法で、テナント レベル、アプリ レベル、または個々のユーザー レベルで適用できます。 こうしたポリシーはリソース組織で実施します。 詳細については、「[B2B コラボレーション ユーザーの条件付きアクセス](https://go.microsoft.com/fwlink/?linkid=857454)」をご覧ください。 個別にゲスト ユーザーを拒否することはできません。

Azure AD B2B、Microsoft 365 グループ、または SharePoint を使用して既に追加したゲストユーザーは、準備ができています。 Microsoft 365 管理者またはチーム所有者は、これらのゲストをそれぞれのチームに追加することができます。 チームに関連付けられている Microsoft 365 グループにゲストを直接追加した場合、ゲストはチームへのアクセス権を取得しますが、Microsoft 365 グループはゲストに招待メールを生成しないので、チームのメンバーがゲストに通知する必要があります。

> [!NOTE]
> ゲストにも [ Microsoft 365 または Office 365 ](https://go.microsoft.com/fwlink/p/?linkid=282347) と [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) のサービスの制限が適用されます。

ゲストの追加は、Azure AD または Microsoft 365 セキュリティ センターで追跡できます。 Microsoft Teams でのゲストの追加は監査され、「Added member to group (グループにメンバーを追加しました)」という Azure AD グループ管理アクティビティとして記録されます。 詳細については、「 [B2B コラボレーションユーザーを監査および報告する](https://docs.microsoft.com/azure/active-directory/external-identities/auditing-and-reporting) 」と「 [コンプライアンスセンターで監査ログを検索](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)する」を参照してください。


## <a name="related-topics"></a>関連項目

[Microsoft Teams でゲスト アクセスを許可する](teams-dependencies.md)

[Microsoft Teams へのゲスト アクセスをオンまたはオフにする](set-up-guests.md)
