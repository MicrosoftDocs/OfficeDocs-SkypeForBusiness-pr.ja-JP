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
description: 組織内のユーザーが会議ブロードキャストをSkypeするには、会議ブロードキャストを有効にする必要があります。 これを行うには、アプリケーションの使い方をWindows PowerShell。 この手順がわかWindows PowerShell、Microsoft パートナーを採用してこの手順を実行することを検討してください。
ms.openlocfilehash: 6cdd7f12483025697b139203907f87f9cd3dc764
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237013"
---
# <a name="enable-skype-meeting-broadcast"></a><span data-ttu-id="604e0-105">Skype 会議ブロードキャストを有効にする</span><span class="sxs-lookup"><span data-stu-id="604e0-105">Enable Skype Meeting Broadcast</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!IMPORTANT]
> <span data-ttu-id="604e0-106">Skype for Businessオンラインは 2021 年 7 月 31 日に廃止され、その時点でサービスへのアクセスが終了します。</span><span class="sxs-lookup"><span data-stu-id="604e0-106">Skype for Business Online is retiring on July 31, 2021, at which time access to the service will end.</span></span> <span data-ttu-id="604e0-107">お客様には、コミュニケーションとチームワークの中核となるMicrosoft Teamsクライアントであるクライアントへのアップグレードを開始Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="604e0-107">We encourage customers to begin the upgrade to Microsoft Teams, the core client for communications and teamwork in Microsoft 365.</span></span>

<span data-ttu-id="604e0-108">組織内のユーザーが会議ブロードキャストをSkypeするには、会議ブロードキャストを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="604e0-108">Before the people in your organization can use Skype Meeting Broadcast, you need to enable it.</span></span> <span data-ttu-id="604e0-109">これを行うには、アプリケーションの使い方をWindows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="604e0-109">To do this, you need to know how to use Windows PowerShell.</span></span> <span data-ttu-id="604e0-110">この手順を実行する方法[Windows PowerShell、Microsoft](https://go.microsoft.com/fwlink/?linkid=391089)パートナーを採用することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="604e0-110">If you don't know Windows PowerShell, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>



> [!NOTE]
> <span data-ttu-id="604e0-111">管理Microsoft Teamsセンターは、管理センター (レガシ ポータルSkype for Business置き換えました。</span><span class="sxs-lookup"><span data-stu-id="604e0-111">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="604e0-112">現在、管理センター Skype for Business管理センターにTeams設定が表示されます。</span><span class="sxs-lookup"><span data-stu-id="604e0-112">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="604e0-113">グローバル管理者の[Azure AD 管理者](/azure/active-directory/roles/permissions-reference)ロールが割り当てられている必要があります。または、Skype for Business 管理センターでSkype for Business機能を管理するには、Teams必要があります。</span><span class="sxs-lookup"><span data-stu-id="604e0-113">You must be assigned the [Azure AD admin role](/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Teams admin center.</span></span> <span data-ttu-id="604e0-114">詳細については、「[Microsoft Teams 管理センターで Skype for Business の設定を管理する](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="604e0-114">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json).</span></span>

  
## <a name="enable-skype-meeting-broadcast-using-the-skype-for-business-admin-center"></a><span data-ttu-id="604e0-115">管理Skypeを使用して会議ブロードキャストSkype for Business有効にする</span><span class="sxs-lookup"><span data-stu-id="604e0-115">Enable Skype Meeting Broadcast using the Skype for Business admin center</span></span>

<span data-ttu-id="604e0-116">![Skype for Business のロゴを表示したアイコン](../images/sfb-logo-30x30.png) **Skype for Business 管理センターの使用**</span><span class="sxs-lookup"><span data-stu-id="604e0-116">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="604e0-117">グローバル管理者アカウントでサインインするか、 で管理者Skype for Businessアカウントにサインインします [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) 。</span><span class="sxs-lookup"><span data-stu-id="604e0-117">Sign in with your global admin account or Skype for Business admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>
    
2. <span data-ttu-id="604e0-118">管理センターで、[管理センター] に **移動Teams。**  >  </span><span class="sxs-lookup"><span data-stu-id="604e0-118">In the admin center, go to **Admin centers** > **Teams**.</span></span>
    
3. <span data-ttu-id="604e0-119">[Teams **管理センターで**、[従来のポータル] [オンライン会議] [ブロードキャスト会議] に移動し、[会議ブロードキャストを有効にする] Skype  >    >  **選択します**。</span><span class="sxs-lookup"><span data-stu-id="604e0-119">In the **Teams admin center**, go to **Legacy portal** > **Online meetings** > **Broadcast meetings**, and then select **Enable Skype Meeting Broadcast**.</span></span>
    
## <a name="enable-skype-meeting-broadcast-using-powershell"></a><span data-ttu-id="604e0-120">PowerShell Skypeして会議ブロードキャストを有効にする</span><span class="sxs-lookup"><span data-stu-id="604e0-120">Enable Skype Meeting Broadcast using PowerShell</span></span>

1. <span data-ttu-id="604e0-121">[PowerShell モジュール Teamsインストールします](/microsoftteams/teams-powershell-install)。</span><span class="sxs-lookup"><span data-stu-id="604e0-121">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="604e0-122">コマンド プロンプトWindows PowerShellし、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="604e0-122">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

   ```powershell
   # When using Teams PowerShell Module
   
   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```
3. <span data-ttu-id="604e0-123">次のコマンドを実行Skype会議ブロードキャストの構成を確認します。</span><span class="sxs-lookup"><span data-stu-id="604e0-123">Confirm your current Skype Meeting Broadcast configuration by running:</span></span>
    
   ```PowerShell
   Get-CsBroadcastMeetingConfiguration
   ```

    <span data-ttu-id="604e0-124">_パラメーター EnableBroadcastMeeting が に設定_ されています `False` 。</span><span class="sxs-lookup"><span data-stu-id="604e0-124">Verify that the parameter  _EnableBroadcastMeeting_ is set to `False`.</span></span>
    
     ![Skype会議ブロードキャストを有効にする組織コマンドレット。](../images/44abe30d-d3df-4ca9-9761-603a7ff78723.png)
  
9. <span data-ttu-id="604e0-126">次Skypeして、組織の会議ブロードキャストを有効にします。</span><span class="sxs-lookup"><span data-stu-id="604e0-126">Enable Skype Meeting Broadcast for your organization by running:</span></span>
    
   ```PowerShell
   Set-CsBroadcastMeetingConfiguration -EnableBroadcastMeeting $True
   ```

    <span data-ttu-id="604e0-127">設定が有効になっているか確認するには、もう一度を実行  `Get-CsBroadcastMeetingConfiguration` します。</span><span class="sxs-lookup"><span data-stu-id="604e0-127">You can confirm that the setting is enabled by running  `Get-CsBroadcastMeetingConfiguration` again.</span></span>
    
     ![Skype会議ブロードキャストを有効にする組織コマンドレット。](../images/788515f0-32c9-415a-9235-6bfbe095e6f3.png)
  
    > [!TIP]
    > <span data-ttu-id="604e0-129">変更を行った後、会議ブロードキャスト ポータルで有効Skype 1 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="604e0-129">After you make the change, it may take up to an hour to take effect in the Skype Meeting Broadcast portal.</span></span> 
  
10. <span data-ttu-id="604e0-130">これで、ユーザーは、ビジネス内の他のユーザーとブロードキャスト会議を開催できます。</span><span class="sxs-lookup"><span data-stu-id="604e0-130">Your users can now hold broadcast meetings with other users in your business.</span></span> <span data-ttu-id="604e0-131">会議ブロードキャストを開始するには、[会議ブロードキャストとは[] Skypeします。](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)</span><span class="sxs-lookup"><span data-stu-id="604e0-131">To get them started, point them to [What is a Skype Meeting Broadcast?](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)</span></span>
    
## <a name="configure-your-network-to-broadcast-meetings-with-external-attendees"></a><span data-ttu-id="604e0-132">外部出席者との会議をブロードキャストするネットワークを構成する</span><span class="sxs-lookup"><span data-stu-id="604e0-132">Configure your network to broadcast meetings with external attendees</span></span>

<span data-ttu-id="604e0-133">ファイアウォールを使用している場合に、社外のユーザー (フェデレーションビジネスではないユーザー) とブロードキャストを開催する場合は[、「Skype](set-up-your-network-for-skype-meeting-broadcast.md)会議ブロードキャスト 用にネットワークを設定する」の手順に従ってネットワークを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="604e0-133">If you have a firewall, and you want to hold broadcasts with people outside of your business (who are not a federated business), you need to configure your network using these instructions: [Set up your network for Skype Meeting Broadcast](set-up-your-network-for-skype-meeting-broadcast.md).</span></span> 
  
<span data-ttu-id="604e0-134">ファイアウォールを構成する経験が十分でない場合は [、Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) パートナーを採用してこの手順を実行することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="604e0-134">If you aren't experienced with configuring your firewall, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>
  
<span data-ttu-id="604e0-135">この手順をスキップし、代わりに別のビジネスをフェデレーションに追加するには、「ユーザーが外部ユーザーに連絡することを許可する」を[Skype for Businessしてください](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)。</span><span class="sxs-lookup"><span data-stu-id="604e0-135">To skip this step and instead add another business to your federation, see [Allow users to contact external Skype for Business users](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="604e0-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="604e0-136">Related topics</span></span>

[<span data-ttu-id="604e0-137">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="604e0-137">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  
[<span data-ttu-id="604e0-138">Skype for Business Online のセットアップ</span><span class="sxs-lookup"><span data-stu-id="604e0-138">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

  
