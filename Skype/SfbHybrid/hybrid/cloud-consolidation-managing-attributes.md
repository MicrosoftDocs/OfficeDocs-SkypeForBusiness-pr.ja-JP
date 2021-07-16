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
localization_priority: Normal
description: この記事では、オンプレミス環境の使用停止後に属性を管理する方法について説明します。
ms.openlocfilehash: 1c862e8c0055fc2eb40efcc7d26bb9a1166ae550
ms.sourcegitcommit: 405b22cfd94e50d651f4c3f73fb46780cd8a6d06
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458993"
---
# <a name="decide-how-to-manage-attributes-after-decommissioning"></a><span data-ttu-id="f1cdc-103">使用停止後に属性を管理する方法を決定する</span><span class="sxs-lookup"><span data-stu-id="f1cdc-103">Decide how to manage attributes after decommissioning</span></span>

<span data-ttu-id="f1cdc-104">既定では、以前に Skype for Business Server に対して有効にされ、その後クラウドに移動されたすべてのユーザーに、オンプレミスの Active Directory で msRTCSIP 属性が構成されています。</span><span class="sxs-lookup"><span data-stu-id="f1cdc-104">By default, all users that were previously enabled for Skype for Business Server and subsequently moved to the cloud still have msRTCSIP attributes configured in your on-premises Active Directory.</span></span> 

<span data-ttu-id="f1cdc-105">これらの属性、特に sip アドレス (msRTCSIP-PrimaryUserAddress) と電話番号 (msRTCSIP-Line) は、引き続き Azure AD に同期されます。</span><span class="sxs-lookup"><span data-stu-id="f1cdc-105">These attributes, in particular sip address (msRTCSIP-PrimaryUserAddress) and potentially phone number (msRTCSIP-Line), continue to sync into Azure AD.</span></span> <span data-ttu-id="f1cdc-106">msRTCSIP 属性に対して変更が必要な場合は、オンプレミスの Active Directory でこれらの変更を行い、Azure AD に同期する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f1cdc-106">If changes are required to any of the msRTCSIP attributes, these changes must be made in the on-premises Active Directory and then sync'd to Azure AD.</span></span> <span data-ttu-id="f1cdc-107">ただし、Skype for Business Server展開が削除されると、これらの属性Skype for Business Serverツールを使用できません。</span><span class="sxs-lookup"><span data-stu-id="f1cdc-107">However, once the Skype for Business Server deployment has been removed, the Skype for Business Server tools will not be available to manage these attributes.</span></span>

<span data-ttu-id="f1cdc-108">この状況を処理するには、次の 2 つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="f1cdc-108">There are two options available for handling this situation:</span></span>

1. <span data-ttu-id="f1cdc-109">サーバー アカウントに対して有効Skype for Businessユーザーはそのままにし、Active Directory ツールを使用して msRTCSIP 属性を管理します。</span><span class="sxs-lookup"><span data-stu-id="f1cdc-109">Leave users that were enabled for Skype for Business server accounts as is, and manage the msRTCSIP attributes using Active Directory tools.</span></span> <span data-ttu-id="f1cdc-110">これにより、移行されたユーザーのサービスが失われるのを防ぐので、完全な使用停止なしでサーバーを削除 (ワイプなど) することで、Skype for Business Server 展開を簡単に削除できます。</span><span class="sxs-lookup"><span data-stu-id="f1cdc-110">This ensures no loss of service for migrated users, and allows you to easily remove the Skype for Business Server deployment by eliminating (e.g. wiping) the servers, without a full decommissioning.</span></span> <span data-ttu-id="f1cdc-111">ただし、新しくライセンスを取得したユーザーは、オンプレミスの Active Directory にこれらの属性を設定し、オンラインで管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f1cdc-111">However, newly licensed users will not have these attributes populated in your on-premises Active Directory and will need to be managed online.</span></span>

2.  <span data-ttu-id="f1cdc-112">オンプレミスの Active Directory で移行されたユーザーからすべての msRTCSIP 属性をクリアし、オンライン ツールを使用してこれらの属性を管理します。</span><span class="sxs-lookup"><span data-stu-id="f1cdc-112">Clear all msRTCSIP attributes from migrated users in your on-premises Active Directory and manage these attributes using online tools.</span></span> <span data-ttu-id="f1cdc-113">このメソッドを使用すると、既存のユーザーと新しいユーザーに対して一貫した管理アプローチが可能になりますが、オンプレミスの使用停止プロセス中に一時的にサービスが失われる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f1cdc-113">This method allows for a consistent management approach for existing and new users, however it may potentially result in a temporary loss of service during the on-premises decommissioning process.</span></span>


## <a name="method-1---manage-sip-addresses-and-phone-numbers-for-users-in-active-directory"></a><span data-ttu-id="f1cdc-114">方法 1 - Active Directory でユーザーの SIP アドレスと電話番号を管理する</span><span class="sxs-lookup"><span data-stu-id="f1cdc-114">Method 1 - Manage sip addresses and phone numbers for users in Active Directory</span></span>

<span data-ttu-id="f1cdc-115">管理者は、オンプレミス展開が使用停止された後でも、Skype for Business Serverからクラウドに移動されたユーザーを管理できます。</span><span class="sxs-lookup"><span data-stu-id="f1cdc-115">Administrators can manage users who were previously moved from an on-premises Skype for Business Server to the cloud, even after the on-premises deployment is decommissioned.</span></span> 

<span data-ttu-id="f1cdc-116">ユーザーの SIP アドレスまたはユーザーの電話番号 (および sip アドレスまたは電話番号に既にオンプレミスの Active Directory に値が含まれる) を変更する場合は、オンプレミスの Active Directory でこれを行い、値を Azure AD に流す必要があります。</span><span class="sxs-lookup"><span data-stu-id="f1cdc-116">If you want to make changes to a user’s sip address or to a user’s phone number (and the sip address or phone number already has a value in the on-premises Active Directory), you must do this in the on-premises Active Directory and let the value(s) flow up to Azure AD.</span></span> <span data-ttu-id="f1cdc-117">これは、オンプレミスのデータを必要とSkype for Business Server。</span><span class="sxs-lookup"><span data-stu-id="f1cdc-117">This does NOT require on-premises Skype for Business Server.</span></span> <span data-ttu-id="f1cdc-118">代わりに、Active Directory ユーザーとコンピューター MMC スナップイン (以下に示す) を使用するか、PowerShell を使用して、オンプレミスの Active Directory でこれらの属性を直接変更できます。</span><span class="sxs-lookup"><span data-stu-id="f1cdc-118">Rather, you can modify these attributes directly in the on-premises Active Directory, using either the Active Directory Users and Computers MMC snap-in (as shown below), or by using PowerShell.</span></span> <span data-ttu-id="f1cdc-119">MMC スナップインを使用している場合は、ユーザーの [プロパティ] ページを開き、[属性エディター] タブをクリックして、変更する適切な属性を探します。</span><span class="sxs-lookup"><span data-stu-id="f1cdc-119">If you are using the MMC snap-in, open the properties page of the user, click Attribute Editor tab, and find the appropriate attributes to modify:</span></span>

- <span data-ttu-id="f1cdc-120">ユーザーの sip アドレスを変更するには、 を変更します `msRTCSIP-PrimaryUserAddress` 。</span><span class="sxs-lookup"><span data-stu-id="f1cdc-120">To modify a user’s sip address, modify the `msRTCSIP-PrimaryUserAddress`.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f1cdc-121">属性に `ProxyAddresses` sip アドレスが含まれている場合は、その値もベスト プラクティスとして更新します。</span><span class="sxs-lookup"><span data-stu-id="f1cdc-121">If the `ProxyAddresses` attribute contains a sip address, also update that value as a best practice.</span></span> <span data-ttu-id="f1cdc-122">入力されている場合、SIP アドレスは O365 によって無視されます。ただし、他のオンプレミス コンポーネント `ProxyAddresses` `msRTCSIP-PrimaryUserAddress` で使用される場合があります。</span><span class="sxs-lookup"><span data-stu-id="f1cdc-122">Although the sip address in `ProxyAddresses` is ignored by O365 if `msRTCSIP-PrimaryUserAddress` is populated, it may be used by other on-premises components.</span></span>

- <span data-ttu-id="f1cdc-123">ユーザーの電話番号を変更するには、値 `msRTCSIP-Line` *が既に設定されている場合に変更します*。</span><span class="sxs-lookup"><span data-stu-id="f1cdc-123">To modify a user’s phone number, modify `msRTCSIP-Line` *if it already has a value*.</span></span>

  ![Active Directory ユーザーとコンピューター ツール](../media/disable-hybrid-1.png)
  
-  <span data-ttu-id="f1cdc-125">ユーザーが移動前にオンプレミスの値を持っていなかった場合は、Skype for Business Online PowerShell モジュールの `msRTCSIP-Line` `onpremLineUri` [Set-CsUser](/powershell/module/skype/set-csuser?view=skype-ps)コマンドレットの - パラメーターを使用して電話番号を変更できます。</span><span class="sxs-lookup"><span data-stu-id="f1cdc-125">If the user did not originally have a value for `msRTCSIP-Line` on-premises before the move, you can modify the phone number using the -`onpremLineUri` parameter in the [Set-CsUser cmdlet](/powershell/module/skype/set-csuser?view=skype-ps) in the Skype for Business Online PowerShell module.</span></span>

<span data-ttu-id="f1cdc-126">これらの手順は、ハイブリッドを無効にした後に作成された新しいユーザーには必要ありません。また、それらのユーザーはクラウドで直接管理できます。</span><span class="sxs-lookup"><span data-stu-id="f1cdc-126">These steps are not necessary for new users created after you disable hybrid, and those users can be managed directly in the cloud.</span></span> <span data-ttu-id="f1cdc-127">これらのメソッドを組み合わせ、msRTCSIP 属性をオンプレミスの Active Directory に配置した状態にした方が快適な場合は、オンプレミスの Skype for Business サーバーをイメージしSkype for Businessできます。</span><span class="sxs-lookup"><span data-stu-id="f1cdc-127">If you are comfortable using the mix of these method as well as with leaving the msRTCSIP attributes in place in your on-premises Active Directory, you can simply re-image the on-premises Skype for Business servers.</span></span> <span data-ttu-id="f1cdc-128">ただし、すべての msRTCSIP 属性をクリアし、従来のアンインストールを実行する場合は、Skype for Business Server 2 を使用します。</span><span class="sxs-lookup"><span data-stu-id="f1cdc-128">However, if you prefer to clear all msRTCSIP attributes and do a traditional uninstall of Skype for Business Server, then use Method 2.</span></span>


## <a name="method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory"></a><span data-ttu-id="f1cdc-129">方法 2 - Active Directory Skype for Businessオンプレミス ユーザーの属性をクリアする</span><span class="sxs-lookup"><span data-stu-id="f1cdc-129">Method 2 - Clear Skype for Business attributes for all on-premises users in Active Directory</span></span>

<span data-ttu-id="f1cdc-130">このオプションでは、以前にオンプレミスのユーザーからクラウドに移動されたユーザー Skype for Business Server再プロビジョニングが必要なので、追加の作業と適切な計画が必要です。</span><span class="sxs-lookup"><span data-stu-id="f1cdc-130">This option requires additional effort and proper planning because users who were previously moved from an on-premises Skype for Business Server to the cloud are required to be re-provisioned.</span></span> <span data-ttu-id="f1cdc-131">これらのユーザーは、2 つの異なるカテゴリに分類できます 電話システム 電話システム。</span><span class="sxs-lookup"><span data-stu-id="f1cdc-131">These users can be categorized into two different categories: users without Phone System and users with Phone System.</span></span> <span data-ttu-id="f1cdc-132">ユーザーが電話システム、オンプレミスの Active Directory で管理される電話番号をクラウドに移行する一環として、電話サービスが一時的に失われる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f1cdc-132">Users with Phone System will experience a temporary loss of phone service as part of transitioning the phone number from being managed in on-premises Active Directory to the cloud.</span></span> <span data-ttu-id="f1cdc-133">**一括ユーザー操作を開始する前に、ユーザー数の少ないユーザーを含むパイロットを電話システムをお勧めします。**</span><span class="sxs-lookup"><span data-stu-id="f1cdc-133">**It's recommended to perform a pilot involving a small number of users with Phone System prior to start bulk user operations.**</span></span> <span data-ttu-id="f1cdc-134">大規模な展開では、ユーザーは異なるタイム ウィンドウ内の小さなグループで処理できます。</span><span class="sxs-lookup"><span data-stu-id="f1cdc-134">For large deployments users can be processed in smaller groups in different time windows.</span></span> 

> [!NOTE] 
> <span data-ttu-id="f1cdc-135">このプロセスは、一致する sip アドレスと UserPrincipalName を持つユーザーに対して最も簡単です。</span><span class="sxs-lookup"><span data-stu-id="f1cdc-135">This process is simplest for users who have a matching sip address and UserPrincipalName.</span></span> <span data-ttu-id="f1cdc-136">これら 2 つの属性で一致しない値を持つユーザーを持つ組織では、スムーズな移行を行う場合は、以下の点に注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f1cdc-136">For organizations that have users with non-matching values across these two attributes, extra care must be taken as noted below for a smooth transition.</span></span>

> [!NOTE]
> <span data-ttu-id="f1cdc-137">自動応答または通話キュー用にオンプレミスハイブリッド アプリケーション エンドポイントを構成している場合は、これらのエンドポイントを Microsoft 365 に移動してから、Skype for Business Server。</span><span class="sxs-lookup"><span data-stu-id="f1cdc-137">If you have configured on-premises hybrid application endpoints for Auto Attendants or Call Queues, be sure to move these endpoints to Microsoft 365 before decommissioning Skype for Business Server.</span></span>


1. <span data-ttu-id="f1cdc-138">PowerShell コマンドレットが空の結果をSkype for Business次のオンプレミスのコマンドレットを確認します。</span><span class="sxs-lookup"><span data-stu-id="f1cdc-138">Confirm the following on-premises Skype for Business PowerShell cmdlet returns an empty result.</span></span> <span data-ttu-id="f1cdc-139">空の結果は、ユーザーがオンプレミスにいて、ユーザーに移動された、または無効になっているMicrosoft 365意味します。</span><span class="sxs-lookup"><span data-stu-id="f1cdc-139">An empty result means no users are homed on-premises and have either been moved to Microsoft 365 or have been disabled:</span></span>

   ```PowerShell
   Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Select-Object Identity, SipAddress, UserPrincipalName, RegistrarPool
   ```

2. <span data-ttu-id="f1cdc-140">次のオンプレミスの Skype for Business Server PowerShell コマンドレットを実行して、ユーザーの現在の電話番号 (LineUri)、UserPrincipalName、および関連情報を記録し、ユーザー データをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="f1cdc-140">Record users' current phones number (LineUri), UserPrincipalName and related info, by executing the following on-premises Skype for Business Server PowerShell cmdlet to export user data:</span></span>

   ```PowerShell
   Get-CsUser | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path  "c:\backup\SfbUserSettings.csv"
   ```

   > [!Important] 
   > <span data-ttu-id="f1cdc-141">ファイルを開いてSfbUserSettings.csv、すべてのユーザー データが正常にエクスポートされたことを確認する前に。</span><span class="sxs-lookup"><span data-stu-id="f1cdc-141">Before proceeding open SfbUserSettings.csv file and confirm all user data has been successfully exported.</span></span> <span data-ttu-id="f1cdc-142">このファイルのコピーを保持してお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f1cdc-142">It's recommended to keep a copy of this file.</span></span>  <span data-ttu-id="f1cdc-143">ユーザーの処理には、次の手順でこのファイルを使用しない。</span><span class="sxs-lookup"><span data-stu-id="f1cdc-143">Do not use this file in the following steps for processing users.</span></span> 

3. <span data-ttu-id="f1cdc-144">次の手順で使用するユーザーのグループを含むファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="f1cdc-144">Create a file with a group of users to be used in the following steps.</span></span> <span data-ttu-id="f1cdc-145">ユーザーの最初のグループが正常に完了したら、次のユーザー グループに進みます。</span><span class="sxs-lookup"><span data-stu-id="f1cdc-145">After the first group of users has completed successfully, proceed with the next group of users.</span></span> <span data-ttu-id="f1cdc-146">次の例では、ユーザーのグループがアルファベット順に選択されますが、ユーザーの処理方法に一致する条件に基づいてユーザーにフィルターを適用できます。</span><span class="sxs-lookup"><span data-stu-id="f1cdc-146">In the example below, the groups of users are selected alphabetically, but you may filter on users based on criteria that matches how you would like to process the users.</span></span>

   ```PowerShell
   Get-CsUser | where userprincipalname -like "abc*" | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path "c:\data\SfbUsers.csv"
   ```

   > [!Important] 
   > <span data-ttu-id="f1cdc-147">ファイルを開いてSfbUsers.csv、ユーザー データが正常にエクスポートされたことを確認する前に。</span><span class="sxs-lookup"><span data-stu-id="f1cdc-147">Before proceeding open SfbUsers.csv file and confirm user data has been successfully exported.</span></span> <span data-ttu-id="f1cdc-148">後の手順で、このファイルから LineUri (電話番号)、UserPrincipalName、SamAccountName、SipAddress が必要になります。</span><span class="sxs-lookup"><span data-stu-id="f1cdc-148">You will need the LineUri (phone number), UserPrincipalName, SamAccountName, and SipAddress from this file in a later step.</span></span>

4. <span data-ttu-id="f1cdc-149">更新する準備ができている一連のユーザー Skype for Business Server Active Directory から、ユーザーに関連する属性情報を削除します。</span><span class="sxs-lookup"><span data-stu-id="f1cdc-149">Delete the attribute information related to Skype for Business Server from active Directory for the set of users you are ready to update.</span></span>  <span data-ttu-id="f1cdc-150">以下に示すように、このプロセスには 2 つの手順があります。</span><span class="sxs-lookup"><span data-stu-id="f1cdc-150">There are 2 steps to this process, as shown below.</span></span>

   > [!Important] 
   > <span data-ttu-id="f1cdc-151">この手順を実行した後の次の AAD Sync サイクルの後、以前にオンプレミス Skype for Business Server からクラウドに移動された 電話システム を持つユーザーは、手順 8 が正常に完了して手順 9 で確認されるまで、通話を送受信する機能を失います。</span><span class="sxs-lookup"><span data-stu-id="f1cdc-151">After the next AAD Sync cycle after running this step, users with Phone System who were previously moved from an on-premises Skype for Business Server to the cloud will lose the ability to make and receive calls until step 8 is successfully completed and confirmed in step 9.</span></span> <span data-ttu-id="f1cdc-152">また、手順 2 に基いてユーザーの電話番号と関連情報を保存済みである必要があります。</span><span class="sxs-lookup"><span data-stu-id="f1cdc-152">In addition, make sure you have saved user's phone numbers and related information as per step 2, since that information is required for that step.</span></span>

 
   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   Disable-CsUser -Identity $user.SipAddress}
   ```

   <span data-ttu-id="f1cdc-153">次に、同じユーザー セットについて、オンプレミスの Active Directory PowerShell を使用して msRTCSIP-DeploymentLocator の値をクリアします。</span><span class="sxs-lookup"><span data-stu-id="f1cdc-153">Next, for the same set of users, clear the value of msRTCSIP-DeploymentLocator using on-premises Active Directory PowerShell:</span></span>

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   Set-ADUser -Identity $user.SamAccountName -Clear msRTCSIP-DeploymentLocator}
   ```

5. <span data-ttu-id="f1cdc-154">次のオンプレミス Active Directory モジュールを実行して、Windows PowerShell コマンドレットを実行して、オンプレミスの Active Directory proxyAddresses に sip アドレス値を追加します。</span><span class="sxs-lookup"><span data-stu-id="f1cdc-154">Run the following on-premise Active Directory Module for Windows PowerShell cmdlet to add sip address value back to the on-premises Active Directory proxyAddresses.</span></span> <span data-ttu-id="f1cdc-155">これにより、この属性に依存する相互運用性の問題が防止されます。</span><span class="sxs-lookup"><span data-stu-id="f1cdc-155">This will prevent interoperability issues that rely on this attribute.</span></span> 

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

6. <span data-ttu-id="f1cdc-156">実行Azure AD Sync</span><span class="sxs-lookup"><span data-stu-id="f1cdc-156">Run Azure AD Sync</span></span>

   ```PowerShell
   Start-ADSyncSyncCycle -PolicyType Delta
   ```

7. <span data-ttu-id="f1cdc-157">ユーザー プロビジョニングが完了するのを待ちます。</span><span class="sxs-lookup"><span data-stu-id="f1cdc-157">Wait for user provisioning to complete.</span></span> <span data-ttu-id="f1cdc-158">ユーザー プロビジョニングの進行状況を監視するには、次の [オンライン PowerShell] コマンドSkype for Business実行します。</span><span class="sxs-lookup"><span data-stu-id="f1cdc-158">You can monitor user provisioning progress by running the following Skype for Business Online PowerShell command.</span></span> <span data-ttu-id="f1cdc-159">次の手順Skype for Business Online PowerShell コマンドは、プロセスが完了すると、空の結果を返します。</span><span class="sxs-lookup"><span data-stu-id="f1cdc-159">The following Skype for Business Online PowerShell command returns an empty result as soon process is completed.</span></span>

   ```PowerShell
   Get-CsOnlineUser -Filter {Enabled -eq $True -and (MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
   ```

8. <span data-ttu-id="f1cdc-160">[オンライン PowerShell] Skype for Businessを実行して電話番号を割り当て、ユーザーに電話番号を割り当電話システム。</span><span class="sxs-lookup"><span data-stu-id="f1cdc-160">Execute the following Skype for Business Online PowerShell command to assign phone numbers and enable users for Phone System:</span></span>
     
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
   >  <span data-ttu-id="f1cdc-161">引き続き Skype for Businessエンドポイント (Skype クライアントまたはサードパーティの電話) がある場合は、-HostedVoiceMail を $true に設定します。</span><span class="sxs-lookup"><span data-stu-id="f1cdc-161">If you still have Skype for Business endpoints (either Skype clients or 3rd party phones), you will also want to set -HostedVoiceMail to $true.</span></span> <span data-ttu-id="f1cdc-162">組織が音声が有効なユーザー Teamsエンドポイントのみを使用している場合、この設定はユーザーには適用されません。</span><span class="sxs-lookup"><span data-stu-id="f1cdc-162">If your organization is only using Teams endpoints for voice enabled users, this setting is not applicable to your users.</span></span> 

9. <span data-ttu-id="f1cdc-163">機能が正電話システムユーザーを確認します。</span><span class="sxs-lookup"><span data-stu-id="f1cdc-163">Confirm users with Phone System functionality have been provisioned correctly.</span></span> <span data-ttu-id="f1cdc-164">次の手順Skype for Business Online PowerShell コマンドは、プロセスが完了すると、空の結果を返します。</span><span class="sxs-lookup"><span data-stu-id="f1cdc-164">The following Skype for Business Online PowerShell command returns an empty result as soon process is completed.</span></span>

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

10. <span data-ttu-id="f1cdc-165">すべてのユーザーが処理されるまで、手順 3 ~ 9 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="f1cdc-165">Repeat steps 3 through 9 until all users are processed.</span></span>

11. <span data-ttu-id="f1cdc-166">次の 2 つの PowerShell コマンドを実行して、すべてのユーザーが正常に処理されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="f1cdc-166">Confirm that all users have been processed successfully by running the following two PowerShell commands.</span></span>

    <span data-ttu-id="f1cdc-167">オンプレミスの PowerShell Skype for Business Serverを使用します。</span><span class="sxs-lookup"><span data-stu-id="f1cdc-167">On-premises Skype for Business Server on-premises PowerShell command:</span></span>

    ```PowerShell
    Get-CsUser | Select-Object SipAddress, UserPrincipalName
    ``` 
    <span data-ttu-id="f1cdc-168">Skype for Businessオンライン PowerShell コマンド:</span><span class="sxs-lookup"><span data-stu-id="f1cdc-168">Skype for Business Online PowerShell command:</span></span>

    ```PowerShell
    Get-CsOnlineUser -Filter {Enabled -eq $True -and (OnPremHostingProvider -ne $null -or MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
    ``` 
12. <span data-ttu-id="f1cdc-169">方法 2 のすべての手順を完了したら、「ハイブリッド[](decommission-move-on-prem-endpoints.md)アプリケーション エンドポイントをオンプレミスからオンラインに移動する」および「オンプレミス[Skype for Business Server](decommission-remove-on-prem.md)を削除する」を参照して、Skype for Business Server オンプレミス展開を削除する追加の手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f1cdc-169">After you have completed all steps in Method 2, see [Move hybrid application endpoints from on-premises to online](decommission-move-on-prem-endpoints.md) and [Remove your on-premises Skype for Business Server](decommission-remove-on-prem.md) for additional steps to remove your Skype for Business Server on-premises deployment.</span></span>


## <a name="see-also"></a><span data-ttu-id="f1cdc-170">関連項目</span><span class="sxs-lookup"><span data-stu-id="f1cdc-170">See also</span></span>

- [<span data-ttu-id="f1cdc-171">クラウドの統合 :TeamsとSkype for Business</span><span class="sxs-lookup"><span data-stu-id="f1cdc-171">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)

- [<span data-ttu-id="f1cdc-172">オンプレミスの Skype for Business 環境を廃止する</span><span class="sxs-lookup"><span data-stu-id="f1cdc-172">Decommission your on-premises Skype for Business environment</span></span>](decommission-on-prem-overview.md)

