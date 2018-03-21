---
title: "Skype 会議ブロードキャストを有効にする"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: micchan
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 5299cce0-850e-42dc-b6ae-2d0ee775c4a9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- SMB
description: "組織のユーザーが Skype 会議ブロードキャストを使用できるようにする前に、それを有効にしておく必要があります。この手順を実行するには、Windows PowerShell の使い方を知っておく必要があります。Windows PowerShell に慣れていない場合は、マイクロソフトのパートナーに依頼してこの手順を実行することを考慮してください。"
ms.openlocfilehash: 3748ca75efcaed479e27fe253c5b3a8399e381d6
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2018
---
# <a name="enable-skype-meeting-broadcast"></a><span data-ttu-id="134c2-105">Skype 会議ブロードキャストを有効にする</span><span class="sxs-lookup"><span data-stu-id="134c2-105">Enable Skype Meeting Broadcast</span></span>

<span data-ttu-id="134c2-p102">[] 組織のユーザーが Skype 会議ブロードキャストを使用できるようにする前に、それを有効にしておく必要があります。この手順を実行するには、Windows PowerShell の使い方を知っておく必要があります。Windows PowerShell に慣れていない場合は、[マイクロソフトのパートナー](https://go.microsoft.com/fwlink/?linkid=391089)に依頼してこの手順を実行することを考慮してください。</span><span class="sxs-lookup"><span data-stu-id="134c2-p102">Before the people in your organization can use Skype Meeting Broadcast, you need to enable it. To do this, you need to know how to use Windows PowerShell. If you don't know Windows PowerShell, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="134c2-p103">Skype 会議ブロードキャスト は既定でオフになっています。これは、ブロードキャスト会議のメディア コンテンツの配布は、ブロードキャストを視聴する数千人のユーザーを対象にきわめて広範囲に配信されるように、Microsoft Azure のコンテンツ配信ネットワーク (CDN) を使用するためです。CDN を経由して配信されるメディア コンテンツはまとめて暗号化され、CDN キャッシュには有効期限が設定されます。また、Azure CDN コンポーネントは、EU データ保護条令に由来する EU モデル契約条項の一部に準拠していない場合があります。この機能を有効にすると、ここに記載されている注意事項に同意したことになります。</span><span class="sxs-lookup"><span data-stu-id="134c2-p103">Skype Meeting Broadcast is turned off by default because distribution of the media content of a broadcast meeting uses Microsoft Azure's Content Delivery Network (CDN) to achieve very high scale to support thousands of people watching a broadcast. The chunked media content passing through the CDN is encrypted, and the CDN cache has a limited lifetime. Also, the Azure CDN component may not yet meet all elements of the EU Model Clauses stemming from the EU Data Protection Directive. By enabling this feature, you acknowledge this notice.</span></span> 
  
## <a name="enable-skype-meeting-broadcast-using-the-skype-for-business-admin-center"></a><span data-ttu-id="134c2-113">Skype for Business 管理センターを使用して Skype 会議ブロードキャストを有効にする</span><span class="sxs-lookup"><span data-stu-id="134c2-113">Enable Skype Meeting Broadcast using the Skype for Business admin center</span></span>

1. <span data-ttu-id="134c2-114">[https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) でOffice 365 のグローバル管理者アカウントを使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="134c2-114">Sign in with your Office 365 global admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>
    
2. <span data-ttu-id="134c2-115">Office 365 の管理センターで**管理センター**に移動する > **ビジネス用の Skype**です。</span><span class="sxs-lookup"><span data-stu-id="134c2-115">In the Office 365 Admin center go to **Admin centers** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="134c2-116">**ビジネス管理センターの Skype**では、**オンライン会議**に移動 > **会議のブロードキャスト**、および、 **Skype 会議のブロードキャストを有効にする**] を選択をします。</span><span class="sxs-lookup"><span data-stu-id="134c2-116">In the **Skype for Business admin center**, go to **Online meetings** > **Broadcast meetings**, and then select **Enable Skype Meeting Broadcast**.</span></span>
    
## <a name="enable-skype-meeting-broadcast-using-powershell"></a><span data-ttu-id="134c2-117">PowerShell を使用して Skype 会議ブロードキャストを有効にする</span><span class="sxs-lookup"><span data-stu-id="134c2-117">Enable Skype Meeting Broadcast using PowerShell</span></span>

1. <span data-ttu-id="134c2-118">Windows PowerShell のバージョン 3.0 以上を実行していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="134c2-118">Verify that you are running version 3.0 or higher of Windows PowerShell.</span></span>
    
1. <span data-ttu-id="134c2-119">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="134c2-119">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="134c2-120">[ **Windows PowerShell**] ウィンドウに「 _Get-Host_」と入力して、バージョンを確認します。</span><span class="sxs-lookup"><span data-stu-id="134c2-120">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="134c2-p104">バージョン 3.0 以降を使用していない場合は、Windows PowerShell の更新プログラムをダウンロードおよびインストールする必要があります。Windows PowerShell をダウンロードして、バージョン 4.0 に更新するには、「[Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845)」を参照してください。メッセージが表示されたら、コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="134c2-p104">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="134c2-p105">Skype for Business Online 用の Windows PowerShell モジュールもインストールする必要があります。このモジュールでは、リモート Windows PowerShell セッションを作成して Skype for Business Online に接続できます。このモジュールは、64 ビット版のコンピューターでのみサポートされており、Microsoft ダウンロード センターの「[Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688)」からダウンロードできます。再起動を求めるメッセージが表示されたら、コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="134c2-p105">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
2. <span data-ttu-id="134c2-127">[ **スタート**] メニューで [ **Windows PowerShell**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="134c2-127">From the **Start Menu**, choose **Windows PowerShell**.</span></span>
    
3. <span data-ttu-id="134c2-128">[ **Windows PowerShell**] ウィンドウで、以下のコマンドを実行して、Office 365 の組織に接続します。</span><span class="sxs-lookup"><span data-stu-id="134c2-128">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
  ```
  $Credential = get-credential
  $O365Session = New-CsOnlineSession -Credential $credential
  Import-PSSession $O365Session
  ```

4. <span data-ttu-id="134c2-129">以下のコマンドを実行して、現在の Skype 会議ブロードキャストの構成を確認します。</span><span class="sxs-lookup"><span data-stu-id="134c2-129">Confirm your current Skype Meeting Broadcast configuration by running:</span></span>
    
  ```
  Get-CsBroadcastMeetingConfiguration
  ```

    <span data-ttu-id="134c2-130">_EnableBroadcastMeeting_ パラメーターが `False` に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="134c2-130">Verify that the parameter  _EnableBroadcastMeeting_ is set to `False`.</span></span>
    
     ![組織に対して Skype Meeting Broadcast を有効にするコマンドレット。](../images/44abe30d-d3df-4ca9-9761-603a7ff78723.png)
  
5. <span data-ttu-id="134c2-132">以下のコマンドを実行して、組織の Skype 会議ブロードキャストを有効にします。</span><span class="sxs-lookup"><span data-stu-id="134c2-132">Enable Skype Meeting Broadcast for your organization by running:</span></span>
    
  ```
  Set-CsBroadcastMeetingConfiguration -EnableBroadcastMeeting $True
  ```

    <span data-ttu-id="134c2-133">`Get-CsBroadcastMeetingConfiguration` をもう一度実行すると、設定が有効になっていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="134c2-133">You can confirm that the setting is enabled by running  `Get-CsBroadcastMeetingConfiguration` again.</span></span>
    
     ![組織に対して Skype Meeting Broadcast を有効にするコマンドレット。](../images/788515f0-32c9-415a-9235-6bfbe095e6f3.png)
  
    > [!TIP]
    > <span data-ttu-id="134c2-135">変更後は、Skype 会議ブロードキャストのポータルに変更が反映されるまでに最長で 1 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="134c2-135">After you make the change, it may take up to an hour to take effect in the Skype Meeting Broadcast portal.</span></span> 
  
6. <span data-ttu-id="134c2-p106">これで、ユーザーは組織の他のユーザーとブロードキャスト会議を開催できます。会議を開催するには、ユーザーに「[Skype 会議ブロードキャストとは](https://support.office.com/en-us/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)」を参照するように指示してください。</span><span class="sxs-lookup"><span data-stu-id="134c2-p106">Your users can now hold broadcast meetings with other users in your business. To get them started, point them to [What is a Skype Meeting Broadcast?](https://support.office.com/en-us/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)</span></span>
    
## <a name="configure-your-network-to-broadcast-meetings-with-external-attendees"></a><span data-ttu-id="134c2-138">ネットワークを構成して、外部の出席者に会議をブロードキャストする</span><span class="sxs-lookup"><span data-stu-id="134c2-138">Configure your network to broadcast meetings with external attendees</span></span>

<span data-ttu-id="134c2-139">ファイアウォールが構成されている場合に組織外 (フェデレーションされていない組織) の参加者とブロードキャストを開催する場合は、「[Skype 会議ブロードキャスト用にネットワークをセットアップする](set-up-your-network-for-skype-meeting-broadcast.md)」の手順に従ってネットワークを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="134c2-139">If you have a firewall, and you want to hold broadcasts with people outside of your business (who are not a federated business), you need to configure your network using these instructions: [Set up your network for Skype Meeting Broadcast](set-up-your-network-for-skype-meeting-broadcast.md).</span></span> 
  
<span data-ttu-id="134c2-140">ファイアウォールの構成に慣れていない場合は、[マイクロソフトのパートナー](https://go.microsoft.com/fwlink/?linkid=391089)に依頼してこの手順を実行することを考慮してください。</span><span class="sxs-lookup"><span data-stu-id="134c2-140">If you aren't experienced with configuring your firewall, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>
  
<span data-ttu-id="134c2-141">この手順をスキップして、代わりに別の組織をフェデレーションに追加する場合は、「[ユーザーが外部の Skype for Business ユーザーに連絡できるようにする](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="134c2-141">To skip this step and instead add another business to your federation, see [Allow users to contact external Skype for Business users](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="134c2-142">See also</span><span class="sxs-lookup"><span data-stu-id="134c2-142">Related topics</span></span>

[<span data-ttu-id="134c2-143">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="134c2-143">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
  
[<span data-ttu-id="134c2-144">Skype for Business Online のセットアップ</span><span class="sxs-lookup"><span data-stu-id="134c2-144">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

