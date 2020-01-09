---
title: Skype 会議ブロードキャストを有効にする
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: micchan
ms.topic: article
ms.assetid: 5299cce0-850e-42dc-b6ae-2d0ee775c4a9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- SMB
description: 組織内のユーザーが Skype 会議ブロードキャストを使用できるようにするには、それを有効にする必要があります。 これを行うには、Windows PowerShell の使い方を知っている必要があります。 Windows PowerShell がわからない場合は、Microsoft パートナーを採用してこの手順を実行することを検討してください。
ms.openlocfilehash: edf9c372a98da9e09d7e9040c6d035e389c8b1ec
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "40989142"
---
# <a name="enable-skype-meeting-broadcast"></a><span data-ttu-id="b4140-105">Skype 会議ブロードキャストを有効にする</span><span class="sxs-lookup"><span data-stu-id="b4140-105">Enable Skype Meeting Broadcast</span></span>

<span data-ttu-id="b4140-106">組織内のユーザーが Skype 会議ブロードキャストを使用できるようにするには、それを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b4140-106">Before the people in your organization can use Skype Meeting Broadcast, you need to enable it.</span></span> <span data-ttu-id="b4140-107">これを行うには、Windows PowerShell の使い方を知っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b4140-107">To do this, you need to know how to use Windows PowerShell.</span></span> <span data-ttu-id="b4140-108">Windows PowerShell がわからない場合は、 [Microsoft パートナー](https://go.microsoft.com/fwlink/?linkid=391089)を採用してこの手順を実行することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="b4140-108">If you don't know Windows PowerShell, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>

  
## <a name="enable-skype-meeting-broadcast-using-the-skype-for-business-admin-center"></a><span data-ttu-id="b4140-109">Skype for Business 管理センターを使用して Skype 会議ブロードキャストを有効にする</span><span class="sxs-lookup"><span data-stu-id="b4140-109">Enable Skype Meeting Broadcast using the Skype for Business admin center</span></span>

<span data-ttu-id="b4140-110">![Skype for Business のロゴを表示したアイコン](../images/sfb-logo-30x30.png) **Skype for Business 管理センターの使用**</span><span class="sxs-lookup"><span data-stu-id="b4140-110">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="b4140-111">Office 365 グローバル管理者アカウントまたは Skype for Business 管理者アカウントでサインイン[https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home)します。</span><span class="sxs-lookup"><span data-stu-id="b4140-111">Sign in with your Office 365 global admin account or Skype for Business admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>
    
2. <span data-ttu-id="b4140-112">管理センターで、[**管理センター** > **チーム**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="b4140-112">In the admin center, go to **Admin centers** > **Teams**.</span></span>
    
3. <span data-ttu-id="b4140-113">**Teams 管理センター**で、[従来の**ポータル** > **オンライン会議** > **ブロードキャスト会議**] に移動し、[ **Skype 会議ブロードキャストを有効に**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b4140-113">In the **Teams admin center**, go to **Legacy portal** > **Online meetings** > **Broadcast meetings**, and then select **Enable Skype Meeting Broadcast**.</span></span>
    
## <a name="enable-skype-meeting-broadcast-using-powershell"></a><span data-ttu-id="b4140-114">PowerShell を使用して Skype 会議ブロードキャストを有効にする</span><span class="sxs-lookup"><span data-stu-id="b4140-114">Enable Skype Meeting Broadcast using PowerShell</span></span>

1. <span data-ttu-id="b4140-115">Windows PowerShell のバージョン3.0 またはそれ以降を実行していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b4140-115">Verify that you are running version 3.0 or higher of Windows PowerShell.</span></span>
    
2. <span data-ttu-id="b4140-116">3.0 以降のバージョンが実行されていることを確認する場合: **[スタート] メニュー** > **[Windows PowerShell]**。</span><span class="sxs-lookup"><span data-stu-id="b4140-116">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
3. <span data-ttu-id="b4140-117">[ _Windows PowerShell_] ウィンドウに「 **Get-Host**」と入力して、バージョンを確認します。</span><span class="sxs-lookup"><span data-stu-id="b4140-117">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
4. <span data-ttu-id="b4140-118">バージョン 3.0 以降を使用していない場合は、Windows PowerShell の更新プログラムをダウンロードおよびインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b4140-118">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="b4140-119">Windows PowerShell をバージョン4.0 にダウンロードして更新するには、「 [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b4140-119">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="b4140-120">メッセージが表示されたら、コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="b4140-120">Restart your computer when you are prompted.</span></span>
    
5. <span data-ttu-id="b4140-p104">Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成できるように、Skype for Business Online の Windows PowerShell モジュールもインストールする必要があります。このモジュールは、64 ビット版のコンピューターでのみサポートされており、「[Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688)」の Microsoft ダウンロード センターからダウンロードできます。メッセージが表示されたら、コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="b4140-p104">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
6. <span data-ttu-id="b4140-124">[**スタート] メニュー**で、[ **Windows PowerShell**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="b4140-124">From the **Start Menu**, choose **Windows PowerShell**.</span></span>
    
7. <span data-ttu-id="b4140-125">[ **Windows PowerShell**] ウィンドウで、次を実行して、Office 365 の組織に接続します。</span><span class="sxs-lookup"><span data-stu-id="b4140-125">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
   ```PowerShell
   $Credential = get-credential
   $O365Session = New-CsOnlineSession -Credential $credential
   Import-PSSession $O365Session
   ```

8. <span data-ttu-id="b4140-126">次を実行して、現在の Skype 会議ブロードキャストの構成を確認します。</span><span class="sxs-lookup"><span data-stu-id="b4140-126">Confirm your current Skype Meeting Broadcast configuration by running:</span></span>
    
   ```PowerShell
   Get-CsBroadcastMeetingConfiguration
   ```

    <span data-ttu-id="b4140-127">パラメーター _EnableBroadcastMeeting_がに`False`設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b4140-127">Verify that the parameter  _EnableBroadcastMeeting_ is set to `False`.</span></span>
    
     ![組織の Skype 会議ブロードキャストを有効にするコマンドレット。](../images/44abe30d-d3df-4ca9-9761-603a7ff78723.png)
  
9. <span data-ttu-id="b4140-129">次を実行して、組織の Skype 会議ブロードキャストを有効にします。</span><span class="sxs-lookup"><span data-stu-id="b4140-129">Enable Skype Meeting Broadcast for your organization by running:</span></span>
    
   ```PowerShell
   Set-CsBroadcastMeetingConfiguration -EnableBroadcastMeeting $True
   ```

    <span data-ttu-id="b4140-130">設定が有効になっていることを確認`Get-CsBroadcastMeetingConfiguration`するには、もう一度実行します。</span><span class="sxs-lookup"><span data-stu-id="b4140-130">You can confirm that the setting is enabled by running  `Get-CsBroadcastMeetingConfiguration` again.</span></span>
    
     ![組織の Skype 会議ブロードキャストを有効にするコマンドレット。](../images/788515f0-32c9-415a-9235-6bfbe095e6f3.png)
  
    > [!TIP]
    > <span data-ttu-id="b4140-132">変更を加えた後は、Skype 会議ブロードキャストのポータルに変更が反映されるまでに最長で1時間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="b4140-132">After you make the change, it may take up to an hour to take effect in the Skype Meeting Broadcast portal.</span></span> 
  
10. <span data-ttu-id="b4140-133">ユーザーは、社内の他のユーザーとブロードキャスト会議を開催できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="b4140-133">Your users can now hold broadcast meetings with other users in your business.</span></span> <span data-ttu-id="b4140-134">開始するには、「 [Skype 会議ブロードキャストとは](https://support.office.com/en-us/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b4140-134">To get them started, point them to [What is a Skype Meeting Broadcast?](https://support.office.com/en-us/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)</span></span>
    
## <a name="configure-your-network-to-broadcast-meetings-with-external-attendees"></a><span data-ttu-id="b4140-135">外部の出席者との会議をブロードキャストするようにネットワークを設定する</span><span class="sxs-lookup"><span data-stu-id="b4140-135">Configure your network to broadcast meetings with external attendees</span></span>

<span data-ttu-id="b4140-136">ファイアウォールを使用していて、一般法人以外の人とのブロードキャストを保留にする場合は、次の手順を使用してネットワークを設定する必要があります。 [Skype 会議ブロードキャスト用にネットワーク](set-up-your-network-for-skype-meeting-broadcast.md)をセットアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b4140-136">If you have a firewall, and you want to hold broadcasts with people outside of your business (who are not a federated business), you need to configure your network using these instructions: [Set up your network for Skype Meeting Broadcast](set-up-your-network-for-skype-meeting-broadcast.md).</span></span> 
  
<span data-ttu-id="b4140-137">ファイアウォールの設定が整っていない場合は、この手順を実行するために[Microsoft パートナー](https://go.microsoft.com/fwlink/?linkid=391089)を採用することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="b4140-137">If you aren't experienced with configuring your firewall, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>
  
<span data-ttu-id="b4140-138">この手順をスキップして、別の企業をフェデレーションに追加する場合は、「[ユーザーが外部の Skype For business ユーザーに連絡できるように](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b4140-138">To skip this step and instead add another business to your federation, see [Allow users to contact external Skype for Business users](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="b4140-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="b4140-139">Related topics</span></span>

[<span data-ttu-id="b4140-140">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="b4140-140">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
  
[<span data-ttu-id="b4140-141">Skype for Business Online のセットアップ</span><span class="sxs-lookup"><span data-stu-id="b4140-141">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

  
 
