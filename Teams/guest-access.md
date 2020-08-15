---
title: Microsoft Teams でのゲスト アクセス
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: sbhatta
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
ms.openlocfilehash: f04fce7f75df32111b2577119c12b14eadf963b9
ms.sourcegitcommit: 20258b691ffc559b1656fd1e57f67f5c3a9e29e1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/15/2020
ms.locfileid: "46761243"
---
# <a name="guest-access-in-microsoft-teams"></a>Microsoft Teams でのゲスト アクセス

ゲスト アクセスにより、組織内のチームは組織外の人に Teams の既存のチームおよびチャネルへのアクセス権を付与することで、それらの人と共同作業することができるようになります。 Microsoft 365、Outlook、Gmail などのビジネス用またはコンシューマー用のメールアカウントを持っているユーザーは、チームのチャット、会議、ファイルに完全にアクセスできるゲストとして参加することができます。 Teams の管理者は、ゲストがチームで使用できる (使用できない) 機能を制御します、「[ゲスト アクセスの管理](manage-guests.md)」をご覧ください。

外部アクセス (フェデレーション) とゲスト アクセスを比較する (および使用するアクセスを決定する) には、「[Teams の他の組織のユーザーと通信する](communicate-with-users-from-other-organizations.md)」をご覧ください。

ゲスト アクセスは Teams の組織全体の設定であり、既定ではオフになっています。 ( [機密ラベル](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)を使用して、個々のチームへのゲストアクセスを制御することができます。)

ゲストを teams に招待する準備ができたら、次のいずれかを実行します。

- 一般に使用するために Teams のゲストアクセスを構成するには、「 [チームのゲストとの共同作業](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)」を参照してください。
- Azure Active Directory を使用するパートナー組織と共同作業し、ゲストがチームアクセスを自己登録できるようにする方法については、「管理され [たゲストで B2B エクストラネットを作成](https://docs.microsoft.com/microsoft-365/solutions/b2b-extranet)する」を参照してください。

ゲスト アクセスは Azure AD および、Microsoft 365 または Office 365 のサービス制限の対象になります。

> [!IMPORTANT]
> ゲスト ユーザーは、共存アップグレード モードの Teams の組織全体の設定に従います。 これは変更できません。

## <a name="licensing-for-guest-access"></a>ゲスト アクセスのライセンス

ゲスト アクセスは、Microsoft 365 Business Standard、Office 365 Enterprise、Office 365 Education のすべてのサブスクリプションに含まれています。 追加の Microsoft 365 または Office 365 ライセンスは不要です。 Teams では追加することができるゲストの数に制限はありません。 ただし、テナントに追加できるゲストの総数は、Azure AD の有料機能によって制限される場合があります。 詳細については、「[Azure AD B2B コラボレーションのライセンス](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance)」に関するページを参照してください。


> [!NOTE]
> Exchange Online プラン 2 などのスタンドアロンの Microsoft 365 または Office 365 サブスクリプションプランのみを持っている組織内のユーザーは、Teams によって組織に属しているものと見なされるため、その同じ組織へのゲストとして招待されることはできません。 これらのユーザーが Teams を使用する場合は、Microsoft 365 Business Standard、Office 365 Enterprise、または Office 365 Education サブスクリプションが割り当てられる必要があります。 

## <a name="who-is-a-guest"></a>ゲストとは何ですか?

ゲストとは、従業員、学生または組織の一員ではないユーザーを指します。 ゲストは組織内での学校アカウントまたは職場アカウントを持ちません。 たとえば、ゲストにはパートナー、製造元、供給元、コンサルタントなどが含まれます。 自分の組織に属していないユーザーを Teams のゲストとして追加することができます。 これは、ビジネス アカウント (すなわち、Azure Active Directory アカウント) または通常のメール アカウント (Outlook.com、Gmail.com、他) を持つすべてのユーザーが、チームとチャネルの操作や機能にフル アクセスできるゲストとして、Teams に参加できることを意味します。

ゲストができることとできないことの詳細については、「[Microsoft Teams でゲスト アクセスを許可する](teams-dependencies.md)」をご覧ください。 または、[チーム メンバーとゲスト機能の比較](guest-experience.md#comparison-of-team-member-and-guest-capabilities)表をご覧ください。 

最後に、Teams のすべてのゲストは、他の Microsoft 365 と同じコンプライアンスおよび監査保護によってカバーされ、Azure AD 内で管理することができます。

## <a name="why-use-guest-access"></a>ゲスト アクセスを使用する理由を教えてください。

ゲスト アクセスにより、Teams を使用している組織は、企業データに対する完全な制御を維持しながら、パートナーにチーム、チャネル内のドキュメント、リソース、チャット、アプリケーションへのアクセスを提供することができます。 

## <a name="understand-the-limitations-for-guests"></a>ゲストに対する制限事項を理解する

ゲストのエクスペリエンスには、仕様上の制限がかかっています。 ゲストのエクスペリエンスを確実に理解して、実際の問題ではないことを修正する試みをしないようにしてください。 Microsoft Teams のゲストで利用できない機能の一部を次に示します。

- OneDrive
- Teams 外部のユーザーの検索
- カレンダー、予約済みの会議、会議の詳細
- PSTN
- 組織図
- チームの作成または修正
- チームの参照
- 個人対個人のチャットへのファイルのアップロード
- 現時点では、チームは、[状態1と状態2のゲストユーザー](https://docs.microsoft.com/azure/active-directory/b2b/user-properties)のみをサポートしています。

ゲストが Teams でできることとできないことの完全なリストについては、「[チーム メンバーとゲスト機能の比較](guest-experience.md#comparison-of-team-member-and-guest-capabilities)」表をご覧ください。 Microsoft 365 レベルでのゲストアクセスの詳細については、「 [組織外の人と共同作業](https://docs.microsoft.com/microsoft-365/solutions/collaborate-with-people-outside-your-organization)を行う」を参照してください。


## <a name="related-topics"></a>関連トピック

[ビジネス製品についてサポートに問い合わせる - 管理者ヘルプ](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)

[3つのレベルの保護を使用してチームを構成する](https://docs.microsoft.com/microsoft-365/solutions/configure-teams-three-tiers-protection)
