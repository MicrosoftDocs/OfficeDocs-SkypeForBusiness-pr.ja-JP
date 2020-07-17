---
title: チームダイヤルパッドの構成
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
description: ユーザーが公衆交換電話網 (PSTN) 機能にアクセスできるように、Teams クライアントでダイヤルパッドを構成する方法について説明します。
ms.openlocfilehash: 44fcbb766cadaa4b31aa065fae80fdcd48c5453f
ms.sourcegitcommit: a94a267c421a78587b0dbbea5fa167aad2882e9b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "45012418"
---
# <a name="dial-pad-configuration"></a><span data-ttu-id="2f89d-103">ダイヤルパッドの構成</span><span class="sxs-lookup"><span data-stu-id="2f89d-103">Dial pad configuration</span></span>

<span data-ttu-id="2f89d-104">チームクライアントでは、ダイヤルパッドを使って、ユーザーが公衆交換電話網 (PSTN) 機能にアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="2f89d-104">In the Teams client, the dial pad enables users to access Public Switched Telephone Network (PSTN) functionality.</span></span> <span data-ttu-id="2f89d-105">ダイヤルパッドは、電話システムのライセンスを持っているユーザーが適切に構成されている場合に利用できます。</span><span class="sxs-lookup"><span data-stu-id="2f89d-105">The dial pad is available for users with a Phone System license, provided they are configured properly.</span></span> <span data-ttu-id="2f89d-106">ダイヤルパッドを表示するには、次の条件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f89d-106">The following criteria are all required for the dial pad to show:</span></span>

- <span data-ttu-id="2f89d-107">ユーザーに有効な電話システム ("MCOEV") ライセンスがある</span><span class="sxs-lookup"><span data-stu-id="2f89d-107">User has an enabled Phone System (“MCOEV”) license</span></span>
- <span data-ttu-id="2f89d-108">ユーザーは Microsoft 通話プランを持っているか、直接ルーティングが有効になっています</span><span class="sxs-lookup"><span data-stu-id="2f89d-108">User has Microsoft Calling Plan or is enabled for Direct Routing</span></span>
- <span data-ttu-id="2f89d-109">ユーザーがエンタープライズ音声を有効にしている</span><span class="sxs-lookup"><span data-stu-id="2f89d-109">User has Enterprise Voice enabled</span></span>
- <span data-ttu-id="2f89d-110">ユーザーは、オンプレミスの Skype for Business ではなく、ホームになっています</span><span class="sxs-lookup"><span data-stu-id="2f89d-110">User is homed online and not in Skype for Business on premises</span></span>
- <span data-ttu-id="2f89d-111">ユーザーがチーム呼び出しポリシーを有効にしている</span><span class="sxs-lookup"><span data-stu-id="2f89d-111">User has Teams Calling Policy enabled</span></span>

<span data-ttu-id="2f89d-112">以下のセクションでは、PowerShell を使用して条件を確認する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2f89d-112">The following sections describe how to use PowerShell to check the criteria.</span></span> <span data-ttu-id="2f89d-113">ほとんどの場合は、Csonline ユーザーコマンドレットの出力でさまざまなプロパティを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f89d-113">In most cases, you need to look at various properties in the output of the Get-CsOnlineUser cmdlet.</span></span> <span data-ttu-id="2f89d-114">例として、ユーザーの UPN または sip アドレスのいずれかを $user と仮定します。</span><span class="sxs-lookup"><span data-stu-id="2f89d-114">Examples assume $user is either the UPN or sip address of the user.</span></span>

## <a name="user-has-an-enabled-phone-system-mcoev-license"></a><span data-ttu-id="2f89d-115">ユーザーに有効な電話システム ("MCOEV") ライセンスがある</span><span class="sxs-lookup"><span data-stu-id="2f89d-115">User has an enabled Phone System (“MCOEV”) license</span></span>

<span data-ttu-id="2f89d-116">ユーザーに割り当てられているプランに、 **CapabilityStatus 属性が Enabled に設定**されていて、**機能計画が mcoev** (電話システムライセンス) に設定されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f89d-116">You must ensure that the assigned plan for the user shows the **CapabilityStatus attribute set to Enabled** and the **Capability Plan set to MCOEV** (Phone System license).</span></span> <span data-ttu-id="2f89d-117">MCOEV、MCOEV1 が表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="2f89d-117">You might see MCOEV, MCOEV1, and so on.</span></span> <span data-ttu-id="2f89d-118">機能計画が MCOEV で開始されている限り、すべての機能を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="2f89d-118">All are acceptable--as long as the Capability Plan starts with MCOEV.</span></span>

<span data-ttu-id="2f89d-119">属性が正しく設定されていることを確認するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="2f89d-119">To check that the attributes are set correctly, use the following command:</span></span>

```
Get-CsOnlineUser -Identity $user|select AssignedPlan|fl
```

<span data-ttu-id="2f89d-120">出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="2f89d-120">The output will look like the following.</span></span> <span data-ttu-id="2f89d-121">**CapabilityStatus**と**機能プラン**の属性を確認する必要があるのは、次の場合だけです。</span><span class="sxs-lookup"><span data-stu-id="2f89d-121">You only need to check the **CapabilityStatus** and the **Capability Plan** attributes:</span></span>

```
<Plan SubscribedPlanId="2f9eda01-4630-4a5c-bdb3-cf195f22d240"  
   ServiceInstance="MicrosoftCommunicationsOnline/NOAM-0M-DMT" 
   CapabilityStatus="Enabled"  
   AssignedTimestamp="2020-04-21T18:31:13Z" 
   ServicePlanId="4828c8ec-dc2e-4779-b502-87ac9ce28ab7" 
   xmlns="http://schemas.microsoft.com/online/directoryservices/change/2008/11"> 
  <Capability> 
     <Capability Plan="MCOEV" 
     xmlns="http://schemas.microsoft.com/online/MCO/2009/01"/> 
  </Capability>
</Plan>
```


## <a name="user-has-microsoft-calling-plan-or-is-enabled-for-direct-routing"></a><span data-ttu-id="2f89d-122">ユーザーは Microsoft 通話プランを持っているか、直接ルーティングが有効になっています</span><span class="sxs-lookup"><span data-stu-id="2f89d-122">User has Microsoft Calling Plan OR is enabled for Direct Routing</span></span>

<span data-ttu-id="2f89d-123">**ユーザーが Microsoft の通話プランを持っている場合**は、 **CapabilityStatus 属性が Enabled に設定さ**れていること、および**機能計画が mcopstn に設定さ**れていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f89d-123">**If the user has Microsoft Calling Plan**, you must ensure that the **CapabilityStatus attribute is set to Enabled**, and that the **Capability Plan is set to MCOPSTN**.</span></span> <span data-ttu-id="2f89d-124">MCOPSTN1、MCOPSTN2 などが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="2f89d-124">You might see MCOPSTN1, MCOPSTN2, and so on.</span></span> <span data-ttu-id="2f89d-125">機能計画が MCOPSTN で開始されている限り、すべてが受け入れられます。</span><span class="sxs-lookup"><span data-stu-id="2f89d-125">All are acceptable--as long as the Capability Plan starts with MCOPSTN.</span></span>

<span data-ttu-id="2f89d-126">属性を確認するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="2f89d-126">To check the attributes, use the following command:</span></span>

```
Get-CsOnlineUser -Identity $user|select AssignedPlan|fl
```

<span data-ttu-id="2f89d-127">出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="2f89d-127">The output will look like the following.</span></span> <span data-ttu-id="2f89d-128">**CapabilityStatus**と**機能プラン**の属性を確認する必要があるのは、次の場合だけです。</span><span class="sxs-lookup"><span data-stu-id="2f89d-128">You only need to check the **CapabilityStatus** and the **Capability Plan** attributes:</span></span>

```  
<Plan SubscribedPlanId="71d1258e-a4e6-443f-884e-0f3d6f644bb1" 
ServiceInstance="MicrosoftCommunicationsOnline/NOAM-0M-DMT" 
CapabilityStatus="Enabled"    
AssignedTimestamp="2018-09-18T18:41:42Z" 
ServicePlanId="5a10155d-f5c1-411a-a8ec-e99aae125390" 
xmlns="http://schemas.microsoft.com/online/directoryservices/change/2008/11">
 <Capability>
    <Capability Plan="MCOPSTN2" 
    xmlns="http://schemas.microsoft.com/online/MCO/2009/01" />
 </Capability>
</Plan>
  ```

<span data-ttu-id="2f89d-129">**ユーザーが直接ルーティングを有効**にしている場合は、OnlineVoiceRoutingPolicy に対して null 以外の値が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f89d-129">**If the user is enabled for Direct Routing**, the user must be assigned a non-null value for OnlineVoiceRoutingPolicy.</span></span> <span data-ttu-id="2f89d-130">属性を確認するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="2f89d-130">To check the attribute, use the following command:</span></span>
  
```
Get-CsOnlineUser -Identity $user|Select OnlineVoiceRoutingPolicy 
```

<span data-ttu-id="2f89d-131">出力に null 以外の値が含まれている必要があります。たとえば、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="2f89d-131">The output should have a non-null value, for example:</span></span>

```
OnlineVoiceRoutingPolicy
------------------------
Test_Policy
```

## <a name="user-has-enterprise-voice-enabled"></a><span data-ttu-id="2f89d-132">ユーザーがエンタープライズ音声を有効にしている</span><span class="sxs-lookup"><span data-stu-id="2f89d-132">User has Enterprise Voice enabled</span></span>

<span data-ttu-id="2f89d-133">ユーザーがエンタープライズ Voip を有効にしているかどうかを確認するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="2f89d-133">To check if the user has Enterprise Voice enabled, use the following command:</span></span>

```
Get-CsOnlineUser -Identity $user|Select EnterpriseVoiceEnabled
```

<span data-ttu-id="2f89d-134">出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="2f89d-134">The output should look like:</span></span>

```
EnterpriseVoiceEnabled
----------------------
                  True

```
 
## <a name="user-is-homed-online-and-not-in-skype-for-business-on-premises"></a><span data-ttu-id="2f89d-135">ユーザーは、オンプレミスの Skype for Business ではなく、ホームになっています</span><span class="sxs-lookup"><span data-stu-id="2f89d-135">User is homed online and not in Skype for Business on premises</span></span>

<span data-ttu-id="2f89d-136">ユーザーがオンプレミスの Skype for Business ではなく、オンラインであることを確認するには、RegistrarPool を null にすることはできません。また、HostingProvider には "sipfed" で始まる値が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f89d-136">To ensure the user is homed online and not in Skype for Business on premises, the RegistrarPool must not be null and the HostingProvider must contain a value that starts with “sipfed.online.”</span></span>  <span data-ttu-id="2f89d-137">値を確認するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="2f89d-137">To check the values, use the following command:</span></span>

```
Get-CsOnlineUser -Identity $user|Select RegistrarPool, HostingProvider
```

<span data-ttu-id="2f89d-138">出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="2f89d-138">The output should be similar to:</span></span>

```
RegistrarPool                 HostingProvider
-------------                 ---------------
sippoolbn10M02.infra.lync.com sipfed.online.lync.com
```

## <a name="user-has-teams-calling-policy-enabled"></a><span data-ttu-id="2f89d-139">ユーザーがチーム呼び出しポリシーを有効にしている</span><span class="sxs-lookup"><span data-stu-id="2f89d-139">User has Teams Calling Policy enabled</span></span>

<span data-ttu-id="2f89d-140">ユーザーの有効な Teamの "ポリシー" は、AllowPrivateCalling が true に設定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f89d-140">The user’s effective TeamsCallingPolicy must have AllowPrivateCalling set to true.</span></span>  <span data-ttu-id="2f89d-141">既定では、ユーザーはグローバルポリシーを継承します。既定では、AllowPrivateCallingPolicy が true に設定されています。</span><span class="sxs-lookup"><span data-stu-id="2f89d-141">By default, users inherit the global policy, which has AllowPrivateCallingPolicy set to true by default.</span></span>

<span data-ttu-id="2f89d-142">ユーザーの TeamAllowPrivateCalling ポリシーを取得し、が true に設定されていることを確認するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="2f89d-142">To get the TeamsCallingPolicy for a user and to check that AllowPrivateCalling is set to true, use the following command:</span></span>

```
if (($p=(get-csonlineuser -Identity $user).TeamsCallingPolicy) -eq $null) {Get-CsTeamsCallingPolicy -Identity global} else {get-csteamscallingpolicy -Identity $p}
```

<span data-ttu-id="2f89d-143">出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="2f89d-143">The output should look like:</span></span>

```
Identity                   : Global
Description                :
AllowPrivateCalling        : True
AllowWebPSTNCalling        : True
AllowVoicemail             : UserOverride
AllowCallGroups            : True
AllowDelegation            : True
AllowCallForwardingToUser  : True
AllowCallForwardingToPhone : True
PreventTollBypass          : False
BusyOnBusyEnabledType      : Disabled
MusicOnHoldEnabledType     : Enabled
``` 

## <a name="additional-notes"></a><span data-ttu-id="2f89d-144">追加のメモ</span><span class="sxs-lookup"><span data-stu-id="2f89d-144">Additional notes</span></span>

-   <span data-ttu-id="2f89d-145">これらの構成変更を行った後、Teams クライアントの再起動が必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="2f89d-145">You may need to restart the Teams client after making any of these configuration changes.</span></span>

-   <span data-ttu-id="2f89d-146">最近上記の条件のいずれかを更新した場合、クライアントが新しい設定を受け取るまでに数時間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="2f89d-146">If you recently updated any of the above criteria, you may need to wait a few hours for the client to receive the new settings.</span></span>

-   <span data-ttu-id="2f89d-147">それでもダイヤルパッドが表示されない場合は、次のコマンドを使用してプロビジョニングエラーがあるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="2f89d-147">If you still don’t see the dial pad, check if there is a provisioning error by using the following command:</span></span>

  ```
  Get-CsOnlineUser -Identity $user|Select McoValidationError
  ```

-    <span data-ttu-id="2f89d-148">24時間以上経過しても問題が解決しない場合は、サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="2f89d-148">If it has been more than 24 hours and you are still seeing problems, contact Support.</span></span>


