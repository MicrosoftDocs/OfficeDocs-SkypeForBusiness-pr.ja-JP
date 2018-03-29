---
title: Skype for Business Server 2015 との相互運用に対応した VTC の構成
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1016aed6-99fe-452e-8b20-81c814808c3d
description: '概要: ビジネス サーバー 2015 の Skype 上で動作する VTC のデバイスを構成します。'
ms.openlocfilehash: a88f34866a2a2147be0f30488e961552c6f19350
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="configure-a-vtc-for-interoperation-with-skype-for-business-server-2015"></a><span data-ttu-id="03558-103">Skype for Business Server 2015 との相互運用に対応した VTC の構成</span><span class="sxs-lookup"><span data-stu-id="03558-103">Configure a VTC for Interoperation with Skype for Business Server 2015</span></span>
 
<span data-ttu-id="03558-104">**の概要:**ビジネス サーバー 2015 の Skype 上で動作する VTC のデバイスを構成します。</span><span class="sxs-lookup"><span data-stu-id="03558-104">**Summary:** Configure the VTC devices to work with Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="03558-105">SIP トランクと CUCM ビデオ ゲートウェイ経由で Skype for Business VIS サーバーに接続する各 VTC に対して、以下の構成カスタマイズ手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="03558-105">You will need to perform the following configuration customization procedures for each VTC that will connect to the Skype for Business VIS server through a SIP trunk and CUCM video gateway.</span></span>
  
<span data-ttu-id="03558-106">ここで説明する設定は、CUCM を構成する方法の例として、VIS. を操作するには</span><span class="sxs-lookup"><span data-stu-id="03558-106">The settings described here are meant only as examples of how CUCM can be configured to work with a VIS.</span></span> <span data-ttu-id="03558-107">CUCM の別の機能を他の方法で設定/使用して同じ結果を実現することもできます。</span><span class="sxs-lookup"><span data-stu-id="03558-107">Other settings and/or usages of alternate CUCM functionality could also be used to achieve the same result.</span></span> <span data-ttu-id="03558-108">特定のシナリオに最適な構成について推奨するものではありません。</span><span class="sxs-lookup"><span data-stu-id="03558-108">No recommendation is implied as to the optimal configuration for a particular scenario.</span></span>
  
### <a name="configure-a-vtc-registered-with-cucm"></a><span data-ttu-id="03558-109">CUCM を使用して登録された VTC を構成する</span><span class="sxs-lookup"><span data-stu-id="03558-109">Configure a VTC registered with CUCM</span></span>

1. <span data-ttu-id="03558-110">VTC の Cisco デバイスにログインし、構成に移動\>システムの構成 -\>プロビジョニングします。</span><span class="sxs-lookup"><span data-stu-id="03558-110">Log in to the Cisco VTC device and navigate to Configuration-\>System Configuration-\>Provisioning.</span></span>
    
2. <span data-ttu-id="03558-111">次の設定を確認し、必要に応じて修正します。</span><span class="sxs-lookup"><span data-stu-id="03558-111">Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="03558-112">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="03558-112">**Parameter**</span></span>|<span data-ttu-id="03558-113">**推奨設定**</span><span class="sxs-lookup"><span data-stu-id="03558-113">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="03558-114">Provisioning Mode</span><span class="sxs-lookup"><span data-stu-id="03558-114">Provisioning Mode</span></span>  <br/> | <span data-ttu-id="03558-115">CUCM</span><span class="sxs-lookup"><span data-stu-id="03558-115">CUCM</span></span> <br/> |
   |<span data-ttu-id="03558-116">ExternalManager Address</span><span class="sxs-lookup"><span data-stu-id="03558-116">ExternalManager Address</span></span>  <br/> | <span data-ttu-id="03558-117">CUCM の FQDN</span><span class="sxs-lookup"><span data-stu-id="03558-117">CUCM's FQDN</span></span> <br/> |
   | <span data-ttu-id="03558-118">ExternalManager ドメイン</span><span class="sxs-lookup"><span data-stu-id="03558-118">ExternalManager Domain</span></span> <br/> |<span data-ttu-id="03558-119">CUCM のドメイン</span><span class="sxs-lookup"><span data-stu-id="03558-119">CUCM's domain</span></span>  <br/> |
   
3. <span data-ttu-id="03558-120">構成 - に移動\>システムの構成 -\>ネットワークです。</span><span class="sxs-lookup"><span data-stu-id="03558-120">Navigate to Configuration-\>System Configuration-\>Network.</span></span>
    
4. <span data-ttu-id="03558-121">次の設定を確認し、必要に応じて修正します。</span><span class="sxs-lookup"><span data-stu-id="03558-121">Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="03558-122">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="03558-122">**Parameter**</span></span>|<span data-ttu-id="03558-123">**推奨設定**</span><span class="sxs-lookup"><span data-stu-id="03558-123">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="03558-124">DNS Domain Name</span><span class="sxs-lookup"><span data-stu-id="03558-124">DNS Domain Name</span></span>  <br/> | <span data-ttu-id="03558-125">CUCM のドメイン名</span><span class="sxs-lookup"><span data-stu-id="03558-125">CUCM's Domain name</span></span> <br/> |
   |<span data-ttu-id="03558-126">DNS Server 1 Address</span><span class="sxs-lookup"><span data-stu-id="03558-126">DNS Server 1 Address</span></span>  <br/> | <span data-ttu-id="03558-127">目的の DNS サーバー アドレス</span><span class="sxs-lookup"><span data-stu-id="03558-127">your desired DNS server address</span></span> <br/> |
   
5. <span data-ttu-id="03558-128">構成 - に移動\>システムの構成 -\>ネットワーク サービスです。</span><span class="sxs-lookup"><span data-stu-id="03558-128">Navigate to Configuration-\>System Configuration-\>Network Services.</span></span> <span data-ttu-id="03558-129">H.323 モードがオフで、SIP モードがオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="03558-129">Ensure that H.323 mode is turned off and SIP mode is turned on.</span></span> 
    
6. <span data-ttu-id="03558-p103">これらのオプションは、CUCM を使用してエンドポイントを登録すると、自動的に設定されます。次の設定を確認し、必要に応じて修正します。</span><span class="sxs-lookup"><span data-stu-id="03558-p103">These options are set automatically when the endpoint is registered with CUCM. Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="03558-132">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="03558-132">**Parameter**</span></span>|<span data-ttu-id="03558-133">**推奨設定**</span><span class="sxs-lookup"><span data-stu-id="03558-133">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="03558-134">H.323 Mode</span><span class="sxs-lookup"><span data-stu-id="03558-134">H.323 Mode</span></span>  <br/> | <span data-ttu-id="03558-135">オフ</span><span class="sxs-lookup"><span data-stu-id="03558-135">Off</span></span> <br/> |
   |<span data-ttu-id="03558-136">HTTP Mode</span><span class="sxs-lookup"><span data-stu-id="03558-136">HTTP Mode</span></span>  <br/> | <span data-ttu-id="03558-137">オン</span><span class="sxs-lookup"><span data-stu-id="03558-137">On</span></span> <br/> |
   | <span data-ttu-id="03558-138">SIP Mode</span><span class="sxs-lookup"><span data-stu-id="03558-138">SIP Mode</span></span> <br/> | <span data-ttu-id="03558-139">オン</span><span class="sxs-lookup"><span data-stu-id="03558-139">On</span></span> <br/> |
   |<span data-ttu-id="03558-140">Telnet Mode</span><span class="sxs-lookup"><span data-stu-id="03558-140">Telnet Mode</span></span>  <br/> | <span data-ttu-id="03558-141">オン</span><span class="sxs-lookup"><span data-stu-id="03558-141">On</span></span> <br/> |
   |<span data-ttu-id="03558-142">WelcomeText</span><span class="sxs-lookup"><span data-stu-id="03558-142">WelcomeText</span></span>  <br/> | <span data-ttu-id="03558-143">オン</span><span class="sxs-lookup"><span data-stu-id="03558-143">On</span></span> <br/> |
   |<span data-ttu-id="03558-144">XMLAPI Mode</span><span class="sxs-lookup"><span data-stu-id="03558-144">XMLAPI Mode</span></span>  <br/> | <span data-ttu-id="03558-145">オン</span><span class="sxs-lookup"><span data-stu-id="03558-145">On</span></span> <br/> |
   
7. <span data-ttu-id="03558-146">構成 - に移動\>システムの構成 -\>SIP。</span><span class="sxs-lookup"><span data-stu-id="03558-146">Navigate to Configuration-\>System Configuration-\>SIP.</span></span>
    
8. <span data-ttu-id="03558-147">次の設定を確認し、必要に応じて修正します。</span><span class="sxs-lookup"><span data-stu-id="03558-147">Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="03558-148">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="03558-148">**Parameter**</span></span>|<span data-ttu-id="03558-149">**推奨設定**</span><span class="sxs-lookup"><span data-stu-id="03558-149">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="03558-150">Profile 1 - DefaultTransport</span><span class="sxs-lookup"><span data-stu-id="03558-150">Profile 1 - DefaultTransport</span></span>  <br/> | <span data-ttu-id="03558-151">TCP</span><span class="sxs-lookup"><span data-stu-id="03558-151">TCP</span></span> <br/> |
   |<span data-ttu-id="03558-152">Profile 1 - Outbound</span><span class="sxs-lookup"><span data-stu-id="03558-152">Profile 1 - Outbound</span></span>  <br/> | <span data-ttu-id="03558-153">オフ</span><span class="sxs-lookup"><span data-stu-id="03558-153">Off</span></span> <br/> |
   |<span data-ttu-id="03558-154">プロファイル 1 - TlsVerify</span><span class="sxs-lookup"><span data-stu-id="03558-154">Profile 1 - TlsVerify</span></span>  <br/> | <span data-ttu-id="03558-155">オン</span><span class="sxs-lookup"><span data-stu-id="03558-155">On</span></span> <br/> |
   |<span data-ttu-id="03558-156">Profile 1 - Type</span><span class="sxs-lookup"><span data-stu-id="03558-156">Profile 1 - Type</span></span>  <br/> | <span data-ttu-id="03558-157">Cisco</span><span class="sxs-lookup"><span data-stu-id="03558-157">Cisco</span></span> <br/> |
   |<span data-ttu-id="03558-158">Profile 1 - URI</span><span class="sxs-lookup"><span data-stu-id="03558-158">Profile 1 - URI</span></span>  <br/> | <span data-ttu-id="03558-159">CUCM 登録時に自動割り当て</span><span class="sxs-lookup"><span data-stu-id="03558-159">Automatically assigned at CUCM registration</span></span> <br/> |
   |<span data-ttu-id="03558-160">Proxy 1 - Address</span><span class="sxs-lookup"><span data-stu-id="03558-160">Proxy 1 - Address</span></span>  <br/> |<span data-ttu-id="03558-161">CUCM のホスト名</span><span class="sxs-lookup"><span data-stu-id="03558-161">The host name of the CUCM</span></span>  <br/> |
   
<span data-ttu-id="03558-p104">これで、VTC が相互運用するように構成されました。サービスを開始する前に、CUCM 側で最後の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="03558-p104">The VTC is now configured for interoperation. Before service can begin, there are final steps to perform on the CUCM side.</span></span>
### <a name="configure-vtc-devices-on-cucm"></a><span data-ttu-id="03558-164">CUCM で VTC デバイスを構成する</span><span class="sxs-lookup"><span data-stu-id="03558-164">Configure VTC devices on CUCM</span></span>

1. <span data-ttu-id="03558-165">CUCM にログインに移動し、Cisco の統合管理 - CM\>デバイス ・\>電話 -\>を検索します。</span><span class="sxs-lookup"><span data-stu-id="03558-165">Log in to CUCM and Navigate to Cisco Unified CM Administration-\>Device-\>Phone-\>Find.</span></span> 
    
2. <span data-ttu-id="03558-p105">構成する VTC デバイスを選択します。[Phone Configuration] 画面で以下の設定を確認し、必要に応じて修正します。これらの設定の変更または確認が完了したら、[**Save**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="03558-p105">Select the VTC device to be configured. Verify the following settings on the Phone Configuration screen, correcting as needed. Once these settings have been changed or verified, click on **Save**.</span></span>
    
   |<span data-ttu-id="03558-169">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="03558-169">**Parameter**</span></span>|<span data-ttu-id="03558-170">**推奨設定**</span><span class="sxs-lookup"><span data-stu-id="03558-170">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="03558-171">Device Information - Phone Button Template</span><span class="sxs-lookup"><span data-stu-id="03558-171">Device Information - Phone Button Template</span></span>  <br/> | <span data-ttu-id="03558-172">標準的な Cisco Telepresence コーデック C40</span><span class="sxs-lookup"><span data-stu-id="03558-172">Standard Cisco Telepresence Codec C40</span></span> <br/> |
   |<span data-ttu-id="03558-173">Device Information - Common Phone Profile</span><span class="sxs-lookup"><span data-stu-id="03558-173">Device Information - Common Phone Profile</span></span>  <br/> | <span data-ttu-id="03558-174">Standard Common Phone Profile</span><span class="sxs-lookup"><span data-stu-id="03558-174">Standard Common Phone Profile</span></span> <br/> |
   |<span data-ttu-id="03558-175">Device Information - Calling Search Space</span><span class="sxs-lookup"><span data-stu-id="03558-175">Device Information - Calling Search Space</span></span>  <br/> | <span data-ttu-id="03558-176">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="03558-176">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="03558-177">Device Information - AAR Calling Search Space</span><span class="sxs-lookup"><span data-stu-id="03558-177">Device Information - AAR Calling Search Space</span></span>  <br/> | <span data-ttu-id="03558-178">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="03558-178">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="03558-179">Device Information - Media Resource Group List</span><span class="sxs-lookup"><span data-stu-id="03558-179">Device Information - Media Resource Group List</span></span>  <br/> | <span data-ttu-id="03558-180">MRGL_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="03558-180">MRGL_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="03558-181">Protocol Specific Information - Device Security Profile</span><span class="sxs-lookup"><span data-stu-id="03558-181">Protocol Specific Information - Device Security Profile</span></span>  <br/> | <span data-ttu-id="03558-182">Cisco Telepresence コーデック C40</span><span class="sxs-lookup"><span data-stu-id="03558-182">Cisco Telepresence Codec C40</span></span> <br/> |
   |<span data-ttu-id="03558-183">Protocol Specific Information - Rerouting Calling Search Space</span><span class="sxs-lookup"><span data-stu-id="03558-183">Protocol Specific Information - Rerouting Calling Search Space</span></span>  <br/> | <span data-ttu-id="03558-184">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="03558-184">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="03558-185">プロトコル固有の情報 - 検索の領域を呼び出す</span><span class="sxs-lookup"><span data-stu-id="03558-185">Protocol Specific Information - SUBSCRIBE Calling Search Space</span></span>  <br/> | <span data-ttu-id="03558-186">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="03558-186">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="03558-187">Protocol Specific Information - SIP Profile</span><span class="sxs-lookup"><span data-stu-id="03558-187">Protocol Specific Information -SIP Profile</span></span>  <br/> | <span data-ttu-id="03558-188">Standard SIP Profile for Telepresence Endpoint</span><span class="sxs-lookup"><span data-stu-id="03558-188">Standard SIP Profile for Telepresence Endpoint</span></span> <br/> |
   
3. <span data-ttu-id="03558-189">VTC 構成を保存したら、デバイスの [Phone Configuration] 画面にもう一度移動します。</span><span class="sxs-lookup"><span data-stu-id="03558-189">Once VTC configuration is saved, re-navigate to the Phone Configuration screen for the device.</span></span> <span data-ttu-id="03558-190">Association グループの画面の上部で、ビデオ相互運用の関連付けをクリックします。</span><span class="sxs-lookup"><span data-stu-id="03558-190">At the top of the screen in the Association group, click on the association for the Video Interop.</span></span> <span data-ttu-id="03558-191">この操作を行うと、[Directory Number Configuration] 画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="03558-191">This brings up the Directory Number Configuration screen.</span></span> 
    
4. <span data-ttu-id="03558-192">次の設定を確認し、必要に応じて修正します。</span><span class="sxs-lookup"><span data-stu-id="03558-192">Verify the following settings, correcting as needed:</span></span> 
    
    <span data-ttu-id="03558-193">次に示すように、[Directory Number Information] と [Directory Number Settings] を適切に変更します。</span><span class="sxs-lookup"><span data-stu-id="03558-193">Make the appropriate changes as shown to the Directory Number Information and the Directory Number Settings.</span></span>
    
   |<span data-ttu-id="03558-194">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="03558-194">**Parameter**</span></span>|<span data-ttu-id="03558-195">**推奨設定**</span><span class="sxs-lookup"><span data-stu-id="03558-195">**Recommended setting**</span></span>|
   |:-----|:-----|
   | <span data-ttu-id="03558-196">Directory Number Information - Route Partition</span><span class="sxs-lookup"><span data-stu-id="03558-196">Directory Number Information - Route Partition</span></span> <br/> | <span data-ttu-id="03558-197">SfBVideoInterop_RoutePartition</span><span class="sxs-lookup"><span data-stu-id="03558-197">SfBVideoInterop_RoutePartition</span></span> <br/> |
   |<span data-ttu-id="03558-198">Directory Number Settings - Calling Search Space</span><span class="sxs-lookup"><span data-stu-id="03558-198">Directory Number Settings - Calling Search Space</span></span>  <br/> | <span data-ttu-id="03558-199">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="03558-199">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="03558-200">MLPP Alternate Party and Confidential Access Level Settings - MLPP Calling Search Space</span><span class="sxs-lookup"><span data-stu-id="03558-200">MLPP Alternate Party and Confidential Access Level Settings - MLPP Calling Search Space</span></span>  <br/> | <span data-ttu-id="03558-201">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="03558-201">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="03558-202">デバイスの表示 (呼び出し元 ID) の 1 を行します。</span><span class="sxs-lookup"><span data-stu-id="03558-202">Line 1 on Device - Display (Caller ID)</span></span>  <br/> | <span data-ttu-id="03558-203">自由に設定</span><span class="sxs-lookup"><span data-stu-id="03558-203">As desired</span></span> <br/> |
   |<span data-ttu-id="03558-204">ASCII 表示 (呼び出し元 ID) のデバイス上の 1 を行します。</span><span class="sxs-lookup"><span data-stu-id="03558-204">Line 1 on Device - ASCII Display (Caller ID)</span></span>  <br/> | <span data-ttu-id="03558-205">自由に設定</span><span class="sxs-lookup"><span data-stu-id="03558-205">As desired</span></span> <br/> |
   
5. <span data-ttu-id="03558-206">変更が完了したら、画面の上部までスクロールし、[**Save**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="03558-206">When finished, scroll to the top of the screen and press **Save**.</span></span> 
    
<span data-ttu-id="03558-p107">これで、この VTC デバイスの構成が完了しました。社内の他の VTC デバイスに対して、このプロセスを繰り返してください。</span><span class="sxs-lookup"><span data-stu-id="03558-p107">Configuration is now complete for this VTC device. You will need to repeat this process for other VTC devices in your enterprise.</span></span>

