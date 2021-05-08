---
title: Microsoft Teams へのユーザー アクセスを管理する
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: ritikag
search.appverid: MET150
description: 組織内のユーザーに対してユーザー ライセンスを割りTeamsまたは削除することで、Teamsへのユーザー アクセスを管理する方法について学習します。
f1.keywords:
- CSH
- ms.teamsadmincenter.signin.domainerror.nolicensedusers
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 770dcea62d6f3dc65f576a3d64a520dd4de2ecad
ms.sourcegitcommit: 950387da2a2c094b7580bcf81ae5d8b6dfba0d6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2021
ms.locfileid: "51637729"
---
# <a name="manage-user-access-to-teams"></a>Teams へのユーザー アクセスを管理する

製品ライセンスを割りTeamsまたは削除することで、ユーザー レベルでMicrosoft Teamsアクセスを管理します。 会議に匿名でTeams参加する場合を除き、組織内の各ユーザーは、Teams ライセンスを持っている必要Teams。 新しいユーザー アカウントをTeamsユーザーに、または既存のアカウントを持つユーザーに新しいユーザーのライセンスを割り当てできます。

既定では、ライセンス プラン (Microsoft 365 Enterprise E3 や Microsoft 365 Business Premium など) がユーザーに割り当てられると、Teams ライセンスが自動的に割り当てられるので、ユーザーは Teams に対して有効になります。 いつでもライセンスを削除Teams割り当てると、ユーザーのライセンス認証を無効または有効にできます。

<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Teams 管理</a>センター から管理されるメッセージング ポリシーを使用して、Teams でユーザーが使用できるチャットおよびチャネル メッセージング機能を制御します。 既定のポリシーを使用するか、組織内のユーザーに対して 1 つ以上のカスタム メッセージング ポリシーを作成できます。 詳細については、「Manage [messaging policies in Teams 」を参照してください](messaging-policies-in-teams.md)。
管理センター Teamsまたは PowerShell を使用してMicrosoft 365ライセンスを管理します。 ライセンスを管理するには、グローバル管理者またはユーザー管理管理者である必要があります。

> [!NOTE]
> プロジェクトや他の動的なイニシアティブTeamsチームを有機的に形成できるよう、すべてのユーザーに対してチームの管理を有効にすることをお勧めします。 パイロットを実行している場合でも、すべてのユーザーに対して Teams を有効にし続け、パイロット グループのユーザーへの通信のみを対象とすると役に立つ場合があります。

## <a name="using-the-microsoft-365-admin-center"></a>管理センター Microsoft 365使用する

Teamsレベルのライセンスは、管理センターのユーザー管理インターフェイスMicrosoft 365直接管理されます。 管理者は、新しいユーザー アカウントの作成時に新しいユーザー、または既存のアカウントを持つユーザーにライセンスを割り当てできます。 

> [!IMPORTANT]
> 管理者は、すべてのライセンスを管理するには、グローバル管理者またはユーザー管理管理者Microsoft Teams必要があります。
管理センター Microsoft 365を使用して、一度Teamsまたは小規模なユーザーのライセンスを管理します。 [ライセンス] Teams (現時点では最大20 人のユーザー) または [アクティブなユーザー]**ページで** 管理できます。 選択する方法は、特定のユーザーの製品ライセンスを管理するか、特定の製品のユーザー ライセンスを管理するかによって異なります。

数百または数千人のユーザーなど、多数のユーザーの Teams ライセンスを管理する必要がある場合は[、powerShell](#using-powershell)またはグループベースのライセンスを[Azure Active Directory (Azure AD)](/azure/active-directory/users-groups-roles/licensing-groups-assign)で使用します。 

### <a name="assign-a-teams-license"></a>ライセンスを割りTeamsする

手順は、[ライセンス] ページと [アクティブなユーザー] ページ **の違****いによって異** なります。  詳細な手順については、「ユーザーにライセンスを割り当 [てる」を参照してください](/microsoft-365/admin/manage/assign-licenses-to-users)。

|||
|---------|---------|
|![ユーザーに対Teamsライセンスが有効になっている場合のスクリーンショット](media/assign-teams-licenses-1.png)    | ![ユーザーに対Teamsライセンスが有効になっている場合のスクリーンショット](media/assign-teams-licenses-2.png)        |

### <a name="remove-a-teams-license"></a>ライセンスを削除Teamsする

> [!IMPORTANT]
> SKU を無効にして有効にするのにTeams約 24 時間かかります。

ユーザーから Teams ライセンスを削除すると、そのユーザーに対して Teams が無効になり、アプリ起動ツールまたはホーム ページに Teams が表示されなくなりました。 詳細な手順については、「ユーザーからのライセンス [の割り当てを解除する」を参照してください](/microsoft-365/admin/manage/remove-licenses-from-users)。

|||
|---------|---------|
|![ユーザーのTeamsが無効になっている場合のスクリーンショット](media/remove-teams-licenses-1.png)    | ![ユーザーのTeamsが無効になっている場合のスクリーンショット](media/remove-teams-licenses-2.png)        |

## <a name="using-powershell"></a>PowerShell の使用

PowerShell を使用して、ユーザーのTeamsライセンスを一括で管理します。 PowerShell を使用してTeams、他のサービス プラン ライセンスと同じ方法で有効または無効にします。 次のように、サービス プランの id がTeams必要です。

- Microsoft Teams: TEAMS1
- Microsoft Teams: GCC: TEAMS_GOV
- Microsoft Teams DoD: TEAMS_DOD

### <a name="assign-teams-licenses-in-bulk"></a>ライセンスをTeams一括で割り当てる

詳細な手順については、「PowerShell を使用して [ユーザー アカウントにライセンスを割り当てる」を参照してください](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)。

### <a name="remove-teams-licenses-in-bulk"></a>一括Teamsライセンスを削除する

詳細な手順については [、「PowerShell](/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) を使用してサービスへのアクセスを無効にする」および「ユーザー ライセンスの割り当て中にサービスへのアクセスを [無効にする」を参照してください](/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses)。

#### <a name="example"></a>例 

次に示すのは[、New-MsolLicenseOptions](/powershell/module/msonline/new-msollicenseoptions)コマンドレットと[Set-MsolUserLicense](/powershell/module/msonline/set-msoluserlicense)コマンドレットを使用して、特定のライセンス プランを持つユーザーの Teams を無効にする方法の例です。 たとえば、次の手順に従って、最初Teamsライセンス プランを持つすべてのユーザーのライセンス認証を無効にします。 次にTeamsアクセス権を持つ必要がある個々のユーザーに対して、Teams。

> [!IMPORTANT]
> [New-MsolLicenseOptions](/powershell/module/msonline/new-msollicenseoptions)コマンドレットを使用すると、カスタム スクリプトで明示的に識別されない限り、以前に無効にしていたすべてのサービスが有効になります。 たとえば、Exchange と Sway の両方を無効にして Teams を無効にする場合は、これをスクリプトに含める必要があります。または、特定したユーザーに対して Exchange と Sway の両方が有効になります。

次のコマンドを実行して、組織内で利用可能なすべてのライセンス プランを表示します。 詳細については [、「PowerShell を使用したライセンスとサービスの表示」を参照してください](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)。


```powershell
Get-MsolAccountSku
```

次のコマンドを実行します。組織名と、前の手順で取得したライセンス プランの識別子 \<CompanyName:License> です。 たとえば、ContosoSchool:ENTERPRISEPACK_STUDENT。

```powershell
$acctSKU="<CompanyName:License>
$x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"
```

次のコマンドを実行してTeamsライセンス プランのアクティブなライセンスを持つすべてのユーザーのライセンス認証を無効にします。

```powershell
Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x
```

## <a name="related-topics"></a>関連トピック

- [Teams アドオン ライセンス](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [追加Teamsライセンスを割り当てる](teams-add-on-licensing/assign-teams-add-on-licenses.md)
- [PowerShell を使用してライセンスとサービスを表示する](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [ライセンスのための製品名とサービス プラン識別子](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [Education SKU リファレンス](sku-reference-edu.md)
