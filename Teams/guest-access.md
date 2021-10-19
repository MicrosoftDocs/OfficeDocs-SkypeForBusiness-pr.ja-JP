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
ms.localizationpriority: high
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.orgwidesettings.guestaccess.overview
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
appliesto:
- Microsoft Teams
description: Microsoft Teams でのゲスト アクセスにより、組織内のチームは組織外の人にチームおよびチャネルへのアクセス権を付与することで、それらの人と共同作業することができるようになります。
ms.openlocfilehash: 2064ca1fdd816f1948af1f0efcda3021a1c7d2cb
ms.sourcegitcommit: 279ab5236431961c5181e2c01a69e5aa4290d381
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2021
ms.locfileid: "60462341"
---
# <a name="guest-access-in-microsoft-teams"></a>Microsoft Teams でのゲスト アクセス

ゲスト アクセスを使用すると、企業データの管理を維持しながら、チーム、チャネル内のドキュメント、リソース、チャット、およびアプリケーションへのアクセスを組織外の人々に提供できます。「[Microsoft 365 と Microsoft Teams を使用してセキュリティで保護された共同作業を設定する](/microsoft-365/solutions/setup-secure-collaboration-with-teams)」を参照してください。

> [!NOTE]
> ただ他の組織の人々を見つけ、電話をかけ、チャットし、会議を設定する場合は、[外部アクセス](manage-external-access.md) を使用します。

ゲストとは、従業員、学生または組織の一員ではないユーザーを指します。 ゲストは組織内での学校アカウントまたは職場アカウントを持ちません。 たとえば、ゲストにはパートナー、製造元、供給元、コンサルタントなどが含まれます。 自分の組織に属していないユーザーを Teams のゲストとして追加することができます。 これは、ビジネス アカウント (すなわち、Azure Active Directory アカウント) または通常のメール アカウント (Outlook.com、Gmail.com、他) を持つすべてのユーザーが、チームとチャネルの操作や機能にアクセスできるゲストとして、Teams に参加できることを意味します。

Teams のゲストは、Microsoft 365 と同様のコンプライアンスと監査による保護の対象となります。また、ゲストを Azure AD 内で管理できます。 ゲスト アクセスは Azure AD および、Microsoft 365 または Office 365 のサービス制限の対象になります。

ゲストのエクスペリエンスには、仕様上の制限があります。ゲストが Teams でできることとできないことの完全なリストについては、「[チーム メンバーとゲスト機能の比較](guest-experience.md#comparison-of-team-member-and-guest-capabilities)」をご覧ください。

> [!IMPORTANT]
> ゲストは、共存アップグレード モードの Teams の組織全体の設定に従います。これは変更できません。

ゲスト アクセスを設定する方法については、「[チームでゲストと共同作業する](/microsoft-365/solutions/collaborate-as-team)」を参照してください。 

外部アクセス (フェデレーション) とゲスト アクセスを比較する (および使用するアクセスを決定する) には、「[Teams の他の組織のユーザーと通信する](communicate-with-users-from-other-organizations.md)」をご覧ください。

## <a name="set-up-guest-access"></a>ゲスト アクセスを設定する

Teams でのゲスト アクセスには、Azure AD、Microsoft 365 グループ、SharePoint の設定など、Microsoft 365 の他の設定を構成する必要があります。 ゲストを Teams に招待する準備ができている場合は、次のいずれかをお読みください。

- 一般的な使用のためにチームのゲスト アクセスを構成する方法については、「 [チームでゲストと共同作業する](/microsoft-365/solutions/collaborate-as-team)」を参照してください。
- Azure Active Directory を使用するパートナー組織とコラボレーションし、ゲストがチーム アクセスに自己登録できるようにするには、「[管理されたゲストで B2B エクストラネットを作成する](/microsoft-365/solutions/b2b-extranet)」を参照してください。

Teams でのゲスト アクセスは組織全体の設定であり、既定ではオンになっています。 [機密ラベル](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)を使用して、個々のチームへのゲスト アクセスを制御できます。

> [!NOTE]
> Microsoft Teams の管理者であり、ゲスト アクセスで問題が発生している場合は、以下の **[テストの実行]** を選択します。それにより、Microsoft 365 管理センターにゲスト アクセス診断が表示されます。 これらのテストでは、構成を確認し、テナントのゲスト アクセスを有効にするための次の手順をすばやくお勧めします。
>> [!div class="nextstepaction"]
>> [テストの実行: ゲスト アクセス](https://aka.ms/TeamsGuestAccessDiagDMC)

### <a name="turning-guest-access-off"></a>ゲスト アクセスをオフにする

Teams でゲスト アクセスをオフにすると、既存のゲストはチームにアクセスできなくなります。 ただし、チームから削除されることはありません。 それらはチーム メンバーに引き続き表示され、@メンションすることができます。 Teams のゲスト アクセスを再度オンにすると、アクセスを回復します。

ゲスト アクセスをオフのままにする場合は、チームの所有者に、チームからゲスト アカウントを手動で削除するようにアドバイスすることをお勧めします。 これらのゲストはアクセスできませんが、チームに自分のアカウントが表示されると、他のチーム メンバーが混乱する可能性があります。

## <a name="how-a-guest-becomes-a-member-of-a-team"></a>ゲストをチームのメンバーにする方法

1. チーム所有者または Microsoft 365 管理者は[チームにゲストを追加](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f)します。
2. ゲストが、チームに関する情報と、チームのメンバーとして要求される事項が記載されたようこそメールを、チーム所有者から受信します。
3. ゲストが招待を承諾します。
  Azure Active Directory の職場や学校のアカウントを持っているゲストは、招待を承諾して、直接認証を受けることができます。 他のユーザーには、ID を検証するためのワンタイム パスコードが送信されます ([ワンタイム パスコード認証](/azure/active-directory/external-identities/one-time-passcode)が必要です)。
4. 招待を承諾すると、ゲストは [チームやチャネルへの参加](https://support.office.com/article/df38ae23-8f85-46d3-b071-cb11b9de5499)、チャネル メッセージに対する受信や応答、[チャネル内のファイルへのアクセス](https://support.office.com/article/access-files-in-channels-c593c78a-27c4-4661-a598-682baa30ca7e)、チャットへの参加、会議への参加、ドキュメントでの共同作業などを行うことができるようになります。 

Teams では、ゲストは明確に特定されます。 ゲスト の名前にはラベル **(ゲスト)** が含まれていて、チャネルにはチームにゲストがいることを示すアイコンが含まれています。 詳しくは、「[ゲストのエクスペリエンスについて](guest-experience.md)」をご覧ください。
  
ゲストは Teams 内からいつでもチームを去ることができます。 詳しくは、「[チームから脱退する方法を教えてください。](https://support.office.com/article/leave-a-team-e481005d-3ec6-4694-b300-375472ba4076)」をご覧ください。

> [!NOTE]
> チームから脱退しても、組織/ディレクトリからゲスト アカウントを削除したことにはなりません。 これは、Microsoft 365 グローバル管理者または Azure AD 管理者が行う必要があります。

## <a name="licensing-for-guest-access"></a>ゲスト アクセスのライセンス

ゲスト アクセスは、Microsoft 365 Business Standard、Microsoft 365 Enterprise、Microsoft 365 Education のすべてのサブスクリプションで使用できます。 追加の Microsoft 365 ライセンスは不要です。 [Azure Active Directory for External Identities の課金モデル](/azure/active-directory/b2b/licensing-guidance) は、Microsoft 365 のゲストに適用されます。 ゲストとして招待できるのは、組織外の人だけです。

## <a name="guest-access-reviews"></a>ゲスト アクセス レビュー

Azure AD を使用してアプリケーションに割り当てられたグループ メンバーまたはユーザーに対するアクセス レビューを作成することができます。 反復的なアクセス レビューを作成することで、時間を節約できます。 アプリケーションやチームにアクセスできるユーザー、またはメンバーのグループであるユーザーを定期的にレビューする必要がある場合は、それらのレビューの頻度を定義することができます。 

ゲスト アクセスのレビューを自分自身で実行したり、ゲストにメンバーシップのレビューを求めたり、アプリケーション所有者またはビジネス意思決定者に対してアクセス レビューを実行するよう求めたりすることができます。 ゲスト アクセス レビューを実行するために、Azure ポータルを使用します。 詳細については、「[Azure AD アクセス レビューでゲスト アクセスを管理する](/azure/active-directory/governance/manage-guest-access-with-access-reviews)」をご覧ください。

## <a name="related-topics"></a>関連項目

[組織外部のユーザーとの共有](/microsoft-365/solutions/collaborate-with-people-outside-your-organization)

[特定の Microsoft 365 グループまたは Microsoft Teams チームにゲストが追加されないようにする](/microsoft-365/solutions/per-group-guest-access)

[セキュリティで保護されたゲスト共有環境を作成する](/microsoft-365/solutions/create-secure-guest-sharing-environment)

[ビジネス製品についてサポートに問い合わせる - 管理者ヘルプ](/microsoft-365/admin/contact-support-for-business-products)

[3 層の保護を使って Teams を構成する](/microsoft-365/solutions/configure-teams-three-tiers-protection)
