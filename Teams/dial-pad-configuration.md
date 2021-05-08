---
title: Teamsパッドの構成
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
description: ユーザーが公衆交換電話網 (PSTN) 機能にアクセスできるよう、Teams クライアントでダイヤル パッドを構成する方法について説明します。
ms.openlocfilehash: 44fcbb766cadaa4b31aa065fae80fdcd48c5453f
ms.sourcegitcommit: a94a267c421a78587b0dbbea5fa167aad2882e9b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "45012418"
---
# <a name="dial-pad-configuration"></a><span data-ttu-id="a3c0a-103">ダイヤル パッドの構成</span><span class="sxs-lookup"><span data-stu-id="a3c0a-103">Dial pad configuration</span></span>

<span data-ttu-id="a3c0a-104">クライアントTeamsダイヤル パッドを使用すると、ユーザーは公衆交換電話網 (PSTN) 機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="a3c0a-104">In the Teams client, the dial pad enables users to access Public Switched Telephone Network (PSTN) functionality.</span></span> <span data-ttu-id="a3c0a-105">ダイヤル パッドは、適切に構成されている場合電話システムライセンスを持つユーザーが使用できます。</span><span class="sxs-lookup"><span data-stu-id="a3c0a-105">The dial pad is available for users with a Phone System license, provided they are configured properly.</span></span> <span data-ttu-id="a3c0a-106">ダイヤル パッドに表示するには、次の条件が必要です。</span><span class="sxs-lookup"><span data-stu-id="a3c0a-106">The following criteria are all required for the dial pad to show:</span></span>

- <span data-ttu-id="a3c0a-107">ユーザーが有効な電話システム ("MCOEV") ライセンスがある</span><span class="sxs-lookup"><span data-stu-id="a3c0a-107">User has an enabled Phone System (“MCOEV”) license</span></span>
- <span data-ttu-id="a3c0a-108">ユーザーが Microsoft 通話プランを使用している、または直接ルーティングが有効になっている</span><span class="sxs-lookup"><span data-stu-id="a3c0a-108">User has Microsoft Calling Plan or is enabled for Direct Routing</span></span>
- <span data-ttu-id="a3c0a-109">ユーザーが有効エンタープライズ VoIPしました</span><span class="sxs-lookup"><span data-stu-id="a3c0a-109">User has Enterprise Voice enabled</span></span>
- <span data-ttu-id="a3c0a-110">ユーザーはオンラインで自宅にいて、オンプレミスSkype for Businessではありません</span><span class="sxs-lookup"><span data-stu-id="a3c0a-110">User is homed online and not in Skype for Business on premises</span></span>
- <span data-ttu-id="a3c0a-111">ユーザーが通話Teams有効になっている</span><span class="sxs-lookup"><span data-stu-id="a3c0a-111">User has Teams Calling Policy enabled</span></span>

<span data-ttu-id="a3c0a-112">次のセクションでは、PowerShell を使用して条件を確認する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a3c0a-112">The following sections describe how to use PowerShell to check the criteria.</span></span> <span data-ttu-id="a3c0a-113">ほとんどの場合、Get-CsOnlineUser コマンドレットの出力でさまざまなプロパティを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3c0a-113">In most cases, you need to look at various properties in the output of the Get-CsOnlineUser cmdlet.</span></span> <span data-ttu-id="a3c0a-114">例では、$userユーザーの UPN アドレスまたは sip アドレスのいずれかです。</span><span class="sxs-lookup"><span data-stu-id="a3c0a-114">Examples assume $user is either the UPN or sip address of the user.</span></span>

## <a name="user-has-an-enabled-phone-system-mcoev-license"></a><span data-ttu-id="a3c0a-115">ユーザーが有効な電話システム ("MCOEV") ライセンスがある</span><span class="sxs-lookup"><span data-stu-id="a3c0a-115">User has an enabled Phone System (“MCOEV”) license</span></span>

<span data-ttu-id="a3c0a-116">ユーザーに割り当てられたプランに **、CapabilityStatus** 属性が [Enabled] に設定され、Capability Plan が **MCOEV** (電話システム) に設定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3c0a-116">You must ensure that the assigned plan for the user shows the **CapabilityStatus attribute set to Enabled** and the **Capability Plan set to MCOEV** (Phone System license).</span></span> <span data-ttu-id="a3c0a-117">MCOEV、MCOEV1 などと表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="a3c0a-117">You might see MCOEV, MCOEV1, and so on.</span></span> <span data-ttu-id="a3c0a-118">機能プランが MCOEV で始まる限り、すべて許容されます。</span><span class="sxs-lookup"><span data-stu-id="a3c0a-118">All are acceptable--as long as the Capability Plan starts with MCOEV.</span></span>

<span data-ttu-id="a3c0a-119">属性が正しく設定されていることを確認するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="a3c0a-119">To check that the attributes are set correctly, use the following command:</span></span>

```
Get-CsOnlineUser -Identity $user|select AssignedPlan|fl
```

<span data-ttu-id="a3c0a-120">出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="a3c0a-120">The output will look like the following.</span></span> <span data-ttu-id="a3c0a-121">CapabilityStatus 属性と **Capability Plan 属性** のみを確認 **する必要** があります。</span><span class="sxs-lookup"><span data-stu-id="a3c0a-121">You only need to check the **CapabilityStatus** and the **Capability Plan** attributes:</span></span>

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


## <a name="user-has-microsoft-calling-plan-or-is-enabled-for-direct-routing"></a><span data-ttu-id="a3c0a-122">ユーザーが Microsoft 通話プランを使用している、または直接ルーティングが有効になっている</span><span class="sxs-lookup"><span data-stu-id="a3c0a-122">User has Microsoft Calling Plan OR is enabled for Direct Routing</span></span>

<span data-ttu-id="a3c0a-123">**ユーザーが Microsoft 通話プラン を** 持っている場合は **、CapabilityStatus** 属性が [有効] に設定され、機能プランが **MCOPSTN** に設定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3c0a-123">**If the user has Microsoft Calling Plan**, you must ensure that the **CapabilityStatus attribute is set to Enabled**, and that the **Capability Plan is set to MCOPSTN**.</span></span> <span data-ttu-id="a3c0a-124">MCOPSTN1、MCOPSTN2 などと表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="a3c0a-124">You might see MCOPSTN1, MCOPSTN2, and so on.</span></span> <span data-ttu-id="a3c0a-125">機能プランが MCOPSTN で始まる限り、すべて許容されます。</span><span class="sxs-lookup"><span data-stu-id="a3c0a-125">All are acceptable--as long as the Capability Plan starts with MCOPSTN.</span></span>

<span data-ttu-id="a3c0a-126">属性を確認するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="a3c0a-126">To check the attributes, use the following command:</span></span>

```
Get-CsOnlineUser -Identity $user|select AssignedPlan|fl
```

<span data-ttu-id="a3c0a-127">出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="a3c0a-127">The output will look like the following.</span></span> <span data-ttu-id="a3c0a-128">CapabilityStatus 属性と **Capability Plan 属性** のみを確認 **する必要** があります。</span><span class="sxs-lookup"><span data-stu-id="a3c0a-128">You only need to check the **CapabilityStatus** and the **Capability Plan** attributes:</span></span>

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

<span data-ttu-id="a3c0a-129">**ユーザーが直接ルーティングに対して有効** になっている場合、ユーザーには OnlineVoiceRoutingPolicy に null 以外の値を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3c0a-129">**If the user is enabled for Direct Routing**, the user must be assigned a non-null value for OnlineVoiceRoutingPolicy.</span></span> <span data-ttu-id="a3c0a-130">属性を確認するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="a3c0a-130">To check the attribute, use the following command:</span></span>
  
```
Get-CsOnlineUser -Identity $user|Select OnlineVoiceRoutingPolicy 
```

<span data-ttu-id="a3c0a-131">出力には null 以外の値が必要です。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="a3c0a-131">The output should have a non-null value, for example:</span></span>

```
OnlineVoiceRoutingPolicy
------------------------
Test_Policy
```

## <a name="user-has-enterprise-voice-enabled"></a><span data-ttu-id="a3c0a-132">ユーザーが有効エンタープライズ VoIPしました</span><span class="sxs-lookup"><span data-stu-id="a3c0a-132">User has Enterprise Voice enabled</span></span>

<span data-ttu-id="a3c0a-133">ユーザーが有効になっているエンタープライズ VoIP、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="a3c0a-133">To check if the user has Enterprise Voice enabled, use the following command:</span></span>

```
Get-CsOnlineUser -Identity $user|Select EnterpriseVoiceEnabled
```

<span data-ttu-id="a3c0a-134">出力は次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="a3c0a-134">The output should look like:</span></span>

```
EnterpriseVoiceEnabled
----------------------
                  True

```
 
## <a name="user-is-homed-online-and-not-in-skype-for-business-on-premises"></a><span data-ttu-id="a3c0a-135">ユーザーはオンラインで自宅にいて、オンプレミスSkype for Businessではありません</span><span class="sxs-lookup"><span data-stu-id="a3c0a-135">User is homed online and not in Skype for Business on premises</span></span>

<span data-ttu-id="a3c0a-136">ユーザーがオンプレミスの Skype for Business ではなくオンラインで自宅にいなければならない場合は、RegistrarPool を null にし、HostingProvider に "sipfed.online" で始まる値を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3c0a-136">To ensure the user is homed online and not in Skype for Business on premises, the RegistrarPool must not be null and the HostingProvider must contain a value that starts with “sipfed.online.”</span></span>  <span data-ttu-id="a3c0a-137">値を確認するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="a3c0a-137">To check the values, use the following command:</span></span>

```
Get-CsOnlineUser -Identity $user|Select RegistrarPool, HostingProvider
```

<span data-ttu-id="a3c0a-138">出力は次の形式である必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3c0a-138">The output should be similar to:</span></span>

```
RegistrarPool                 HostingProvider
-------------                 ---------------
sippoolbn10M02.infra.lync.com sipfed.online.lync.com
```

## <a name="user-has-teams-calling-policy-enabled"></a><span data-ttu-id="a3c0a-139">ユーザーが通話Teams有効になっている</span><span class="sxs-lookup"><span data-stu-id="a3c0a-139">User has Teams Calling Policy enabled</span></span>

<span data-ttu-id="a3c0a-140">ユーザーの有効な TeamsCallingPolicy には、AllowPrivateCalling が true に設定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3c0a-140">The user’s effective TeamsCallingPolicy must have AllowPrivateCalling set to true.</span></span>  <span data-ttu-id="a3c0a-141">既定では、ユーザーはグローバル ポリシーを継承します。AllowPrivateCallingPolicy は既定で true に設定されています。</span><span class="sxs-lookup"><span data-stu-id="a3c0a-141">By default, users inherit the global policy, which has AllowPrivateCallingPolicy set to true by default.</span></span>

<span data-ttu-id="a3c0a-142">ユーザーの TeamsCallingPolicy を取得し、AllowPrivateCalling が true に設定されているのを確認するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="a3c0a-142">To get the TeamsCallingPolicy for a user and to check that AllowPrivateCalling is set to true, use the following command:</span></span>

```
if (($p=(get-csonlineuser -Identity $user).TeamsCallingPolicy) -eq $null) {Get-CsTeamsCallingPolicy -Identity global} else {get-csteamscallingpolicy -Identity $p}
```

<span data-ttu-id="a3c0a-143">出力は次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="a3c0a-143">The output should look like:</span></span>

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

## <a name="additional-notes"></a><span data-ttu-id="a3c0a-144">その他のメモ</span><span class="sxs-lookup"><span data-stu-id="a3c0a-144">Additional notes</span></span>

-   <span data-ttu-id="a3c0a-145">これらの構成変更を行った後Teamsクライアントを再起動する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="a3c0a-145">You may need to restart the Teams client after making any of these configuration changes.</span></span>

-   <span data-ttu-id="a3c0a-146">上記の条件を最近更新した場合は、クライアントが新しい設定を受信するまで数時間待つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3c0a-146">If you recently updated any of the above criteria, you may need to wait a few hours for the client to receive the new settings.</span></span>

-   <span data-ttu-id="a3c0a-147">それでもダイヤル パッドが表示しない場合は、次のコマンドを使用してプロビジョニング エラーが発生した場合を確認します。</span><span class="sxs-lookup"><span data-stu-id="a3c0a-147">If you still don’t see the dial pad, check if there is a provisioning error by using the following command:</span></span>

  ```
  Get-CsOnlineUser -Identity $user|Select McoValidationError
  ```

-    <span data-ttu-id="a3c0a-148">24 時間を超え、問題が引き続き発生する場合は、サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="a3c0a-148">If it has been more than 24 hours and you are still seeing problems, contact Support.</span></span>


