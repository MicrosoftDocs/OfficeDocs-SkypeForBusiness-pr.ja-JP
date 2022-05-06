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
ms.openlocfilehash: b838b965430a007fa74320d7dbebdcf7ee36c3a9
ms.sourcegitcommit: 140c34f20f9cd48d7180ff03fddd60f5d1d3459f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2022
ms.locfileid: "65249019"
---
# <a name="decide-how-to-manage-attributes-after-decommissioning"></a>使用停止後に属性を管理する方法を決定する

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]


既定では、Skype for Business Serverを有効にしてからクラウドに移動したすべてのユーザーには、オンプレミスの Active Directoryで msRTCSIP 属性が構成されています。 

これらの属性 (特に sip アドレス (msRTCSIP-PrimaryUserAddress) と電話番号 (msRTCSIP-Line) は引き続きAzure ADに同期されます。 msRTCSIP 属性のいずれかに変更が必要な場合は、これらの変更をオンプレミスの Active Directoryで行い、Azure ADに同期する必要があります。 ただし、Skype for Business Serverデプロイが削除されると、Skype for Business Server ツールはこれらの属性を管理できなくなります。

この状況を処理するには、次の 2 つのオプションを使用できます。

1. Skype for Business サーバー アカウントに対して有効にされたユーザーはそのままにして、Active Directory ツールを使用して msRTCSIP 属性を管理します。 この方法により、移行されたユーザーのサービスが失われなくなり、完全な使用停止なしでサーバーを削除 (ワイプなど) することで、Skype for Business Server展開を削除できます。 ただし、新しくライセンスを取得したユーザーは、オンプレミスの Active Directoryにこれらの属性を設定せず、オンラインで管理する必要があります。

2.  オンプレミスの Active Directory内の移行されたユーザーからすべての msRTCSIP 属性をクリアし、オンライン ツールを使用してこれらの属性を管理します。 このメソッドを使用すると、既存のユーザーと新しいユーザーに対して一貫した管理方法を使用できます。 ただし、オンプレミスの使用停止プロセス中にサービスが一時的に失われる可能性があります。


## <a name="method-1---manage-sip-addresses-and-phone-numbers-for-users-in-active-directory"></a>方法 1 - Active Directory でユーザーの sip アドレスと電話番号を管理する

管理者は、オンプレミスのデプロイが使用停止になった後でも、オンプレミスのSkype for Business Serverからクラウドに移動されたユーザーを管理できます。 

ユーザーの sip アドレスまたはユーザーの電話番号 (および sip アドレスまたは電話番号が既にオンプレミスの Active Directoryに値を持つ) に変更を加える場合は、オンプレミスの Active Directoryで変更を行い、値を最大Azure ADまでフローさせる必要があります。 このメソッドでは、オンプレミスのSkype for Business Serverは必要ありません。 代わりに、オンプレミスの Active Directoryで直接、Active Directory ユーザーとコンピューター MMC スナップイン (以下に示すように) を使用するか、PowerShell を使用して、これらの属性を変更できます。 MMC スナップインを使用している場合は、ユーザーの [プロパティ] ページを開き、[属性エディター] タブをクリックして、変更する適切な属性を見つけます。

- ユーザーの sip アドレスを変更 `msRTCSIP-PrimaryUserAddress`するには、.

    > [!NOTE]
    > 属性に `ProxyAddresses` SIP アドレスが含まれている場合は、ベスト プラクティスとしてその値も更新します。 入力されている場合`msRTCSIP-PrimaryUserAddress`、O365 では SIP アドレス`ProxyAddresses`は無視されますが、他のオンプレミス コンポーネントで使用される場合があります。

- ユーザーの電話番号を変更するには、*値が既にあるかどうかを* 変更`msRTCSIP-Line`します。

  ![Active Directory ユーザーとコンピューター ツール。](../media/disable-hybrid-1.png)


- ユーザーが移動前にオンプレミスの値`msRTCSIP-Line`を持っていなかった場合は、Teams PowerShell モジュールの [Set-CsPhoneNumberAssignment コマンドレット](/powershell/module/teams/set-csphonenumberassignment)のパラメーターを使用して`-PhoneNumber`電話番号を変更できます。

これらの手順は、ハイブリッドを無効にした後に作成された新しいユーザーには必要ありません。これらのユーザーはクラウドで直接管理できます。 これらの方法を組み合わせて使用し、msRTCSIP 属性をオンプレミスの Active Directoryに配置したままにしておいても問題ない場合は、オンプレミスのSkype for Business サーバーを再イメージ化できます。 ただし、すべての msRTCSIP 属性をクリアし、Skype for Business Serverの従来のアンインストールを実行する場合は、方法 2 を使用します。


## <a name="method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory"></a>方法 2 - Active Directory 内のすべてのオンプレミス ユーザーのSkype for Business属性をクリアする

このオプションでは、オンプレミスのSkype for Business Serverからクラウドに移行したユーザーを再プロビジョニングする必要があるため、より多くの労力と適切な計画が必要です。 これらのユーザーは、電話システムのないユーザーと電話システムを持つユーザーの 2 つの異なるカテゴリに分類できます。 電話システムを持つユーザーは、電話番号をクラウドにオンプレミスの Active Directoryで管理から移行する一環として、電話サービスが一時的に失われます。 **一括ユーザー操作を開始する前に、電話システムを持つ少数のユーザーを含むパイロットを実行することをお勧めします。** 大規模なデプロイの場合、ユーザーは異なる時間枠内の小さいグループで処理できます。 

> [!NOTE] 
> このプロセスは、一致する sip アドレスと UserPrincipalName を持つユーザーにとって最も簡単です。 これら 2 つの属性で一致しない値を持つユーザーがいる組織の場合は、スムーズな移行のために、以下に示すように注意する必要があります。

> [!NOTE]
> 自動応答または通話キュー用にオンプレミスのハイブリッド アプリケーション エンドポイントを構成している場合は、Skype for Business Serverを使用停止する前に、これらのエンドポイントをMicrosoft 365に移動してください。 詳細については、「 [オンプレミス環境を使用停止する前にハイブリッド アプリケーション エンドポイントを移行する](decommission-move-on-prem-endpoints.md)」を参照してください。  


1. PowerShell コマンドレットが空の結果を返すSkype for Business、次のオンプレミスを確認します。 空の結果は、ユーザーがオンプレミスに所属せず、Microsoft 365に移動されたか、無効になっていることを意味します。

   ```PowerShell
   Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Select-Object Identity, SipAddress, UserPrincipalName, RegistrarPool
   ```

2. 次のオンプレミス Skype for Business Server PowerShell コマンドレットを実行してユーザー データをエクスポートすることで、ユーザーの現在の電話番号 (LineUri)、UserPrincipalName、関連情報を記録します。

   ```PowerShell
   Get-CsUser | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path  "c:\backup\SfbUserSettings.csv"
   ```

   > [!Important] 
   > ファイルSfbUserSettings.csv開く前に、すべてのユーザー データが正常にエクスポートされたことを確認します。 このファイルのコピーを保持することをお勧めします。  次の手順では、ユーザーを処理するためにこのファイルを使用しないでください。 

3. 次の手順で使用するユーザーのグループを含むファイルを作成します。 最初のユーザー グループが正常に完了したら、次のユーザー グループに進みます。 次の例では、ユーザーのグループがアルファベット順に選択されています。 ユーザーを処理する方法に一致する条件に基づいて、ユーザーをフィルター処理できます。

   ```PowerShell
   Get-CsUser | where userprincipalname -like "abc*" | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path "c:\data\SfbUsers.csv"
   ```

   > [!Important] 
   > 続行する前SfbUsers.csvファイルを開き、ユーザー データが正常にエクスポートされたことを確認します。 後の手順で、このファイルから LineUri (電話番号)、UserPrincipalName、SamAccountName、SipAddress が必要になります。

4. 更新する準備ができている一連のユーザーの active Directory から、Skype for Business Serverに関連する属性情報を削除します。  次に示すように、このプロセスには 2 つの手順があります。

   > [!Important] 
   > この手順を実行した後の次のAAD Sync サイクルの後、オンプレミスのSkype for Business Serverからクラウドに移行された電話システムを持つユーザーは、手順 8 が正常に完了し、手順 9 で確認されるまで、通話の発信と受信を行う機能が失われます。 さらに、手順 2 に従ってユーザーの電話番号と関連情報が保存されていることを確認してください。これは、その手順に必要な情報であるためです。

 
   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   Disable-CsUser -Identity $user.SipAddress}
   ```

   次に、同じ一連のユーザーに対して、オンプレミスの Active Directory PowerShell を使用して msRTCSIP-DeploymentLocator の値をクリアします。

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   Set-ADUser -Identity $user.SamAccountName -Clear msRTCSIP-DeploymentLocator}
   ```

5. オンプレミスの Active Directory proxyAddresses に sip アドレス値を追加するには、次の オンプレミスの Active Directory Module for Windows PowerShell コマンドレットを実行します。 このアクションは、この属性に依存する相互運用性の問題を防ぎます。 

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

6. Azure AD Syncを実行する

   ```PowerShell
   Start-ADSyncSyncCycle -PolicyType Delta
   ```

7. ユーザー プロビジョニングが完了するまで待ちます。 次のTeams PowerShell コマンドを実行して、ユーザー プロビジョニングの進行状況を監視できます。 次のTeams PowerShell コマンドは、プロセスが完了するとすぐに空の結果を返します。

   ```PowerShell
   Get-CsOnlineUser -Filter {IsSipEnabled -eq $True} | Where UserValidationErrors -ne $null | Select SipAddress,InterpretedUserType,UserValidationErrors
   ```

8. 電話番号を割り当て、電話システムのユーザーを有効にするには、次のTeams PowerShell コマンドを実行します。


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
   >  Skype for Business エンドポイント (Skype クライアントまたはサード パーティ製の電話) が残っている場合は、-HostedVoiceMail を $true に設定することもできます。 組織が音声対応ユーザーに対してのみ Teams エンドポイントを使用している場合、この設定はユーザーには適用されません。 

9. 電話システム機能を持つユーザーが正しくプロビジョニングされていることを確認します。 次のTeams PowerShell コマンドは、プロセスが完了するとすぐに空の結果を返します。

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers)
   {
   if($user.LineUri)
        {
                $u=Get-CsOnlineUser -Identity $user.SipAddress
                if ($u.LineURI -ne $user.LineUri -or $u.EnterpriseVoiceEnabled -ne $true)
                {
                Get-CsOnlineUser -Identity $user.SipAddress | fl SipAddress, InterpretedUserType, OnPremLineURI, LineURI, EnterpriseVoiceEnabled
                }
        }
   }
   ``` 

10. すべてのユーザーが処理されるまで、手順 3 ~ 9 を繰り返します。

11. 次の 2 つの PowerShell コマンドを実行して、すべてのユーザーが正常に処理されたことを確認します。

    オンプレミス Skype for Business Serverオンプレミスの PowerShell コマンド:

    ```PowerShell
    Get-CsUser | Select-Object SipAddress, UserPrincipalName
    ``` 

    PowerShell コマンドをTeamsします。

    ```PowerShell
    Get-CsOnlineUser -Filter {IsSipEnabled -eq $True} | where {UserValidationErrors -ne $null} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, UserValidationErrors
    ``` 

12. 方法 2 のすべての手順を完了したら、「[ハイブリッド アプリケーション エンドポイントをオンプレミスからオンラインに移動する](decommission-move-on-prem-endpoints.md)」と「[オンプレミスのSkype for Business Serverを削除](decommission-remove-on-prem.md)する」を参照して、Skype for Business Serverのオンプレミス展開を削除する追加の手順を説明します。


## <a name="see-also"></a>関連項目

- [TeamsとSkype for Businessのクラウド統合](cloud-consolidation.md)

- [オンプレミスの Skype for Business 環境を廃止する](decommission-on-prem-overview.md)

