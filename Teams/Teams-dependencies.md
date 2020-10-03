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
ms.reviewer: rafarhi
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
description: Microsoft Teams のゲスト アクセス機能を 4 つの異なる承認レベルで管理します。
ms.openlocfilehash: e74152bc61bdf0bb793338b50ddcd5da62e9b2d0
ms.sourcegitcommit: 43e5a4aac11c20dd5a4c35b59695f309e1559e82
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/03/2020
ms.locfileid: "48346188"
---
# <a name="authorize-guest-access-in-microsoft-teams"></a>Microsoft Teams でのゲスト アクセスを承認する

組織の要件を満たすために、4つの異なるレベルの承認を通じて Teams のゲストアクセス機能を管理することができます。 すべての認証レベルは、Microsoft 365 組織に適用されます。 それぞれの承認レベルによって、ゲストのエクスペリエンスが次の通り制御されます。

- **Azure Active Directory**: Teams のゲストアクセスは、Azure AD 企業間 (B2B) プラットフォームに依存します。 この承認レベルは、ゲストのエクスペリエンスをディレクトリ、テナント、およびアプリケーション レベルで制御します。
- **Teams**: teams のゲストエクスペリエンスのみを制御します。
- **Microsoft 365 グループ**: Microsoft 365 グループおよび Teams のゲストエクスペリエンスを制御します。
- **Sharepoint と onedrive**: Sharepoint、Onedrive、Microsoft 365 グループ、および Teams のゲストエクスペリエンスを制御します。

これらの異なる承認レベルにより、組織におけるゲスト アクセスを柔軟にセットアップできるようになります。 たとえば、チームのゲストユーザーに対して、組織全体でのゲストユーザーの許可を許可しない場合は、Teams のゲストアクセスを無効にするだけです。 別の例: Azure AD、チーム、グループのレベルでゲストアクセスを有効にすることもできますが、選択した [チームに対して、データ分類が機密情報のような1つ以上の条件に一致するゲストユーザーの追加を無効に](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)することができます。 SharePoint と OneDrive には、Microsoft 365 グループに依存しない独自のゲストアクセス設定があります。

エンドツーエンドのゲストアクセスの構成手順については、「 [チームのゲストとの共同作業](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)」をご覧ください。

> [!NOTE]
> ゲストは、「[Microsoft 365 および Office 365 サービスの説明](https://go.microsoft.com/fwlink/p/?linkid=282347)」および「[Azure AD B2B コラボレーションの制限での制限](https://docs.microsoft.com/azure/active-directory/external-identities/current-limitations)」に記載されているサービスの制限の対象となります。 

次の図は、Azure Active Directory、Teams、および Microsoft 365 間でのゲストアクセス承認の依存関係の付与と統合の方法を示しています。

![ゲスト アクセスの承認の依存関係の図](media/teams_dependencies_image1.png)

次の図は、一般的なゲスト アクセスの招待と引き換えフローを通じて、ユーザーの作業環境がアクセス許可モデルとどのように連動するかを大まかに示しています。

![招待と引き換えフローの図](media/authorize-guest-image1.png)

ここで注意すべきことは、アプリ、ボット、コネクタには、ユーザーアカウントに固有のアクセス許可や承認が必要であることです。 それぞれに付与する必要があります。 同様に SharePoint は、特定のユーザー、ユーザーのグループ、またはサイト レベルであっても、外部共有の境界を追加することがあります。

上の 2 つの図は、[Visio](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/media/teams_dependencies.vsdx?raw=true) でも同じように利用することができます。

## <a name="control-guest-access-in-azure-active-directory"></a>Azure Active Directory のゲスト アクセスを管理する

Azure AD を使用し、外部の共同作業者をゲストとして、どんな方法で、テナントに招待できるかどうかを決定します。 Azure B2B のゲスト アクセスの詳細については、「[Azure Active Directory B2B のゲスト ユーザー アクセスとは](https://docs.microsoft.com/azure/active-directory/b2b/what-is-b2b)」を参照してください。 Azure AD の役割に関する詳細については、「[Azure Active Directory テナントでパートナー組織からユーザーにアクセス許可を付与する](https://docs.microsoft.com/azure/active-directory/b2b/add-guest-to-role)」を参照してください。

招待状の設定は、組織レベルで適用され、ディレクトリおよびアプリケーションレベルでゲストのエクスペリエンスを制御します。 [外部コラボレーションの設定](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/CompanyRelationshipsMenuBlade/Settings)でこれらの設定を構成できます。

Azure AD には、外部ユーザーを構成する次の設定があります。

- [ゲストユーザーアクセスの制限](https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-restrict-guest-permissions)

- [**管理者とゲスト招待元ロールのユーザーが招待可能**]: [**はい**] の場合、管理者およびゲスト招待元ロールのユーザーがテナントにゲストを招待することができます。 [**いいえ**] の場合、管理者およびユーザーはゲストをテナントに招待できません。
- [**メンバーが招待可能**]: ディレクトリの管理者以外のメンバーがゲストを招待できるようにするには、このポリシーを [**はい**] に設定します (推奨)。 管理者だけがゲストを追加できるようにする場合は、このポリシーを [**いいえ**] に設定します。 [**いいえ**] に設定すると、管理者以外の Teams 所有者のゲスト エクスペリエンスが制限され、管理者により AAD に追加されたゲストだけを Teams に追加できることに注意してください。
- [**ゲストが招待可能**]: [**はい**] の場合、自分のディレクトリ内のゲストは他のゲストを招待して、Azure AD によってセキュリティが確保された SharePoint サイトや Azure リソースなどでそれらのゲストと共同作業を行うことができます。 [**いいえ**] の場合、組織と共同作業を行う他のゲストをゲストが招待することはできません。
    > [!IMPORTANT]
    > 現在、Teams はゲスト招待者の役割をサポートしていないため、[**ゲストが招待できる**] を [**はい**] に設定しても、ゲストは Teams 内の他のゲストを招待できません。
 
ゲストを招待できるユーザーを制御する方法について詳しくは、「 [B2B の外部グループ作業を有効にする」と「ゲストを招待できるユーザーを管理する](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations)」をご覧ください。

> [!NOTE]
> どのドメインをゲストとしてテナントに招待できるかを管理することもできます。 「 [特定の組織からの B2B ユーザーへの招待を許可またはブロックする」を](https://docs.microsoft.com/azure/active-directory/external-identities/allow-deny-list)参照してください。

ユーザー ゲスト アカウントを手動で Azure AD B2B に追加する必要はありません。ゲストを Teams に追加すると、アカウントは自動的にディレクトリに追加されます。

### <a name="licensing-for-guest-access"></a>ゲスト アクセスのライセンス

ゲストアクセスライセンスは、Azure AD の外部 Id 価格を使用し、月間のアクティブなゲストに基づいています。 詳細については、「 [AZURE AD の請求モデル](https://docs.microsoft.com/azure/active-directory/external-identities/external-identities-pricing) 」を参照してください。

> [!NOTE]
> Exchange Online プラン 2 などのスタンドアロン Office 365 サブスクリプションプランのみを持っている組織内のユーザーは、Teams によって組織に属しているものと見なされるため、その同じ組織へのゲストとして招待されることはできません。 これらのユーザーが Teams を使用する場合は、Microsoft 365 Business Standard、Office 365 Enterprise、または Office 365 Education サブスクリプションが割り当てられる必要があります。 

## <a name="external-access-federation-vs-guest-access"></a>外部アクセス (フェデレーション) とゲスト アクセス

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="related-topics"></a>関連項目

- [Microsoft 365 ゲストの共有設定のリファレンス](https://docs.microsoft.com/Office365/Enterprise/microsoft-365-guest-settings)

[Microsoft 365 とのセキュリティで保護されたコラボレーションを設定する](https://docs.microsoft.com/microsoft-365/solutions/setup-secure-collaboration-with-teams)
