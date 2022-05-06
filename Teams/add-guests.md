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
ms.localizationpriority: medium
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
description: 管理者は、Microsoft Teamsデスクトップ クライアントと Web クライアント、および B2B コラボレーション ポータルAzure Active Directory組織に新しいゲストを追加する方法について説明します。
ms.openlocfilehash: e70b32face0948446ba084f0150dc4da7c9a69b6
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58611776"
---
# <a name="add-a-guest-to-a-team"></a>チームにゲストを追加する

Outlook、Gmail などの勤務先または通常のメール アカウントを持っているユーザーは、ゲストとして Teams に参加することができます。

管理者は、次の 2 つの方法で新しいゲストを組織に追加できます。

- グローバル管理者または Teams 管理者とチーム所有者は、Teams クライアントまたは Teams 管理センターでチームにゲストを追加できます。 詳細については、「[ゲストをチームに追加する](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f)」を参照してください。 ゲスト アクセスをまだ設定していない場合は、「[チームでゲストと共同で作業する](/microsoft-365/solutions/collaborate-as-team)」の手順を実行してください。

- Azure Active Directory (Azure AD) B2B コラボレーションを使用して組織にゲストを追加する。 詳細については、「[クイック スタート: Azure portalのディレクトリにゲストを追加する」を参照してください](/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal)。

管理者は、"ゲスト招待元" ロールを割り当てることで、組織内の他のユーザーにゲストを追加する権限を委任することもできます。 詳細については、「[B2B の外部コラボレーションを有効にしてゲストを招待できるユーザー管理する](/azure/active-directory/external-identities/delegate-invitations)」を参照してください。

Azure AD B2B コラボレーションを使用すると、組織は B2B ユーザーに対して条件付きアクセスと多要素認証 (MFA) ポリシーを適用できます。 これらのポリシーは、組織のフルタイムの従業員とメンバーに対して有効にするのと同じ方法で、テナント レベル、アプリ レベル、または個々のユーザー レベルで適用できます。 こうしたポリシーはリソース組織で実施します。 詳細については、「[B2B コラボレーション ユーザーの条件付きアクセス](/azure/active-directory/external-identities/conditional-access)」をご覧ください。 個々のゲストをブロックすることはできません。

Azure AD B2B、Microsoft 365 グループ、またはSharePointを介して既に追加したゲストは、すぐにアクセスできます。 Microsoft 365管理者またはチーム所有者は、それらのゲストをそれぞれのチームに追加できます。 チームに関連付けられているMicrosoft 365 グループにゲストを直接追加した場合、ゲストはチームにアクセスできますが、Microsoft 365 グループはゲストに招待メールを生成しないため、チームの誰かがゲストに通知する必要があります。

> [!NOTE]
> ゲストにも [ Microsoft 365 または Office 365 ](/office365/servicedescriptions/office-365-service-descriptions-technet-library) と [Azure Active Directory](/azure/active-directory/external-identities/current-limitations) のサービスの制限が適用されます。

ゲストの追加は、Azure AD または Microsoft 365 セキュリティ センターで追跡できます。 Microsoft Teams でのゲストの追加は監査され、「Added member to group (グループにメンバーを追加しました)」という Azure AD グループ管理アクティビティとして記録されます。 詳細については、「 [B2B コラボレーション ユーザーの監査とレポート](/azure/active-directory/external-identities/auditing-and-reporting) 」および [コンプライアンス センターで監査ログを検索する方法に関する説明を](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)参照してください。


## <a name="related-topics"></a>関連項目

[Microsoft Teams でゲスト アクセスを許可する](teams-dependencies.md)

[Microsoft Teams へのゲスト アクセスをオンまたはオフにする](set-up-guests.md)