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
ms.openlocfilehash: d7f850855ab131267b20bae07b015127777a21f4
ms.sourcegitcommit: 9bee7cb9433bfc687387647a102f814dc52c8591
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2022
ms.locfileid: "64839068"
---
# <a name="guest-access-in-microsoft-teams"></a>Microsoft Teams でのゲスト アクセス

ゲストアクセスを使用すると、企業データの管理を維持しながら、チーム、チャネル内のドキュメント、リソース、チャット、およびアプリケーションへのアクセスを組織外の人々に提供できます。 「[Microsoft 365 と Microsoft Teams を使用してセキュリティで保護された共同作業を設定する](/microsoft-365/solutions/setup-secure-collaboration-with-teams)」を参照してください。 Teams でのゲスト アクセスは組織全体の設定であり、既定ではオンになっています。 [機密ラベル](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)を使用して、個々のチームへのゲスト アクセスを制御できます。

> [!NOTE]
> ただ他の組織の人々を見つけ、電話をかけ、チャットし、会議を設定する場合は、[外部アクセス](manage-external-access.md) を使用します。

ゲストとは、組織の学校または職場アカウントを持っていないユーザーです。 たとえば、ゲストにはパートナー、製造元、供給元、コンサルタントなどが含まれます。 自分の組織に属していないユーザーを Teams のゲストとして追加することができます。 これは、ビジネス アカウント (すなわち、Azure Active Directory アカウント) または通常のメール アカウント (Outlook.com、Gmail.com、他) を持つすべてのユーザーが、チームとチャネルの操作や機能にアクセスできるゲストとして、Teams に参加できることを意味します。

Teams にゲストを招待すると、ゲスト アカウントが Azure Active Directory に作成され、他の Microsoft 365 ユーザーと同じコンプライアンスと監査保護の対象になります。ゲスト アクセスは Azure AD および Microsoft 365 のサービス制限の対象になります。

ゲストのエクスペリエンスには、仕様上の制限があります。ゲストが Teams で実行できる操作と実行できない操作の一覧は、「[Microsoft Teams のゲスト アクセス](guest-experience.md)」を参照してください。

> [!IMPORTANT]
> ゲストは、共存アップグレード モードの Teams の組織全体の設定に従います。これは変更できません。

外部アクセス (フェデレーション) とゲスト アクセスを比較する (および使用するアクセスを決定する) には、「[Teams の他の組織のユーザーと通信する](communicate-with-users-from-other-organizations.md)」をご覧ください。

共有チャネルを使用すると、ゲスト アクセスの代替手段が提供されるため、Azure AD でゲスト アカウントを必要とせずに、組織外のユーザーを招待できます。ゲスト アクセスと共有チャネルを比較するには、「[外部コラボレーションを計画する](/microsoft-365/solutions/plan-external-collaboration)」を参照してください。

ゲスト アクセスを設定する方法については、「[チームでゲストと共同作業する](/microsoft-365/solutions/collaborate-as-team)」を参照してください。 

## <a name="set-up-guest-access"></a>ゲスト アクセスを設定する

Teams でのゲスト アクセスには、Azure AD、Microsoft 365 グループ、SharePoint の設定など、Microsoft 365 の他の設定を構成する必要があります。 ゲストを Teams に招待する準備ができている場合は、次のいずれかをお読みください。

- 一般的な使用のためにチームのゲスト アクセスを構成する方法については、「 [チームでゲストと共同作業する](/microsoft-365/solutions/collaborate-as-team)」を参照してください。
- Azure Active Directory を使用するパートナー組織とコラボレーションし、ゲストがチーム アクセスに自己登録できるようにするには、「[管理されたゲストで B2B エクストラネットを作成する](/microsoft-365/solutions/b2b-extranet)」を参照してください。

> [!NOTE]
> Microsoft Teams の管理者であり、ゲスト アクセスで問題が発生している場合は、以下の **[テストの実行]** を選択します。それにより、Microsoft 365 管理センターにゲスト アクセス診断が表示されます。 これらのテストでは、構成を確認し、テナントのゲスト アクセスを有効にするための次の手順をすばやくお勧めします。
>> [!div class="nextstepaction"]
>> [テストの実行: ゲスト アクセス](https://aka.ms/TeamsGuestAccessDiagDMC)

## <a name="how-a-guest-gets-added-to-a-team"></a>ゲストをチームに追加する方法

1. チーム所有者または Microsoft 365 管理者は[チームにゲストを追加](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f)します。
2. ゲストは、チームに関する情報と、チームに追加されたときの注意点が記載されたようこそメールをチーム所有者から受信します。
3. ゲストが招待を承諾します。
  Azure Active Directory の職場や学校のアカウントを持っているゲストは、招待を承諾して、直接認証を受けることができます。 他のユーザーには、ID を検証するためのワンタイム パスコードが送信されます ([ワンタイム パスコード認証](/azure/active-directory/external-identities/one-time-passcode)が必要です)。
4. 招待を承諾すると、ゲストは [チームやチャネルへの参加](https://support.office.com/article/df38ae23-8f85-46d3-b071-cb11b9de5499)、チャネル メッセージに対する受信や応答、[チャネル内のファイルへのアクセス](https://support.office.com/article/access-files-in-channels-c593c78a-27c4-4661-a598-682baa30ca7e)、チャットへの参加、会議への参加、ドキュメントでの共同作業などを行うことができるようになります。 

Teams では、ゲストは明確に特定されます。 ゲスト の名前にはラベル **(ゲスト)** が含まれていて、チャネルにはチームにゲストがいることを示すアイコンが含まれています。 詳しくは、「[ゲストのエクスペリエンスについて](guest-experience.md)」をご覧ください。
  
ゲストは Teams 内からいつでもチームを去ることができます。 詳しくは、「[チームから脱退する方法を教えてください。](https://support.office.com/article/leave-a-team-e481005d-3ec6-4694-b300-375472ba4076)」をご覧ください。

> [!NOTE]
> チームから脱退しても、組織/ディレクトリからゲスト アカウントを削除したことにはなりません。 これは、Microsoft 365 グローバル管理者または Azure AD 管理者が行う必要があります。

## <a name="licensing-for-guest-access"></a>ゲスト アクセスのライセンス

ゲスト アクセスは、Microsoft 365 Business Standard、Microsoft 365 Enterprise、Microsoft 365 Education のすべてのサブスクリプションで使用できます。 追加の Microsoft 365 ライセンスは不要です。 [Azure Active Directory for External Identities の課金モデル](/azure/active-directory/b2b/licensing-guidance) は、Microsoft 365 のゲストに適用されます。 ゲストとして招待できるのは、組織外の人だけです。

> [!NOTE]
> Teams では、ゲスト アカウントを Azure AD メンバー アカウントに変換したり、Azure AD メンバー アカウントをゲスト アカウントに変換したりすることはサポートされていません。

## <a name="guest-access-reviews"></a>ゲスト アクセス レビュー

Azure AD を使用して、グループ内のユーザーまたはアプリケーションに割り当てられているユーザーのアクセス レビューを作成できます。 反復的なアクセス レビューを作成することで、時間を節約できます。 アプリケーション、チーム、またはグループにアクセスできるユーザーを定期的にレビューする必要がある場合は、それらのレビューの頻度を定義できます。 

自分でゲスト アクセス レビューを実行したり、ゲストにアクセス レビューを実行するよう要求したり、アプリケーションの所有者またはビジネス意思決定者に対してアクセス レビューを実行するよう要求したりできます。 ゲスト アクセス レビューを実行するために、Azure ポータルを使用します。 詳細については、「[Azure AD アクセス レビューでゲスト アクセスを管理する](/azure/active-directory/governance/manage-guest-access-with-access-reviews)」をご覧ください。

## <a name="related-topics"></a>関連項目

[組織外部のユーザーとの共有](/microsoft-365/solutions/collaborate-with-people-outside-your-organization)

[特定の Microsoft 365 グループまたは Microsoft Teams チームにゲストが追加されないようにする](/microsoft-365/solutions/per-group-guest-access)

[セキュリティで保護されたゲスト共有環境を作成する](/microsoft-365/solutions/create-secure-guest-sharing-environment)

[ビジネス製品についてサポートに問い合わせる - 管理者ヘルプ](/microsoft-365/admin/contact-support-for-business-products)

[3 層の保護を使って Teams を構成する](/microsoft-365/solutions/configure-teams-three-tiers-protection)
