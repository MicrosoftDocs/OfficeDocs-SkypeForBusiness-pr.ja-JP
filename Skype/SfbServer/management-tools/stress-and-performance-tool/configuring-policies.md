---
title: Skype for Business Server 2015 Stress and Performance Tool のポリシーの構成
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Skype for Business Server 2015 Stress and Performance Tool のポリシー構成。
ms.openlocfilehash: bb049d5740d74e5ebeacd8a21d00e2644da61a7c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815037"
---
# <a name="configuring-policies-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="d7575-103">Skype for Business Server 2015 Stress and Performance Tool のポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="d7575-103">Configuring policies for the Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="d7575-104">Skype for Business Server 2015 Stress and Performance Tool のポリシー構成。</span><span class="sxs-lookup"><span data-stu-id="d7575-104">Policy configuration for Skype for Business Server 2015 Stress and Performance Tool.</span></span>
  
<span data-ttu-id="d7575-105">Stress and Performance Tool を実行する前に、Skype for Business Server 2015 で構成できるいくつかのポリシーと他の領域があります。</span><span class="sxs-lookup"><span data-stu-id="d7575-105">There are several policies and other areas that you can configure in Skype for Business Server 2015, prior to running the Stress and Performance Tool:</span></span>
  
- [<span data-ttu-id="d7575-106">アーカイブ ポリシー</span><span class="sxs-lookup"><span data-stu-id="d7575-106">Archiving policy</span></span>](configuring-policies.md#ArchivingPolicy)
    
- [<span data-ttu-id="d7575-107">会議ポリシー</span><span class="sxs-lookup"><span data-stu-id="d7575-107">Conferencing policy</span></span>](configuring-policies.md#ConferencingPolicy)
    
- [<span data-ttu-id="d7575-108">連絡先ポリシー</span><span class="sxs-lookup"><span data-stu-id="d7575-108">Contacts policy</span></span>](configuring-policies.md#ContactsPolicy)
    
- [<span data-ttu-id="d7575-109">フェデレーション ポリシー</span><span class="sxs-lookup"><span data-stu-id="d7575-109">Federation policy</span></span>](configuring-policies.md#FederationPolicy)
    
- [<span data-ttu-id="d7575-110">通話受付管理ポリシー</span><span class="sxs-lookup"><span data-stu-id="d7575-110">Call Admission Control policy</span></span>](configuring-policies.md#CACPolicy)
    
- [<span data-ttu-id="d7575-111">音声ルーティング ルール</span><span class="sxs-lookup"><span data-stu-id="d7575-111">Voice Routing rules</span></span>](configuring-policies.md#VoiceRoutingRules)
    
- [<span data-ttu-id="d7575-112">会議アテンダント アプリケーション</span><span class="sxs-lookup"><span data-stu-id="d7575-112">Conference Attendant application</span></span>](configuring-policies.md#ConfAttendantApp)
    
- [<span data-ttu-id="d7575-113">サーバー コール パーク サービス</span><span class="sxs-lookup"><span data-stu-id="d7575-113">Server Call Park service</span></span>](configuring-policies.md#ServerCallParkServ)
    
- [<span data-ttu-id="d7575-114">緊急電話</span><span class="sxs-lookup"><span data-stu-id="d7575-114">Emergency calls</span></span>](configuring-policies.md#EmergencyCalls)
    
- [<span data-ttu-id="d7575-115">応答グループ アプリケーションの構成</span><span class="sxs-lookup"><span data-stu-id="d7575-115">Configuring Response Group application</span></span>](configuring-policies.md#ConfigResponseGroupApp)
    
## <a name="archiving-policy"></a><span data-ttu-id="d7575-116">アーカイブ ポリシー</span><span class="sxs-lookup"><span data-stu-id="d7575-116">Archiving policy</span></span>
<span data-ttu-id="d7575-117"><a name="ArchivingPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="d7575-117"><a name="ArchivingPolicy"> </a></span></span>

<span data-ttu-id="d7575-118">Skype for Business Server トポロジにアーカイブ サーバーが展開されている場合は、次のスクリプトArchivingPolicy.ps1できます。</span><span class="sxs-lookup"><span data-stu-id="d7575-118">If you have an Archiving server deployed in your Skype for Business Server topology, you can look at the ArchivingPolicy.ps1 script.</span></span> <span data-ttu-id="d7575-119">さらにサポートが必要な場合は、アーカイブと Web 会議のコマンドレットを確認してください。</span><span class="sxs-lookup"><span data-stu-id="d7575-119">If you need further assistance, check out the Archiving and Web Conferencing cmdlets.</span></span>
  
## <a name="conferencing-policy"></a><span data-ttu-id="d7575-120">会議ポリシー</span><span class="sxs-lookup"><span data-stu-id="d7575-120">Conferencing policy</span></span>
<span data-ttu-id="d7575-121"><a name="ConferencingPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="d7575-121"><a name="ConferencingPolicy"> </a></span></span>

<span data-ttu-id="d7575-122">電話会議には、次のスクリプトMeetingPolicy.ps1があります。</span><span class="sxs-lookup"><span data-stu-id="d7575-122">For conferencing, we have the MeetingPolicy.ps1 script.</span></span> <span data-ttu-id="d7575-123">さらにサポートが必要な場合は、Web 会議のコマンドレットを確認してください。</span><span class="sxs-lookup"><span data-stu-id="d7575-123">If you need further assistance, check out the Web Conferencing cmdlets.</span></span>
  
## <a name="contacts-policy"></a><span data-ttu-id="d7575-124">連絡先ポリシー</span><span class="sxs-lookup"><span data-stu-id="d7575-124">Contacts policy</span></span>
<span data-ttu-id="d7575-125"><a name="ContactsPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="d7575-125"><a name="ContactsPolicy"> </a></span></span>

<span data-ttu-id="d7575-126">ContactsPolicy.ps1は、確認する必要があるサンプルです。</span><span class="sxs-lookup"><span data-stu-id="d7575-126">ContactsPolicy.ps1 script will be the sample you'll need to review.</span></span> <span data-ttu-id="d7575-127">さらに参照が必要な場合は、IM とプレゼンスのコマンドレットが役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d7575-127">The IM and Presence cmdlets will help if you need further references.</span></span>
  
## <a name="federation-policy"></a><span data-ttu-id="d7575-128">フェデレーション ポリシー</span><span class="sxs-lookup"><span data-stu-id="d7575-128">Federation policy</span></span>
<span data-ttu-id="d7575-129"><a name="FederationPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="d7575-129"><a name="FederationPolicy"> </a></span></span>

<span data-ttu-id="d7575-130">フェデレーションのサンプル スクリプトはFederationPolicy.ps1。</span><span class="sxs-lookup"><span data-stu-id="d7575-130">The sample script for federation is FederationPolicy.ps1.</span></span> <span data-ttu-id="d7575-131">詳細な情報が必要な場合に確認するコマンドレットは、エッジ サーバー、フェデレーション、および外部アクセスです。</span><span class="sxs-lookup"><span data-stu-id="d7575-131">The cmdlets to review, if you need further insight, will be Edge Server, federation, and external access.</span></span>
  
## <a name="call-admission-control-policy"></a><span data-ttu-id="d7575-132">通話受付管理ポリシー</span><span class="sxs-lookup"><span data-stu-id="d7575-132">Call Admission Control policy</span></span>
<span data-ttu-id="d7575-133"><a name="CACPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="d7575-133"><a name="CACPolicy"> </a></span></span>

<span data-ttu-id="d7575-134">このポリシーのBandwidthPolicy.ps1参照できます。</span><span class="sxs-lookup"><span data-stu-id="d7575-134">You can reference BandwidthPolicy.ps1 for this policy.</span></span> <span data-ttu-id="d7575-135">通話受付管理のコマンドレットには、さらに詳しい情報もあります。</span><span class="sxs-lookup"><span data-stu-id="d7575-135">The Call Admission Control cmdlets will have further information as well.</span></span>
  
## <a name="voice-routing-rules"></a><span data-ttu-id="d7575-136">音声ルーティング ルール</span><span class="sxs-lookup"><span data-stu-id="d7575-136">Voice Routing rules</span></span>
<span data-ttu-id="d7575-137"><a name="VoiceRoutingRules"> </a></span><span class="sxs-lookup"><span data-stu-id="d7575-137"><a name="VoiceRoutingRules"> </a></span></span>

<span data-ttu-id="d7575-138">音声ルーティングのサンプル スクリプトRoutingRules.ps1必要です。</span><span class="sxs-lookup"><span data-stu-id="d7575-138">You'll need the RoutingRules.ps1 sample script for Voice Routing.</span></span> <span data-ttu-id="d7575-139">これらのルールを構成する場合は、ユーザー作成時に指定できるよう、電話コンテキスト (/Location Profile または /SimpleName) と内部/外部エリア コードをメモします。</span><span class="sxs-lookup"><span data-stu-id="d7575-139">When you're configuring these rules, take note of the phone context (that is, /Location Profile or /SimpleName) and Internal/External Area Codes, so that you can specify them when creating users.</span></span> <span data-ttu-id="d7575-140">また、LyncPerfTool の構成中 (特に PSTN-UC および UC-PSTN 用) に必要になります。</span><span class="sxs-lookup"><span data-stu-id="d7575-140">You'll also need them during LyncPerfTool configuration (specifically for PSTN-UC and UC-PSTN).</span></span>
  
<span data-ttu-id="d7575-141">たとえば、RoutingRules.ps1 の例の **New-CsDialPlan** コマンドレットの呼び出しの SimpleName パラメーターは、次の図の LocationProfile 値に使用UserProfileGenerator.exe。</span><span class="sxs-lookup"><span data-stu-id="d7575-141">For example, the SimpleName parameter in the call to the **New-CsDialPlan** cmdlet in the RoutingRules.ps1 example should be used for the LocationProfile value in the following figure of UserProfileGenerator.exe:</span></span>
  
![Skype for Business 読み込み構成ツール、音声シナリオ タブ、会話の詳細設定。](../../media/59f42e4e-8f1e-4d43-9ae2-9e6026191951.png)
  
<span data-ttu-id="d7575-143">詳細については、次のコマンドレットをエンタープライズ VoIPできます。</span><span class="sxs-lookup"><span data-stu-id="d7575-143">For details, you can review the Enterprise Voice cmdlets.</span></span>
  
## <a name="conference-attendant-application"></a><span data-ttu-id="d7575-144">会議アテンダント アプリケーション</span><span class="sxs-lookup"><span data-stu-id="d7575-144">Conference Attendant application</span></span>
<span data-ttu-id="d7575-145"><a name="ConfAttendantApp"> </a></span><span class="sxs-lookup"><span data-stu-id="d7575-145"><a name="ConfAttendantApp"> </a></span></span>

<span data-ttu-id="d7575-146">最初に、次のConferenceAutoAttendantConfiguration.ps1します。</span><span class="sxs-lookup"><span data-stu-id="d7575-146">First review the ConferenceAutoAttendantConfiguration.ps1 script.</span></span> <span data-ttu-id="d7575-147">次のように、LyncPerfTool 構成ツールに入力して構成を生成するために、ConferencingAutoAttendant 電話番号 (既定では 11211111111) をメモする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d7575-147">You'll want to take note of the ConferencingAutoAttendant phone number (1121111111 by default), so that you can enter it into the LyncPerfTool configuration tool for configuration generation, as below:</span></span>
  
![[音声シナリオ] タブに電話会議の負荷レベルと電話番号が表示されます。](../../media/a3ea5fc0-8b3d-4842-b809-f137f470dbdc.png)
  
<span data-ttu-id="d7575-149">詳細については、電話会議とダイヤルイン会議のコマンドレットを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7575-149">You'll find more details in the Conferencing and Dial-in Conferencing cmdlets.</span></span>
  
## <a name="server-call-park-service"></a><span data-ttu-id="d7575-150">サーバー コール パーク サービス</span><span class="sxs-lookup"><span data-stu-id="d7575-150">Server Call Park service</span></span>
<span data-ttu-id="d7575-151"><a name="ServerCallParkServ"> </a></span><span class="sxs-lookup"><span data-stu-id="d7575-151"><a name="ServerCallParkServ"> </a></span></span>

<span data-ttu-id="d7575-152">これは、既定では実際には無効になっています。</span><span class="sxs-lookup"><span data-stu-id="d7575-152">This is actually disabled by default.</span></span> <span data-ttu-id="d7575-153">テストする必要がある場合CallParkConfiguration.ps1サンプル スクリプトを確認できます。</span><span class="sxs-lookup"><span data-stu-id="d7575-153">You can review the CallParkConfiguration.ps1 sample script if you need to test this.</span></span> <span data-ttu-id="d7575-154">さらに、コール パーク アプリケーションのコマンドレットを必要に応じて確認してください。</span><span class="sxs-lookup"><span data-stu-id="d7575-154">Additionally, check out the Call Park Application cmdlets as needed.</span></span>
  
## <a name="emergency-calls"></a><span data-ttu-id="d7575-155">緊急電話</span><span class="sxs-lookup"><span data-stu-id="d7575-155">Emergency calls</span></span>
<span data-ttu-id="d7575-156"><a name="EmergencyCalls"> </a></span><span class="sxs-lookup"><span data-stu-id="d7575-156"><a name="EmergencyCalls"> </a></span></span>

<span data-ttu-id="d7575-157">緊急電話のストレステストとパフォーマンス テストを構成するには、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d7575-157">You'll need to perform the following steps to configure stress and performance testing for emergency calls:</span></span>
  
1. <span data-ttu-id="d7575-158">緊急電話のボイス ルートを設定します。</span><span class="sxs-lookup"><span data-stu-id="d7575-158">Set up a voice route for emergency calls.</span></span> <span data-ttu-id="d7575-159">このボイス ルートの設定RoutingRules.ps1、"Route **E911 to PSTN"** というコメントの下で確認できます。</span><span class="sxs-lookup"><span data-stu-id="d7575-159">You can use the RoutingRules.ps1 script, and check under the comment " **Route E911 to PSTN** " for an example of how to set up this voice route.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="d7575-160">次のコマンド例RoutingRules.ps1 911 ではなく番号 119 を含む番号パターンです。</span><span class="sxs-lookup"><span data-stu-id="d7575-160">The example command in RoutingRules.ps1 has a number pattern that includes the number 119 rather than 911.</span></span> <span data-ttu-id="d7575-161">負荷テスト中に、911 (または実際のローカル緊急電話番号) を使用して、ローカルの緊急オペレーターへの偶発的な呼び出しを防ぐ必要があります。</span><span class="sxs-lookup"><span data-stu-id="d7575-161">You should avoid using 911 (or your actual local emergency number) to prevent accidental calls to your local emergency operators during your load testing.</span></span> <span data-ttu-id="d7575-162">この構成はシミュレーションのみを目的とします。</span><span class="sxs-lookup"><span data-stu-id="d7575-162">Remember, this configuration is for simulation purposes only!</span></span> 
  
2. <span data-ttu-id="d7575-163">次の図に示すように、UserProvisioningTool の **[Location Info Service Config]** タブの値を入力して、アドレスを構成します。</span><span class="sxs-lookup"><span data-stu-id="d7575-163">Configure addresses by filling in the values on the **Location Info Service Config** tab in the UserProvisioningTool, as shown in the following figure:</span></span>
    
     ![アドレス、サブネット、スイッチ、およびポートの数を示すユーザー プロビジョニング ツール。](../../media/ebe85a0c-750f-4301-97d4-d158a40ea98a.png)
  
3. <span data-ttu-id="d7575-165">UserProvisioningTool にすべてを入力した後、[LIS 構成ファイルの生成] **ボタンをクリック** します。</span><span class="sxs-lookup"><span data-stu-id="d7575-165">When you've entered everything into the UserProvisioningTool, click the **Generate LIS Config Files** button.</span></span>
    
4. <span data-ttu-id="d7575-166">ポート、サブネット、スイッチ、ワイヤレス アクセス ポイント (WAP) 用の CSV ファイルと、Stress and Performance ツール用の XML ファイルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="d7575-166">Now CSV files for ports, subnets, switches, and wireless access points (WAPs), as well as an XML file for the Stress and Performance tool will be generated.</span></span> <span data-ttu-id="d7575-167">このスクリプトを使用して場所情報サービス (LIS) を構成する場合は、入力に CSV ファイルLisConfiguration.ps1できます。</span><span class="sxs-lookup"><span data-stu-id="d7575-167">You can use the CSV files for inputs when configuring the Location Information service (LIS) with the LisConfiguration.ps1 script.</span></span> <span data-ttu-id="d7575-168">これを行うには、Locations0.xml ファイルを Stress and Performance Tool 実行可能ファイル (LyncPerfTool.exe) と同じフォルダーに移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d7575-168">To do this, you'll need to move the Locations0.xml file to the same folder as the Stress and Performance Tool executable (LyncPerfTool.exe).</span></span> <span data-ttu-id="d7575-169">これにより、場所プロファイル (ダイヤル プラン) のシナリオを実行できます。</span><span class="sxs-lookup"><span data-stu-id="d7575-169">This will let you run location profile (dial plan) scenarios.</span></span>
    
## <a name="configuring-response-group-application"></a><span data-ttu-id="d7575-170">応答グループ アプリケーションの構成</span><span class="sxs-lookup"><span data-stu-id="d7575-170">Configuring Response Group application</span></span>
<span data-ttu-id="d7575-171"><a name="ConfigResponseGroupApp"> </a></span><span class="sxs-lookup"><span data-stu-id="d7575-171"><a name="ConfigResponseGroupApp"> </a></span></span>

<span data-ttu-id="d7575-172">サンプル スクリプトは次ResponseGroupConfiguration.ps1。</span><span class="sxs-lookup"><span data-stu-id="d7575-172">The sample script is ResponseGroupConfiguration.ps1.</span></span> <span data-ttu-id="d7575-173">さらに構成の詳細を確認する応答グループ アプリケーションコマンドレットも用意されています。</span><span class="sxs-lookup"><span data-stu-id="d7575-173">There are also Response Group application cmdlets to review for further configuration details.</span></span> <span data-ttu-id="d7575-174">次の図は、構成の詳細の一部を示しています。</span><span class="sxs-lookup"><span data-stu-id="d7575-174">The following diagram will show some of the configuration details:</span></span>
  
![テスト用の既存のワークフローを示す応答グループ構成ツール。](../../media/e218a345-4813-4332-8cff-b48de05017ef.jpg)
  

