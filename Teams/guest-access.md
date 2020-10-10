---
title: Microsoft Teams でのゲスト アクセス
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: rafarhi
audience: admin
search.appverid: MET150
localization_priority: Normal
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.orgwidesettings.guestaccess.overview
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
appliesto:
- Microsoft Teams
description: Microsoft Teams でのゲスト アクセスにより、組織内のチームは組織外の人にチームおよびチャネルへのアクセス権を付与することで、それらの人と共同作業することができるようになります。
ms.openlocfilehash: 6efaa942b3818d8fb5aaca7a07b9300f1c731dca
ms.sourcegitcommit: 43823358e7e1c1cece72a69a2ceb4eff86d3f927
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/10/2020
ms.locfileid: "48416852"
---
# <a name="guest-access-in-microsoft-teams"></a>Microsoft Teams でのゲスト アクセス

ゲストアクセスを使用すると、組織外のユーザーに対して、チーム、チャネル内のドキュメント、リソース、チャット、アプリケーションへのアクセスを提供することができ、企業データを管理する必要はありません。

ゲストとは、従業員、学生または組織の一員ではないユーザーを指します。 ゲストは組織内での学校アカウントまたは職場アカウントを持ちません。 たとえば、ゲストにはパートナー、製造元、供給元、コンサルタントなどが含まれます。 自分の組織に属していないユーザーを Teams のゲストとして追加することができます。 つまり、ビジネスアカウント (Azure Active Directory アカウント) またはコンシューマーのメールアカウント (Outlook.com、Gmail.com、他のアカウント) を持つユーザーは、teams でゲストとして参加し、チームとチャネルのエクスペリエンスにアクセスできます。

Teams の管理者は、 [ゲストが teams で使用できる (または使用できない) 機能を制御](manage-guests.md)します。 Teams のゲストは、他の Microsoft 365 と同じコンプライアンスおよび監査保護によってカバーされ、Azure AD 内で管理することができます。 ゲスト アクセスは Azure AD および、Microsoft 365 または Office 365 のサービス制限の対象になります。

ゲストのエクスペリエンスには、仕様上の制限がかかっています。 チームでゲストができることとできないことの詳細については、「 [チームメンバーとゲストの機能の比較](guest-experience.md#comparison-of-team-member-and-guest-capabilities)」を参照してください。

> [!IMPORTANT]
> ゲスト ユーザーは、共存アップグレード モードの Teams の組織全体の設定に従います。 これは変更できません。

外部アクセス (フェデレーション) とゲスト アクセスを比較する (および使用するアクセスを決定する) には、「[Teams の他の組織のユーザーと通信する](communicate-with-users-from-other-organizations.md)」をご覧ください。

## <a name="set-up-guest-access"></a>ゲストアクセスを設定する

Teams のゲストアクセスには、Azure AD、Microsoft 365 グループ、SharePoint の設定など、Microsoft 365 でその他の設定を構成する必要があります。 ゲストを teams に招待する準備ができたら、次のいずれかを実行します。

- 一般に使用するために Teams のゲストアクセスを構成するには、「 [チームのゲストとの共同作業](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)」を参照してください。
- Azure Active Directory を使用するパートナー組織と共同作業し、ゲストがチームアクセスを自己登録できるようにする方法については、「管理され [たゲストで B2B エクストラネットを作成](https://docs.microsoft.com/microsoft-365/solutions/b2b-extranet)する」を参照してください。

Teams のゲストアクセスは組織全体の設定であり、既定ではオフになっています。 [機密ラベル](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)を使用して、個々のチームへのゲストアクセスを制御することができます。

## <a name="how-a-guest-becomes-a-member-of-a-team"></a>ゲストをチームのメンバーにする方法

1. チーム所有者または Microsoft 365 管理者が、 [ゲストをチームに追加](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f)します。
2. ゲストが、チームに関する情報と、チームのメンバーとして要求される事項が記載されたようこそメールを、チーム所有者から受信します。
3. ゲストが招待を承諾します。
  Azure Active Directory で職場または学校のアカウントを使用しているゲストユーザーは、招待を承諾して直接認証することができます。 他のユーザーは、1回限りのパスコードを送信して、身元を確認します ([1 回限りのパスコード認証](https://docs.microsoft.com/azure/active-directory/external-identities/one-time-passcode) が必要です)。
4. 招待を承諾すると、ゲストは [チームやチャネルへの参加](https://support.office.com/article/df38ae23-8f85-46d3-b071-cb11b9de5499)、チャネル メッセージに対する受信や応答、[チャネル内のファイルへのアクセス](https://support.office.com/article/access-files-in-channels-c593c78a-27c4-4661-a598-682baa30ca7e)、チャットへの参加、会議への参加、ドキュメントでの共同作業などを行うことができるようになります。 

Teams では、ゲストは明確に特定されます。 ゲスト ユーザーの名前にはラベル **(ゲスト)** が含まれていて、チャネルにはチームにゲストが存在していることを示すアイコンが含まれています。 詳しくは、「[ゲストのエクスペリエンスについて](guest-experience.md)」をご覧ください。
  
ゲストは Teams 内からいつでもチームを去ることができます。 詳しくは、「[チームから脱退する方法を教えてください。](https://support.office.com/article/leave-a-team-e481005d-3ec6-4694-b300-375472ba4076)」をご覧ください。

> [!NOTE]
> チームから脱退しても、組織のディレクトリからゲストアカウントが削除されることはありません。 これは、Microsoft 365 グローバル管理者または Azure AD 管理者が行う必要があります。

## <a name="licensing-for-guest-access"></a>ゲスト アクセスのライセンス

ゲストアクセスは、すべての Microsoft 365 ビジネス標準、Microsoft 365 Enterprise、および Microsoft 365 エデュケーションサブスクリプションに含まれています。 追加の Microsoft 365 ライセンスは必要ありません。 Teams では追加することができるゲストの数に制限はありません。 ただし、テナントに追加できるゲストの総数は、Azure AD の有料機能によって制限される場合があります。 詳細については、「 [AZURE AD の外部 id の課金モデル](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance)」を参照してください。

> [!NOTE]
> Exchange Online Plan 2 などのスタンドアロンの Microsoft 365 サブスクリプションプランのみを使用している組織内のユーザーは、これらのユーザーが同じ組織に属していると見なされるため、組織のゲストとして招待することはできません。 これらのユーザーが Teams を使用する場合は、Microsoft 365 Business Standard、Office 365 Enterprise、または Office 365 Education サブスクリプションが割り当てられる必要があります。 

## <a name="guest-access-reviews"></a>ゲストアクセスのレビュー

Azure AD を使用してアプリケーションに割り当てられたグループ メンバーまたはユーザーに対するアクセス レビューを作成することができます。 反復的なアクセス レビューを作成することで、時間を節約できます。 アプリケーション、チーム、またはグループのメンバーにアクセスできるユーザーを定期的にレビューする必要がある場合は、それらのレビューの頻度を定義できます。 

ゲスト アクセスのレビューを自分自身で実行したり、ゲストにメンバーシップのレビューを求めたり、アプリケーション所有者またはビジネス意思決定者に対してアクセス レビューを実行するよう求めたりすることができます。 ゲスト アクセス レビューを実行するために、Azure ポータルを使用します。 詳細については、「[Azure AD アクセス レビューでゲスト アクセスを管理する](https://docs.microsoft.com/azure/active-directory/governance/manage-guest-access-with-access-reviews)」をご覧ください。

## <a name="related-topics"></a>関連項目

[組織外の人と共同作業する](https://docs.microsoft.com/microsoft-365/solutions/collaborate-with-people-outside-your-organization)

[特定の Microsoft 365 グループまたは Microsoft Teams チームからのゲストユーザーをブロックする](https://docs.microsoft.com/microsoft-365/solutions/per-group-guest-access)

[セキュリティで保護されたゲスト共有環境を作成する](https://docs.microsoft.com/microsoft-365/solutions/create-secure-guest-sharing-environment)

[ビジネス製品についてサポートに問い合わせる - 管理者ヘルプ](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)

[3つのレベルの保護を使用してチームを構成する](https://docs.microsoft.com/microsoft-365/solutions/configure-teams-three-tiers-protection)
