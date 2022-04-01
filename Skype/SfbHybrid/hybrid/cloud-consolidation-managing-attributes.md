---
title: 使用停止後に属性を管理する方法を決定する
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.prod: skype-for-business-itpro
search.appverid: MET150
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
audience: ITPro
f1.keywords:
- NOCSH
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
description: この記事では、オンプレミス環境の使用停止後に属性を管理する方法について説明します。
ms.openlocfilehash: 2186a3e3c3c1858a9ae071932d5bf4f6d2c72c1c
ms.sourcegitcommit: 2388838163812eeabcbd5331aaf680b79da3ccba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/31/2022
ms.locfileid: "64592902"
---
# <a name="decide-how-to-manage-attributes-after-decommissioning"></a>使用停止後に属性を管理する方法を決定する

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]


既定では、クラウドに対して有効Skype for Business Serverし、クラウドに移動したユーザーには、引き続き msRTCSIP 属性が構成オンプレミスの Active Directory。 

これらの属性、特に sip アドレス (msRTCSIP-PrimaryUserAddress) と電話番号 (msRTCSIP-Line) は、引き続き Azure AD。 msRTCSIP 属性に対して変更が必要な場合は、これらの変更を オンプレミスの Active Directory で行い、同期して Azure AD。 ただし、Skype for Business Server展開が削除されると、Skype for Business Serverツールを使用してこれらの属性を管理することはできません。

この状況を処理するには、次の 2 つのオプションがあります。

1. サーバー アカウントに対して有効Skype for Businessユーザーはそのままにし、Active Directory ツールを使用して msRTCSIP 属性を管理します。 この方法では、移行されたユーザーのサービスが失われるのを防ぐと、サーバーを完全に使用停止せずにサーバーを削除 (ワイプなど) することで、Skype for Business Server 展開を削除できます。 ただし、新しくライセンスを取得したユーザーには、これらの属性がオンプレミスの Active Directoryされ、オンラインで管理する必要があります。

2.  移行されたユーザーからすべての msRTCSIP 属性を削除し、オンプレミスの Active Directoryツールを使用してこれらの属性を管理します。 このメソッドを使用すると、既存のユーザーと新しいユーザーに対して一貫した管理方法を使用できます。 ただし、オンプレミスの使用停止プロセス中にサービスが一時的に失われる可能性があります。


## <a name="method-1---manage-sip-addresses-and-phone-numbers-for-users-in-active-directory"></a>方法 1 - Active Directory でユーザーの SIP アドレスと電話番号を管理する

管理者は、オンプレミス展開が使用停止された後でも、Skype for Business Serverからクラウドに移動されたユーザーを管理できます。 

ユーザーの sip アドレスまたはユーザーの電話番号 (および sip アドレスまたは電話番号に既に オンプレミスの Active Directory の値が設定されている) を変更する場合は、オンプレミスの Active Directory に変更を加え、値を Azure AD まで流す必要があります。 このメソッドでは、オンプレミスのデータを必要とSkype for Business Server。 代わりに、オンプレミスの Active Directory でこれらの属性を直接変更するか、Active Directory ユーザーとコンピューター MMC スナップイン (以下に示すように) を使用するか、PowerShell を使用して変更できます。 MMC スナップインを使用している場合は、ユーザーの [プロパティ] ページを開き、[属性エディター] タブをクリックして、変更する適切な属性を探します。

- ユーザーの sip アドレスを変更するには、 を変更します `msRTCSIP-PrimaryUserAddress`。

    > [!NOTE]
    > 属性に `ProxyAddresses` sip アドレスが含まれている場合は、その値もベスト プラクティスとして更新します。 入力されている場合、 `ProxyAddresses` SIP アドレスは O365 `msRTCSIP-PrimaryUserAddress` によって無視されます。ただし、他のオンプレミス コンポーネントで使用される場合があります。

- ユーザーの電話番号を変更するには、値 `msRTCSIP-Line`が *既に設定されている場合は変更します*。

  ![Active Directory ユーザーとコンピューター ツール。](../media/disable-hybrid-1.png)


- `msRTCSIP-Line` `-PhoneNumber`ユーザーが移動前にオンプレミスの値を持っていなかった場合は、Teams PowerShell モジュールの [Set-CsPhoneNumberAssignment](/powershell/module/teams/set-csphonenumberassignment) コマンドレットのパラメーターを使用して電話番号を変更できます。

これらの手順は、ハイブリッドを無効にした後に作成された新しいユーザーには必要ありません。また、それらのユーザーはクラウドで直接管理できます。 これらのメソッドを組み合わせ、msRTCSIP 属性を オンプレミスの Active Directory に置き去りにした方が良い場合は、オンプレミスの Skype for Business サーバーを再イメージできます。 ただし、すべての msRTCSIP 属性をクリアし、従来のアンインストールを実行する場合は、Skype for Business Server 2 を使用します。


## <a name="method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory"></a>方法 2 - Active Directory Skype for Businessオンプレミス ユーザーの属性をクリアする

このオプションでは、オンプレミスのユーザーからクラウドに移動されたユーザー Skype for Business Server再プロビジョニングする必要があるため、より多くの労力と適切な計画が必要です。 これらのユーザーは、2 つの異なるカテゴリに分類できます 電話システム 電話システム。 ユーザーが電話システム、電話番号をクラウドに移行する一環として、電話サービスが一時的に失われるオンプレミスの Active Directory発生します。 **一括ユーザー操作を開始する前に、ユーザー数の少ないユーザーを含むパイロットを電話システムをお勧めします。** 大規模な展開では、ユーザーは異なるタイム ウィンドウ内の小さなグループで処理できます。 

> [!NOTE] 
> このプロセスは、一致する sip アドレスと UserPrincipalName を持つユーザーに対して最も簡単です。 これら 2 つの属性で一致しない値を持つユーザーを持つ組織では、スムーズな移行を行う場合は、以下の点に注意する必要があります。

> [!NOTE]
> 自動応答または通話キュー用にオンプレミスハイブリッド アプリケーション エンドポイントを構成している場合は、これらのエンドポイントを Microsoft 365 に移動してから、Skype for Business Server。 詳細については、「オンプレミス環境を使用停止する前にハイブリッド アプリケーション エンドポイントを移行する [」を参照してください](decommission-move-on-prem-endpoints.md)。  


1. PowerShell コマンドレットが空の結果をSkype for Business次のオンプレミスのコマンドレットを確認します。 空の結果は、ユーザーがオンプレミスにいて、ユーザーに移動された、または無効になっているMicrosoft 365意味します。

   ```PowerShell
   Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Select-Object Identity, SipAddress, UserPrincipalName, RegistrarPool
   ```

2. 次のオンプレミスの Skype for Business Server PowerShell コマンドレットを実行して、ユーザーの現在の電話番号 (LineUri)、UserPrincipalName、および関連情報を記録し、ユーザー データをエクスポートします。

   ```PowerShell
   Get-CsUser | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path  "c:\backup\SfbUserSettings.csv"
   ```

   > [!Important] 
   > ファイルを開いてSfbUserSettings.csv、すべてのユーザー データが正常にエクスポートされたことを確認する前に。 このファイルのコピーを保持してお勧めします。  ユーザーの処理には、次の手順でこのファイルを使用しない。 

3. 次の手順で使用するユーザーのグループを含むファイルを作成します。 ユーザーの最初のグループが正常に完了したら、次のユーザー グループに進みます。 次の例では、ユーザーのグループがアルファベット順に選択されています。 ユーザーの処理方法に一致する条件に基づいて、ユーザーにフィルターを適用できます。

   ```PowerShell
   Get-CsUser | where userprincipalname -like "abc*" | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path "c:\data\SfbUsers.csv"
   ```

   > [!Important] 
   > ファイルを開いてSfbUsers.csv、ユーザー データが正常にエクスポートされたことを確認する前に。 後の手順で、このファイルから LineUri (電話番号)、UserPrincipalName、SamAccountName、SipAddress が必要になります。

4. 更新する準備ができているユーザー Skype for Business Server、active Directory からユーザーに関連する属性情報を削除します。  以下に示すように、このプロセスには 2 つの手順があります。

   > [!Important] 
   > この手順を実行した後の次の AAD Sync サイクルの後、オンプレミス Skype for Business Server からクラウドに移動された 電話システム を持つユーザーは、手順 8 が正常に完了し、手順 9 で確認されるまで、通話を送受信する機能を失います。 また、手順 2 に基いてユーザーの電話番号と関連情報を保存済みである必要があります。

 
   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   Disable-CsUser -Identity $user.SipAddress}
   ```

   次に、同じ一連のユーザーに対して、PowerShell を使用して msRTCSIP-DeploymentLocator の値オンプレミスの Active Directoryします。

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   Set-ADUser -Identity $user.SamAccountName -Clear msRTCSIP-DeploymentLocator}
   ```

5. sip アドレスの値を proxyAddresses にオンプレミスの Active Directoryするには、次の オンプレミスの Active Directory モジュールを実行Windows PowerShellします。 このアクションは、この属性に依存する相互運用性の問題を防止します。 

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
     $userUpn=$user.UserPrincipalName
     $userSip=$user.SipAddress
     $proxies=Get-ADUser -Filter "UserPrincipalName -eq '$userUpn'" -properties * | Select-Object @{Name="proxyAddresses";Expression={$_.proxyAddresses}}
     if(($null -eq $proxies) -or ($proxies.proxyAddresses -NotContains $userSip))
     {
             Get-ADUser -Filter "UserPrincipalName -eq '$userUpn'" | Set-ADUser -Add @{"proxyAddresses"=$user.SipAddress}
     }
   }
   ```

6. 実行Azure AD Sync

   ```PowerShell
   Start-ADSyncSyncCycle -PolicyType Delta
   ```

7. ユーザー プロビジョニングが完了するのを待ちます。 PowerShell コマンドで次のコマンドを実行して、ユーザー のプロビジョニングTeams監視できます。 次の手順Teams PowerShell コマンドは、プロセスが完了すると、空の結果を返します。

   ```PowerShell
   Get-CsOnlineUser -Filter {Enabled -eq $True -and (UserValidationErrors -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
   ```

8. 電話番号を割り当て、ユーザーの電話番号を有効にするには電話システム PowerShell コマンドTeams実行します。


   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   if($user.LineUri)
        {
             Set-CsPhoneNumberAssignment -Identity $user.SipAddress -PhoneNumber $user.LineUri.Replace("tel:","") -PhoneNumberType DirectRouting
        }
   }
   ```

   > [!Note]
   >  引き続き Skype for Business エンドポイント (Skype クライアントまたはサードパーティの電話) がある場合は、-HostedVoiceMail を $true に設定します。 組織が音声が有効なユーザー Teamsエンドポイントのみを使用している場合、この設定はユーザーには適用されません。 

9. 機能が正電話システムユーザーを確認します。 次の手順Teams PowerShell コマンドは、プロセスが完了すると、空の結果を返します。

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers)
   {
   if($user.LineUri)
        {
                $u=Get-CsOnlineUser -Identity $user.SipAddress
                if ($u.LineURI -ne $user.LineUri -or $u.EnterpriseVoiceEnabled -ne $true)
                {
                Get-CsOnlineUser -Identity $user.SipAddress | fl SipAddress, InterpretedUserType, OnPremLineURI, LineURI, EnterpriseVoiceEnabled, HostedVoicemail
                }
        }
   }
   ``` 

10. すべてのユーザーが処理されるまで、手順 3 ~ 9 を繰り返します。

11. 次の 2 つの PowerShell コマンドを実行して、すべてのユーザーが正常に処理されたことを確認します。

    オンプレミスの PowerShell Skype for Business Server次のコマンドを実行します。

    ```PowerShell
    Get-CsUser | Select-Object SipAddress, UserPrincipalName
    ``` 

    Teams PowerShell コマンド:

    ```PowerShell
    Get-CsOnlineUser -Filter {Enabled -eq $True -and (OnPremHostingProvider -ne $null -or MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
    ``` 

12. 方法 2 のすべての手順を完了したら、「ハイブリッド アプリケーション エンドポイントをオンプレミス[](decommission-move-on-prem-endpoints.md)からオンラインに移動する」および「オンプレミス [Skype for Business Server](decommission-remove-on-prem.md) を削除する」を参照して、Skype for Business Server オンプレミス展開を削除する追加の手順を参照してください。


## <a name="see-also"></a>関連項目

- [クラウドの統合 :TeamsとSkype for Business](cloud-consolidation.md)

- [オンプレミスの Skype for Business 環境を廃止する](decommission-on-prem-overview.md)

