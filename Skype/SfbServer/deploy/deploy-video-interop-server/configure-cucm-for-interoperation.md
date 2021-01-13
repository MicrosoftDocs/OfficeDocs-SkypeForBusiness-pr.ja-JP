---
title: Skype for Business Server との相互運用のための CUCM の構成
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
ms.assetid: eab3d9f6-ec40-49bf-9162-1a7f5a59451f
description: '概要: Skype for Business Server と動作する CUCM を構成します。'
ms.openlocfilehash: 82fa48a185b22973d35bc19484e733e6436ba43e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49837117"
---
# <a name="configure-cucm-for-interoperation-with-skype-for-business-server"></a><span data-ttu-id="b5db4-103">Skype for Business Server との相互運用のための CUCM の構成</span><span class="sxs-lookup"><span data-stu-id="b5db4-103">Configure CUCM for Interoperation with Skype for Business Server</span></span>
 
<span data-ttu-id="b5db4-104">**概要:** Skype for Business Server と動作する CUCM を構成します。</span><span class="sxs-lookup"><span data-stu-id="b5db4-104">**Summary:** Configure CUCM to work with Skype for Business Server.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="b5db4-105">この機能は、TCP を使用したトランクセットアップのみを使用して、Cisco Unified Communications Manager (CallManager または CUCM) バージョン 10.5 でテストされます。</span><span class="sxs-lookup"><span data-stu-id="b5db4-105">This capability is tested with Cisco Unified Communications Manager (CallManager, or CUCM) version 10.5 using Trunks setup over TCP only.</span></span> <span data-ttu-id="b5db4-106">次に進む前に、CUCM 環境がこれらの条件を満たしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b5db4-106">Verify that the CUCM environment meets these criteria before proceeding.</span></span> 
  
<span data-ttu-id="b5db4-107">ここで説明する設定は、VIS を使用するように CUCM を構成する方法の例としてのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="b5db4-107">The settings described here are meant only as examples of how CUCM can be configured to work with a VIS.</span></span> <span data-ttu-id="b5db4-108">代替 CUCM 機能のその他の設定や使用法も、同じ結果を得る目的で使用できます。</span><span class="sxs-lookup"><span data-stu-id="b5db4-108">Other settings and/or usages of alternate CUCM functionality could also be used to achieve the same result.</span></span> <span data-ttu-id="b5db4-109">特定のシナリオに最適な構成に関する推奨事項は示されていません。</span><span class="sxs-lookup"><span data-stu-id="b5db4-109">No recommendation is implied as to the optimal configuration for a particular scenario.</span></span>
  
<span data-ttu-id="b5db4-110">VIS と相互運用するには、多くの CUCM 設定を確認または変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b5db4-110">A number of CUCM settings need to be confirmed or changed for interoperation with the VIS.</span></span> <span data-ttu-id="b5db4-111">必要な設定が見つからないのを避けるため、以下の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="b5db4-111">Follow the procedures below in order to avoid missing required settings.</span></span>
  
### <a name="configure-the-cucm"></a><span data-ttu-id="b5db4-112">CUCM を構成する</span><span class="sxs-lookup"><span data-stu-id="b5db4-112">Configure the CUCM</span></span>

1. <span data-ttu-id="b5db4-113">CUCM にログインし、[Cisco Unified CM Administration- \> Call Routing- \> Class of Control- Partition] に移動 \> します。</span><span class="sxs-lookup"><span data-stu-id="b5db4-113">Log in to CUCM and navigate to Cisco Unified CM Administration-\>Call Routing-\>Class of Control-\>Partition.</span></span>
    
2. <span data-ttu-id="b5db4-114">[パーティション構成] 画面で、パーティション名と説明を入力し、[新規追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="b5db4-114">In the Partition Configuration screen, enter the partition name and description and click on **Add New**.</span></span>
    
3. <span data-ttu-id="b5db4-115">[Cisco Unified CM Administration- \> Call Routing- \> Class of Control- Calling Search \> Space] に移動します。</span><span class="sxs-lookup"><span data-stu-id="b5db4-115">Navigate to Cisco Unified CM Administration-\>Call Routing-\>Class of Control-\>Calling Search Space.</span></span>
    
4. <span data-ttu-id="b5db4-116">[Calling Search Space Configuration] 画面で、呼び出し元の検索スペースの名前を入力し、[Selected Partitions] に作成したパーティションの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="b5db4-116">In the Calling Search Space Configuration screen, enter the name for the calling search space, and in Selected Partitions, enter the name of the partition you just created.</span></span> <span data-ttu-id="b5db4-117">完了したら **、[保存** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b5db4-117">Click **Save** when done.</span></span>
    
5. <span data-ttu-id="b5db4-118">[Cisco Unified CM Administration- \> System- \> Security- \> SIP Trunk Security Profile] に移動します。</span><span class="sxs-lookup"><span data-stu-id="b5db4-118">Navigate to Cisco Unified CM Administration-\>System-\>Security-\>SIP Trunk Security Profile.</span></span>
    
6. <span data-ttu-id="b5db4-119">[SIP トランク セキュリティ プロファイルの構成] 画面で、[SIP トランク セキュリティ プロファイル情報] オプションを次のように設定し、[新規追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="b5db4-119">In the SIP Trunk Security Profile Configuration screen, set the SIP Trunk Security Profile Information options as shown, and click on **Add New**.</span></span>
    
   |<span data-ttu-id="b5db4-120">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="b5db4-120">**Parameter**</span></span>|<span data-ttu-id="b5db4-121">**推奨される設定値**</span><span class="sxs-lookup"><span data-stu-id="b5db4-121">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="b5db4-122">名前</span><span class="sxs-lookup"><span data-stu-id="b5db4-122">Name</span></span>  <br/> |<span data-ttu-id="b5db4-123">SfBVideoInterop_SecurityProfile</span><span class="sxs-lookup"><span data-stu-id="b5db4-123">SfBVideoInterop_SecurityProfile</span></span>  <br/> |
   |<span data-ttu-id="b5db4-124">デバイス セキュリティ モード</span><span class="sxs-lookup"><span data-stu-id="b5db4-124">Device Security Mode</span></span>  <br/> |<span data-ttu-id="b5db4-125">セキュリティで保護されていない</span><span class="sxs-lookup"><span data-stu-id="b5db4-125">Non Secure</span></span>  <br/> |
   |<span data-ttu-id="b5db4-126">受信トランスポートの種類</span><span class="sxs-lookup"><span data-stu-id="b5db4-126">Incoming Transport Type</span></span>  <br/> |<span data-ttu-id="b5db4-127">TCP + UDP</span><span class="sxs-lookup"><span data-stu-id="b5db4-127">TCP + UDP</span></span>  <br/> |
   |<span data-ttu-id="b5db4-128">送信トランスポートの種類</span><span class="sxs-lookup"><span data-stu-id="b5db4-128">Outgoing Transport Type</span></span>  <br/> |<span data-ttu-id="b5db4-129">TCP</span><span class="sxs-lookup"><span data-stu-id="b5db4-129">TCP</span></span>  <br/> |
   |<span data-ttu-id="b5db4-130">受信ポート</span><span class="sxs-lookup"><span data-stu-id="b5db4-130">Incoming Port</span></span>  <br/> |<span data-ttu-id="b5db4-131">5060</span><span class="sxs-lookup"><span data-stu-id="b5db4-131">5060</span></span>  <br/> |
   
7. <span data-ttu-id="b5db4-132">[Cisco Unified CM Administration- \> Device- \> Device Settings- \> SIP Profile] に移動します。</span><span class="sxs-lookup"><span data-stu-id="b5db4-132">Navigate to Cisco Unified CM Administration-\>Device-\>Device Settings-\>SIP Profile.</span></span>
    
8. <span data-ttu-id="b5db4-133">[SIP プロファイル構成] 画面で、[SIP プロファイル情報] オプションを次のように設定します。</span><span class="sxs-lookup"><span data-stu-id="b5db4-133">In the SIP Profile Configuration screen, set the SIP Profile Information options as shown.</span></span> 
    
   |<span data-ttu-id="b5db4-134">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="b5db4-134">**Parameter**</span></span>|<span data-ttu-id="b5db4-135">**推奨される設定値**</span><span class="sxs-lookup"><span data-stu-id="b5db4-135">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="b5db4-136">名前</span><span class="sxs-lookup"><span data-stu-id="b5db4-136">Name</span></span>  <br/> |<span data-ttu-id="b5db4-137">SfBVideoInterop_SIPProfile</span><span class="sxs-lookup"><span data-stu-id="b5db4-137">SfBVideoInterop_SIPProfile</span></span>  <br/> |
   |<span data-ttu-id="b5db4-138">説明</span><span class="sxs-lookup"><span data-stu-id="b5db4-138">Description</span></span>  <br/> |<span data-ttu-id="b5db4-139">SfBVideoInterop_SIPProfile</span><span class="sxs-lookup"><span data-stu-id="b5db4-139">SfBVideoInterop_SIPProfile</span></span>  <br/> |
   
9. <span data-ttu-id="b5db4-140">同じ画面で、[SDP プロファイル情報] セクションまで下にスクロールします。</span><span class="sxs-lookup"><span data-stu-id="b5db4-140">On the same screen, scroll down to the SDP Profile Information section.</span></span> <span data-ttu-id="b5db4-141">[ **早期提供と** 再招待] オプションの SDP セッション レベルの帯域幅修飾子は、既定で TIAS と AS に設定されています。</span><span class="sxs-lookup"><span data-stu-id="b5db4-141">The **SDP Session-level Bandwidth Modifier for Early Offer and Re-invites** option is set by default to TIAS and AS.</span></span> <span data-ttu-id="b5db4-142">このオプションを TIAS にのみ変更します。</span><span class="sxs-lookup"><span data-stu-id="b5db4-142">Change this option to TIAS only.</span></span> <span data-ttu-id="b5db4-143">このオプションを既定の設定のままにした場合、Skype for Business Server は SIP メッセージの帯域幅修飾子情報を理解しません。</span><span class="sxs-lookup"><span data-stu-id="b5db4-143">If you leave this option at its default setting, Skype for Business Server will not understand the bandwidth modifier information in the SIP message.</span></span> <span data-ttu-id="b5db4-144">TIAS は Transport Independent Application Specific を意味し、AS はアプリケーション固有を意味します。</span><span class="sxs-lookup"><span data-stu-id="b5db4-144">TIAS means Transport Independent Application Specific while AS means Application Specific.</span></span> <span data-ttu-id="b5db4-145">これらは RFC3890 で指定されている SIP オプションです。</span><span class="sxs-lookup"><span data-stu-id="b5db4-145">These are SIP options specified in RFC3890.</span></span>
    
10. <span data-ttu-id="b5db4-146">同じ画面で、さらに下にスクロールします。</span><span class="sxs-lookup"><span data-stu-id="b5db4-146">On the same screen, scroll down further.</span></span> <span data-ttu-id="b5db4-147">SIP プロファイルのトランク固有の構成で、音声通話とビデオ通話の早期提供サポートを選択し、必須 (必要に応じて **MTP** を挿入) オプションに設定します。</span><span class="sxs-lookup"><span data-stu-id="b5db4-147">Under the SIP Profile's Trunk Specific Configuration, select **Early Offer Support for voice and video calls** and set it to the **Mandatory (insert MTP if needed)** option.</span></span> <span data-ttu-id="b5db4-148">これにより、CUCM で早期オファーを使用して発信 SIP 通話を設定できます。</span><span class="sxs-lookup"><span data-stu-id="b5db4-148">This will enable CUCM to set up an outgoing SIP call with Early Offer.</span></span> <span data-ttu-id="b5db4-149">CUCM 8.5 以降の新機能の 1 つは、メディア終端ポイント (MTP) を必要とせず、早期オファーによる発信通話セットアップをサポートする点です。</span><span class="sxs-lookup"><span data-stu-id="b5db4-149">One new feature in CUCM 8.5 and beyond is that it supports outgoing call setup with Early Offer without requiring Media Termination Point (MTP).</span></span>
    
11. <span data-ttu-id="b5db4-150">[SIP オプション ping] セクションで、[OPTIONS Ping を有効にして、サービスの種類が 'なし (既定)' のトランクの宛先の状態を監視する] チェック ボックスがオンになっています。</span><span class="sxs-lookup"><span data-stu-id="b5db4-150">Verify that in the SIP Options ping section, the box is checked next to "Enable OPTIONS Ping to monitor destination status for Trunks with Service Type 'None (Default)'."</span></span>
    
12. <span data-ttu-id="b5db4-151">完了したら、[新規追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="b5db4-151">When you are finished, click on **Add New**.</span></span>
    
13. <span data-ttu-id="b5db4-152">[Cisco Unified CM Administration- \> Device- Trunk] に移動 \> します。</span><span class="sxs-lookup"><span data-stu-id="b5db4-152">Navigate to Cisco Unified CM Administration-\>Device-\>Trunk.</span></span> 
    
14. <span data-ttu-id="b5db4-153">デバイス プロトコルを SIP に設定し、[次へ] を **押します**。</span><span class="sxs-lookup"><span data-stu-id="b5db4-153">Set the Device Protocol to SIP and press **Next**.</span></span>
    
15. <span data-ttu-id="b5db4-154">[デバイス情報] で、デバイス名と説明 (おそらく SfBVideoInterop_SIPTrunk など) を設定し、メディア リソース グループの一覧を、適切なメディア リソースを含む MRGL に設定します。</span><span class="sxs-lookup"><span data-stu-id="b5db4-154">Under Device Information, Set the Device Name and Description (probably to something like SfBVideoInterop_SIPTrunk), and set the Media Resource Group List to an MRGL that contains the right media resources.</span></span> 
    
16. <span data-ttu-id="b5db4-155">さらに下にスクロールします。</span><span class="sxs-lookup"><span data-stu-id="b5db4-155">Scroll down further.</span></span> <span data-ttu-id="b5db4-156">ビデオ通話にメディア終端ポイント (MTP) は必要ありません 。まだオフにされていない場合は、オフにします。</span><span class="sxs-lookup"><span data-stu-id="b5db4-156">Media Termination Point (MTP) is not required for Video Calls, if it is not already unchecked, uncheck it.</span></span> <span data-ttu-id="b5db4-157">アクティブなすべての **Unified CM ノードで実行するオプションをオンにします**。</span><span class="sxs-lookup"><span data-stu-id="b5db4-157">Check the option to **Run on all active Unified CM Nodes**.</span></span> <span data-ttu-id="b5db4-158">すべての CUCM ノードを Skype for Business Server 構成に追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b5db4-158">Please note that you should add all CUCM nodes to the Skype for Business Server configuration.</span></span>
    
17. <span data-ttu-id="b5db4-159">さらに下にスクロールします。</span><span class="sxs-lookup"><span data-stu-id="b5db4-159">Scroll down further.</span></span> <span data-ttu-id="b5db4-160">次に示すように、[着信呼び出しと接続済みパーティの設定] オプションを設定します。</span><span class="sxs-lookup"><span data-stu-id="b5db4-160">Set the Inbound Calls and Connected Party Settings options as shown.</span></span>
    
    |<span data-ttu-id="b5db4-161">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="b5db4-161">**Parameter**</span></span>|<span data-ttu-id="b5db4-162">**推奨される設定値**</span><span class="sxs-lookup"><span data-stu-id="b5db4-162">**Recommended setting**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="b5db4-163">Calling Search Space</span><span class="sxs-lookup"><span data-stu-id="b5db4-163">Calling Search Space</span></span>  <br/> |<span data-ttu-id="b5db4-164">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="b5db4-164">CSS_SfBVideoInterop</span></span>  <br/> |
    |<span data-ttu-id="b5db4-165">AAR Calling Search Space</span><span class="sxs-lookup"><span data-stu-id="b5db4-165">AAR Calling Search Space</span></span>  <br/> |<span data-ttu-id="b5db4-166">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="b5db4-166">CSS_SfBVideoInterop</span></span>  <br/> |
    |<span data-ttu-id="b5db4-167">接続されたパーティー変換 CSS</span><span class="sxs-lookup"><span data-stu-id="b5db4-167">Connected Party Transformation CSS</span></span>  <br/> |<span data-ttu-id="b5db4-168">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="b5db4-168">CSS_SfBVideoInterop</span></span>  <br/> |
   
18. <span data-ttu-id="b5db4-169">さらに下にスクロールします。</span><span class="sxs-lookup"><span data-stu-id="b5db4-169">Scroll down further.</span></span> <span data-ttu-id="b5db4-170">SIP トランク構成の [SIP 情報の宛先] セクションで、VIS プールの FQDN またはプール内の個々の VIS サーバーの IP アドレスを指定します (複数のエントリを追加)。</span><span class="sxs-lookup"><span data-stu-id="b5db4-170">Under the SIP Information Destination section of the SIP Trunk configuration, specify the VIS Pool's FQDN or the IP address of individual VIS servers in the pool (adding multiple entries).</span></span> <span data-ttu-id="b5db4-171">[Destination Port] で、VIS が CUCM からの接続をリッスンしているポートを指定します (既定値は 6001 です)。</span><span class="sxs-lookup"><span data-stu-id="b5db4-171">In the Destination Port specify the Port that VIS is listening at for connections from CUCM (the default is 6001).</span></span> <span data-ttu-id="b5db4-172">また、次に示すように、前に作成した SIP トランク セキュリティ プロファイルと SIP プロファイルも指定します。</span><span class="sxs-lookup"><span data-stu-id="b5db4-172">Also specify the SIP Trunk security profile and SIP profile you created earlier, as shown.</span></span>
    
    |<span data-ttu-id="b5db4-173">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="b5db4-173">**Parameter**</span></span>|<span data-ttu-id="b5db4-174">**推奨される設定値**</span><span class="sxs-lookup"><span data-stu-id="b5db4-174">**Recommended setting**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="b5db4-175">SIP トランク セキュリティ プロファイル</span><span class="sxs-lookup"><span data-stu-id="b5db4-175">SIP Trunk Security Profile</span></span>  <br/> |<span data-ttu-id="b5db4-176">SfBVideoInterop_SecurityProfile</span><span class="sxs-lookup"><span data-stu-id="b5db4-176">SfBVideoInterop_SecurityProfile</span></span>  <br/> |
    |<span data-ttu-id="b5db4-177">呼び出し元の検索スペースの再ルーティング</span><span class="sxs-lookup"><span data-stu-id="b5db4-177">Rerouting Calling Search Space</span></span>  <br/> |<span data-ttu-id="b5db4-178">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="b5db4-178">CSS_SfBVideoInterop</span></span>  <br/> |
    |<span data-ttu-id="b5db4-179">Out-of-Dialog Refer Calling Search Space</span><span class="sxs-lookup"><span data-stu-id="b5db4-179">Out-of-Dialog Refer Calling Search Space</span></span>  <br/> |<span data-ttu-id="b5db4-180">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="b5db4-180">CSS_SfBVideoInterop</span></span>  <br/> |
    |<span data-ttu-id="b5db4-181">Subscribe Calling Search Space</span><span class="sxs-lookup"><span data-stu-id="b5db4-181">Subscribe Calling Search Space</span></span>  <br/> |<span data-ttu-id="b5db4-182">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="b5db4-182">CSS_SfBVideoInterop</span></span>  <br/> |
    |<span data-ttu-id="b5db4-183">SIP プロファイル</span><span class="sxs-lookup"><span data-stu-id="b5db4-183">SIP Profile</span></span>  <br/> |<span data-ttu-id="b5db4-184">SfBVideoInterop_SIPProfile</span><span class="sxs-lookup"><span data-stu-id="b5db4-184">SfBVideoInterop_SIPProfile</span></span>  <br/> |
    |<span data-ttu-id="b5db4-185">DTMF Signaling Method</span><span class="sxs-lookup"><span data-stu-id="b5db4-185">DTMF Signaling Method</span></span>  <br/> |<span data-ttu-id="b5db4-186">RFC 2833</span><span class="sxs-lookup"><span data-stu-id="b5db4-186">RFC 2833</span></span>  <br/> |
   
19.  <span data-ttu-id="b5db4-187">さらに下にスクロールします。</span><span class="sxs-lookup"><span data-stu-id="b5db4-187">Scroll down further.</span></span> <span data-ttu-id="b5db4-188">システムに応じてレコーディング情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="b5db4-188">Set the Recording Information as appropriate for your system.</span></span> <span data-ttu-id="b5db4-189">[なし] に設定したままで **問題ありません**。</span><span class="sxs-lookup"><span data-stu-id="b5db4-189">It's fine to leave it set to **None**.</span></span> 
    
20. <span data-ttu-id="b5db4-190">完了したら、[新規追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="b5db4-190">When you are finished, click on **Add New**.</span></span>
    
21. <span data-ttu-id="b5db4-191">[Cisco Unified CM Administration- \> Call Routing- \> Route/Hunt- \> Route Pattern] に移動します。</span><span class="sxs-lookup"><span data-stu-id="b5db4-191">Navigate to Cisco Unified CM Administration-\>Call Routing-\>Route/Hunt-\>Route pattern.</span></span>
    
22. <span data-ttu-id="b5db4-192">[ルート パターン構成] 画面で、以下に示すパターン定義パラメーターを入力します。</span><span class="sxs-lookup"><span data-stu-id="b5db4-192">In the Route Pattern Configuration screen, enter the Pattern definition parameters shown below.</span></span> <span data-ttu-id="b5db4-193">[呼び出し済みパーティ変換] セクションまで下にスクロールし、次に示すようにマスクを設定し、完了したら [新規追加] **をクリック** します。</span><span class="sxs-lookup"><span data-stu-id="b5db4-193">Scroll down to the Called Party Transformations section and set the mask as shown, and then click on **Add New** when finished.</span></span>
    
    |<span data-ttu-id="b5db4-194">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="b5db4-194">**Parameter**</span></span>|<span data-ttu-id="b5db4-195">**推奨される設定値**</span><span class="sxs-lookup"><span data-stu-id="b5db4-195">**Recommended setting**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="b5db4-196">ルート パターン</span><span class="sxs-lookup"><span data-stu-id="b5db4-196">Route Pattern</span></span>  <br/> |<span data-ttu-id="b5db4-197">7779999</span><span class="sxs-lookup"><span data-stu-id="b5db4-197">7779999</span></span>  <br/> |
    |<span data-ttu-id="b5db4-198">ルート パーティション</span><span class="sxs-lookup"><span data-stu-id="b5db4-198">Route Partition</span></span>  <br/> |<span data-ttu-id="b5db4-199">SfBVideoInterop_RoutePartition</span><span class="sxs-lookup"><span data-stu-id="b5db4-199">SfBVideoInterop_RoutePartition</span></span>  <br/> |
    |<span data-ttu-id="b5db4-200">説明</span><span class="sxs-lookup"><span data-stu-id="b5db4-200">Description</span></span>  <br/> |<span data-ttu-id="b5db4-201">SfBVideoInterop のパーティション</span><span class="sxs-lookup"><span data-stu-id="b5db4-201">Partition for SfBVideoInterop</span></span>  <br/> |
    |<span data-ttu-id="b5db4-202">ゲートウェイ/ルート一覧</span><span class="sxs-lookup"><span data-stu-id="b5db4-202">Gateway/Route List</span></span>  <br/> |<span data-ttu-id="b5db4-203">SfBVideoInterop_SIPTrunk</span><span class="sxs-lookup"><span data-stu-id="b5db4-203">SfBVideoInterop_SIPTrunk</span></span>  <br/> |
    |<span data-ttu-id="b5db4-204">呼び出されたパーティー変換マスク</span><span class="sxs-lookup"><span data-stu-id="b5db4-204">Called Party Transform Mask</span></span>  <br/> |<span data-ttu-id="b5db4-205">+14257779999</span><span class="sxs-lookup"><span data-stu-id="b5db4-205">+14257779999</span></span>  <br/> |
   
23. <span data-ttu-id="b5db4-206">[Cisco Unified CM Administration- \> Call Routing- \> SIP Route Pattern] に移動します。</span><span class="sxs-lookup"><span data-stu-id="b5db4-206">Navigate to Cisco Unified CM Administration-\>Call Routing-\>SIP Route Pattern.</span></span>
    
24. <span data-ttu-id="b5db4-207">[SIP ルート パターン構成] 画面で、パターン定義オプションを次のように設定し、[新規追加] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="b5db4-207">In the SIP Route Pattern Configuration screen, set the Pattern Definition options as shown, and click on **Add New**.</span></span>
    
    |<span data-ttu-id="b5db4-208">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="b5db4-208">**Parameter**</span></span>|<span data-ttu-id="b5db4-209">**推奨される設定値**</span><span class="sxs-lookup"><span data-stu-id="b5db4-209">**Recommended setting**</span></span>|
    |:-----|:-----|
    | <span data-ttu-id="b5db4-210">パターンの使用</span><span class="sxs-lookup"><span data-stu-id="b5db4-210">Pattern Usage</span></span> <br/> |<span data-ttu-id="b5db4-211">ドメイン ルーティング</span><span class="sxs-lookup"><span data-stu-id="b5db4-211">Domain Routing</span></span>  <br/> |
    |<span data-ttu-id="b5db4-212">IPv4 パターン</span><span class="sxs-lookup"><span data-stu-id="b5db4-212">IPv4 Pattern</span></span>  <br/> |<span data-ttu-id="b5db4-213">contoso.com (IPv6 を使用する場合は空白のままにします)</span><span class="sxs-lookup"><span data-stu-id="b5db4-213">contoso.com (leave blank if using IPv6)</span></span>  <br/> |
    |<span data-ttu-id="b5db4-214">IPv6 パターン</span><span class="sxs-lookup"><span data-stu-id="b5db4-214">IPv6 Pattern</span></span>  <br/> |<span data-ttu-id="b5db4-215">contoso.com (IPv4 を使用する場合は空白のままにします)</span><span class="sxs-lookup"><span data-stu-id="b5db4-215">contoso.com (leave blank if using IPv4)</span></span>  <br/> |
    |<span data-ttu-id="b5db4-216">説明</span><span class="sxs-lookup"><span data-stu-id="b5db4-216">Description</span></span>  <br/> |<span data-ttu-id="b5db4-217">MEDIARV への SIPRoute パターン</span><span class="sxs-lookup"><span data-stu-id="b5db4-217">SIPRoute Pattern to mediarv</span></span>  <br/> |
    |<span data-ttu-id="b5db4-218">ルート パーティション</span><span class="sxs-lookup"><span data-stu-id="b5db4-218">Route Partition</span></span>  <br/> |<span data-ttu-id="b5db4-219">SfBVideoInterop_RoutePartition</span><span class="sxs-lookup"><span data-stu-id="b5db4-219">SfBVideoInterop_RoutePartition</span></span>  <br/> |
    |<span data-ttu-id="b5db4-220">SIP トランク/ルート一覧</span><span class="sxs-lookup"><span data-stu-id="b5db4-220">SIP Trunk/Route List</span></span>  <br/> |<span data-ttu-id="b5db4-221">SfBVideoInterop_SIPTrunk</span><span class="sxs-lookup"><span data-stu-id="b5db4-221">SfBVideoInterop_SIPTrunk</span></span>  <br/> |
    |<span data-ttu-id="b5db4-222">[ブロック パターン] チェック ボックス</span><span class="sxs-lookup"><span data-stu-id="b5db4-222">Block Pattern checkbox</span></span>  <br/> |<span data-ttu-id="b5db4-223">オフのままにする</span><span class="sxs-lookup"><span data-stu-id="b5db4-223">leave unchecked</span></span>  <br/> |
   
25. <span data-ttu-id="b5db4-224">オーディオまたはビデオのビット レートを既定の設定から変更した場合は、既定値に戻す必要があります。</span><span class="sxs-lookup"><span data-stu-id="b5db4-224">If you have changed the audio or video bit rates from the default settings, you will need to return them to the defaults.</span></span> <span data-ttu-id="b5db4-225">音声ビデオ通話のビット レートを設定するには、[Cisco Unified CM Administration- \> System- \> Region Information- Region] に移動 \> します。</span><span class="sxs-lookup"><span data-stu-id="b5db4-225">To set the bit rate for Audio/Video calls, navigate to Cisco Unified CM Administration-\>System-\>Region Information-\>Region.</span></span> <span data-ttu-id="b5db4-226">参照用の既定値を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="b5db4-226">The defaults are shown below for reference:</span></span>
    
    |<span data-ttu-id="b5db4-227">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="b5db4-227">**Parameter**</span></span>|<span data-ttu-id="b5db4-228">**推奨される設定値**</span><span class="sxs-lookup"><span data-stu-id="b5db4-228">**Recommended setting**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="b5db4-229">Region</span><span class="sxs-lookup"><span data-stu-id="b5db4-229">Region</span></span>  <br/> |<span data-ttu-id="b5db4-230">既定値</span><span class="sxs-lookup"><span data-stu-id="b5db4-230">Default</span></span>  <br/> |
    |<span data-ttu-id="b5db4-231">オーディオ コーデックの基本設定の一覧</span><span class="sxs-lookup"><span data-stu-id="b5db4-231">Audio Codec Preference List</span></span>  <br/> |<span data-ttu-id="b5db4-232">システムの既定値</span><span class="sxs-lookup"><span data-stu-id="b5db4-232">System Default</span></span>  <br/> |
    |<span data-ttu-id="b5db4-233">最大オーディオ ビット レート</span><span class="sxs-lookup"><span data-stu-id="b5db4-233">Maximum Audio Bit Rate</span></span>  <br/> |<span data-ttu-id="b5db4-234">64 kbps (G.722、G.711)</span><span class="sxs-lookup"><span data-stu-id="b5db4-234">64 kbps (G.722, G.711)</span></span>  <br/> |
    |<span data-ttu-id="b5db4-235">ビデオ通話の最大セッション ビット レート</span><span class="sxs-lookup"><span data-stu-id="b5db4-235">Maximum Session Bit Rate for Video Calls</span></span>  <br/> |<span data-ttu-id="b5db4-236">200000 kbps</span><span class="sxs-lookup"><span data-stu-id="b5db4-236">200000 kbps</span></span>  <br/> |
    |<span data-ttu-id="b5db4-237">最大セッション ビット レート</span><span class="sxs-lookup"><span data-stu-id="b5db4-237">Maximum Session Bit Rate</span></span>  <br/> |<span data-ttu-id="b5db4-238">2000000000 kbps</span><span class="sxs-lookup"><span data-stu-id="b5db4-238">2000000000 kbps</span></span>  <br/> |
   
<span data-ttu-id="b5db4-239">この時点で、CUCM ビデオ ゲートウェイは VIS を使用するように構成されています。</span><span class="sxs-lookup"><span data-stu-id="b5db4-239">At this point the CUCM video gateway is configured to work with the VIS.</span></span> <span data-ttu-id="b5db4-240">対応する構成は、統合する各 VTC で行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="b5db4-240">Corresponding configuration will need to be done on each VTC you wish to integrate.</span></span>
> [!NOTE]
> <span data-ttu-id="b5db4-241">回復性を向上させるために、この CUCM ゲートウェイが 2 つ目のビデオ相互運用サーバーまたは VIS プールで動作する構成が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="b5db4-241">To improve resiliency, you may want to configure this CUCM gateway to work with a second Video Interop Server or VIS pool.</span></span> <span data-ttu-id="b5db4-242">詳細 [については、「復元メカニズム」](../../plan-your-deployment/video-interop-server.md#resiliency) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b5db4-242">See [Resiliency mechanisms](../../plan-your-deployment/video-interop-server.md#resiliency) for more information.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b5db4-243">関連項目</span><span class="sxs-lookup"><span data-stu-id="b5db4-243">See also</span></span>

[<span data-ttu-id="b5db4-244">Skype for Business Server との相互運用のための VTC の構成</span><span class="sxs-lookup"><span data-stu-id="b5db4-244">Configure a VTC for Interoperation with Skype for Business Server</span></span>](configure-a-vtc-for-interoperation.md)
