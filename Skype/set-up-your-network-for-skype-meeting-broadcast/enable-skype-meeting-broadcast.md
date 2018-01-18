---
title: "Skype の会議のブロードキャストを有効にします。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 5299cce0-850e-42dc-b6ae-2d0ee775c4a9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: SMB
description: "組織内のユーザーは、Skype の会議のブロードキャストを使用できます、前に有効にする必要があります。 これを行うには、Windows PowerShell を使用する方法を理解する必要があります。 Windows PowerShell がわからない場合は、自動的にこの手順を実行するマイクロソフトのパートナーの採用を検討してください。"
ms.openlocfilehash: 975f0304f2053e23375c5eabc62ec224bedc02e7
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/15/2017
---
# <a name="enable-skype-meeting-broadcast"></a><span data-ttu-id="56488-105">Skype の会議のブロードキャストを有効にします。</span><span class="sxs-lookup"><span data-stu-id="56488-105">Enable Skype Meeting Broadcast</span></span>

<span data-ttu-id="56488-106">組織内のユーザーは、Skype の会議のブロードキャストを使用できます、前に有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="56488-106">Before the people in your organization can use Skype Meeting Broadcast, you need to enable it.</span></span> <span data-ttu-id="56488-107">これを行うには、Windows PowerShell を使用する方法を理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="56488-107">To do this, you need to know how to use Windows PowerShell.</span></span> <span data-ttu-id="56488-108">Windows PowerShell がわからない場合は、自動的にこの手順を実行するのには[マイクロソフトのパートナー](https://go.microsoft.com/fwlink/?linkid=391089)の採用を検討してください。</span><span class="sxs-lookup"><span data-stu-id="56488-108">If you don't know Windows PowerShell, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="56488-109">Skype の会議のブロードキャストは、ブロードキャストの会議のメディア コンテンツの配布では、Microsoft Azure のコンテンツ配信ネットワーク (CDN) を使用して、ブロードキャストを視聴する人の何千ものサポートに非常に高い拡張性を実現するため、デフォルトで無効には。</span><span class="sxs-lookup"><span data-stu-id="56488-109">Skype Meeting Broadcast is turned off by default because distribution of the media content of a broadcast meeting uses Microsoft Azure's Content Delivery Network (CDN) to achieve very high scale to support thousands of people watching a broadcast.</span></span> <span data-ttu-id="56488-110">CDN を通過するチャンクのメディア コンテンツが暗号化され、CDN キャッシュには、一定期間のみ有効です。</span><span class="sxs-lookup"><span data-stu-id="56488-110">The chunked media content passing through the CDN is encrypted, and the CDN cache has a limited lifetime.</span></span> <span data-ttu-id="56488-111">また、Azure CDN コンポーネントまだ満たしていない EU データ保護指令から生じる EU モデルの句のすべての要素です。</span><span class="sxs-lookup"><span data-stu-id="56488-111">Also, the Azure CDN component may not yet meet all elements of the EU Model Clauses stemming from the EU Data Protection Directive.</span></span> <span data-ttu-id="56488-112">この機能を有効にすると、この通知を確認します。</span><span class="sxs-lookup"><span data-stu-id="56488-112">By enabling this feature, you acknowledge this notice.</span></span> 
  
## <a name="enable-skype-meeting-broadcast-using-the-skype-for-business-admin-center"></a><span data-ttu-id="56488-113">ビジネス管理センターに、Skype を使用して、Skype 会議のブロードキャストを有効にします。</span><span class="sxs-lookup"><span data-stu-id="56488-113">Enable Skype Meeting Broadcast using the Skype for Business admin center</span></span>

1. <span data-ttu-id="56488-114">Office 365 グローバル管理アカウントを使用して、[https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) にサインインします。</span><span class="sxs-lookup"><span data-stu-id="56488-114">Sign in with your Office 365 global admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>
    
2. <span data-ttu-id="56488-115">Office 365 の管理センターで**管理センター**に移動する > **ビジネス用の Skype**です。</span><span class="sxs-lookup"><span data-stu-id="56488-115">In the Office 365 Admin center go to **Admin centers** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="56488-116">**ビジネス管理センターの Skype**では、**オンライン会議**に移動 > **会議のブロードキャスト**、および、 **Skype 会議のブロードキャストを有効にする**] を選択をします。</span><span class="sxs-lookup"><span data-stu-id="56488-116">In the **Skype for Business admin center**, go to **Online meetings** > **Broadcast meetings**, and then select **Enable Skype Meeting Broadcast**.</span></span>
    
## <a name="enable-skype-meeting-broadcast-using-powershell"></a><span data-ttu-id="56488-117">PowerShell を使用して、Skype 会議のブロードキャストを有効にします。</span><span class="sxs-lookup"><span data-stu-id="56488-117">Enable Skype Meeting Broadcast using PowerShell</span></span>

1. <span data-ttu-id="56488-118">3.0 以降の Windows PowerShell のバージョンを実行していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="56488-118">Verify that you are running version 3.0 or higher of Windows PowerShell.</span></span>
    
1. <span data-ttu-id="56488-119">3.0 以降のバージョンを実行することを確認するのには: **[スタート] メニュー** > **Windows PowerShell**。</span><span class="sxs-lookup"><span data-stu-id="56488-119">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="56488-120">[ **Windows PowerShell**] ウィンドウに「 _Get-Host_」と入力して、バージョンを確認します。</span><span class="sxs-lookup"><span data-stu-id="56488-120">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="56488-p104">バージョン 3.0 以降を使用していない場合は、Windows PowerShell の更新プログラムをダウンロードおよびインストールする必要があります。Windows PowerShell をダウンロードして、バージョン 4.0 に更新するには、「[Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845)」を参照してください。メッセージが表示されたら、コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="56488-p104">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="56488-p105">Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成できるように、Skype for Business Online の Windows PowerShell モジュールもインストールする必要があります。このモジュールは、64 ビット版のコンピューターでのみサポートされており、「[Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688)」の Microsoft ダウンロード センターからダウンロードできます。メッセージが表示されたら、コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="56488-p105">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
2. <span data-ttu-id="56488-127">[**スタート] メニュー**から**Windows PowerShell**を選択します。</span><span class="sxs-lookup"><span data-stu-id="56488-127">From the **Start Menu**, choose **Windows PowerShell**.</span></span>
    
3. <span data-ttu-id="56488-128">[ **Windows PowerShell**] ウィンドウで、次を実行して、Office 365 の組織に接続します。</span><span class="sxs-lookup"><span data-stu-id="56488-128">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
  ```
  $Credential = get-credential
  $O365Session = New-CsOnlineSession -Credential $credential
  Import-PSSession $O365Session
  ```

4. <span data-ttu-id="56488-129">実行して、現在の Skype 会議のブロードキャストの構成を確認します。</span><span class="sxs-lookup"><span data-stu-id="56488-129">Confirm your current Skype Meeting Broadcast configuration by running:</span></span>
    
  ```
  Get-CsBroadcastMeetingConfiguration
  ```

    <span data-ttu-id="56488-130">パラメーター _EnableBroadcastMeeting_に設定されていることを確認`False`。</span><span class="sxs-lookup"><span data-stu-id="56488-130">Verify that the parameter  _EnableBroadcastMeeting_ is set to `False`.</span></span>
    
     ![Skype 会議をブロードキャストを有効にする組織のコマンドレットです。](../images/44abe30d-d3df-4ca9-9761-603a7ff78723.png)
  
5. <span data-ttu-id="56488-132">Skype 会議のブロードキャストの組織を実行して有効。 にします。</span><span class="sxs-lookup"><span data-stu-id="56488-132">Enable Skype Meeting Broadcast for your organization by running:</span></span>
    
  ```
  Set-CsBroadcastMeetingConfiguration -EnableBroadcastMeeting $True
  ```

    <span data-ttu-id="56488-133">実行して、設定が有効になっていることを確認することができます`Get-CsBroadcastMeetingConfiguration`もう一度。</span><span class="sxs-lookup"><span data-stu-id="56488-133">You can confirm that the setting is enabled by running  `Get-CsBroadcastMeetingConfiguration` again.</span></span>
    
     ![Skype の会議のブロードキャストは、組織のコマンドレットを有効にします。](../images/788515f0-32c9-415a-9235-6bfbe095e6f3.png)
  
    > [!TIP]
    > <span data-ttu-id="56488-135">変更を加えた後、かかる場合があります 1 時間 Skype 会議のブロードキャストのポータルで有効にします。</span><span class="sxs-lookup"><span data-stu-id="56488-135">After you make the change, it may take up to an hour to take effect in the Skype Meeting Broadcast portal.</span></span> 
  
6. <span data-ttu-id="56488-136">ユーザーは、ビジネスで他のユーザーと会議をブロードキャストを今すぐ保持できます。</span><span class="sxs-lookup"><span data-stu-id="56488-136">Your users can now hold broadcast meetings with other users in your business.</span></span> <span data-ttu-id="56488-137">ポイントするために開始、 [Skype の会議のブロードキャストとは何ですか?](https://support.office.com/en-us/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)</span><span class="sxs-lookup"><span data-stu-id="56488-137">To get them started, point them to [What is a Skype Meeting Broadcast?](https://support.office.com/en-us/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)</span></span>
    
## <a name="configure-your-network-to-broadcast-meetings-with-external-attendees"></a><span data-ttu-id="56488-138">外部の出席者を含む会議をブロードキャストするのには、ネットワークを構成します。</span><span class="sxs-lookup"><span data-stu-id="56488-138">Configure your network to broadcast meetings with external attendees</span></span>

<span data-ttu-id="56488-139">ブロードキャスト (メンバーは、ビジネスの連合)、組織外からの人を保持する場合、ファイアウォールがある場合、次の手順を使用してネットワークを構成する必要があります: [Skype 会議のブロードキャストのネットワークをセットアップ](set-up-your-network-for-skype-meeting-broadcast.md)します。</span><span class="sxs-lookup"><span data-stu-id="56488-139">If you have a firewall, and you want to hold broadcasts with people outside of your business (who are not a federated business), you need to configure your network using these instructions: [Set up your network for Skype Meeting Broadcast](set-up-your-network-for-skype-meeting-broadcast.md).</span></span> 
  
<span data-ttu-id="56488-140">した経験がお使いのファイアウォールを構成する場合は、自動的にこの手順を実行するのには[マイクロソフトのパートナー](https://go.microsoft.com/fwlink/?linkid=391089)の採用を検討してください。</span><span class="sxs-lookup"><span data-stu-id="56488-140">If you aren't experienced with configuring your firewall, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>
  
<span data-ttu-id="56488-141">この手順を省略し、代わりに別のビジネスをフェデレーションに追加するのには、[ビジネス ユーザー向けの外部の Skype に連絡を許可する](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="56488-141">To skip this step and instead add another business to your federation, see [Allow users to contact external Skype for Business users](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="56488-142">関連トピック</span><span class="sxs-lookup"><span data-stu-id="56488-142">Related topics</span></span>

[<span data-ttu-id="56488-143">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="56488-143">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
  
[<span data-ttu-id="56488-144">Skype for Business Online のセットアップ</span><span class="sxs-lookup"><span data-stu-id="56488-144">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

