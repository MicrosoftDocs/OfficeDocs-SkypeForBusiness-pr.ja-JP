---
title: ハイブリッドを無効にしてクラウドへの移行を完了する
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
localization_priority: Normal
description: この記事では、Teams と Skype for Business のクラウド統合の一環としてハイブリッドを無効にする詳細な手順について説明します。
ms.openlocfilehash: 36ec3cba2d821cc8554e0fba95108756c83b7b3d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120356"
---
# <a name="disable-hybrid-to-complete-migration-to-the-cloud-overview"></a>ハイブリッドを無効にしてクラウドへの移行を完了する: 概要

すべてのユーザーをオンプレミスからクラウドに移行した後は、オンプレミスの Skype for Business の配置を使用停止にすることができます。 ハードウェアを削除する以外に、ハイブリッドを無効にして、オンプレミス展開を Microsoft 365 または Office 365 から論理的に分離する必要があります。 ハイブリッドを無効にするには、3 つの手順があります。

1. Microsoft 365 または Microsoft 365 または 365 をポイントOffice更新します。

2. Microsoft 365 または 365 組織で共有 SIP アドレス空間 ("スプリット ドメイン" とも呼ばれる) を無効Officeします。

3. オンプレミスで Microsoft 365 または Microsoft 365 または Office無効にします。

次の手順では、Skype for Business Server のオンプレミス展開を Office 365 から論理的に分離し、1 つの単位として一緒に実行する必要があります。 各手順の詳細については、以下の記事で説明します。 完了したら、以下で参照する 2 つの方法のいずれかを使用して、オンプレミスの Skype for Business Deployment を使用停止できます。

> [!Important] 
>この論理的な分離が完了すると、オンプレミス Active Directory の msRTCSIP 属性には値が残り、Azure AD Connect を介して Azure AD に同期されます。 オンプレミス環境を使用停止する方法は、これらの属性をそのままにするか、最初にオンプレミスの Active Directory から削除するかによって異なります。 オンプレミスから移行した後にオンプレミスの msRTCSIP 属性をクリアすると、ユーザーのサービスが失われる可能性があります。 2 つの使用停止の方法の詳細とトレードオフについては、後述します。

## <a name="disable-hybrid-to-complete-migration-to-the-cloud-detailed-steps"></a>ハイブリッドを無効にしてクラウドへの移行を完了する: 詳細な手順

1. *Microsoft 365 または 365 をポイントOffice DNS を更新します。* オンプレミス組織の組織の外部 DNS を更新して、Skype for Business レコードがオンプレミス展開ではなく Microsoft 365 または Office 365 を指す必要があります。 具体的には次のとおりです。

    |レコードの種類|Name|TTL|Value|
    |---|---|---|---|
    |SRV|_sipfederationtls._tcp|3600|100 1 5061 sipfed.online.lync。 <span>com|
    |SRV|_sip._tls|3600|100 1 443 sipdir.online.lync。 <span>com|
    |CNAME| lyncdiscover|   3600|   webdir.online.lync。 <span>com|
    |CNAME| sip|    3600|   sipdir.online.lync。 <span>com|

    さらに、会議またはダイヤルインの CNAME レコード (存在する場合) を削除できます。 最後に、内部ネットワーク内の Skype for Business の DNS レコードを削除する必要があります。

    > [!Note] 
    > まれに、DNS をオンプレミスのポイントから Microsoft 365 または Office 365 に変更すると、他の組織がフェデレーション構成を更新するまで、他の組織とのフェデレーションが停止する場合があります。
    >
    > - 以前のダイレクト フェデレーション モデル (許可パートナー サーバーとも呼ばれる) を使用しているフェデレーション組織は、プロキシ FQDN を削除するために、組織の許可されたドメイン エントリを更新する必要があります。 この従来のフェデレーション モデルは DNS SRV レコードに基づいていないので、組織がクラウドに移行すると、このような構成は古くなる。
    > 
    > - sipfed.online.lync のホスティング プロバイダーが有効になっていないフェデレーション組織。 <span>com は構成を更新して有効にする必要があります。 この状況は、フェデレーション組織が純粋にオンプレミスであり、ハイブリッドテナントまたはオンライン テナントとフェデレーションしたことがない場合にのみ可能です。 このような場合、ホスティング プロバイダーを有効にするまで、これらの組織とのフェデレーションは機能しません。
    >
    > フェデレーション パートナーが直接フェデレーションを使用している可能性がある、またはオンラインまたはハイブリッド組織とフェデレーションしていないと疑われる場合は、クラウドへの移行を完了する準備をしている間に、この情報に関する通信を送信してください。


2.  *Microsoft 365 または 365 組織の共有 sip アドレスOffice無効にします。* 次のコマンドは、Skype for Business Online PowerShell ウィンドウから実行する必要があります。

     ```PowerShell
     Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false
     ```
 
3.  *オンプレミスで Microsoft 365 または Microsoft 365 または Office無効にします。* 以下のコマンドは、オンプレミスの PowerShell ウィンドウから実行する必要があります。

     ```PowerShell
     Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false
     ```

## <a name="managing-attributes-after-moving-users-from-on-premises-to-the-cloud"></a>オンプレミスからクラウドにユーザーを移動した後の属性の管理

既定では、Skype for Business Server で以前に有効にされ、その後クラウドに移動されたすべてのユーザーに、オンプレミスの Active Directory で msRTCSIP 属性が構成されています。 これらの属性、特に sip アドレス (msRTCSIP-PrimaryUserAddress) と電話番号 (msRTCSIP-Line) は、引き続き Azure AD に同期されます。 msRTCSIP 属性に対して変更が必要な場合は、オンプレミスの Active Directory でこれらの変更を行い、Azure AD に同期する必要があります。 ただし、Skype for Business Server 展開が削除されると、Skype for Business Server ツールを使用してこれらの属性を管理することはできません。

この状況を処理するには、次の 2 つのオプションがあります。

1. Skype for Business サーバー アカウントで有効にされたユーザーはそのままにし、Active Directory ツールを使用して msRTCSIP 属性を管理します。 これにより、移行されたユーザーのサービスが失われるのを防ぐので、完全な使用停止なしでサーバーを削除 (ワイプなど) することで、Skype for Business Server の展開を簡単に削除できます。 ただし、新しくライセンスを取得したユーザーは、オンプレミスの Active Directory にこれらの属性を設定し、オンラインで管理する必要があります。

2.  オンプレミスの Active Directory で移行されたユーザーからすべての msRTCSIP 属性をクリアし、オンライン ツールを使用してこれらの属性を管理します。 このメソッドを使用すると、既存のユーザーと新しいユーザーに対して一貫した管理アプローチが可能になりますが、オンプレミスの使用停止プロセス中に一時的にサービスが失われる可能性があります。


### <a name="method-1---manage-sip-addresses-and-phone-numbers-for-users-in-active-directory"></a>方法 1 - Active Directory でユーザーの SIP アドレスと電話番号を管理する

管理者は、オンプレミスの展開が使用停止された後でも、オンプレミスの Skype for Business Server からクラウドに以前に移動されたユーザーを管理できます。 ユーザーの SIP アドレスまたはユーザーの電話番号 (および sip アドレスまたは電話番号に既にオンプレミスの Active Directory に値が含まれる) を変更する場合は、オンプレミスの Active Directory でこれを行い、値を Azure AD に流す必要があります。 これは、オンプレミスの Skype for Business Server を必要としません。 代わりに、Active Directory ユーザーとコンピューター MMC スナップイン (以下に示す) を使用するか、PowerShell を使用して、オンプレミスの Active Directory でこれらの属性を直接変更できます。 MMC スナップインを使用している場合は、ユーザーの [プロパティ] ページを開き、[属性エディター] タブをクリックして、変更する適切な属性を探します。

- ユーザーの sip アドレスを変更するには、 を変更します `msRTCSIP-PrimaryUserAddress` 。 属性に sip `ProxyAddresses` アドレスが含まれている場合は、その値もベスト プラクティスとして更新してください。 入力されている場合、SIP アドレスは O365 によって無視されます。ただし、他のオンプレミス コンポーネント `ProxyAddresses` `msRTCSIP-PrimaryUserAddress` で使用される場合があります。

- ユーザーの電話番号を変更するには、値 `msRTCSIP-Line` *が既に設定されている場合に変更します*。

  ![Active Directory ユーザーとコンピューター ツール](../media/disable-hybrid-1.png)
  
-  ユーザーが移動前にオンプレミスの値を持っていなかった場合は、Skype for Business Online PowerShell モジュールの `msRTCSIP-Line` `onpremLineUri` [Set-CsUser](/powershell/module/skype/set-csuser?view=skype-ps) コマンドレットの - パラメーターを使用して電話番号を変更できます。

これらの手順は、ハイブリッドを無効にした後に作成された新しいユーザーには必要ありません。また、それらのユーザーはクラウドで直接管理できます。 これらのメソッドを組み合わせ、msRTCSIP 属性をオンプレミスの Active Directory に置き去りにする場合は、オンプレミスの Skype for Business サーバーを簡単に再イメージできます。 ただし、すべての msRTCSIP 属性をクリアし、Skype for Business Server の従来のアンインストールを行う場合は、方法 2 を使用します。


### <a name="method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory"></a>方法 2 - Active Directory のすべてのオンプレミス ユーザーの Skype for Business 属性をクリアする

このオプションでは、オンプレミスの Skype for Business Server からクラウドに移動したユーザーを再プロビジョニングする必要があるため、追加の作業と適切な計画が必要です。 これらのユーザーは、電話システムのないユーザーと電話システムを持つユーザーの 2 つの異なるカテゴリに分類できます。 電話システムを使用しているユーザーは、オンプレミスの Active Directory で管理されている電話番号からクラウドへの移行の一環として、電話サービスが一時的に失われる可能性があります。 **一括ユーザー操作を開始する前に、電話システムを使用するユーザーの数が少ないパイロットを実行してください。** 大規模な展開では、ユーザーは異なるタイム ウィンドウ内の小さなグループで処理できます。 

> [!NOTE]
> このプロセスは、一致する sip アドレスと UserPrincipalName を持つユーザーに対して最も簡単です。 これら 2 つの属性で一致しない値を持つユーザーを持つ組織では、スムーズな移行を行う場合は、以下の点に注意する必要があります。 


1. 次のオンプレミスの Skype for Business PowerShell コマンドレットが空の結果を返します。 空の結果は、ユーザーがオンプレミスにいて、365 から 365 に移動Office無効になっている場合を意味します。

   ```PowerShell
   Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Select-Object Identity, SipAddress, UserPrincipalName, RegistrarPool
   ```

2. 次のオンプレミスの Skype for Business Server PowerShell コマンドレットを実行して、ユーザーの現在の電話番号 (LineUri)、UserPrincipalName、および関連情報を記録し、ユーザー データをエクスポートします。

   ```PowerShell
   Get-CsUser | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path  "c:\backup\SfbUserSettings.csv"
   ```

   > [!Important] 
   > ファイルを開いてSfbUserSettings.csv、すべてのユーザー データが正常にエクスポートされたことを確認する前に。 このファイルのコピーを保持してお勧めします。  ユーザーの処理には、次の手順でこのファイルを使用しない。 

3. 次の手順で使用するユーザーのグループを含むファイルを作成します。 ユーザーの最初のグループが正常に完了したら、次のユーザー グループに進みます。 次の例では、ユーザーのグループがアルファベット順に選択されますが、ユーザーの処理方法に一致する条件に基づいてユーザーにフィルターを適用できます。

   ```PowerShell
   Get-CsUser | where userprincipalname -like "abc*" | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path "c:\data\SfbUsers.csv"
   ```

   > [!Important] 
   > ファイルを開いてSfbUsers.csv、ユーザー データが正常にエクスポートされたことを確認する前に。 後の手順で、このファイルから LineUri (電話番号)、UserPrincipalName、SamAccountName、SipAddress が必要になります。

4. 更新する準備ができている一連のユーザーのアクティブ ディレクトリから Skype for Business Server に関連する属性情報を削除します。  以下に示すように、このプロセスには 2 つの手順があります。

   > [!Important] 
   > この手順を実行した後の次の AAD 同期サイクルの後、以前にオンプレミスの Skype for Business Server からクラウドに移動された電話システムを持つユーザーは、手順 8 が正常に完了して手順 9 で確認されるまで、通話を送受信する機能を失います。 また、手順 2 に基いてユーザーの電話番号と関連情報を保存済みである必要があります。

 
   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   Disable-CsUser -Identity $user.SipAddress}
   ```

   次に、同じユーザー セットについて、オンプレミスの Active Directory PowerShell を使用して msRTCSIP-DeploymentLocator の値をクリアします。

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   Set-ADUser -Identity $user.SamAccountName -Clear msRTCSIP-DeploymentLocator}
   ```

5. 次のオンプレミスの Skype for Business PowerShell コマンドレットを実行して、オンプレミスの Active Directory proxyAddresses に sip アドレス値を追加します。 これにより、この属性に依存する相互運用性の問題が防止されます。 

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

6. Azure AD同期を実行する

   ```PowerShell
   Start-ADSyncSyncCycle -PolicyType Delta
   ```

7. ユーザー プロビジョニングが完了するのを待ちます。 次の Skype for Business Online PowerShell コマンドを実行して、ユーザー プロビジョニングの進行状況を監視できます。 次の Skype for Business Online PowerShell コマンドは、プロセスが完了すると、空の結果を返します。

   ```PowerShell
   Get-CsOnlineUser -Filter {Enabled -eq $True -and (MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
   ```

8. 次の Skype for Business Online PowerShell コマンドを実行して電話番号を割り当て、電話システムのユーザーを有効にする。
     
   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   if($user.LineUri)
        {
                Set-CsUser -Identity $user.SipAddress -OnPremLineURI $user.LineUri -EnterpriseVoiceEnabled $True
        }
   }
    ```

   > [!Note]
   >  Skype for Business エンドポイント (Skype クライアントまたはサードパーティ製電話) がまだ存在する場合は、-HostedVoiceMail を $true に設定します。 組織で音声が有効なユーザーに Teams エンドポイントのみを使用している場合、この設定はユーザーには適用されません。 

9. 電話システム機能を持つユーザーが正しくプロビジョニングされていることを確認します。 次の Skype for Business Online PowerShell コマンドは、プロセスが完了すると、空の結果を返します。

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

    オンプレミスの Skype for Business Server オンプレミス PowerShell コマンド:

    ```PowerShell
    Get-CsUser | Select-Object SipAddress, UserPrincipalName
    ``` 
    Skype for Business Online PowerShell コマンド:

    ```PowerShell
    Get-CsOnlineUser -Filter {Enabled -eq $True -and (OnPremHostingProvider -ne $null -or MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
    ``` 


## <a name="see-also"></a>関連項目

[Teams と Skype for Business のクラウド統合](cloud-consolidation.md)