---
title: Skype for Business Server 2015 応力とパフォーマンスツールのポリシーを構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 11/11/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7e1435e2-d073-4265-8067-ebcb5bf28835
description: Skype for Business Server 2015 のストレスとパフォーマンスツールのポリシー構成。
ms.openlocfilehash: bfdf0d9875a37f7f4a1f98aa24cd6fd5c3176a00
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816196"
---
# <a name="configuring-policies-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="b1293-103">Skype for Business Server 2015 応力とパフォーマンスツールのポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="b1293-103">Configuring policies for the Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="b1293-104">Skype for Business Server 2015 のストレスとパフォーマンスツールのポリシー構成。</span><span class="sxs-lookup"><span data-stu-id="b1293-104">Policy configuration for Skype for Business Server 2015 Stress and Performance Tool.</span></span>
  
<span data-ttu-id="b1293-105">「Skype for Business Server 2015 では、ストレスとパフォーマンスのツールを実行する前に構成できるいくつかのポリシーとその他の領域があります。</span><span class="sxs-lookup"><span data-stu-id="b1293-105">There are several policies and other areas that you can configure in Skype for Business Server 2015, prior to running the Stress and Performance Tool:</span></span>
  
- [<span data-ttu-id="b1293-106">アーカイブポリシー</span><span class="sxs-lookup"><span data-stu-id="b1293-106">Archiving policy</span></span>](configuring-policies.md#ArchivingPolicy)
    
- [<span data-ttu-id="b1293-107">会議ポリシー</span><span class="sxs-lookup"><span data-stu-id="b1293-107">Conferencing policy</span></span>](configuring-policies.md#ConferencingPolicy)
    
- [<span data-ttu-id="b1293-108">連絡先ポリシー</span><span class="sxs-lookup"><span data-stu-id="b1293-108">Contacts policy</span></span>](configuring-policies.md#ContactsPolicy)
    
- [<span data-ttu-id="b1293-109">フェデレーションポリシー</span><span class="sxs-lookup"><span data-stu-id="b1293-109">Federation policy</span></span>](configuring-policies.md#FederationPolicy)
    
- [<span data-ttu-id="b1293-110">通話受付制御ポリシー</span><span class="sxs-lookup"><span data-stu-id="b1293-110">Call Admission Control policy</span></span>](configuring-policies.md#CACPolicy)
    
- [<span data-ttu-id="b1293-111">ボイスルーティングルール</span><span class="sxs-lookup"><span data-stu-id="b1293-111">Voice Routing rules</span></span>](configuring-policies.md#VoiceRoutingRules)
    
- [<span data-ttu-id="b1293-112">会議アテンダントアプリケーション</span><span class="sxs-lookup"><span data-stu-id="b1293-112">Conference Attendant application</span></span>](configuring-policies.md#ConfAttendantApp)
    
- [<span data-ttu-id="b1293-113">サーバーコールパークサービス</span><span class="sxs-lookup"><span data-stu-id="b1293-113">Server Call Park service</span></span>](configuring-policies.md#ServerCallParkServ)
    
- [<span data-ttu-id="b1293-114">緊急通話</span><span class="sxs-lookup"><span data-stu-id="b1293-114">Emergency calls</span></span>](configuring-policies.md#EmergencyCalls)
    
- [<span data-ttu-id="b1293-115">応答グループアプリケーションを構成する</span><span class="sxs-lookup"><span data-stu-id="b1293-115">Configuring Response Group application</span></span>](configuring-policies.md#ConfigResponseGroupApp)
    
## <a name="archiving-policy"></a><span data-ttu-id="b1293-116">アーカイブポリシー</span><span class="sxs-lookup"><span data-stu-id="b1293-116">Archiving policy</span></span>
<span data-ttu-id="b1293-117"><a name="ArchivingPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="b1293-117"><a name="ArchivingPolicy"> </a></span></span>

<span data-ttu-id="b1293-118">Skype for Business Server トポロジにアーカイブサーバーが展開されている場合は、ArchivingPolicy スクリプトを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1293-118">If you have an Archiving server deployed in your Skype for Business Server topology, you can look at the ArchivingPolicy.ps1 script.</span></span> <span data-ttu-id="b1293-119">さらにサポートが必要な場合は、「アーカイブと Web 会議のコマンドレット」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b1293-119">If you need further assistance, check out the Archiving and Web Conferencing cmdlets.</span></span>
  
## <a name="conferencing-policy"></a><span data-ttu-id="b1293-120">会議ポリシー</span><span class="sxs-lookup"><span data-stu-id="b1293-120">Conferencing policy</span></span>
<span data-ttu-id="b1293-121"><a name="ConferencingPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="b1293-121"><a name="ConferencingPolicy"> </a></span></span>

<span data-ttu-id="b1293-122">会議の場合は、"会議ポリシー. ps1" スクリプトを使います。</span><span class="sxs-lookup"><span data-stu-id="b1293-122">For conferencing, we have the MeetingPolicy.ps1 script.</span></span> <span data-ttu-id="b1293-123">さらにサポートが必要な場合は、「Web 会議コマンドレット」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b1293-123">If you need further assistance, check out the Web Conferencing cmdlets.</span></span>
  
## <a name="contacts-policy"></a><span data-ttu-id="b1293-124">連絡先ポリシー</span><span class="sxs-lookup"><span data-stu-id="b1293-124">Contacts policy</span></span>
<span data-ttu-id="b1293-125"><a name="ContactsPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="b1293-125"><a name="ContactsPolicy"> </a></span></span>

<span data-ttu-id="b1293-126">ContactsPolicy スクリプトは、確認する必要があるサンプルです。</span><span class="sxs-lookup"><span data-stu-id="b1293-126">ContactsPolicy.ps1 script will be the sample you'll need to review.</span></span> <span data-ttu-id="b1293-127">IM とプレゼンスのコマンドレットは、さらに参照が必要な場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="b1293-127">The IM and Presence cmdlets will help if you need further references.</span></span>
  
## <a name="federation-policy"></a><span data-ttu-id="b1293-128">フェデレーションポリシー</span><span class="sxs-lookup"><span data-stu-id="b1293-128">Federation policy</span></span>
<span data-ttu-id="b1293-129"><a name="FederationPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="b1293-129"><a name="FederationPolicy"> </a></span></span>

<span data-ttu-id="b1293-130">フェデレーションのサンプルスクリプトは FederationPolicy です。</span><span class="sxs-lookup"><span data-stu-id="b1293-130">The sample script for federation is FederationPolicy.ps1.</span></span> <span data-ttu-id="b1293-131">さらに詳しい情報が必要な場合は、確認するコマンドレットはエッジサーバー、フェデレーション、外部アクセスになります。</span><span class="sxs-lookup"><span data-stu-id="b1293-131">The cmdlets to review, if you need further insight, will be Edge Server, federation, and external access.</span></span>
  
## <a name="call-admission-control-policy"></a><span data-ttu-id="b1293-132">通話受付制御ポリシー</span><span class="sxs-lookup"><span data-stu-id="b1293-132">Call Admission Control policy</span></span>
<span data-ttu-id="b1293-133"><a name="CACPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="b1293-133"><a name="CACPolicy"> </a></span></span>

<span data-ttu-id="b1293-134">このポリシーについては、BandwidthPolicy を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1293-134">You can reference BandwidthPolicy.ps1 for this policy.</span></span> <span data-ttu-id="b1293-135">通話受付制御コマンドレットについては、さらに詳しい情報も含まれています。</span><span class="sxs-lookup"><span data-stu-id="b1293-135">The Call Admission Control cmdlets will have further information as well.</span></span>
  
## <a name="voice-routing-rules"></a><span data-ttu-id="b1293-136">ボイスルーティングルール</span><span class="sxs-lookup"><span data-stu-id="b1293-136">Voice Routing rules</span></span>
<span data-ttu-id="b1293-137"><a name="VoiceRoutingRules"> </a></span><span class="sxs-lookup"><span data-stu-id="b1293-137"><a name="VoiceRoutingRules"> </a></span></span>

<span data-ttu-id="b1293-138">ボイスルーティング用の RoutingRules サンプルスクリプトが必要です。</span><span class="sxs-lookup"><span data-stu-id="b1293-138">You'll need the RoutingRules.ps1 sample script for Voice Routing.</span></span> <span data-ttu-id="b1293-139">これらのルールを構成している場合は、電話のコンテキスト (¥ Location Profile または/simplename) と内部または外部の市外局番をメモして、ユーザーを作成するときに指定できます。</span><span class="sxs-lookup"><span data-stu-id="b1293-139">When you're configuring these rules, take note of the phone context (that is, /Location Profile or /SimpleName) and Internal/External Area Codes, so that you can specify them when creating users.</span></span> <span data-ttu-id="b1293-140">また、LyncPerfTool 構成 (特に PSTN-UC および UC-PSTN 用) でも必要になります。</span><span class="sxs-lookup"><span data-stu-id="b1293-140">You'll also need them during LyncPerfTool configuration (specifically for PSTN-UC and UC-PSTN).</span></span>
  
<span data-ttu-id="b1293-141">たとえば、RoutingRules の例の**CsDialPlan**コマンドレットの呼び出しの simplename パラメーターは、UserProfileGenerator の次の図の locationprofile 値として使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1293-141">For example, the SimpleName parameter in the call to the **New-CsDialPlan** cmdlet in the RoutingRules.ps1 example should be used for the LocationProfile value in the following figure of UserProfileGenerator.exe:</span></span>
  
![Skype for Business Load Configuration Tool、[Voice Scenarios] タブ、会話の詳細設定](../../media/59f42e4e-8f1e-4d43-9ae2-9e6026191951.png)
  
<span data-ttu-id="b1293-143">詳細については、「エンタープライズボイスのコマンドレット」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1293-143">For details, you can review the Enterprise Voice cmdlets.</span></span>
  
## <a name="conference-attendant-application"></a><span data-ttu-id="b1293-144">会議アテンダントアプリケーション</span><span class="sxs-lookup"><span data-stu-id="b1293-144">Conference Attendant application</span></span>
<span data-ttu-id="b1293-145"><a name="ConfAttendantApp"> </a></span><span class="sxs-lookup"><span data-stu-id="b1293-145"><a name="ConfAttendantApp"> </a></span></span>

<span data-ttu-id="b1293-146">まず、ConferenceAutoAttendantConfiguration スクリプトを確認します。</span><span class="sxs-lookup"><span data-stu-id="b1293-146">First review the ConferenceAutoAttendantConfiguration.ps1 script.</span></span> <span data-ttu-id="b1293-147">ConferencingAutoAttendant 電話番号 (既定では 1121111111) をメモしておくと、次のように、これを LyncPerfTool 構成ツールに入力して構成を生成することができます。</span><span class="sxs-lookup"><span data-stu-id="b1293-147">You'll want to take note of the ConferencingAutoAttendant phone number (1121111111 by default), so that you can enter it into the LyncPerfTool configuration tool for configuration generation, as below:</span></span>
  
![電話会議負荷レベルと電話番号を表示している [Voice Scenarios] タブ](../../media/a3ea5fc0-8b3d-4842-b809-f137f470dbdc.png)
  
<span data-ttu-id="b1293-149">詳細については、「会議とダイヤルイン会議のコマンドレット」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1293-149">You'll find more details in the Conferencing and Dial-in Conferencing cmdlets.</span></span>
  
## <a name="server-call-park-service"></a><span data-ttu-id="b1293-150">サーバーコールパークサービス</span><span class="sxs-lookup"><span data-stu-id="b1293-150">Server Call Park service</span></span>
<span data-ttu-id="b1293-151"><a name="ServerCallParkServ"> </a></span><span class="sxs-lookup"><span data-stu-id="b1293-151"><a name="ServerCallParkServ"> </a></span></span>

<span data-ttu-id="b1293-152">これは、実際には既定では無効になっています。</span><span class="sxs-lookup"><span data-stu-id="b1293-152">This is actually disabled by default.</span></span> <span data-ttu-id="b1293-153">これをテストする必要がある場合は、CallParkConfiguration. ps1 サンプルスクリプトを確認できます。</span><span class="sxs-lookup"><span data-stu-id="b1293-153">You can review the CallParkConfiguration.ps1 sample script if you need to test this.</span></span> <span data-ttu-id="b1293-154">さらに、必要に応じて、コールパークアプリケーションのコマンドレットもご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b1293-154">Additionally, check out the Call Park Application cmdlets as needed.</span></span>
  
## <a name="emergency-calls"></a><span data-ttu-id="b1293-155">緊急通話</span><span class="sxs-lookup"><span data-stu-id="b1293-155">Emergency calls</span></span>
<span data-ttu-id="b1293-156"><a name="EmergencyCalls"> </a></span><span class="sxs-lookup"><span data-stu-id="b1293-156"><a name="EmergencyCalls"> </a></span></span>

<span data-ttu-id="b1293-157">緊急通話のストレスとパフォーマンスのテストを構成するには、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1293-157">You'll need to perform the following steps to configure stress and performance testing for emergency calls:</span></span>
  
1. <span data-ttu-id="b1293-158">緊急通話のためのボイスルートを設定します。</span><span class="sxs-lookup"><span data-stu-id="b1293-158">Set up a voice route for emergency calls.</span></span> <span data-ttu-id="b1293-159">このボイスルートの設定方法の例については、RoutingRules スクリプトを使用して、コメント " **E911 へのルーティング**" を確認してください。</span><span class="sxs-lookup"><span data-stu-id="b1293-159">You can use the RoutingRules.ps1 script, and check under the comment " **Route E911 to PSTN** " for an example of how to set up this voice route.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="b1293-160">RoutingRules の例のコマンドには、911ではなく数値119を含む数値パターンが含まれています。</span><span class="sxs-lookup"><span data-stu-id="b1293-160">The example command in RoutingRules.ps1 has a number pattern that includes the number 119 rather than 911.</span></span> <span data-ttu-id="b1293-161">ロードテスト中に、お客様の地域の緊急対応オペレーターへの偶発的な通話を防ぐため、911 (または実際のローカル緊急電話番号) の使用は避けてください。</span><span class="sxs-lookup"><span data-stu-id="b1293-161">You should avoid using 911 (or your actual local emergency number) to prevent accidental calls to your local emergency operators during your load testing.</span></span> <span data-ttu-id="b1293-162">この構成はシミュレーション目的でのみ使用することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="b1293-162">Remember, this configuration is for simulation purposes only!</span></span> 
  
2. <span data-ttu-id="b1293-163">次の図に示すように、Userプロビジョニングツールの [**位置情報] サービス構成**タブの値を入力して、アドレスを構成します。</span><span class="sxs-lookup"><span data-stu-id="b1293-163">Configure addresses by filling in the values on the **Location Info Service Config** tab in the UserProvisioningTool, as shown in the following figure:</span></span>
    
     ![アドレス、サブネット、スイッチ、ポートの数を表示している User Provisioning Tool](../../media/ebe85a0c-750f-4301-97d4-d158a40ea98a.png)
  
3. <span data-ttu-id="b1293-165">Userプロビジョニングツールにすべての情報を入力したら、[ **LIS 構成ファイルの生成**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="b1293-165">When you've entered everything into the UserProvisioningTool, click the **Generate LIS Config Files** button.</span></span>
    
4. <span data-ttu-id="b1293-166">これにより、ポート、サブネット、スイッチ、ワイヤレスアクセスポイント (Wap) の CSV ファイル、およびストレスとパフォーマンスツールの XML ファイルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="b1293-166">Now CSV files for ports, subnets, switches, and wireless access points (WAPs), as well as an XML file for the Stress and Performance tool will be generated.</span></span> <span data-ttu-id="b1293-167">LisConfiguration スクリプトを使用して位置情報サービス (LIS) を構成するときに、CSV ファイルを入力用に使うことができます。</span><span class="sxs-lookup"><span data-stu-id="b1293-167">You can use the CSV files for inputs when configuring the Location Information service (LIS) with the LisConfiguration.ps1 script.</span></span> <span data-ttu-id="b1293-168">そのためには、Locations0 ファイルを、ストレスとパフォーマンスツールの実行可能ファイル (LyncPerfTool) と同じフォルダーに移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1293-168">To do this, you'll need to move the Locations0.xml file to the same folder as the Stress and Performance Tool executable (LyncPerfTool.exe).</span></span> <span data-ttu-id="b1293-169">これにより、位置情報プロファイル (ダイヤルプラン) のシナリオを実行できるようになります。</span><span class="sxs-lookup"><span data-stu-id="b1293-169">This will let you run location profile (dial plan) scenarios.</span></span>
    
## <a name="configuring-response-group-application"></a><span data-ttu-id="b1293-170">応答グループアプリケーションを構成する</span><span class="sxs-lookup"><span data-stu-id="b1293-170">Configuring Response Group application</span></span>
<span data-ttu-id="b1293-171"><a name="ConfigResponseGroupApp"> </a></span><span class="sxs-lookup"><span data-stu-id="b1293-171"><a name="ConfigResponseGroupApp"> </a></span></span>

<span data-ttu-id="b1293-172">サンプルスクリプトは ResponseGroupConfiguration. ps1 です。</span><span class="sxs-lookup"><span data-stu-id="b1293-172">The sample script is ResponseGroupConfiguration.ps1.</span></span> <span data-ttu-id="b1293-173">さらに構成の詳細を確認する応答グループのアプリケーションコマンドレットもあります。</span><span class="sxs-lookup"><span data-stu-id="b1293-173">There are also Response Group application cmdlets to review for further configuration details.</span></span> <span data-ttu-id="b1293-174">次の図は、構成の詳細の一部を示しています。</span><span class="sxs-lookup"><span data-stu-id="b1293-174">The following diagram will show some of the configuration details:</span></span>
  
![既存のテスト用ワークフローを表示している Response Group Configuration Tool](../../media/e218a345-4813-4332-8cff-b48de05017ef.jpg)
  

