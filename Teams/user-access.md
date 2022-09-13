---
title: Microsoft Teams へのユーザー アクセスを管理する
manager: SerdarSoysal
ms.author: mikeplum
author: MikePlumleyMSFT
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: ritikag
search.appverid: MET150
description: 組織内のユーザーに Teams ライセンスを割り当てるか削除することで、Teams へのユーザー アクセスを管理する方法について説明します。
f1.keywords:
- CSH
- ms.teamsadmincenter.signin.domainerror.nolicensedusers
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9affb1fc93bf79cd7f583f0e74b02bd06f604f0d
ms.sourcegitcommit: 9de6b0b03f433e71fe239d292387eed33c11b531
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/13/2022
ms.locfileid: "67657257"
---
# <a name="manage-user-access-to-teams"></a>Teams へのユーザー アクセスを管理する

ユーザー レベルで Teams へのアクセスを管理するには、Microsoft Teams 製品ライセンスを割り当てるか削除します。 Teams 会議に匿名で参加する場合を除き、組織内の各ユーザーは Teams を使用する前に Teams ライセンスを持っている必要があります。 新しいユーザー アカウントが作成されたとき、または既存のアカウントを持つユーザーに Teams ライセンスを新しいユーザーに割り当てることができます。

既定では、ライセンス プラン (Microsoft 365 Enterprise E3 やMicrosoft 365 Business Premiumなど) がユーザーに割り当てられると、Teams ライセンスが自動的に割り当てられ、ユーザーは Teams に対して有効になります。 ユーザーの Teams を無効または有効にするには、いつでもライセンスを削除または割り当てます。

<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Teams 管理 センター</a>から管理されるメッセージング ポリシーを使用して、Teams のユーザーが利用できるチャットとチャネルのメッセージング機能を制御します。 既定のポリシーを使用することも、組織内のユーザーに対して 1 つ以上のカスタム メッセージング ポリシーを作成することもできます。 詳細については、「 [Teams でのメッセージング ポリシーの管理](messaging-policies-in-teams.md)」を参照してください。
Microsoft 365 管理センターまたは PowerShell を使用して Teams ライセンスを管理します。 ライセンスを管理するには、グローバル管理者またはユーザー管理管理者である必要があります。

> [!NOTE]
> すべてのユーザーに Teams を有効にして、プロジェクトやその他の動的イニシアチブに対してチームを有機的に形成できるようにすることをお勧めします。 パイロットを実行している場合でも、Teams をすべてのユーザーに対して有効にしておくと役に立ちますが、ユーザーのパイロット グループへの通信のみをターゲットにしてください。

## <a name="using-the-microsoft-365-admin-center"></a>Microsoft 365 管理センターの使用

Teams ユーザー レベルのライセンスは、Microsoft 365 管理センターユーザー管理インターフェイスを使用して直接管理されます。 管理者は、新しいユーザー アカウントが作成されたときに、または既存のアカウントを持つユーザーにライセンスを割り当てることができます。

> [!IMPORTANT]
> Microsoft Teams ライセンスを管理するには、管理者にグローバル管理者またはユーザー管理管理者特権が必要です。
Microsoft 365 管理センターを使用して、個々のユーザーまたは小規模なユーザー セットの Teams ライセンスを一度に管理します。 Teams ライセンスは、[ **ライセンス** ] ページ (一度に最大 20 人のユーザー) または **[アクティブ ユーザー]** ページで管理できます。 選択する方法は、特定のユーザーの製品ライセンスを管理するか、特定の製品のユーザー ライセンスを管理するかによって異なります。

数百または数千のユーザーなど、多数のユーザーの Teams ライセンスを管理する必要がある場合は、[Azure Active Directory (Azure AD) で PowerShell またはグループベースのライセンスを](/azure/active-directory/users-groups-roles/licensing-groups-assign)[使用](#using-powershell)します。 

### <a name="assign-a-teams-license"></a>Teams ライセンスを割り当てる

手順は、[ **ライセンス** ] ページと [ **アクティブ ユーザー** ] ページのどちらを使用するかによって異なります。  詳細な手順については、「 [ユーザーにライセンスを割り当てる」を](/microsoft-365/admin/manage/assign-licenses-to-users)参照してください。

|&nbsp;|&nbsp;|
|---------|---------|
|![ユーザーに対して有効になっている Teams ライセンスのスクリーンショット 1。](media/assign-teams-licenses-1.png)    | ![ユーザーに対して有効になっている Teams ライセンスのスクリーンショット 2](media/assign-teams-licenses-2.png)        |

### <a name="remove-a-teams-license"></a>Teams ライセンスを削除する

> [!IMPORTANT]
> Teams SKU を無効にするには、約 24 時間かかります。

ユーザーから Teams ライセンスを削除すると、そのユーザーに対して Teams が無効になり、アプリ起動ツールまたはホームページに Teams が表示されなくなります。 詳細な手順については、「 [ユーザーからのライセンスの割り当て解除](/microsoft-365/admin/manage/remove-licenses-from-users)」を参照してください。

|&nbsp;|&nbsp;|
|---------|---------|
|![ユーザーに対して無効になっている Teams ライセンスのスクリーンショット 1。](media/remove-teams-licenses-1.png)    | ![ユーザーに対して無効になっている Teams ライセンスのスクリーンショット 2](media/remove-teams-licenses-2.png)        |

## <a name="using-powershell"></a>PowerShell の使用

PowerShell を使用して、ユーザーの Teams ライセンスを一括管理します。 PowerShell を使用して Teams を有効または無効にすることは、他のサービス プラン ライセンスと同じ方法で行います。 Teams のサービス プランの識別子が必要です。これは次のとおりです。

- Microsoft Teams: TEAMS1
- Microsoft Teams for GCC: TEAMS_GOV
- Microsoft Teams for DoD: TEAMS_DOD

### <a name="assign-teams-licenses-in-bulk"></a>Teams ライセンスを一括で割り当てる

詳細な手順については、「 [PowerShell を使用してユーザー アカウントにライセンスを割り当てる](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)」を参照してください。

### <a name="remove-teams-licenses-in-bulk"></a>Teams ライセンスを一括で削除する

詳細な手順については、「 [PowerShell でサービスへのアクセスを無効にする](/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) 」と「 [ユーザー ライセンスの割り当て中にサービスへのアクセスを無効にする](/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses)」を参照してください。

#### <a name="example"></a>例 

[New-MsolLicenseOptions](/powershell/module/msonline/new-msollicenseoptions) コマンドレットと [Set-MsolUserLicense](/powershell/module/msonline/set-msoluserlicense) コマンドレットを使用して、特定のライセンスプランを持つユーザーに対して Teams を無効にする方法の例を次に示します。 たとえば、次の手順に従って、最初に特定のライセンスプランを持つすべてのユーザーに対して Teams を無効にします。 次に、Teams にアクセスする必要がある個々のユーザーごとに Teams を有効にします。

> [!IMPORTANT]
> [New-MsolLicenseOptions](/powershell/module/msonline/new-msollicenseoptions) コマンドレットを使用すると、カスタム スクリプトで明示的に識別されない限り、以前に無効にされていたすべてのサービスが有効になります。 たとえば、Exchange とSwayの両方を無効にしたまま Teams も無効にする場合は、これをスクリプトに含める必要があります。また、特定したユーザーに対して Exchange とSwayの両方が有効になります。

次のコマンドを実行して、組織内で使用可能なすべてのライセンス プランを表示します。 詳細については、「 [PowerShell でライセンスとサービスを表示する](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)」を参照してください。


```powershell
Get-MsolAccountSku
```

次のコマンドを実行します。 \<CompanyName:License> ここで、組織名と、前の手順で取得したライセンス プランの識別子を指定します。 たとえば、ContosoSchool:ENTERPRISEPACK_STUDENT。

```powershell
$acctSKU="<CompanyName:License>
$x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"
```

次のコマンドを実行して、ライセンス プランのアクティブなライセンスを持っているすべてのユーザーに対して Teams を無効にします。

```powershell
Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x
```

## <a name="related-topics"></a>関連項目

- [Teams アドオン ライセンス](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [Teams アドオン ライセンスの割り当て](teams-add-on-licensing/assign-teams-add-on-licenses.md)
- [PowerShell を使用してライセンスとサービスを表示する](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [ライセンスのための製品名とサービス プラン識別子](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [Education SKU リファレンス](sku-reference-edu.md)
