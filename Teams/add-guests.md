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
description: 管理者は、デスクトップおよび Web クライアントと B2B コラボレーション ポータルで、Microsoft Teamsゲストを組織Azure Active Directoryする方法について説明します。
ms.openlocfilehash: 1d44aff9b62a5ba6de7c22499f5a20f187d7781b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109083"
---
# <a name="add-a-guest-to-a-team"></a>チームにゲストを追加する

Outlook、Gmail などの勤務先または通常のメール アカウントを持っているユーザーは、ゲストとして Teams に参加することができます。

管理者は、次の 2 つの方法で新しいゲストを組織に追加できます。

- グローバル管理者または Teams 管理者とチーム所有者は、Teams クライアントまたは Teams 管理センターでチームにゲストを追加できます。 詳細については、「[ゲストをチームに追加する](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f)」を参照してください。 ゲスト アクセスをまだ設定していない場合は、「[チームでゲストと共同で作業する](/microsoft-365/solutions/collaborate-as-team)」の手順を実行してください。

- Azure Active Directory (Azure AD) B2B コラボレーションを使用して組織にゲストを追加する。 詳細については、「クイック スタート [: Azure Portal でゲストをディレクトリに追加する」を参照してください](/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal)。

管理者は、"ゲスト招待元" ロールを割り当てることで、組織内の他のユーザーにゲストを追加する権限を委任することもできます。 詳細については、「[B2B の外部コラボレーションを有効にしてゲストを招待できるユーザー管理する](/azure/active-directory/external-identities/delegate-invitations)」を参照してください。

Azure AD B2B コラボレーションを使用すると、組織は B2B ユーザーに対して条件付きアクセスと多要素認証 (MFA) ポリシーを適用できます。 これらのポリシーは、組織のフルタイムの従業員とメンバーに対して有効にするのと同じ方法で、テナント レベル、アプリ レベル、または個々のユーザー レベルで適用できます。 こうしたポリシーはリソース組織で実施します。 詳細については、「[B2B コラボレーション ユーザーの条件付きアクセス](/azure/active-directory/external-identities/conditional-access)」をご覧ください。 個々のゲストをブロックできない。

Azure AD B2B、Microsoft 365 グループ、または SharePointを使用して追加したゲストは準備が整っています。 管理者Microsoft 365チーム所有者は、それぞれのチームにこれらのゲストを追加できます。 チームに関連付けられている Microsoft 365 グループにゲストを直接追加すると、ゲストはチームにアクセスできますが、Microsoft 365 グループはゲストへの招待メールを生成しないので、チームの誰かがゲストに通知する必要があります。

> [!NOTE]
> ゲストにも [ Microsoft 365 または Office 365 ](/office365/servicedescriptions/office-365-service-descriptions-technet-library) と [Azure Active Directory](/azure/active-directory/external-identities/current-limitations) のサービスの制限が適用されます。

ゲストの追加は、Azure AD または Microsoft 365 セキュリティ センターで追跡できます。 Microsoft Teams でのゲストの追加は監査され、「Added member to group (グループにメンバーを追加しました)」という Azure AD グループ管理アクティビティとして記録されます。 詳細については [、「B2B](/azure/active-directory/external-identities/auditing-and-reporting) コラボレーション ユーザーの監査とレポート作成」と「コンプライアンス センターで監査ログを検索 [する」を参照してください](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)。


## <a name="related-topics"></a>関連トピック

[Microsoft Teams でゲスト アクセスを許可する](teams-dependencies.md)

[Microsoft Teams へのゲスト アクセスをオンまたはオフにする](set-up-guests.md)