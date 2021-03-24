---
title: Microsoft Teams でのゲスト アクセスを承認する
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- SPO_Content
- m365initiative-externalcollab
ms.reviewer: rafarhi
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
description: Microsoft Teams のゲスト アクセス機能を 4 つの異なる承認レベルで管理します。
ms.openlocfilehash: d52fdeb1f9867ac1faa0f8cf77023109155a8967
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094469"
---
# <a name="authorize-guest-access-in-microsoft-teams"></a>Microsoft Teams でのゲスト アクセスを承認する

組織の要件を満たすために、Teams のゲスト アクセス機能を 4 つの異なる承認レベルで管理することができます。 すべての承認レベルが Microsoft 365 組織に適用されます。 それぞれの承認レベルによって、ゲストのエクスペリエンスが次の通り制御されます。

- **Azure Active Directory**: Teams のゲスト アクセスは、Azure Active Directory ビジネス ツー ビジネス (B2B) プラットフォームに依存します。 この承認レベルは、ゲストのエクスペリエンスをディレクトリ、テナント、およびアプリケーション レベルで制御します。
- **Teams**: Teams のゲストエクスペリエンスのみを管理します。
- **Microsoft 365 グループ**: Microsoft 365 グループおよび Teams でのゲスト エクスペリエンスを制御します。
- **SharePoint と OneDrive**: SharePoint、OneDrive、Microsoft 365 グループ、およびチームのゲスト エクスペリエンスを制御します。

これらの異なる承認レベルにより、組織におけるゲスト アクセスを柔軟にセットアップできるようになります。 たとえば、自分の Microsoft Teams でゲスト ユーザーを許可せず、組織全体では許可する場合、Microsoft Teams でゲスト アクセスをオフにするだけです。 別の例: Azure AD、Teams、Groups レベルでゲスト アクセスを有効にしつつ、[1 つ以上の基準 (データ分類が社外秘に等しいなど) に一致する選択したチームに対するゲスト ユーザーの追加を無効にする](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)ことができます。 SharePoint と OneDrive には、Microsoft 365 グループに依存しない独自のゲスト アクセス設定があります。

エンドツーエンドのゲスト アクセス設定手順については、「[チームでゲストと共同で作業する](/microsoft-365/solutions/collaborate-as-team)」を参照してください。

> [!NOTE]
> ゲストは、「[Microsoft 365 および Office 365 サービスの説明](/office365/servicedescriptions/office-365-service-descriptions-technet-library)」および「[Azure AD B2B コラボレーションの制限での制限](/azure/active-directory/external-identities/current-limitations)」に記載されているサービスの制限の対象となります。 

次の図では、Azure Active Directory、Teams、および Microsoft 365 との間でゲスト アクセスの承認の依存関係がどのように与えられているか、および組み合わされているかを示します。

> [!div class="mx-imgBorder"]
> ![ゲスト アクセスの承認の依存関係の図](media/teams_dependencies_image1.png)

次の図は、一般的なゲスト アクセスの招待と引き換えフローを通じて、ユーザーの作業環境がアクセス許可モデルとどのように連動するかを大まかに示しています。

> [!div class="mx-imgBorder"]
> ![招待と引き換えフローの図](media/authorize-guest-image1.png)

ここで重要なことは、アプリ、ボット、コネクタが独自のアクセス許可のセットや、ユーザー アカウントに固有の同意が必要な可能性があることです。 それぞれに付与する必要があります。 同様に SharePoint は、特定のユーザー、ユーザーのグループ、またはサイト レベルであっても、外部共有の境界を追加することがあります。

上の 2 つの図は、[Visio](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/media/teams_dependencies.vsdx?raw=true) でも同じように利用することができます。

## <a name="control-guest-access-in-azure-active-directory"></a>Azure Active Directory のゲスト アクセスを管理する

Azure AD を使用し、外部の共同作業者をゲストとして、どんな方法で、テナントに招待できるかどうかを決定します。 Azure B2B のゲスト アクセスの詳細については、「[Azure Active Directory B2B のゲスト ユーザー アクセスとは](/azure/active-directory/b2b/what-is-b2b)」を参照してください。 Azure AD の役割に関する詳細については、「[Azure Active Directory テナントでパートナー組織からユーザーにアクセス許可を付与する](/azure/active-directory/b2b/add-guest-to-role)」を参照してください。

招待の設定は、組織レベルで適用され、ディレクトリ、アプリケーション レベルでゲストのエクスペリエンスを制御します。 これらの設定は、[外部コラボレーション設定](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/CompanyRelationshipsMenuBlade/Settings)で構成できます。

Azure AD には、外部ユーザーを構成する次の設定があります。

- [[ゲスト ユーザー アクセスの制限]](/azure/active-directory/users-groups-roles/users-restrict-guest-permissions)

- [**管理者とゲスト招待元ロールのユーザーが招待可能**]: [**はい**] の場合、管理者およびゲスト招待元ロールのユーザーがテナントにゲストを招待することができます。 [**いいえ**] の場合、管理者およびユーザーはゲストをテナントに招待できません。
- [**メンバーが招待可能**]: ディレクトリの管理者以外のメンバーがゲストを招待できるようにするには、このポリシーを [**はい**] に設定します (推奨)。 管理者だけがゲストを追加できるようにする場合は、このポリシーを [**いいえ**] に設定します。 [**いいえ**] に設定すると、管理者以外の Teams 所有者のゲスト エクスペリエンスが制限され、管理者により AAD に追加されたゲストだけを Teams に追加できることに注意してください。
- [**ゲストが招待可能**]: [**はい**] の場合、自分のディレクトリ内のゲストは他のゲストを招待して、Azure AD によってセキュリティが確保された SharePoint サイトや Azure リソースなどでそれらのゲストと共同作業を行うことができます。 [**いいえ**] の場合、組織と共同作業を行う他のゲストをゲストが招待することはできません。 **[はい]** に設定されている場合でも、ゲストはチームの他のゲストを招待できません。
 
ゲストを招待できるユーザーの制御の詳細については、「[B2B の外部コラボレーションを有効にしてゲストを招待できるユーザー管理する](/azure/active-directory/b2b/delegate-invitations)」を参照してください。

> [!NOTE]
> どのドメインをゲストとしてテナントに招待できるかを管理することもできます。 「[B2B ユーザーに対する特定組織からの招待を許可またはブロックする](/azure/active-directory/external-identities/allow-deny-list)」を参照してください。

ユーザー ゲスト アカウントを手動で Azure AD B2B に追加する必要はありません。ゲストを Teams に追加すると、アカウントは自動的にディレクトリに追加されます。

### <a name="licensing-for-guest-access"></a>ゲスト アクセスのライセンス

ゲスト アクセス ライセンスは、Azure AD External Identities の料金を使用し、毎月のアクティブ ゲストに基づいています。 「[Azure AD External Identities の課金モデル](/azure/active-directory/external-identities/external-identities-pricing)」をご覧ください。

> [!NOTE]
> Exchange Online プラン 2 などのスタンドアロン Office 365 サブスクリプションプランのみを持っている組織内のユーザーは、Teams によって組織に属しているものと見なされるため、その同じ組織へのゲストとして招待されることはできません。 これらのユーザーが Teams を使用する場合は、Microsoft 365 Business Standard、Office 365 Enterprise、または Office 365 Education サブスクリプションが割り当てられる必要があります。 

## <a name="external-access-federation-vs-guest-access"></a>外部アクセス (フェデレーション) とゲスト アクセス

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="related-topics"></a>関連項目

- [Microsoft 365 ゲストの共有設定のリファレンス](/Office365/Enterprise/microsoft-365-guest-settings)

[Microsoft 365 とセキュリティで保護された共同作業を設定する](/microsoft-365/solutions/setup-secure-collaboration-with-teams)