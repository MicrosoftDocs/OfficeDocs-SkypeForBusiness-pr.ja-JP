---
title: Microsoft 365 または Office 365 で Microsoft Teams Rooms を展開する
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: このトピックでは、Microsoft 365 または Office 365 を使用して Microsoft Teams Rooms を展開する方法について説明します。Teams または Skype for Business と Exchange はどちらもオンラインです。
ms.openlocfilehash: e3f72c86f88ab449b48b80d6bef06d0858c44b53
ms.sourcegitcommit: 1165a74b1d2e79e1a085b01e0e00f7c65483d729
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/08/2021
ms.locfileid: "61355646"
---
# <a name="deploy-microsoft-teams-rooms-with-microsoft-365-or-office-365"></a>Microsoft 365 または Office 365 で Microsoft Teams Rooms を展開する

このトピックでは、Microsoft 365 または Office 365 を使用して Microsoft Teams Rooms をデプロイする方法について説明します。Microsoft Teamsと Exchange両方がオンラインです。

## <a name="requirements"></a>要件

Microsoft Teams Rooms を Microsoft 365 または Office 365 で展開する前に、要件を満たしていることをご確認ください。 詳細については、「[Microsoft Teams Rooms の要件](requirements.md)」をご覧ください。

### <a name="add-a-resource-account"></a>リソース アカウントを追加する

1. Exchange Online PowerShell に接続します。 手順については、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。

2. Exchange Online PowerShell で、新しい会議室メールボックスを作成するか、既存の会議室メールボックスを変更します。 既定では、ルーム メールボックスにはアカウントが関連付けられているので、Microsoft Teams で認証できるルーム メールボックスを作成または変更するときに、アカウントを追加する必要があります。

   - 新しい会議室メールボックスを作成するには、次の構文を使用します。

     ``` PowerShell
     New-Mailbox -MicrosoftOnlineServicesID <Office365 ID> -Name <String> -Alias ConferenceRoom01 -Room -EnableRoomMailboxAccount $true  -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```
     この例では、次の設定で新しい会議室メールボックスを作成します:

     - アカウント: ConferenceRoom01@contoso.com
  
     - 名前: ConferenceRoom01

     - エイリアス: ConferenceRoom01

     - アカウントのパスワード: P@ $ $W 0rd5959

     ``` PowerShell
     New-Mailbox -MicrosoftOnlineServicesID ConferenceRoom01@contoso.com -Name "ConferenceRoom01" -Alias ConferenceRoom01 -Room -EnableRoomMailboxAccount $true  -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - 既存の会議室メールボックスを変更するには、次の構文を使用します。

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     この例では、エイリアス値 ConferenceRoom02 を持つ既存の会議室メールボックスのアカウントを有効にし、パスワードを 9898P@$$W 0rd に設定します。 既存のエイリアス値が ConferenceRoom02@contoso.com アカウントが削除されます。

     ``` PowerShell
     Set-Mailbox -Identity ConferenceRoom02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   構文とパラメーターの詳細については、「[New-Mailbox](/powershell/module/exchange/mailboxes/new-mailbox)」と「[Set-Mailbox](/powershell/module/exchange/mailboxes/set-mailbox)」を参照してください。

3. Exchange Online PowerShell で、会議の操作性を向上させるために、次のように会議室メールボックスの設定を構成します。

   - AutomateProcessing: AutoAccept (会議の開催者は、人の介入なしに会議室の予約決定を直接受け取る)。

   - AddOrganizerToSubject: $false (会議の開催者は、会議出席依頼の件名に追加されません。)

   - DeleteComments: $false (受信した会議出席依頼のメッセージ本文内のテキストを保持します。)

   - DeleteSubject: $false (受信した会議出席依頼の件名を保持します。)

   - RemovePrivateProperty: $false (開催者が送信した元の会議出席依頼のプライベート フラグを指定された値のままにしておきます。)

   - AddAdditionalResponse: $true (AdditionalResponse パラメーターで指定されたテキストが会議出席依頼に追加されます。)

   - AdditionalResponse: "This is a Microsoft Teams Meeting room!" (会議出席依頼に追加するテキスト)。

   この例では、ConferenceRoom01 という名前の会議室メールボックスでこれらの設定を構成します。

   ``` PowerShell
   Set-CalendarProcessing -Identity "ConferenceRoom01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams Meeting room!"
   ```

   構文とパラメーターの詳細については、「[Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing)」を参照してください。

4. Connect MS Online PowerShell に移動して、Active Directory の設定を行います。 `Connect-MsolService`PowerShell コマンドレット。 Active Directory の詳細については、「[Azure ActiveDirectory (MSOnline) 1.0](/powershell/azure/active-directory/overview?view=azureadps-1.0)」を参照してください。

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0) はサポートされていません。

5. 次の構文を使用して、パスワードの有効期限を決して設定します。

   ```PowerShell
   Set-MsolUser -UserPrincipalName <UPN> -PasswordNeverExpires $true
   ```

   <!--
   ```PowerShell
   Set-AzureADUserPassword -UserPrincipalName <Account> -EnforceChangePasswordPolicy $false
   ```  -->

   この例では、アカウントアカウントのパスワードを ConferenceRoom01@contoso.onmicrosoft.com に設定します。

   ```PowerShell
   Set-MsolUser -UserPrincipalName "ConferenceRoom01@contoso.com" -PasswordNeverExpires $true
   ```

   <!-- 
   ```PowerShell
   Set-AzureADUserPassword -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -EnforceChangePasswordPolicy $false
   ``` -->

   次のコマンドを実行して、アカウントの電話番号を設定することもできます。

   ```PowerShell
   Set-MsolUser -UserPrincipalName <UPN> -PhoneNumber <phone number>
   ```

   <!-- 
   ```PowerShell
   Set-AzureADUser -UserPrincipalName <Account> -PhoneNumber "<PhoneNumber>"
   ```  -->

    > [!NOTE]
    > パスワードが [有効期限なし] に設定されていない場合、アカウントが有効期限に達すると、アカウントはデバイスにサインインしなくなりました。 その後、アカウントのパスワードを変更し、会議室でローカルTeams必要があります。 ユーザーは、パスワードの有効期限が切れているTeams会議室で会議に参加できません。

6. リソース アカウントには、有効なライセンスまたはMicrosoft 365ライセンスがOffice 365必要です。または、ExchangeがMicrosoft Teams機能しません。 ライセンスを持っている場合は、リソース アカウントに使用場所を割り当てる必要があります。これにより、アカウントで使用できるライセンス SKU が決されます。 `Get-MsolAccountSku` を使用して、 <!-- Get-AzureADSubscribedSku --> 次のように、Microsoft 365 または Office 365 組織で使用できる SKU の一覧を取得できます。

   ```Powershell
   Get-MsolAccountSku
   ```

   <!--
   ```Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```  -->

   次に、`Set-MsolUserLicense` コマンドレットを使用してライセンスを追加  <!--Set-AzureADUserLicense --> することができます。 この例では、アカウントミーティング ルームライセンスを追加します。

   ```PowerShell
   Set-MsolUser -UserPrincipalName "ConferenceRoom01@contoso.com" -UsageLocation "US"
   Set-MsolUserLicense -UserPrincipalName "ConferenceRoom01@contoso.com" -AddLicenses "Contoso:MEETING_ROOM"
   ```

   <!-- 
   ```Powershell
   Set-AzureADUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -UsageLocation "US"
   Set-AzureADUserLicense -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -AddLicenses "Contoso:MEETING_ROOM"
   ```   -->

   詳細な手順については、「[Office 365 PowerShell を使用してライセンスをユーザー アカウントに割り当てる](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)」を参照してください。

   このアカウントに電話システム機能を追加することもできますが、最初に構成する必要があります。 詳細については[、「電話システムの](../what-is-phone-system-in-office-365.md)詳細」を参照してください。 この例では、PSTN 国内通話プランと国際通話プランを追加します。

   ```PowerShell
   Set-MsolUserLicense -UserPrincipalName ConferenceRoom01@contoso.com -AddLicenses "Contoso:MCOPSTN2"
   ```


## <a name="validate"></a>検証

検証の場合は、任意のクライアント クライアントMicrosoft Teams作成したアカウントにサインインできます。

## <a name="see-also"></a>関連項目

[Microsoft Teams Rooms のアカウントを構成する](rooms-configure-accounts.md)

[Microsoft Teams Rooms を計画する](rooms-plan.md)

[Microsoft Teams Rooms をデプロイする](rooms-deploy.md)

[Microsoft Teams Rooms コンソールを構成する](console.md)

[Microsoft Teams Rooms を管理する](rooms-manage.md)

[Microsoft Teams Rooms ライセンス](rooms-licensing.md)
