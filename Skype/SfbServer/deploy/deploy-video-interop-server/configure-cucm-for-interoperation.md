---
title: Skype for Business Server との相互運用用に CUCM を構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: eab3d9f6-ec40-49bf-9162-1a7f5a59451f
description: '概要: Skype for Business Server で動作するように CUCM を構成します。'
ms.openlocfilehash: b0087e54b91b8c11bfcaba0c1eb732183db252bd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34302795"
---
# <a name="configure-cucm-for-interoperation-with-skype-for-business-server"></a><span data-ttu-id="3e229-103">Skype for Business Server との相互運用用に CUCM を構成する</span><span class="sxs-lookup"><span data-stu-id="3e229-103">Configure CUCM for Interoperation with Skype for Business Server</span></span>
 
<span data-ttu-id="3e229-104">**概要:** Skype for Business Server で動作するように CUCM を構成します。</span><span class="sxs-lookup"><span data-stu-id="3e229-104">**Summary:** Configure CUCM to work with Skype for Business Server.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="3e229-105">この機能は、TCP 経由の Trunks セットアップを使って、Cisco ユニファイドコミュニケーションマネージャー (CallManager、または CUCM) バージョン10.5 でテストされています。</span><span class="sxs-lookup"><span data-stu-id="3e229-105">This capability is tested with Cisco Unified Communications Manager (CallManager, or CUCM) version 10.5 using Trunks setup over TCP only.</span></span> <span data-ttu-id="3e229-106">作業を続行する前に、CUCM 環境がこれらの条件を満たしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="3e229-106">Verify that the CUCM environment meets these criteria before proceeding.</span></span> 
  
<span data-ttu-id="3e229-107">ここで説明する設定は、VIS と連携するように CUCM を設定する方法の例としてのみ使用されています。</span><span class="sxs-lookup"><span data-stu-id="3e229-107">The settings described here are meant only as examples of how CUCM can be configured to work with a VIS.</span></span> <span data-ttu-id="3e229-108">CUCM の別の機能を他の方法で設定/使用して同じ結果を実現することもできます。</span><span class="sxs-lookup"><span data-stu-id="3e229-108">Other settings and/or usages of alternate CUCM functionality could also be used to achieve the same result.</span></span> <span data-ttu-id="3e229-109">特定のシナリオ向けの最適な構成に関する推奨事項は示されていません。</span><span class="sxs-lookup"><span data-stu-id="3e229-109">No recommendation is implied as to the optimal configuration for a particular scenario.</span></span>
  
<span data-ttu-id="3e229-p103">VIS との相互運用を実現するには、多くの CUCM の設定を確認または変更する必要があります。必要な設定を確実に実行するには、以下の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="3e229-p103">A number of CUCM settings need to be confirmed or changed for interoperation with the VIS. Follow the procedures below in order to avoid missing required settings.</span></span>
  
### <a name="configure-the-cucm"></a><span data-ttu-id="3e229-112">CUCM を構成する</span><span class="sxs-lookup"><span data-stu-id="3e229-112">Configure the CUCM</span></span>

1. <span data-ttu-id="3e229-113">CUCM にログインして、「Cisco ユニファイ CM 管理-\>通話ルーティング-\>制御\>パーティションのクラス」に移動します。</span><span class="sxs-lookup"><span data-stu-id="3e229-113">Log in to CUCM and navigate to Cisco Unified CM Administration-\>Call Routing-\>Class of Control-\>Partition.</span></span>
    
2. <span data-ttu-id="3e229-114">[Partition Configuration] 画面で、パーティションの名前と説明を入力し、[**Add New**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e229-114">In the Partition Configuration screen, enter the partition name and description and click on **Add New**.</span></span>
    
3. <span data-ttu-id="3e229-115">「Cisco ユニファイド CM の管理\>」に移動\>します。コントロール\>呼び出しの検索スペースのクラスを指定します。</span><span class="sxs-lookup"><span data-stu-id="3e229-115">Navigate to Cisco Unified CM Administration-\>Call Routing-\>Class of Control-\>Calling Search Space.</span></span>
    
4. <span data-ttu-id="3e229-p104">[Calling Search Space Configuration] 画面で、Calling Search Space (コーリング サーチ スペース) の名前を入力し、[Selected Partitions] には直前に作成したパーティーションの名前を入力します。完了したら、[**Save**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e229-p104">In the Calling Search Space Configuration screen, enter the name for the calling search space, and in Selected Partitions, enter the name of the partition you just created. Click **Save** when done.</span></span>
    
5. <span data-ttu-id="3e229-118">「Cisco ユニファイド CM 管理-\>システム-\>セキュリティ-\>SIP トランクセキュリティプロファイル」に移動します。</span><span class="sxs-lookup"><span data-stu-id="3e229-118">Navigate to Cisco Unified CM Administration-\>System-\>Security-\>SIP Trunk Security Profile.</span></span>
    
6. <span data-ttu-id="3e229-119">[SIP Trunk Security Profile Configuration] 画面で、図のように [SIP Trunk Security Profile Information] のオプションを設定し、[**Add New**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e229-119">In the SIP Trunk Security Profile Configuration screen, set the SIP Trunk Security Profile Information options as shown, and click on **Add New**.</span></span>
    
   |<span data-ttu-id="3e229-120">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="3e229-120">**Parameter**</span></span>|<span data-ttu-id="3e229-121">**推奨設定**</span><span class="sxs-lookup"><span data-stu-id="3e229-121">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="3e229-122">名前</span><span class="sxs-lookup"><span data-stu-id="3e229-122">Name</span></span>  <br/> |<span data-ttu-id="3e229-123">SfBVideoInterop_SecurityProfile</span><span class="sxs-lookup"><span data-stu-id="3e229-123">SfBVideoInterop_SecurityProfile</span></span>  <br/> |
   |<span data-ttu-id="3e229-124">Device Security Mode</span><span class="sxs-lookup"><span data-stu-id="3e229-124">Device Security Mode</span></span>  <br/> |<span data-ttu-id="3e229-125">Non Secure</span><span class="sxs-lookup"><span data-stu-id="3e229-125">Non Secure</span></span>  <br/> |
   |<span data-ttu-id="3e229-126">Incoming Transport Type</span><span class="sxs-lookup"><span data-stu-id="3e229-126">Incoming Transport Type</span></span>  <br/> |<span data-ttu-id="3e229-127">TCP + UDP</span><span class="sxs-lookup"><span data-stu-id="3e229-127">TCP + UDP</span></span>  <br/> |
   |<span data-ttu-id="3e229-128">Outgoing Transport Type</span><span class="sxs-lookup"><span data-stu-id="3e229-128">Outgoing Transport Type</span></span>  <br/> |<span data-ttu-id="3e229-129">TCP</span><span class="sxs-lookup"><span data-stu-id="3e229-129">TCP</span></span>  <br/> |
   |<span data-ttu-id="3e229-130">Incoming Port</span><span class="sxs-lookup"><span data-stu-id="3e229-130">Incoming Port</span></span>  <br/> |<span data-ttu-id="3e229-131">5060</span><span class="sxs-lookup"><span data-stu-id="3e229-131">5060</span></span>  <br/> |
   
7. <span data-ttu-id="3e229-132">「Cisco ユニファイド CM の管理\>-デバイス\>の設定-\>SIP プロフィール」に移動します。</span><span class="sxs-lookup"><span data-stu-id="3e229-132">Navigate to Cisco Unified CM Administration-\>Device-\>Device Settings-\>SIP Profile.</span></span>
    
8. <span data-ttu-id="3e229-133">[SIP Profile Configuration] 画面で、図のように [SIP Profile Information] のオプションを設定します。</span><span class="sxs-lookup"><span data-stu-id="3e229-133">In the SIP Profile Configuration screen, set the SIP Profile Information options as shown.</span></span> 
    
   |<span data-ttu-id="3e229-134">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="3e229-134">**Parameter**</span></span>|<span data-ttu-id="3e229-135">**推奨設定**</span><span class="sxs-lookup"><span data-stu-id="3e229-135">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="3e229-136">Name</span><span class="sxs-lookup"><span data-stu-id="3e229-136">Name</span></span>  <br/> |<span data-ttu-id="3e229-137">SfBVideoInterop_SIPProfile</span><span class="sxs-lookup"><span data-stu-id="3e229-137">SfBVideoInterop_SIPProfile</span></span>  <br/> |
   |<span data-ttu-id="3e229-138">説明</span><span class="sxs-lookup"><span data-stu-id="3e229-138">Description</span></span>  <br/> |<span data-ttu-id="3e229-139">SfBVideoInterop_SIPProfile</span><span class="sxs-lookup"><span data-stu-id="3e229-139">SfBVideoInterop_SIPProfile</span></span>  <br/> |
   
9. <span data-ttu-id="3e229-140">同じ画面で、[SDP プロファイル情報] セクションまで下にスクロールします。</span><span class="sxs-lookup"><span data-stu-id="3e229-140">On the same screen, scroll down to the SDP Profile Information section.</span></span> <span data-ttu-id="3e229-141">[**SDP Session-level Bandwidth Modifier for Early Offer and Re-invites**] オプションは、既定では [TIAS and AS] に設定されています。</span><span class="sxs-lookup"><span data-stu-id="3e229-141">The **SDP Session-level Bandwidth Modifier for Early Offer and Re-invites** option is set by default to TIAS and AS.</span></span> <span data-ttu-id="3e229-142">このオプションを [TIAS only] に変更します。</span><span class="sxs-lookup"><span data-stu-id="3e229-142">Change this option to TIAS only.</span></span> <span data-ttu-id="3e229-143">このオプションを既定の設定のままにした場合、Skype for Business Server は SIP メッセージの帯域幅の補助情報を認識しません。</span><span class="sxs-lookup"><span data-stu-id="3e229-143">If you leave this option at its default setting, Skype for Business Server will not understand the bandwidth modifier information in the SIP message.</span></span> <span data-ttu-id="3e229-144">TIAS は Transport Independent Application Specific (トランスポート非依存アプリケーション固有) の意味で、AS は Application Specific (アプリケーション固有) の意味です。</span><span class="sxs-lookup"><span data-stu-id="3e229-144">TIAS means Transport Independent Application Specific while AS means Application Specific.</span></span> <span data-ttu-id="3e229-145">これらは、RFC3890 で規定されている SIP のオプションです。</span><span class="sxs-lookup"><span data-stu-id="3e229-145">These are SIP options specified in RFC3890.</span></span>
    
10. <span data-ttu-id="3e229-146">同じ画面で、さらに下にスクロールします。</span><span class="sxs-lookup"><span data-stu-id="3e229-146">On the same screen, scroll down further.</span></span> <span data-ttu-id="3e229-147">SIP プロフィールのトランク固有の構成で、「**音声通話とビデオ通話の早期サポート**」を選択して、「**必須 (必要に応じて MTP を挿入)** 」オプションを設定します。</span><span class="sxs-lookup"><span data-stu-id="3e229-147">Under the SIP Profile's Trunk Specific Configuration, select **Early Offer Support for voice and video calls** and set it to the **Mandatory (insert MTP if needed)** option.</span></span> <span data-ttu-id="3e229-148">この設定を行うと、CUCM で、Early Offer (アーリー オファー) を使用して発信 SIP 通話を設定できるようになります。</span><span class="sxs-lookup"><span data-stu-id="3e229-148">This will enable CUCM to set up an outgoing SIP call with Early Offer.</span></span> <span data-ttu-id="3e229-149">CUCM 8.5 以降の新機能の 1 つとして、メディア終端ポイント (MTP) が必要でない、Early Offer を使用した発信通話の設定をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="3e229-149">One new feature in CUCM 8.5 and beyond is that it supports outgoing call setup with Early Offer without requiring Media Termination Point (MTP).</span></span>
    
11. <span data-ttu-id="3e229-150">[SIP Options ping] セクションで、[Enable OPTIONS Ping to monitor destination status for Trunks with Service Type 'None (Default)'] の横にあるボックスがオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3e229-150">Verify that in the SIP Options ping section, the box is checked next to "Enable OPTIONS Ping to monitor destination status for Trunks with Service Type 'None (Default)'."</span></span>
    
12. <span data-ttu-id="3e229-151">終了したら、[**Add New**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e229-151">When you are finished, click on **Add New**.</span></span>
    
13. <span data-ttu-id="3e229-152">「Cisco 統合 CM 管理-\>デバイス-\>トランク」に移動します。</span><span class="sxs-lookup"><span data-stu-id="3e229-152">Navigate to Cisco Unified CM Administration-\>Device-\>Trunk.</span></span> 
    
14. <span data-ttu-id="3e229-153">[Device Protocol] を [SIP] に設定し、[**Next**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e229-153">Set the Device Protocol to SIP and press **Next**.</span></span>
    
15. <span data-ttu-id="3e229-154">[Device Information] で、[Device Name] と [Description] (通常は "SfBVideoInterop_SIPTrunk" の形式) の設定を行い、[Media Resource Group List] を、適切なメディア リソースが含まれる MRGL に設定します。</span><span class="sxs-lookup"><span data-stu-id="3e229-154">Under Device Information, Set the Device Name and Description (probably to something like SfBVideoInterop_SIPTrunk), and set the Media Resource Group List to an MRGL that contains the right media resources.</span></span> 
    
16. <span data-ttu-id="3e229-155">さらに下にスクロールします。</span><span class="sxs-lookup"><span data-stu-id="3e229-155">Scroll down further.</span></span> <span data-ttu-id="3e229-156">ビデオ通話には [Media Termination Point (MTP)] は不要であり、まだオフにされていない場合はオフにします。</span><span class="sxs-lookup"><span data-stu-id="3e229-156">Media Termination Point (MTP) is not required for Video Calls, if it is not already unchecked, uncheck it.</span></span> <span data-ttu-id="3e229-157">[**Run on all active Unified CM Nodes**] のオプションをオンにします。</span><span class="sxs-lookup"><span data-stu-id="3e229-157">Check the option to **Run on all active Unified CM Nodes**.</span></span> <span data-ttu-id="3e229-158">Skype for Business Server の設定には、すべての CUCM ノードを追加する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="3e229-158">Please note that you should add all CUCM nodes to the Skype for Business Server configuration.</span></span>
    
17. <span data-ttu-id="3e229-159">さらに下にスクロールします。</span><span class="sxs-lookup"><span data-stu-id="3e229-159">Scroll down further.</span></span> <span data-ttu-id="3e229-160">以下に示すように、[Inbound Calls and Connected Party Settings] のオプションを設定します。</span><span class="sxs-lookup"><span data-stu-id="3e229-160">Set the Inbound Calls and Connected Party Settings options as shown.</span></span>
    
    |<span data-ttu-id="3e229-161">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="3e229-161">**Parameter**</span></span>|<span data-ttu-id="3e229-162">**推奨設定**</span><span class="sxs-lookup"><span data-stu-id="3e229-162">**Recommended setting**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="3e229-163">Calling Search Space</span><span class="sxs-lookup"><span data-stu-id="3e229-163">Calling Search Space</span></span>  <br/> |<span data-ttu-id="3e229-164">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="3e229-164">CSS_SfBVideoInterop</span></span>  <br/> |
    |<span data-ttu-id="3e229-165">AAR Calling Search Space</span><span class="sxs-lookup"><span data-stu-id="3e229-165">AAR Calling Search Space</span></span>  <br/> |<span data-ttu-id="3e229-166">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="3e229-166">CSS_SfBVideoInterop</span></span>  <br/> |
    |<span data-ttu-id="3e229-167">Connected Party Transformation CSS</span><span class="sxs-lookup"><span data-stu-id="3e229-167">Connected Party Transformation CSS</span></span>  <br/> |<span data-ttu-id="3e229-168">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="3e229-168">CSS_SfBVideoInterop</span></span>  <br/> |
   
18. <span data-ttu-id="3e229-169">さらに下にスクロールします。</span><span class="sxs-lookup"><span data-stu-id="3e229-169">Scroll down further.</span></span> <span data-ttu-id="3e229-170">SIP トランク構成の「SIP 情報の送信先」セクションで、VIS Pool の FQDN またはプール内の個々の VIS サーバーの IP アドレスを指定します (複数のエントリを追加する)。</span><span class="sxs-lookup"><span data-stu-id="3e229-170">Under the SIP Information Destination section of the SIP Trunk configuration, specify the VIS Pool's FQDN or the IP address of individual VIS servers in the pool (adding multiple entries).</span></span> <span data-ttu-id="3e229-171">[Destination Port] で、VIS が CUCM からの接続をリッスンするポートを指定します (既定値は 6001)。</span><span class="sxs-lookup"><span data-stu-id="3e229-171">In the Destination Port specify the Port that VIS is listening at for connections from CUCM (the default is 6001).</span></span> <span data-ttu-id="3e229-172">また以下のように、以前に作成した SIP トランクのセキュリティ プロファイルと SIP プロファイルも指定します。</span><span class="sxs-lookup"><span data-stu-id="3e229-172">Also specify the SIP Trunk security profile and SIP profile you created earlier, as shown.</span></span>
    
    |<span data-ttu-id="3e229-173">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="3e229-173">**Parameter**</span></span>|<span data-ttu-id="3e229-174">**推奨設定**</span><span class="sxs-lookup"><span data-stu-id="3e229-174">**Recommended setting**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="3e229-175">SIP Trunk Security Profile</span><span class="sxs-lookup"><span data-stu-id="3e229-175">SIP Trunk Security Profile</span></span>  <br/> |<span data-ttu-id="3e229-176">SfBVideoInterop_SecurityProfile</span><span class="sxs-lookup"><span data-stu-id="3e229-176">SfBVideoInterop_SecurityProfile</span></span>  <br/> |
    |<span data-ttu-id="3e229-177">Rerouting Calling Search Space</span><span class="sxs-lookup"><span data-stu-id="3e229-177">Rerouting Calling Search Space</span></span>  <br/> |<span data-ttu-id="3e229-178">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="3e229-178">CSS_SfBVideoInterop</span></span>  <br/> |
    |<span data-ttu-id="3e229-179">Out-of-Dialog Refer Calling Search Space</span><span class="sxs-lookup"><span data-stu-id="3e229-179">Out-of-Dialog Refer Calling Search Space</span></span>  <br/> |<span data-ttu-id="3e229-180">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="3e229-180">CSS_SfBVideoInterop</span></span>  <br/> |
    |<span data-ttu-id="3e229-181">Subscribe Calling Search Space</span><span class="sxs-lookup"><span data-stu-id="3e229-181">Subscribe Calling Search Space</span></span>  <br/> |<span data-ttu-id="3e229-182">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="3e229-182">CSS_SfBVideoInterop</span></span>  <br/> |
    |<span data-ttu-id="3e229-183">SIP Profile</span><span class="sxs-lookup"><span data-stu-id="3e229-183">SIP Profile</span></span>  <br/> |<span data-ttu-id="3e229-184">SfBVideoInterop_SIPProfile</span><span class="sxs-lookup"><span data-stu-id="3e229-184">SfBVideoInterop_SIPProfile</span></span>  <br/> |
    |<span data-ttu-id="3e229-185">DTMF Signaling Method</span><span class="sxs-lookup"><span data-stu-id="3e229-185">DTMF Signaling Method</span></span>  <br/> |<span data-ttu-id="3e229-186">RFC 2833</span><span class="sxs-lookup"><span data-stu-id="3e229-186">RFC 2833</span></span>  <br/> |
   
19.  <span data-ttu-id="3e229-187">さらに下にスクロールします。</span><span class="sxs-lookup"><span data-stu-id="3e229-187">Scroll down further.</span></span> <span data-ttu-id="3e229-188">システムに適した [Recording Information] の設定を行います。</span><span class="sxs-lookup"><span data-stu-id="3e229-188">Set the Recording Information as appropriate for your system.</span></span> <span data-ttu-id="3e229-189">**[なし**] に設定したままにしておくこともできます。</span><span class="sxs-lookup"><span data-stu-id="3e229-189">It's fine to leave it set to **None**.</span></span> 
    
20. <span data-ttu-id="3e229-190">終了したら、[**Add New**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e229-190">When you are finished, click on **Add New**.</span></span>
    
21. <span data-ttu-id="3e229-191">「Cisco ユニファイド CM の管理\>」に移動\>します。通話\>ルーティング-ルート/ハント-ルートパターン。</span><span class="sxs-lookup"><span data-stu-id="3e229-191">Navigate to Cisco Unified CM Administration-\>Call Routing-\>Route/Hunt-\>Route pattern.</span></span>
    
22. <span data-ttu-id="3e229-p111">[Route Pattern Configuration] 画面で、以下に示すようにパターン定義のパラメーターを入力します。[Called Party Transformations] セクションまで下にスクロールし、以下に示すようにマスクを設定して、完了したら [**Add New**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e229-p111">In the Route Pattern Configuration screen, enter the Pattern definition parameters shown below. Scroll down to the Called Party Transformations section and set the mask as shown, and then click on **Add New** when finished.</span></span>
    
    |<span data-ttu-id="3e229-194">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="3e229-194">**Parameter**</span></span>|<span data-ttu-id="3e229-195">**推奨設定**</span><span class="sxs-lookup"><span data-stu-id="3e229-195">**Recommended setting**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="3e229-196">Route Pattern</span><span class="sxs-lookup"><span data-stu-id="3e229-196">Route Pattern</span></span>  <br/> |<span data-ttu-id="3e229-197">7779999</span><span class="sxs-lookup"><span data-stu-id="3e229-197">7779999</span></span>  <br/> |
    |<span data-ttu-id="3e229-198">Route Partition</span><span class="sxs-lookup"><span data-stu-id="3e229-198">Route Partition</span></span>  <br/> |<span data-ttu-id="3e229-199">SfBVideoInterop_RoutePartition</span><span class="sxs-lookup"><span data-stu-id="3e229-199">SfBVideoInterop_RoutePartition</span></span>  <br/> |
    |<span data-ttu-id="3e229-200">Description</span><span class="sxs-lookup"><span data-stu-id="3e229-200">Description</span></span>  <br/> |<span data-ttu-id="3e229-201">Partition for SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="3e229-201">Partition for SfBVideoInterop</span></span>  <br/> |
    |<span data-ttu-id="3e229-202">Gateway/Route List</span><span class="sxs-lookup"><span data-stu-id="3e229-202">Gateway/Route List</span></span>  <br/> |<span data-ttu-id="3e229-203">SfBVideoInterop_SIPTrunk</span><span class="sxs-lookup"><span data-stu-id="3e229-203">SfBVideoInterop_SIPTrunk</span></span>  <br/> |
    |<span data-ttu-id="3e229-204">Called Party Transform Mask</span><span class="sxs-lookup"><span data-stu-id="3e229-204">Called Party Transform Mask</span></span>  <br/> |<span data-ttu-id="3e229-205">+14257779999</span><span class="sxs-lookup"><span data-stu-id="3e229-205">+14257779999</span></span>  <br/> |
   
23. <span data-ttu-id="3e229-206">「Cisco ユニファイド CM 管理-\>通話ルーティング-\>SIP ルートパターン」に移動します。</span><span class="sxs-lookup"><span data-stu-id="3e229-206">Navigate to Cisco Unified CM Administration-\>Call Routing-\>SIP Route Pattern.</span></span>
    
24. <span data-ttu-id="3e229-207">[SIP Route Pattern Configuration] 画面で、以下に示すように [Pattern Definition] のオプションを設定し、[**Add New**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e229-207">In the SIP Route Pattern Configuration screen, set the Pattern Definition options as shown, and click on **Add New**.</span></span>
    
    |<span data-ttu-id="3e229-208">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="3e229-208">**Parameter**</span></span>|<span data-ttu-id="3e229-209">**推奨設定**</span><span class="sxs-lookup"><span data-stu-id="3e229-209">**Recommended setting**</span></span>|
    |:-----|:-----|
    | <span data-ttu-id="3e229-210">Pattern Usage</span><span class="sxs-lookup"><span data-stu-id="3e229-210">Pattern Usage</span></span> <br/> |<span data-ttu-id="3e229-211">Domain Routing</span><span class="sxs-lookup"><span data-stu-id="3e229-211">Domain Routing</span></span>  <br/> |
    |<span data-ttu-id="3e229-212">IPv4 Pattern</span><span class="sxs-lookup"><span data-stu-id="3e229-212">IPv4 Pattern</span></span>  <br/> |<span data-ttu-id="3e229-213">contoso.com (IPv6 を使用する場合は空白のまま)</span><span class="sxs-lookup"><span data-stu-id="3e229-213">contoso.com (leave blank if using IPv6)</span></span>  <br/> |
    |<span data-ttu-id="3e229-214">IPv6 Pattern</span><span class="sxs-lookup"><span data-stu-id="3e229-214">IPv6 Pattern</span></span>  <br/> |<span data-ttu-id="3e229-215">contoso.com (IPv4 を使用する場合は空白のまま)</span><span class="sxs-lookup"><span data-stu-id="3e229-215">contoso.com (leave blank if using IPv4)</span></span>  <br/> |
    |<span data-ttu-id="3e229-216">Description</span><span class="sxs-lookup"><span data-stu-id="3e229-216">Description</span></span>  <br/> |<span data-ttu-id="3e229-217">SIPRoute Pattern to mediarv</span><span class="sxs-lookup"><span data-stu-id="3e229-217">SIPRoute Pattern to mediarv</span></span>  <br/> |
    |<span data-ttu-id="3e229-218">Route Partition</span><span class="sxs-lookup"><span data-stu-id="3e229-218">Route Partition</span></span>  <br/> |<span data-ttu-id="3e229-219">SfBVideoInterop_RoutePartition</span><span class="sxs-lookup"><span data-stu-id="3e229-219">SfBVideoInterop_RoutePartition</span></span>  <br/> |
    |<span data-ttu-id="3e229-220">SIP Trunk/Route List</span><span class="sxs-lookup"><span data-stu-id="3e229-220">SIP Trunk/Route List</span></span>  <br/> |<span data-ttu-id="3e229-221">SfBVideoInterop_SIPTrunk</span><span class="sxs-lookup"><span data-stu-id="3e229-221">SfBVideoInterop_SIPTrunk</span></span>  <br/> |
    |<span data-ttu-id="3e229-222">[Block Pattern] チェック ボックス</span><span class="sxs-lookup"><span data-stu-id="3e229-222">Block Pattern checkbox</span></span>  <br/> |<span data-ttu-id="3e229-223">オフのまま</span><span class="sxs-lookup"><span data-stu-id="3e229-223">leave unchecked</span></span>  <br/> |
   
25. <span data-ttu-id="3e229-224">音声またはビデオのビット レートを既定の設定から変更した場合は、それらを既定に戻す必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e229-224">If you have changed the audio or video bit rates from the default settings, you will need to return them to the defaults.</span></span> <span data-ttu-id="3e229-225">音声/ビデオ通話のビットレートを設定するには、「Cisco 統合 CM 管理\>\>\>」に移動します。</span><span class="sxs-lookup"><span data-stu-id="3e229-225">To set the bit rate for Audio/Video calls, navigate to Cisco Unified CM Administration-\>System-\>Region Information-\>Region.</span></span> <span data-ttu-id="3e229-226">参照用に既定値を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="3e229-226">The defaults are shown below for reference:</span></span>
    
    |<span data-ttu-id="3e229-227">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="3e229-227">**Parameter**</span></span>|<span data-ttu-id="3e229-228">**推奨設定**</span><span class="sxs-lookup"><span data-stu-id="3e229-228">**Recommended setting**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="3e229-229">Region</span><span class="sxs-lookup"><span data-stu-id="3e229-229">Region</span></span>  <br/> |<span data-ttu-id="3e229-230">既定</span><span class="sxs-lookup"><span data-stu-id="3e229-230">Default</span></span>  <br/> |
    |<span data-ttu-id="3e229-231">オーディオコーデックの基本設定リスト</span><span class="sxs-lookup"><span data-stu-id="3e229-231">Audio Codec Preference List</span></span>  <br/> |<span data-ttu-id="3e229-232">システムの既定値</span><span class="sxs-lookup"><span data-stu-id="3e229-232">System Default</span></span>  <br/> |
    |<span data-ttu-id="3e229-233">オーディオビットレートの最大値</span><span class="sxs-lookup"><span data-stu-id="3e229-233">Maximum Audio Bit Rate</span></span>  <br/> |<span data-ttu-id="3e229-234">64 kbps (722, G)</span><span class="sxs-lookup"><span data-stu-id="3e229-234">64 kbps (G.722, G.711)</span></span>  <br/> |
    |<span data-ttu-id="3e229-235">ビデオ通話の最大セッションビットレート</span><span class="sxs-lookup"><span data-stu-id="3e229-235">Maximum Session Bit Rate for Video Calls</span></span>  <br/> |<span data-ttu-id="3e229-236">20万 kbps</span><span class="sxs-lookup"><span data-stu-id="3e229-236">200000 kbps</span></span>  <br/> |
    |<span data-ttu-id="3e229-237">セッションの最大ビットレート</span><span class="sxs-lookup"><span data-stu-id="3e229-237">Maximum Session Bit Rate</span></span>  <br/> |<span data-ttu-id="3e229-238">20億 kbps</span><span class="sxs-lookup"><span data-stu-id="3e229-238">2000000000 kbps</span></span>  <br/> |
   
<span data-ttu-id="3e229-239">この時点で、CUCM ビデオゲートウェイは、VIS と連携するように構成されています。</span><span class="sxs-lookup"><span data-stu-id="3e229-239">At this point the CUCM video gateway is configured to work with the VIS.</span></span> <span data-ttu-id="3e229-240">対応する構成は、統合する各 VTC に対して行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e229-240">Corresponding configuration will need to be done on each VTC you wish to integrate.</span></span>
> [!NOTE]
> <span data-ttu-id="3e229-241">回復性を向上させるために、2つ目のビデオ相互運用サーバーまたは VIS プールで動作するように、この CUCM ゲートウェイを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="3e229-241">To improve resiliency, you may want to configure this CUCM gateway to work with a second Video Interop Server or VIS pool.</span></span> <span data-ttu-id="3e229-242">詳細については、「[Resiliency mechanisms](../../plan-your-deployment/video-interop-server.md#resiliency)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e229-242">See [Resiliency mechanisms](../../plan-your-deployment/video-interop-server.md#resiliency) for more information.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3e229-243">関連項目</span><span class="sxs-lookup"><span data-stu-id="3e229-243">See also</span></span>

[<span data-ttu-id="3e229-244">Skype for Business Server との相互運用用に VTC を構成する</span><span class="sxs-lookup"><span data-stu-id="3e229-244">Configure a VTC for Interoperation with Skype for Business Server</span></span>](configure-a-vtc-for-interoperation.md)
