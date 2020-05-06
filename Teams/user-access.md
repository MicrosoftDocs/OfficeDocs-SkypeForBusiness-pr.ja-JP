---
title: Microsoft Teams へのユーザー アクセスを管理する
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
f1.keywords:
- CSH
ms.reviewer: ritikag
search.appverid: MET150
description: 組織内のユーザーに Teams のライセンスを割り当てまたは削除して、チームへのユーザーアクセスを管理する方法について説明します。
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 32ab8f68ef1c37fbb5cb724b322b4db0ee757b84
ms.sourcegitcommit: 09ff11f8e4f6a93cedc34a5d732a133163df79a0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "44042274"
---
# <a name="manage-user-access-to-teams"></a>Teams へのユーザー アクセスを管理する

Microsoft Teams 製品ライセンスを割り当てたり、削除したりして、ユーザーレベルでチームへのアクセスを管理します。 組織内の各ユーザーは、Teams を使用する前に Teams ライセンスを所有している必要があります。 新しいユーザーアカウントが作成されたとき、または既存のアカウントを持つユーザーに新しいユーザーのチームライセンスを割り当てることができます。

既定では、ライセンス計画 (Microsoft 365 Enterprise E3 や Microsoft 365 Business Premium など) がユーザーに割り当てられている場合、Teams ライセンスが自動的に割り当てられ、ユーザーはチームに対して有効になります。 ライセンスを削除するか、いつでも割り当てて、ユーザーに対して Teams を有効または無効にすることができます。

Teams のライセンスは、Microsoft 365 管理センターまたは PowerShell を使用して管理します。 ライセンスを管理するには、グローバル管理者またはユーザー管理者である必要があります。

> [!NOTE]
> チームがプロジェクトやその他の動的なイニシアチブのために organically を形成できるように、すべてのユーザーに対して Teams を有効にすることをお勧めします。 パイロットを実行している場合でも、チームをすべてのユーザーに対して有効にしたままにしておくと便利な場合がありますが、ユーザーのパイロットグループとの通信のみを対象としています。

## <a name="using-the-microsoft-365-admin-center"></a>Microsoft 365 管理センターを使用する

Microsoft 365 管理センターを使用して、個々のユーザーまたは少数のユーザーの Teams ライセンスを一度に管理します。 Teams のライセンスは、[**ライセンス**] ページ (同時に最大20人のユーザーの場合) または [**アクティブなユーザー** ] ページで管理できます。 選択する方法は、特定のユーザーの製品ライセンスを管理するか、特定の製品のユーザーライセンスを管理するかによって異なります。

数百または数千のユーザーなど、多数のユーザーの Teams ライセンスを管理する必要がある場合は、 [Azure Active Directory (AZURE AD) で](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)Powershell またはグループベースのライセンスを[使用](#using-powershell)します。 

### <a name="assign-a-teams-license"></a>Teams ライセンスを割り当てる

この手順は、[**ライセンス**] ページまたは [**アクティブなユーザー** ] ページのどちらを使用するかによって異なります。  詳細な手順については、「[ユーザーにライセンスを割り当てる](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)」を参照してください。

|||
|---------|---------|
|![ユーザーに対して有効になっている Teams ライセンスのスクリーンショット](media/assign-teams-licenses-1.png)    | ![ユーザーに対して有効になっている Teams ライセンスのスクリーンショット](media/assign-teams-licenses-2.png)        |

### <a name="remove-a-teams-license"></a>Teams ライセンスを削除する

ユーザーからチームライセンスを削除すると、そのユーザーに対してチームが無効になり、アプリ起動ツールまたはホームページで teams が表示されなくなります。 詳細な手順については、「[ユーザーからライセンスの割り当てを解除](https://docs.microsoft.com/microsoft-365/admin/manage/remove-licenses-from-users)する」をご覧ください。

|||
|---------|---------|
|![ユーザーが無効にした Teams ライセンスのスクリーンショット](media/remove-teams-licenses-1.png)    | ![ユーザーが無効にした Teams ライセンスのスクリーンショット](media/remove-teams-licenses-2.png)        |

## <a name="using-powershell"></a>PowerShell を使用する場合

PowerShell を使用して、ユーザーの Teams ライセンスを一括で管理します。 他のサービスプランライセンスの場合と同様に、PowerShell を使用して Teams を有効または無効にします。 Teams のサービスプランの識別子が必要です。次のようになります。

- Microsoft Teams: TEAMS1
- Microsoft Teams for GCC: TEAMS_GOV
- Microsoft Teams (DoD): TEAMS_DOD

### <a name="assign-teams-licenses-in-bulk"></a>Teams ライセンスを一括で割り当てる

詳細な手順については、「 [PowerShell を使用してライセンスをユーザーアカウントに割り当てる](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)」を参照してください。

### <a name="remove-teams-licenses-in-bulk"></a>Teams ライセンスを一括で削除する

詳細な手順については、「 [PowerShell を使ったサービスへのアクセスを無効に](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell)する」および「[ユーザーライセンスの割り当て中にサービスへのアクセスを無効](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses)にする」を参照

#### <a name="example"></a>例 

次の例は、 [MsolLicenseOptions](https://docs.microsoft.com/powershell/module/msonline/new-msollicenseoptions)と[set-msoluserlicense](https://docs.microsoft.com/powershell/module/msonline/set-msoluserlicense)コマンドレットを使用して、特定のライセンス計画を持っているユーザーのチームを無効にする方法を示しています。 たとえば、次の手順に従って、特定のライセンス計画を持っているすべてのユーザーに対して Teams の使用を無効にします。 次に、Teams にアクセスする必要がある個々のユーザーに対して Teams を有効にします。

> [!IMPORTANT]
> カスタムスクリプトで明示的に指定されていない限り、 [MsolLicenseOptions](https://docs.microsoft.com/powershell/module/msonline/new-msollicenseoptions)コマンドレットによって、以前に無効になっていたすべてのサービスが有効になります。 たとえば、チームを無効にしている間も Exchange と Sway の両方を無効のままにしておく必要がある場合は、これをスクリプトに含めるか、または Exchange と Sway の両方を有効にして、特定のユーザーに対して有効にする必要があります。

次のコマンドを実行して、組織内で利用可能なすべてのライセンスプランを表示します。 詳細については、「 [PowerShell でライセンスとサービスを表示](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)する」を参照してください。

      Get-MsolAccountSku

次のコマンドを実行し\<ます。ここで、"CompanyName: ライセンス>" は、組織名と、前の手順で取得したライセンスプランの識別子です。 たとえば、ContosoSchool: ENTERPRISEPACK_STUDENT とします。

      $acctSKU="<CompanyName:License>
      $x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"

ライセンス計画のアクティブなライセンスを所有しているすべてのユーザーのチームを無効にするには、次のコマンドを実行します。

      Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x

## <a name="manage-teams-at-the-organization-level"></a>組織レベルでチームを管理する

[!INCLUDE [global-switch-expiry-note](includes/global-switch-expiry-note.md)]

## <a name="related-topics"></a>関連項目

- [Teams アドオンライセンス](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [Teams のアドオンライセンスを割り当てる](teams-add-on-licensing/assign-teams-add-on-licenses.md)
- [PowerShell でライセンスとサービスを表示する](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [ライセンスのための製品名とサービス プラン識別子](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [エデュケーション SKU リファレンス](sku-reference-edu.md)