---
title: Skype for Business Server との相互運用のための VTC の構成
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1016aed6-99fe-452e-8b20-81c814808c3d
description: '概要: Skype for Business Server で動作する VTC デバイスを構成します。'
ms.openlocfilehash: 7697fd9f33a4fece4871b056a05264ece888d357
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802077"
---
# <a name="configure-a-vtc-for-interoperation-with-skype-for-business-server"></a><span data-ttu-id="5c1f1-103">Skype for Business Server との相互運用のための VTC の構成</span><span class="sxs-lookup"><span data-stu-id="5c1f1-103">Configure a VTC for Interoperation with Skype for Business Server</span></span>
 
<span data-ttu-id="5c1f1-104">**概要:** Skype for Business Server で動作する VTC デバイスを構成します。</span><span class="sxs-lookup"><span data-stu-id="5c1f1-104">**Summary:** Configure the VTC devices to work with Skype for Business Server.</span></span>
  
<span data-ttu-id="5c1f1-105">SIP トランクと Cisco Unified Communications Manager (CallManager または CUCM) ビデオ ゲートウェイを介して Skype for Business VIS サーバーに接続する各 VTC に対して、次の構成カスタマイズ手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c1f1-105">You will need to perform the following configuration customization procedures for each VTC that will connect to the Skype for Business VIS server through a SIP trunk and Cisco Unified Communications Manager (CallManager, or CUCM) video gateway.</span></span>
  
<span data-ttu-id="5c1f1-106">ここで説明する設定は、VIS で動作するように CUCM を構成する方法の例としてのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="5c1f1-106">The settings described here are meant only as examples of how CUCM can be configured to work with a VIS.</span></span> <span data-ttu-id="5c1f1-107">代替 CUCM 機能のその他の設定や使用法も、同じ結果を得る目的で使用できます。</span><span class="sxs-lookup"><span data-stu-id="5c1f1-107">Other settings and/or usages of alternate CUCM functionality could also be used to achieve the same result.</span></span> <span data-ttu-id="5c1f1-108">特定のシナリオに最適な構成に関する推奨事項は示されていません。</span><span class="sxs-lookup"><span data-stu-id="5c1f1-108">No recommendation is implied as to the optimal configuration for a particular scenario.</span></span>
  
### <a name="configure-a-vtc-registered-with-cucm"></a><span data-ttu-id="5c1f1-109">CUCM に登録された VTC を構成する</span><span class="sxs-lookup"><span data-stu-id="5c1f1-109">Configure a VTC registered with CUCM</span></span>

1. <span data-ttu-id="5c1f1-110">Cisco VTC デバイスにログインし、[Configuration- \> System Configuration- \> Provisioning] に移動します。</span><span class="sxs-lookup"><span data-stu-id="5c1f1-110">Log in to the Cisco VTC device and navigate to Configuration-\>System Configuration-\>Provisioning.</span></span>
    
2. <span data-ttu-id="5c1f1-111">次の設定を確認し、必要に応じて修正します。</span><span class="sxs-lookup"><span data-stu-id="5c1f1-111">Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="5c1f1-112">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="5c1f1-112">**Parameter**</span></span>|<span data-ttu-id="5c1f1-113">**推奨される設定値**</span><span class="sxs-lookup"><span data-stu-id="5c1f1-113">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="5c1f1-114">プロビジョニング モード</span><span class="sxs-lookup"><span data-stu-id="5c1f1-114">Provisioning Mode</span></span>  <br/> | <span data-ttu-id="5c1f1-115">CUCM</span><span class="sxs-lookup"><span data-stu-id="5c1f1-115">CUCM</span></span> <br/> |
   |<span data-ttu-id="5c1f1-116">ExternalManager アドレス</span><span class="sxs-lookup"><span data-stu-id="5c1f1-116">ExternalManager Address</span></span>  <br/> | <span data-ttu-id="5c1f1-117">CUCM の FQDN</span><span class="sxs-lookup"><span data-stu-id="5c1f1-117">CUCM's FQDN</span></span> <br/> |
   | <span data-ttu-id="5c1f1-118">ExternalManager ドメイン</span><span class="sxs-lookup"><span data-stu-id="5c1f1-118">ExternalManager Domain</span></span> <br/> |<span data-ttu-id="5c1f1-119">CUCM のドメイン</span><span class="sxs-lookup"><span data-stu-id="5c1f1-119">CUCM's domain</span></span>  <br/> |
   
3. <span data-ttu-id="5c1f1-120">[構成- システム構成 \> - ネットワーク] \> に移動します。</span><span class="sxs-lookup"><span data-stu-id="5c1f1-120">Navigate to Configuration-\>System Configuration-\>Network.</span></span>
    
4. <span data-ttu-id="5c1f1-121">次の設定を確認し、必要に応じて修正します。</span><span class="sxs-lookup"><span data-stu-id="5c1f1-121">Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="5c1f1-122">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="5c1f1-122">**Parameter**</span></span>|<span data-ttu-id="5c1f1-123">**推奨される設定値**</span><span class="sxs-lookup"><span data-stu-id="5c1f1-123">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="5c1f1-124">DNS ドメイン名</span><span class="sxs-lookup"><span data-stu-id="5c1f1-124">DNS Domain Name</span></span>  <br/> | <span data-ttu-id="5c1f1-125">CUCM のドメイン名</span><span class="sxs-lookup"><span data-stu-id="5c1f1-125">CUCM's Domain name</span></span> <br/> |
   |<span data-ttu-id="5c1f1-126">DNS サーバー 1 のアドレス</span><span class="sxs-lookup"><span data-stu-id="5c1f1-126">DNS Server 1 Address</span></span>  <br/> | <span data-ttu-id="5c1f1-127">目的の DNS サーバー アドレス</span><span class="sxs-lookup"><span data-stu-id="5c1f1-127">your desired DNS server address</span></span> <br/> |
   
5. <span data-ttu-id="5c1f1-128">[構成- システム構成 \> - ネットワーク \> サービス] に移動します。</span><span class="sxs-lookup"><span data-stu-id="5c1f1-128">Navigate to Configuration-\>System Configuration-\>Network Services.</span></span> <span data-ttu-id="5c1f1-129">H.323 モードがオフで、SIP モードがオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5c1f1-129">Ensure that H.323 mode is turned off and SIP mode is turned on.</span></span> 
    
6. <span data-ttu-id="5c1f1-130">これらのオプションは、エンドポイントが CUCM に登録されている場合に自動的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="5c1f1-130">These options are set automatically when the endpoint is registered with CUCM.</span></span> <span data-ttu-id="5c1f1-131">次の設定を確認し、必要に応じて修正します。</span><span class="sxs-lookup"><span data-stu-id="5c1f1-131">Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="5c1f1-132">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="5c1f1-132">**Parameter**</span></span>|<span data-ttu-id="5c1f1-133">**推奨される設定値**</span><span class="sxs-lookup"><span data-stu-id="5c1f1-133">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="5c1f1-134">H.323 モード</span><span class="sxs-lookup"><span data-stu-id="5c1f1-134">H.323 Mode</span></span>  <br/> | <span data-ttu-id="5c1f1-135">オフ</span><span class="sxs-lookup"><span data-stu-id="5c1f1-135">Off</span></span> <br/> |
   |<span data-ttu-id="5c1f1-136">HTTP モード</span><span class="sxs-lookup"><span data-stu-id="5c1f1-136">HTTP Mode</span></span>  <br/> | <span data-ttu-id="5c1f1-137">オン</span><span class="sxs-lookup"><span data-stu-id="5c1f1-137">On</span></span> <br/> |
   | <span data-ttu-id="5c1f1-138">SIP モード</span><span class="sxs-lookup"><span data-stu-id="5c1f1-138">SIP Mode</span></span> <br/> | <span data-ttu-id="5c1f1-139">オン</span><span class="sxs-lookup"><span data-stu-id="5c1f1-139">On</span></span> <br/> |
   |<span data-ttu-id="5c1f1-140">Telnet モード</span><span class="sxs-lookup"><span data-stu-id="5c1f1-140">Telnet Mode</span></span>  <br/> | <span data-ttu-id="5c1f1-141">オン</span><span class="sxs-lookup"><span data-stu-id="5c1f1-141">On</span></span> <br/> |
   |<span data-ttu-id="5c1f1-142">WelcomeText</span><span class="sxs-lookup"><span data-stu-id="5c1f1-142">WelcomeText</span></span>  <br/> | <span data-ttu-id="5c1f1-143">オン</span><span class="sxs-lookup"><span data-stu-id="5c1f1-143">On</span></span> <br/> |
   |<span data-ttu-id="5c1f1-144">XMLAPI モード</span><span class="sxs-lookup"><span data-stu-id="5c1f1-144">XMLAPI Mode</span></span>  <br/> | <span data-ttu-id="5c1f1-145">オン</span><span class="sxs-lookup"><span data-stu-id="5c1f1-145">On</span></span> <br/> |
   
7. <span data-ttu-id="5c1f1-146">[構成- システム構成- \> \> SIP] に移動します。</span><span class="sxs-lookup"><span data-stu-id="5c1f1-146">Navigate to Configuration-\>System Configuration-\>SIP.</span></span>
    
8. <span data-ttu-id="5c1f1-147">次の設定を確認し、必要に応じて修正します。</span><span class="sxs-lookup"><span data-stu-id="5c1f1-147">Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="5c1f1-148">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="5c1f1-148">**Parameter**</span></span>|<span data-ttu-id="5c1f1-149">**推奨される設定値**</span><span class="sxs-lookup"><span data-stu-id="5c1f1-149">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="5c1f1-150">プロファイル 1 - DefaultTransport</span><span class="sxs-lookup"><span data-stu-id="5c1f1-150">Profile 1 - DefaultTransport</span></span>  <br/> | <span data-ttu-id="5c1f1-151">TCP</span><span class="sxs-lookup"><span data-stu-id="5c1f1-151">TCP</span></span> <br/> |
   |<span data-ttu-id="5c1f1-152">プロファイル 1 - 送信</span><span class="sxs-lookup"><span data-stu-id="5c1f1-152">Profile 1 - Outbound</span></span>  <br/> | <span data-ttu-id="5c1f1-153">オフ</span><span class="sxs-lookup"><span data-stu-id="5c1f1-153">Off</span></span> <br/> |
   |<span data-ttu-id="5c1f1-154">プロファイル 1 - TlsVerify</span><span class="sxs-lookup"><span data-stu-id="5c1f1-154">Profile 1 - TlsVerify</span></span>  <br/> | <span data-ttu-id="5c1f1-155">オン</span><span class="sxs-lookup"><span data-stu-id="5c1f1-155">On</span></span> <br/> |
   |<span data-ttu-id="5c1f1-156">プロファイル 1 - 種類</span><span class="sxs-lookup"><span data-stu-id="5c1f1-156">Profile 1 - Type</span></span>  <br/> | <span data-ttu-id="5c1f1-157">Cisco</span><span class="sxs-lookup"><span data-stu-id="5c1f1-157">Cisco</span></span> <br/> |
   |<span data-ttu-id="5c1f1-158">プロファイル 1 - URI</span><span class="sxs-lookup"><span data-stu-id="5c1f1-158">Profile 1 - URI</span></span>  <br/> | <span data-ttu-id="5c1f1-159">CUCM 登録時に自動的に割り当てられる</span><span class="sxs-lookup"><span data-stu-id="5c1f1-159">Automatically assigned at CUCM registration</span></span> <br/> |
   |<span data-ttu-id="5c1f1-160">プロキシ 1 - アドレス</span><span class="sxs-lookup"><span data-stu-id="5c1f1-160">Proxy 1 - Address</span></span>  <br/> |<span data-ttu-id="5c1f1-161">CUCM のホスト名</span><span class="sxs-lookup"><span data-stu-id="5c1f1-161">The host name of the CUCM</span></span>  <br/> |
   
<span data-ttu-id="5c1f1-162">これで、VTC が相互運用用に構成されます。</span><span class="sxs-lookup"><span data-stu-id="5c1f1-162">The VTC is now configured for interoperation.</span></span> <span data-ttu-id="5c1f1-163">サービスを開始する前に、CUCM 側で実行する最後の手順があります。</span><span class="sxs-lookup"><span data-stu-id="5c1f1-163">Before service can begin, there are final steps to perform on the CUCM side.</span></span>
### <a name="configure-vtc-devices-on-cucm"></a><span data-ttu-id="5c1f1-164">CUCM で VTC デバイスを構成する</span><span class="sxs-lookup"><span data-stu-id="5c1f1-164">Configure VTC devices on CUCM</span></span>

1. <span data-ttu-id="5c1f1-165">CUCM にログインし、[Cisco Unified CM Administration- \> Device- \> Phone- \> Find] に移動します。</span><span class="sxs-lookup"><span data-stu-id="5c1f1-165">Log in to CUCM and Navigate to Cisco Unified CM Administration-\>Device-\>Phone-\>Find.</span></span> 
    
2. <span data-ttu-id="5c1f1-166">構成する VTC デバイスを選択します。</span><span class="sxs-lookup"><span data-stu-id="5c1f1-166">Select the VTC device to be configured.</span></span> <span data-ttu-id="5c1f1-167">[電話の構成] 画面で次の設定を確認し、必要に応じて修正します。</span><span class="sxs-lookup"><span data-stu-id="5c1f1-167">Verify the following settings on the Phone Configuration screen, correcting as needed.</span></span> <span data-ttu-id="5c1f1-168">これらの設定を変更または確認したら、[保存] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="5c1f1-168">Once these settings have been changed or verified, click on **Save**.</span></span>
    
   |<span data-ttu-id="5c1f1-169">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="5c1f1-169">**Parameter**</span></span>|<span data-ttu-id="5c1f1-170">**推奨される設定値**</span><span class="sxs-lookup"><span data-stu-id="5c1f1-170">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="5c1f1-171">デバイス情報 - 電話ボタン テンプレート</span><span class="sxs-lookup"><span data-stu-id="5c1f1-171">Device Information - Phone Button Template</span></span>  <br/> | <span data-ttu-id="5c1f1-172">標準 Cisco Telepresence Codec C40</span><span class="sxs-lookup"><span data-stu-id="5c1f1-172">Standard Cisco Telepresence Codec C40</span></span> <br/> |
   |<span data-ttu-id="5c1f1-173">デバイス情報 - 共通電話プロファイル</span><span class="sxs-lookup"><span data-stu-id="5c1f1-173">Device Information - Common Phone Profile</span></span>  <br/> | <span data-ttu-id="5c1f1-174">Standard Common Phone Profile</span><span class="sxs-lookup"><span data-stu-id="5c1f1-174">Standard Common Phone Profile</span></span> <br/> |
   |<span data-ttu-id="5c1f1-175">デバイス情報 - 通話検索スペース</span><span class="sxs-lookup"><span data-stu-id="5c1f1-175">Device Information - Calling Search Space</span></span>  <br/> | <span data-ttu-id="5c1f1-176">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="5c1f1-176">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="5c1f1-177">デバイス情報 - AAR 通話検索スペース</span><span class="sxs-lookup"><span data-stu-id="5c1f1-177">Device Information - AAR Calling Search Space</span></span>  <br/> | <span data-ttu-id="5c1f1-178">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="5c1f1-178">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="5c1f1-179">デバイス情報 - メディア リソース グループの一覧</span><span class="sxs-lookup"><span data-stu-id="5c1f1-179">Device Information - Media Resource Group List</span></span>  <br/> | <span data-ttu-id="5c1f1-180">MRGL_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="5c1f1-180">MRGL_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="5c1f1-181">プロトコル固有の情報 - デバイス セキュリティ プロファイル</span><span class="sxs-lookup"><span data-stu-id="5c1f1-181">Protocol Specific Information - Device Security Profile</span></span>  <br/> | <span data-ttu-id="5c1f1-182">Cisco Telepresence Codec C40</span><span class="sxs-lookup"><span data-stu-id="5c1f1-182">Cisco Telepresence Codec C40</span></span> <br/> |
   |<span data-ttu-id="5c1f1-183">プロトコル固有の情報 - 呼び出し元の検索スペースの再ルーティング</span><span class="sxs-lookup"><span data-stu-id="5c1f1-183">Protocol Specific Information - Rerouting Calling Search Space</span></span>  <br/> | <span data-ttu-id="5c1f1-184">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="5c1f1-184">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="5c1f1-185">プロトコル固有の情報 - SUBSCRIBE Calling Search Space</span><span class="sxs-lookup"><span data-stu-id="5c1f1-185">Protocol Specific Information - SUBSCRIBE Calling Search Space</span></span>  <br/> | <span data-ttu-id="5c1f1-186">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="5c1f1-186">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="5c1f1-187">プロトコル固有の情報 -SIP プロファイル</span><span class="sxs-lookup"><span data-stu-id="5c1f1-187">Protocol Specific Information -SIP Profile</span></span>  <br/> | <span data-ttu-id="5c1f1-188">Telepresence エンドポイントの標準 SIP プロファイル</span><span class="sxs-lookup"><span data-stu-id="5c1f1-188">Standard SIP Profile for Telepresence Endpoint</span></span> <br/> |
   
3. <span data-ttu-id="5c1f1-189">VTC 構成を保存したら、デバイスの [電話の構成] 画面に再び移動します。</span><span class="sxs-lookup"><span data-stu-id="5c1f1-189">Once VTC configuration is saved, re-navigate to the Phone Configuration screen for the device.</span></span> <span data-ttu-id="5c1f1-190">関連付けグループの画面の上部で、ビデオ相互運用機能の関連付けをクリックします。</span><span class="sxs-lookup"><span data-stu-id="5c1f1-190">At the top of the screen in the Association group, click on the association for the Video Interop.</span></span> <span data-ttu-id="5c1f1-191">これにより、[ディレクトリ番号の構成] 画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5c1f1-191">This brings up the Directory Number Configuration screen.</span></span> 
    
4. <span data-ttu-id="5c1f1-192">次の設定を確認し、必要に応じて修正します。</span><span class="sxs-lookup"><span data-stu-id="5c1f1-192">Verify the following settings, correcting as needed:</span></span> 
    
    <span data-ttu-id="5c1f1-193">[ディレクトリ番号情報] および [ディレクトリ番号の設定] に示すように、適切な変更を行います。</span><span class="sxs-lookup"><span data-stu-id="5c1f1-193">Make the appropriate changes as shown to the Directory Number Information and the Directory Number Settings.</span></span>
    
   |<span data-ttu-id="5c1f1-194">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="5c1f1-194">**Parameter**</span></span>|<span data-ttu-id="5c1f1-195">**推奨される設定値**</span><span class="sxs-lookup"><span data-stu-id="5c1f1-195">**Recommended setting**</span></span>|
   |:-----|:-----|
   | <span data-ttu-id="5c1f1-196">ディレクトリ番号情報 - ルート パーティション</span><span class="sxs-lookup"><span data-stu-id="5c1f1-196">Directory Number Information - Route Partition</span></span> <br/> | <span data-ttu-id="5c1f1-197">SfBVideoInterop_RoutePartition</span><span class="sxs-lookup"><span data-stu-id="5c1f1-197">SfBVideoInterop_RoutePartition</span></span> <br/> |
   |<span data-ttu-id="5c1f1-198">ディレクトリ番号の設定 - 通話検索スペース</span><span class="sxs-lookup"><span data-stu-id="5c1f1-198">Directory Number Settings - Calling Search Space</span></span>  <br/> | <span data-ttu-id="5c1f1-199">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="5c1f1-199">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="5c1f1-200">MLPP 代替パーティーと機密アクセス レベルの設定 - MLPP 通話検索スペース</span><span class="sxs-lookup"><span data-stu-id="5c1f1-200">MLPP Alternate Party and Confidential Access Level Settings - MLPP Calling Search Space</span></span>  <br/> | <span data-ttu-id="5c1f1-201">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="5c1f1-201">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="5c1f1-202">デバイスの 1 行目 - 表示 (発信者番号)</span><span class="sxs-lookup"><span data-stu-id="5c1f1-202">Line 1 on Device - Display (Caller ID)</span></span>  <br/> | <span data-ttu-id="5c1f1-203">必要に応じて</span><span class="sxs-lookup"><span data-stu-id="5c1f1-203">As desired</span></span> <br/> |
   |<span data-ttu-id="5c1f1-204">デバイスの行 1 - ASCII 表示 (発信者番号)</span><span class="sxs-lookup"><span data-stu-id="5c1f1-204">Line 1 on Device - ASCII Display (Caller ID)</span></span>  <br/> | <span data-ttu-id="5c1f1-205">必要に応じて</span><span class="sxs-lookup"><span data-stu-id="5c1f1-205">As desired</span></span> <br/> |
   
5. <span data-ttu-id="5c1f1-206">完了したら、画面の上部までスクロールし、[保存] を **押します**。</span><span class="sxs-lookup"><span data-stu-id="5c1f1-206">When finished, scroll to the top of the screen and press **Save**.</span></span> 
    
<span data-ttu-id="5c1f1-207">これで、この VTC デバイスの構成が完了しました。</span><span class="sxs-lookup"><span data-stu-id="5c1f1-207">Configuration is now complete for this VTC device.</span></span> <span data-ttu-id="5c1f1-208">企業内の他の VTC デバイスに対してこのプロセスを繰り返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c1f1-208">You will need to repeat this process for other VTC devices in your enterprise.</span></span>

