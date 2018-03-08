---
title: "Skype 会議メディアを有効にします。"
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
description: "組織内のユーザー] を使用する Skype 会議メディアを有効にする必要があります。これを行うには、Windows PowerShell を使用する方法を理解する必要があります。Windows PowerShell がわからない場合は、この手順を行うには Microsoft パートナーを雇うを検討してください。"
ms.openlocfilehash: 3748ca75efcaed479e27fe253c5b3a8399e381d6
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="enable-skype-meeting-broadcast"></a><span data-ttu-id="c1bed-105">Skype 会議メディアを有効にします。</span><span class="sxs-lookup"><span data-stu-id="c1bed-105">Enable Skype Meeting Broadcast</span></span>

<span data-ttu-id="c1bed-p102">組織内のユーザー] を使用する Skype 会議メディアを有効にする必要があります。これを行うには、Windows PowerShell を使用する方法を理解する必要があります。Windows PowerShell がわからない場合は、この手順を行うには[Microsoft パートナー](https://go.microsoft.com/fwlink/?linkid=391089)を雇うを検討してください。</span><span class="sxs-lookup"><span data-stu-id="c1bed-p102">Before the people in your organization can use Skype Meeting Broadcast, you need to enable it. To do this, you need to know how to use Windows PowerShell. If you don't know Windows PowerShell, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="c1bed-p103">Skype 会議メディア既定でオフになってブロードキャスト会議のメディア コンテンツの配布は、ブロードキャストの視聴の桁をサポートする最高のスケールを達成するために Microsoft Azure のコンテンツ配信ネットワーク (CDN) を使用するためです。CDN 通過チャンク メディア コンテンツが暗号化され、CDN キャッシュが一定期間のみ有効です。また、Azure CDN コンポーネントがまだを満たしていない EU データ保護ディレクティブから生じる EU モデル句のすべての要素。この機能を有効にすると、この通知を確認します。</span><span class="sxs-lookup"><span data-stu-id="c1bed-p103">Skype Meeting Broadcast is turned off by default because distribution of the media content of a broadcast meeting uses Microsoft Azure's Content Delivery Network (CDN) to achieve very high scale to support thousands of people watching a broadcast. The chunked media content passing through the CDN is encrypted, and the CDN cache has a limited lifetime. Also, the Azure CDN component may not yet meet all elements of the EU Model Clauses stemming from the EU Data Protection Directive. By enabling this feature, you acknowledge this notice.</span></span> 
  
## <a name="enable-skype-meeting-broadcast-using-the-skype-for-business-admin-center"></a><span data-ttu-id="c1bed-113">Business 管理センターの Skype を使用して、Skype 会議メディアを有効にします。</span><span class="sxs-lookup"><span data-stu-id="c1bed-113">Enable Skype Meeting Broadcast using the Skype for Business admin center</span></span>

1. <span data-ttu-id="c1bed-114">[Https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home)での自分の Office 365 グローバル管理者アカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="c1bed-114">Sign in with your Office 365 global admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>
    
2. <span data-ttu-id="c1bed-115">Office 365 管理センターで**管理センター**に移動 > **Skype for Business**します。</span><span class="sxs-lookup"><span data-stu-id="c1bed-115">In the Office 365 Admin center go to **Admin centers** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="c1bed-116">**Skype for Business 管理センター**で、[**オンライン会議**] に移動 > **会議をブロードキャスト**して、 **Skype 会議メディアを有効にする**] を選びますします。</span><span class="sxs-lookup"><span data-stu-id="c1bed-116">In the **Skype for Business admin center**, go to **Online meetings** > **Broadcast meetings**, and then select **Enable Skype Meeting Broadcast**.</span></span>
    
## <a name="enable-skype-meeting-broadcast-using-powershell"></a><span data-ttu-id="c1bed-117">PowerShell を使用して、Skype 会議メディアを有効にします。</span><span class="sxs-lookup"><span data-stu-id="c1bed-117">Enable Skype Meeting Broadcast using PowerShell</span></span>

1. <span data-ttu-id="c1bed-118">Windows PowerShell の 3.0 以降のバージョンを実行することを確認します。</span><span class="sxs-lookup"><span data-stu-id="c1bed-118">Verify that you are running version 3.0 or higher of Windows PowerShell.</span></span>
    
1. <span data-ttu-id="c1bed-119">3.0 以降のバージョンが実行していることを確認する: **[スタート] メニュー** > **Windows PowerShell**します。</span><span class="sxs-lookup"><span data-stu-id="c1bed-119">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="c1bed-120">**Windows PowerShell**のウィンドウで_ホストの取得_を入力して、バージョンを確認してください。</span><span class="sxs-lookup"><span data-stu-id="c1bed-120">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="c1bed-p104">バージョン 3.0 以降をお持ちでない場合は、ダウンロードして、Windows PowerShell への更新プログラムをインストールする必要があります。[Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845)をダウンロードして 4.0 への Windows PowerShell を更新するを参照してください。表示されたら、お使いのコンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="c1bed-p104">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="c1bed-p105">Skype for Business Online できるようにする Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成するのには、Windows PowerShell モジュールをインストールする必要もします。このモジュールでは、64 ビット版コンピューターにのみサポートされているが、 [Skype for Business Online 用の Windows PowerShell モジュール](https://go.microsoft.com/fwlink/?LinkId=294688)では、Microsoft ダウンロード センターからダウンロードできます。求められた場合は、お使いのコンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="c1bed-p105">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
2. <span data-ttu-id="c1bed-127">**[スタート] メニュー**で、 **Windows PowerShell**を選択します。</span><span class="sxs-lookup"><span data-stu-id="c1bed-127">From the **Start Menu**, choose **Windows PowerShell**.</span></span>
    
3. <span data-ttu-id="c1bed-128">**Windows PowerShell**ウィンドウで、実行して、Office 365 の組織に接続します。</span><span class="sxs-lookup"><span data-stu-id="c1bed-128">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
  ```
  $Credential = get-credential
  $O365Session = New-CsOnlineSession -Credential $credential
  Import-PSSession $O365Session
  ```

4. <span data-ttu-id="c1bed-129">実行して、現在の Skype 会議メディアの構成を確認します。</span><span class="sxs-lookup"><span data-stu-id="c1bed-129">Confirm your current Skype Meeting Broadcast configuration by running:</span></span>
    
  ```
  Get-CsBroadcastMeetingConfiguration
  ```

    <span data-ttu-id="c1bed-130">パラメーター _EnableBroadcastMeeting_に設定されていることを確認`False`します。</span><span class="sxs-lookup"><span data-stu-id="c1bed-130">Verify that the parameter  _EnableBroadcastMeeting_ is set to `False`.</span></span>
    
     ![Skype 会議メディアを有効にする組織コマンドレット。](../images/44abe30d-d3df-4ca9-9761-603a7ff78723.png)
  
5. <span data-ttu-id="c1bed-132">Skype 会議メディアの組織を実行して有効。 にします。</span><span class="sxs-lookup"><span data-stu-id="c1bed-132">Enable Skype Meeting Broadcast for your organization by running:</span></span>
    
  ```
  Set-CsBroadcastMeetingConfiguration -EnableBroadcastMeeting $True
  ```

    <span data-ttu-id="c1bed-133">実行して、設定が有効になっていることを確認できる`Get-CsBroadcastMeetingConfiguration`もう一度します。</span><span class="sxs-lookup"><span data-stu-id="c1bed-133">You can confirm that the setting is enabled by running  `Get-CsBroadcastMeetingConfiguration` again.</span></span>
    
     ![Skype 会議メディアには、組織のコマンドレットが有効にします。](../images/788515f0-32c9-415a-9235-6bfbe095e6f3.png)
  
    > [!TIP]
    > <span data-ttu-id="c1bed-135">変更を加えた後にかかることがあります 1 時間を Skype 会議メディア ポータルで有効にします。</span><span class="sxs-lookup"><span data-stu-id="c1bed-135">After you make the change, it may take up to an hour to take effect in the Skype Meeting Broadcast portal.</span></span> 
  
6. <span data-ttu-id="c1bed-p106">ユーザーは、ビジネスで他のユーザーとの会議をブロードキャストを今すぐ保持できます。作業を開始して、対象とする[Skype 会議メディアとは何ですか?](https://support.office.com/en-us/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)</span><span class="sxs-lookup"><span data-stu-id="c1bed-p106">Your users can now hold broadcast meetings with other users in your business. To get them started, point them to [What is a Skype Meeting Broadcast?](https://support.office.com/en-us/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)</span></span>
    
## <a name="configure-your-network-to-broadcast-meetings-with-external-attendees"></a><span data-ttu-id="c1bed-138">外部の参加者との会議をブロードキャストするネットワークを構成します。</span><span class="sxs-lookup"><span data-stu-id="c1bed-138">Configure your network to broadcast meetings with external attendees</span></span>

<span data-ttu-id="c1bed-139">ファイアウォールがあり、ブロードキャスト (メンバーは、フェデレーション ビジネス) ビジネス以外の相手を保持する場合は、次の手順を使用して、ネットワークを構成する必要があります。: [Skype 会議メディア用にネットワークを設定](set-up-your-network-for-skype-meeting-broadcast.md)します。</span><span class="sxs-lookup"><span data-stu-id="c1bed-139">If you have a firewall, and you want to hold broadcasts with people outside of your business (who are not a federated business), you need to configure your network using these instructions: [Set up your network for Skype Meeting Broadcast](set-up-your-network-for-skype-meeting-broadcast.md).</span></span> 
  
<span data-ttu-id="c1bed-140">ファイアウォールの設定に経験豊富な場合は、この手順を行うには[Microsoft パートナー](https://go.microsoft.com/fwlink/?linkid=391089)を雇うを検討してください。</span><span class="sxs-lookup"><span data-stu-id="c1bed-140">If you aren't experienced with configuring your firewall, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>
  
<span data-ttu-id="c1bed-141">この手順をスキップして、代わりに、フェデレーションを別の企業を追加、[ユーザーが外部の Skype for Business ユーザーに連絡できるようにする](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c1bed-141">To skip this step and instead add another business to your federation, see [Allow users to contact external Skype for Business users](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="c1bed-142">関連トピック</span><span class="sxs-lookup"><span data-stu-id="c1bed-142">Related topics</span></span>

[<span data-ttu-id="c1bed-143">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="c1bed-143">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
  
[<span data-ttu-id="c1bed-144">Skype for Business Online をセットアップします。</span><span class="sxs-lookup"><span data-stu-id="c1bed-144">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

