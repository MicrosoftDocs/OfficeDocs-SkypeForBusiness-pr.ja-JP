---
title: PowerShell を使用してチームへのゲスト アクセスを制御する
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
f1.keywords:
- NOCSH
description: PowerShell を使用して、Microsoft Teams のすべてのチームまたは特定のチームへのゲストアクセスを許可またはブロックする方法について説明します。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 28d8109f772a448d61e189a6b0a8aa1c45feb5af
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "43902592"
---
<a name="use-powershell-to-control-guest-access-to-a-team"></a>PowerShell を使用してチームへのゲスト アクセスを制御する
================================================

Microsoft 365 管理センターと Azure Active Directory (Azure AD) ポータルのほかに、Windows PowerShell を使用してゲストアクセスを制御することもできます。 PowerShell を使用すると、次の操作を行うことができます。
  
- すべてのチームと Microsoft 365 グループへのゲストアクセスを許可またはブロックする

- すべてのチームと Microsoft 365 グループにゲストを追加できるようにする

- 特定のチームまたは Office 365 グループのゲスト ユーザーを許可または拒否する

詳細については、「 [Microsoft 365 グループでゲストアクセスを管理](https://docs.microsoft.com/office365/admin/create-groups/manage-guest-access-in-groups#use-powershell-to-control-guest-access)する」の「PowerShell を使用してゲストアクセスを制御する」を参照してください。

  
PowerShell を使用して、ドメインに基づいてゲスト ユーザーの許可と拒否を行うこともできます。 たとえば、ある企業 (Contoso) が別の企業 (Fabrikam) とパートナーシップを結んでいると仮定します。 Fabrikam 社を [許可] リストに追加すると、Contoso 社のユーザーは Fabrikam のユーザーをゲストとしてグループに追加できるようになります。 詳細については、「 [Microsoft 365 グループへのゲストアクセスを許可/ブロックする](https://go.microsoft.com/fwlink/?linkid=854001)」を参照してください。
  
チーム内のゲストをブロックし、それでも SharePoint サイトへのアクセスを許可する場合は、Azure AD Powershell コマンドレットを使用して、SharePoint サイトの外部共有が有効になっていることを前提として、Company オブジェクトの AllowGuestsToAccessGroups パラメーターを無効にすることができます。

## <a name="use-powershell-to-turn-guest-access-on-or-off"></a>PowerShell を使用してゲスト アクセスをオンまたはオフにする

1.    Skype for Business Online PowerShell モジュールを次からダウンローします https://www.microsoft.com/download/details.aspx?id=39366
 
2.    PowerShell セッションを Skype for Business Online エンドポイントに接続します。

    ```PowerShell
    Import-Module SkypeOnlineConnector
    $Cred = Get-Credential
    $CSSession = New-CsOnlineSession -Credential $Cred
    Import-PSSession -Session $CSSession
    ```
3.    設定を確認して、`AllowGuestUser` が `$False` の場合は、[Set-CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) コマンドレットを使用して `$True` に設定します。

    ```PowerShell
    Get-CsTeamsClientConfiguration

    Identity                         : Global
    AllowEmailIntoChannel            : True
    RestrictedSenderList             :
    AllowDropBox                     : True
    AllowBox                         : True
    AllowGoogleDrive                 : True
    AllowShareFile                   : True
    AllowOrganizationTab             : True
    AllowSkypeBusinessInterop        : True
    ContentPin                       : RequiredOutsideScheduleMeeting
    AllowResourceAccountSendMessage  : True
    ResourceAccountContentAccess     : NoAccess
    AllowGuestUser                   : True
    AllowScopedPeopleSearchandAccess : False
    
    Set-CsTeamsClientConfiguration -AllowGuestUser $True -Identity Global
    ```
これで、自分の組織の Teams にゲスト ユーザーを入れることができるようになりました。


## <a name="guest-access-vs-external-access"></a>ゲストアクセスと外部アクセス

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]
