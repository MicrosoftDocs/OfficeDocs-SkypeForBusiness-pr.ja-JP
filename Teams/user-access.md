---
title: Microsoft Teams へのユーザー アクセスを管理する
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: ritikag
search.appverid: MET150
description: 組織内のユーザーにTeams ライセンスを割り当てるか削除することで、Teamsへのユーザー アクセスを管理する方法について説明します。
f1.keywords:
- CSH
- ms.teamsadmincenter.signin.domainerror.nolicensedusers
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0d467e2e3fcdff6e688c13d952f434e635f7d038
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62384125"
---
# <a name="manage-user-access-to-teams"></a>Teams へのユーザー アクセスを管理する

ユーザー レベルでTeamsへのアクセスを管理するには、Microsoft Teams製品ライセンスを割り当てるか削除します。 匿名で会議Teams参加する場合を除き、組織内の各ユーザーは、Teamsを使用する前に、Teams ライセンスを持っている必要があります。 新しいユーザー アカウントが作成されたとき、または既存のアカウントを持つユーザーに、新しいユーザーに対してTeams ライセンスを割り当てることができます。

既定では、ライセンス プラン (Microsoft 365 Enterprise E3 やMicrosoft 365 Business Premiumなど) がユーザーに割り当てられると、Teams ライセンスが自動的に割り当てられ、ユーザーはTeamsに対して有効になります。 ライセンスをいつでも削除または割り当てることで、ユーザーのTeamsを無効または有効にすることができます。

<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Teams管理センター</a>から管理されるメッセージング ポリシーを使用して、Teamsのユーザーが利用できるチャットとチャネルのメッセージング機能を制御します。 既定のポリシーを使用することも、組織内のユーザーに対して 1 つ以上のカスタム メッセージング ポリシーを作成することもできます。 詳細については、「[Teamsのメッセージング ポリシーの管理](messaging-policies-in-teams.md)」を参照してください。
Microsoft 365 管理センターまたは PowerShell を使用して、Teams ライセンスを管理します。 ライセンスを管理するには、グローバル管理者またはユーザー管理管理者である必要があります。

> [!NOTE]
> プロジェクトやその他の動的なイニシアチブのためにチームを有機的に形成できるように、すべてのユーザーに対してTeamsを有効にすることをお勧めします。 パイロットを実行している場合でも、すべてのユーザーに対してTeamsを有効にしておくと役に立ちますが、ターゲットはユーザーのパイロット グループへの通信のみです。

## <a name="using-the-microsoft-365-admin-center"></a>Microsoft 365 管理センターの使用

Teamsユーザー レベルのライセンスは、Microsoft 365 管理センターユーザー管理インターフェイスを使用して直接管理されます。 管理者は、新しいユーザー アカウントが作成されたときに、または既存のアカウントを持つユーザーにライセンスを割り当てることができます。 

> [!IMPORTANT]
> Microsoft Teams ライセンスを管理するには、管理者にグローバル管理者またはユーザー管理管理者特権が必要です。
Microsoft 365 管理センターを使用して、個々のユーザーまたは小規模なユーザー セットのTeams ライセンスを一度に管理します。 Teamsライセンスは、[**ライセンス**] ページ (一度に最大 20 人のユーザー) または **[アクティブ なユーザー**] ページで管理できます。 選択する方法は、特定のユーザーの製品ライセンスを管理するか、特定の製品のユーザー ライセンスを管理するかによって異なります。

数百または数千のユーザーなど、多数のユーザーのTeams ライセンスを管理する必要がある場合は、[powerShell またはグループ ベースのライセンスをAzure Active Directory (Azure AD) で](/azure/active-directory/users-groups-roles/licensing-groups-assign)[使用](#using-powershell)します。 

### <a name="assign-a-teams-license"></a>Teams ライセンスを割り当てる

手順は、[ **ライセンス** ] ページと [ **アクティブ ユーザー** ] ページのどちらを使用するかによって異なります。  詳細な手順については、「 [ユーザーにライセンスを割り当てる」を](/microsoft-365/admin/manage/assign-licenses-to-users)参照してください。

|&nbsp;|&nbsp;|
|---------|---------|
|![ユーザーに対して有効になっているTeamsライセンスのスクリーンショット 1。](media/assign-teams-licenses-1.png)    | ![ユーザーのライセンスが有効になっているTeamsのスクリーンショット 2](media/assign-teams-licenses-2.png)        |

### <a name="remove-a-teams-license"></a>Teams ライセンスを削除する

> [!IMPORTANT]
> Teams SKU を無効にするには、約 24 時間かかります。

Teams ライセンスをユーザーから削除すると、そのユーザーに対してTeamsが無効になり、アプリ起動ツールまたはホームページにTeamsが表示されなくなります。 詳細な手順については、「 [ユーザーからのライセンスの割り当て解除](/microsoft-365/admin/manage/remove-licenses-from-users)」を参照してください。

|&nbsp;|&nbsp;|
|---------|---------|
|![ユーザーに対して無効になっているTeams ライセンスのスクリーンショット 1。](media/remove-teams-licenses-1.png)    | ![ユーザーに対して無効になっているTeams ライセンスのスクリーンショット 2](media/remove-teams-licenses-2.png)        |

## <a name="using-powershell"></a>PowerShell の使用

PowerShell を使用して、ユーザーのTeams ライセンスを一括管理します。 PowerShell を使用してTeamsを有効または無効にすることは、他のサービス プラン ライセンスと同じ方法で行います。 Teamsのサービス プランの識別子が必要です。これは次のとおりです。

- Microsoft Teams: TEAMS1
- GCCのMicrosoft Teams: TEAMS_GOV
- DoD のMicrosoft Teams: TEAMS_DOD

### <a name="assign-teams-licenses-in-bulk"></a>Teams ライセンスを一括で割り当てる

詳細な手順については、「 [PowerShell を使用してユーザー アカウントにライセンスを割り当てる](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)」を参照してください。

### <a name="remove-teams-licenses-in-bulk"></a>Teams ライセンスを一括で削除する

詳細な手順については、「 [PowerShell でサービスへのアクセスを無効にする](/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) 」と「 [ユーザー ライセンスの割り当て中にサービスへのアクセスを無効にする](/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses)」を参照してください。

#### <a name="example"></a>例 

[New-MsolLicenseOptions](/powershell/module/msonline/new-msollicenseoptions) コマンドレットと [Set-MsolUserLicense](/powershell/module/msonline/set-msoluserlicense) コマンドレットを使用して、特定のライセンス プランを持つユーザーのTeamsを無効にする方法の例を次に示します。 たとえば、次の手順に従って、最初に特定のライセンスプランを持つすべてのユーザーのTeamsを無効にします。 次に、Teamsにアクセスする必要がある個々のユーザーのTeamsを有効にします。

> [!IMPORTANT]
> [New-MsolLicenseOptions](/powershell/module/msonline/new-msollicenseoptions) コマンドレットを使用すると、カスタム スクリプトで明示的に識別されない限り、以前に無効にされていたすべてのサービスが有効になります。 たとえば、ExchangeとSwayの両方を無効にしたままにして、Teamsも無効にする場合は、これをスクリプトに含める必要があります。また、特定したユーザーに対してExchangeとSwayの両方を有効にする必要があります。

次のコマンドを実行して、組織内で使用可能なすべてのライセンス プランを表示します。 詳細については、「 [PowerShell でライセンスとサービスを表示する](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)」を参照してください。


```powershell
Get-MsolAccountSku
```

次のコマンドを実行します。 \<CompanyName:License> ここで、組織名と、前の手順で取得したライセンス プランの識別子を指定します。 たとえば、ContosoSchool:ENTERPRISEPACK_STUDENT。

```powershell
$acctSKU="<CompanyName:License>
$x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"
```

次のコマンドを実行して、ライセンス プランのアクティブなライセンスを持っているすべてのユーザーのTeamsを無効にします。

```powershell
Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x
```

## <a name="related-topics"></a>関連項目

- [アドオン ライセンスをTeamsする](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [アドオン ライセンスTeams割り当てる](teams-add-on-licensing/assign-teams-add-on-licenses.md)
- [PowerShell を使用してライセンスとサービスを表示する](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [ライセンスのための製品名とサービス プラン識別子](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [Education SKU リファレンス](sku-reference-edu.md)
