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
f1.keywords:
- NOCSH
ms.custom:
- SMB
description: 組織内のユーザーが Skype 会議ブロードキャストを使う前に、有効にする必要があります。 これを行うには、その使い方を知Windows PowerShell。 この手順を実行Windows PowerShell、Microsoft パートナーを採用することを検討してください。
ms.openlocfilehash: fed56c850d1d909bdd72bda0eb8c1dcd24df0f10
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2021
ms.locfileid: "50568893"
---
# <a name="enable-skype-meeting-broadcast"></a><span data-ttu-id="4607f-105">Skype 会議ブロードキャストを有効にする</span><span class="sxs-lookup"><span data-stu-id="4607f-105">Enable Skype Meeting Broadcast</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4607f-106">Skype for Business Online は 2021 年 7 月 31 日に廃止され、サービスへのアクセスが終了します。</span><span class="sxs-lookup"><span data-stu-id="4607f-106">Skype for Business Online is retiring on July 31, 2021, at which time access to the service will end.</span></span> <span data-ttu-id="4607f-107">Microsoft 365 のコミュニケーションとチームワークのコア クライアントである Microsoft Teams へのアップグレードを開始する方法をお勧めしています。</span><span class="sxs-lookup"><span data-stu-id="4607f-107">We encourage customers to begin the upgrade to Microsoft Teams, the core client for communications and teamwork in Microsoft 365.</span></span>

<span data-ttu-id="4607f-108">組織内のユーザーが Skype 会議ブロードキャストを使用するには、それを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4607f-108">Before the people in your organization can use Skype Meeting Broadcast, you need to enable it.</span></span> <span data-ttu-id="4607f-109">この操作を行うには、この機能の使い方をWindows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="4607f-109">To do this, you need to know how to use Windows PowerShell.</span></span> <span data-ttu-id="4607f-110">この手順を実行 [Windows PowerShell、Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) パートナーを採用することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="4607f-110">If you don't know Windows PowerShell, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>



> [!NOTE]
> <span data-ttu-id="4607f-111">Microsoft Teams 管理センターは、Skype for Business 管理センター (従来のポータル) に置き換えました。</span><span class="sxs-lookup"><span data-stu-id="4607f-111">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="4607f-112">Skype for Business を管理するためのすべての設定が Teams 管理センターに表示されます。</span><span class="sxs-lookup"><span data-stu-id="4607f-112">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="4607f-113">Teams 管理センターで Skype for Business [AD](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) を管理するには、グローバル管理者または Skype for Business 管理者の Azure 管理者の役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="4607f-113">You must be assigned the [Azure AD admin role](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Teams admin center.</span></span> <span data-ttu-id="4607f-114">詳細については、「[Microsoft Teams 管理センターで Skype for Business の設定を管理する](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4607f-114">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json).</span></span>

  
## <a name="enable-skype-meeting-broadcast-using-the-skype-for-business-admin-center"></a><span data-ttu-id="4607f-115">Skype for Business 管理センターを使用して Skype 会議ブロードキャストを有効にする</span><span class="sxs-lookup"><span data-stu-id="4607f-115">Enable Skype Meeting Broadcast using the Skype for Business admin center</span></span>

<span data-ttu-id="4607f-116">![Skype for Business のロゴを表示したアイコン](../images/sfb-logo-30x30.png) **Skype for Business 管理センターの使用**</span><span class="sxs-lookup"><span data-stu-id="4607f-116">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="4607f-117">グローバル管理者アカウントまたは Skype for Business 管理者アカウントでサインインします [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) 。</span><span class="sxs-lookup"><span data-stu-id="4607f-117">Sign in with your global admin account or Skype for Business admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>
    
2. <span data-ttu-id="4607f-118">管理センターで、管理センターの Teams **に移動**  >  **します**。</span><span class="sxs-lookup"><span data-stu-id="4607f-118">In the admin center, go to **Admin centers** > **Teams**.</span></span>
    
3. <span data-ttu-id="4607f-119">Teams 管理 **センターで**、従来のポータルのオンライン会議ブロードキャスト会議に移動し、[Skype 会議ブロードキャストを有効にする  >    >  **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="4607f-119">In the **Teams admin center**, go to **Legacy portal** > **Online meetings** > **Broadcast meetings**, and then select **Enable Skype Meeting Broadcast**.</span></span>
    
## <a name="enable-skype-meeting-broadcast-using-powershell"></a><span data-ttu-id="4607f-120">PowerShell を使用して Skype 会議ブロードキャストを有効にする</span><span class="sxs-lookup"><span data-stu-id="4607f-120">Enable Skype Meeting Broadcast using PowerShell</span></span>

1. <span data-ttu-id="4607f-121">Teams [PowerShell モジュールをインストールします](https://docs.microsoft.com/microsoftteams/teams-powershell-install)。</span><span class="sxs-lookup"><span data-stu-id="4607f-121">Install the [Teams PowerShell module](https://docs.microsoft.com/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="4607f-122">コマンド プロンプトWindows PowerShellし、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="4607f-122">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

   ```powershell
   # When using Teams PowerShell Module
   
   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```
3. <span data-ttu-id="4607f-123">次のコマンドを実行して、現在の Skype 会議ブロードキャストの構成を確認します。</span><span class="sxs-lookup"><span data-stu-id="4607f-123">Confirm your current Skype Meeting Broadcast configuration by running:</span></span>
    
   ```PowerShell
   Get-CsBroadcastMeetingConfiguration
   ```

    <span data-ttu-id="4607f-124">_パラメーター EnableBroadcastMeeting_ が設定されています `False` 。</span><span class="sxs-lookup"><span data-stu-id="4607f-124">Verify that the parameter  _EnableBroadcastMeeting_ is set to `False`.</span></span>
    
     ![Skype 会議ブロードキャストの組織コマンドレットを有効にします。](../images/44abe30d-d3df-4ca9-9761-603a7ff78723.png)
  
9. <span data-ttu-id="4607f-126">次のコマンドを実行して、組織の Skype 会議ブロードキャストを有効にします。</span><span class="sxs-lookup"><span data-stu-id="4607f-126">Enable Skype Meeting Broadcast for your organization by running:</span></span>
    
   ```PowerShell
   Set-CsBroadcastMeetingConfiguration -EnableBroadcastMeeting $True
   ```

    <span data-ttu-id="4607f-127">設定が有効になっているか確認するには、もう一度実行  `Get-CsBroadcastMeetingConfiguration` します。</span><span class="sxs-lookup"><span data-stu-id="4607f-127">You can confirm that the setting is enabled by running  `Get-CsBroadcastMeetingConfiguration` again.</span></span>
    
     ![Skype 会議ブロードキャストの組織コマンドレットを有効にします。](../images/788515f0-32c9-415a-9235-6bfbe095e6f3.png)
  
    > [!TIP]
    > <span data-ttu-id="4607f-129">変更後、Skype 会議ブロードキャスト ポータルで有効になれるのに最大で 1 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="4607f-129">After you make the change, it may take up to an hour to take effect in the Skype Meeting Broadcast portal.</span></span> 
  
10. <span data-ttu-id="4607f-130">これで、ユーザーは、ビジネスの他のユーザーとブロードキャスト会議を開催できます。</span><span class="sxs-lookup"><span data-stu-id="4607f-130">Your users can now hold broadcast meetings with other users in your business.</span></span> <span data-ttu-id="4607f-131">会議を開始するには、Skype 会議ブロードキャストとは [何かを示します。](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)</span><span class="sxs-lookup"><span data-stu-id="4607f-131">To get them started, point them to [What is a Skype Meeting Broadcast?](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)</span></span>
    
## <a name="configure-your-network-to-broadcast-meetings-with-external-attendees"></a><span data-ttu-id="4607f-132">外部出席者との会議をブロードキャストするネットワークを構成する</span><span class="sxs-lookup"><span data-stu-id="4607f-132">Configure your network to broadcast meetings with external attendees</span></span>

<span data-ttu-id="4607f-133">ファイアウォールを使用している場合に、社外のユーザー (フェデレーション企業ではない) とのブロードキャストを保留にする場合は、次の手順を使用してネットワークを構成する必要があります [。Skype](set-up-your-network-for-skype-meeting-broadcast.md)会議ブロードキャスト用にネットワークをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="4607f-133">If you have a firewall, and you want to hold broadcasts with people outside of your business (who are not a federated business), you need to configure your network using these instructions: [Set up your network for Skype Meeting Broadcast](set-up-your-network-for-skype-meeting-broadcast.md).</span></span> 
  
<span data-ttu-id="4607f-134">ファイアウォールの構成にまだ時間がかからなかった場合は [、Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) パートナーにこの手順を採用することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="4607f-134">If you aren't experienced with configuring your firewall, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>
  
<span data-ttu-id="4607f-135">この手順をスキップし、代わりに別のビジネスをフェデレーションに追加するには、「ユーザーが外部の Skype for Business ユーザーに連絡することを許可する [」を参照してください](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)。</span><span class="sxs-lookup"><span data-stu-id="4607f-135">To skip this step and instead add another business to your federation, see [Allow users to contact external Skype for Business users](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="4607f-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="4607f-136">Related topics</span></span>

[<span data-ttu-id="4607f-137">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="4607f-137">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
  
[<span data-ttu-id="4607f-138">Skype for Business Online のセットアップ</span><span class="sxs-lookup"><span data-stu-id="4607f-138">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

  
 
