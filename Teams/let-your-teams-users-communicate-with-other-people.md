---
title: 他の組織の Teams ユーザーとの通信
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 09/12/2018
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.audience: Admin
search.appverid: MET150
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: ms.teamsadmincenter.externalaccess.overview
description: ユーザーが別の組織のユーザーと通信できるように Teams を構成する方法を説明します。
ms.openlocfilehash: c3faf65dd3f36c193a75e74e73d90bf5e9be11df
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32222372"
---
# <a name="let-your-teams-users-chat-and-communicate-with-users-in-another-teams-organization"></a><span data-ttu-id="bda20-103">Teams のユーザーが別の Teams 組織のユーザーとチャットおよび通信できるようにする</span><span class="sxs-lookup"><span data-stu-id="bda20-103">To turn on external access, see  Let your Teams users chat and communicate with users in another Teams organization.</span></span>

<span data-ttu-id="bda20-104">次の場合、この記事で説明する手順をご利用ください。</span><span class="sxs-lookup"><span data-stu-id="bda20-104">Use the steps in this article when:</span></span>
  
- <span data-ttu-id="bda20-105">社内の複数のドメインにユーザーがいる場合。</span><span class="sxs-lookup"><span data-stu-id="bda20-105">You have users in different domains in your business.</span></span> <span data-ttu-id="bda20-106">たとえば、Rob@ContosoEast.com と Ann@ContosoWest.com のような場合。</span><span class="sxs-lookup"><span data-stu-id="bda20-106">For example, Rob@ContosoEast.com and Ann@ContosoWest.com.</span></span>
    
- <span data-ttu-id="bda20-107">組織内のユーザーが特定の組織外の会社のユーザーと連絡する際に、Teams を使用させたい場合。</span><span class="sxs-lookup"><span data-stu-id="bda20-107">You want the people in your organization to use Teams to contact people in specific businesses outside of your organization.</span></span>
    
- <span data-ttu-id="bda20-108">ユーザーのメール アドレスを使用して、世界中の Teams のユーザーは誰でもそのユーザーを検索して連絡を取れるようにする場合。</span><span class="sxs-lookup"><span data-stu-id="bda20-108">You want anyone else in the world who uses Teams to be able to find and contact you, using your email address.</span></span> <span data-ttu-id="bda20-109">これは、ユーザーともう 1 人のユーザーの両方が外部アクセスを有効にしてお互いのドメインを許可している場合に可能になります。</span><span class="sxs-lookup"><span data-stu-id="bda20-109">If you and another user both enable External Access and allow each other's domains, this will work.</span></span> <span data-ttu-id="bda20-110">正常に動作しない場合は、もう 1 人のユーザーの構成でユーザーのドメインがブロックされていないかを確認してもらいます。</span><span class="sxs-lookup"><span data-stu-id="bda20-110">If it doesn't work, the other user should make sure his or her configuration isn't blocking your domain.</span></span>

<span data-ttu-id="bda20-111">こうすることで、他のユーザーがユーザーを検索し、ユーザーと通話し、インスタント メッセージを送信し、ユーザーとの会議を設定できるようになります。</span><span class="sxs-lookup"><span data-stu-id="bda20-111">This will allow users to find, call, and send you instant messages, as well as set up meetings with you.</span></span> <span data-ttu-id="bda20-112">外部のユーザーがチームとチャネルにアクセスできるようにする場合に適した方法は、ゲスト アクセスです。</span><span class="sxs-lookup"><span data-stu-id="bda20-112">If you want external users to have access to teams and channels, guest access might be a better way to go.</span></span> <span data-ttu-id="bda20-113">この記事の手順に従って[ゲスト アクセスを有効にする](set-up-guests.md)と、ユーザーが通信できるようになります。</span><span class="sxs-lookup"><span data-stu-id="bda20-113">Follow the steps in this article and make sure to [turn on guest access](set-up-guests.md) so that users can communicate.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bda20-114">現在、組織外部の現在 AAD/テナントのゲストではない外部ユーザーに Microsoft Teams クライアント内でフェデレーションするには、ハイブリッド環境が正しく設定され、Skype for Business Online へ移行してある必要があります。</span><span class="sxs-lookup"><span data-stu-id="bda20-114">In order to currently federate within the Microsoft Teams client to an external user outside of your organization who's not currently a Guest of your AAD/Tenant, you must be correctly setup for hybrid and moved to Skype for Business Online.</span></span> <span data-ttu-id="bda20-115">2019 年 2 月 25 日現在、SIP プロフィールのユーザーが Skype for Business Online に属している場合を除き、Teams ではネイティブのフェデレーションはまだサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="bda20-115">As of 2/25/2019, Teams doesn't yet support native federation without the user of the SIP profile being homed in Skype for Business Online.</span></span> <span data-ttu-id="bda20-116">ハイブリッド環境でアカウントを設定した後に Teams に移行する場合の詳細については、「[Skype for Business のハイブリッド展開を Teams にアップグレードする](https://docs.microsoft.com/ja-JP/microsoftteams/upgrade-to-teams-execute-skypeforbusinesshybrid)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bda20-116">For more on setting up your account for Hybrid and then moved to Teams, please see [Upgrade Skype for Business Hybrid Deployment to Teams](https://docs.microsoft.com/ja-JP/microsoftteams/upgrade-to-teams-execute-skypeforbusinesshybrid).</span></span>

## <a name="let-your-teams-users-chat-and-communicate-with-users-in-another-teams-organization"></a><span data-ttu-id="bda20-117">Teams のユーザーが別の Teams 組織のユーザーとチャットおよび通信できるようにする</span><span class="sxs-lookup"><span data-stu-id="bda20-117">To turn on external access, see  Let your Teams users chat and communicate with users in another Teams organization.</span></span>

<span data-ttu-id="bda20-118">以下の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="bda20-118">Follow these steps to change the collation:</span></span>

### <a name="step-1---make-sure-to-set-up-the-ports-and-urls-that-are-needed"></a><span data-ttu-id="bda20-119">手順 1 - 必要なポートと URL を正しく設定します。</span><span class="sxs-lookup"><span data-stu-id="bda20-119">Step 1 - Make sure to set up the ports and URLs that are needed.</span></span>

<span data-ttu-id="bda20-120">**企業間の通信を設定する場合に最もよく発生する問題は、[Office 365 の URL と IP アドレスの範囲](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges)の設定ミスによるものです。**</span><span class="sxs-lookup"><span data-stu-id="bda20-120">**The most common issue people encounter when setting up business-to-business communication is getting their [Office 365 URLs and IP address ranges](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges) right.**</span></span>

### <a name="step-2---enable-your-organization-to-communicate-with-another-teams-organization"></a><span data-ttu-id="bda20-121">手順 2 - 組織が別の Teams の組織と通信できるようにする設定</span><span class="sxs-lookup"><span data-stu-id="bda20-121">Step 2 - Enable your organization to communicate with another Teams organization</span></span>

<span data-ttu-id="bda20-122">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Microsoft Teams 管理センターを使用する**</span><span class="sxs-lookup"><span data-stu-id="bda20-122">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

   1. <span data-ttu-id="bda20-123">左側のナビゲーションで、[**組織全体の設定**]  >  [**外部アクセス**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="bda20-123">In the left navigation, go to **Org-wide settings** > **External access**.</span></span> 

   2. <span data-ttu-id="bda20-124">[**外部アクセス**] ページの上部で、[**外部アクセス**] をクリックして [**オン**] にします。</span><span class="sxs-lookup"><span data-stu-id="bda20-124">At the top of the **External access** page, click **External access** to **On**.</span></span> 

   3. <span data-ttu-id="bda20-125">すべての Teams の組織に対して、組織内のユーザーとの通信を許可する場合は、手順 5 に進みます。</span><span class="sxs-lookup"><span data-stu-id="bda20-125">If you want to allow all Teams organizations to communicate with users in your organization, skip to step 5.</span></span> 
   
   4. <span data-ttu-id="bda20-126">組織内のユーザーと通信できる組織を制限する場合は、特定のドメイン以外のすべての組織を許可する方法と、特定の組織のみを許可する方法とがあります。</span><span class="sxs-lookup"><span data-stu-id="bda20-126">If you want to limit which organizations can communicate with users in your organization you can either allow all but some domains, or only allow specific organizations.</span></span> <span data-ttu-id="bda20-127">特定のドメイン以外のすべての組織を許可するには、[**ドメインの追加**] をクリックしてブロックするドメインを追加します。</span><span class="sxs-lookup"><span data-stu-id="bda20-127">To allow all but some domains, add the domains you want to block by clicking **Add domain**.</span></span> <span data-ttu-id="bda20-128">[**ドメインの追加**] ウィンドウで、ドメイン名を入力して [**ブロック**] をクリックし、[**完了**] をクリックします。 </span><span class="sxs-lookup"><span data-stu-id="bda20-128">In the **Add a domain** pane, put in the domain name, click **Blocked** and then **Done**.</span></span> <span data-ttu-id="bda20-129">通信を特定の組織に制限するには、それらの組織のドメインを [**許可**] の状態でリストに追加します。</span><span class="sxs-lookup"><span data-stu-id="bda20-129">To limit communications to specific organizatioins, add those domains to the list with a status of **Alowed**.</span></span> <span data-ttu-id="bda20-130">[許可] リストにいずれかのドメインを追加すると、他の組織との通信は、[許可] リストにドメインが表示される組織との通信のみに制限されます。</span><span class="sxs-lookup"><span data-stu-id="bda20-130">Once you have added any domain to the Allow list, communications to other organizations will be limited to only those organizations whose domains are in the Allow list.</span></span> 
   
   5. <span data-ttu-id="bda20-131">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bda20-131">Click **Save**.</span></span> 

   6. <span data-ttu-id="bda20-132">他の Teams の組織の管理者も同じ手順を実行したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="bda20-132">Then make sure the admin in the other Teams  organization does these same steps.</span></span> <span data-ttu-id="bda20-133">たとえば、ある他の組織でその組織のユーザーと通信できる組織を制限している場合は、その組織の管理者は、**許可されたドメイン**のリストにお客様の会社のドメインを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bda20-133">For example, in their **allowed domains** list, their admin needs to enter the domain for your business if they limit which organizations can communicate with their users.</span></span> 

### <a name="step-3---test-it"></a><span data-ttu-id="bda20-134">手順 3 - テスト</span><span class="sxs-lookup"><span data-stu-id="bda20-134">Step 3 - Test it</span></span>
<span data-ttu-id="bda20-135">設定をテストするには、組織のファイアウォールの外側にいる Teams ユーザーが必要です。</span><span class="sxs-lookup"><span data-stu-id="bda20-135">To test your setup, you need a Teams user who's not behind your firewall.</span></span>
  
   1. <span data-ttu-id="bda20-136">お客様ともう 1 つの組織の管理者が [**外部アクセス**] 設定の変更をそれぞれ完了すると、テストを開始できます。</span><span class="sxs-lookup"><span data-stu-id="bda20-136">After you and the admin from the organization have changed the **External access** settings, you should be good to go.</span></span>
    
   2. <span data-ttu-id="bda20-137">Teams アプリで、メール アドレスを使用してユーザーを検索し、チャットの要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="bda20-137">In the Teams app, search for the person by email address, and send a request to chat.</span></span>
    
   3. <span data-ttu-id="bda20-138">お客様宛にチャットの要求を送信するよう、Teams の連絡先に依頼します。</span><span class="sxs-lookup"><span data-stu-id="bda20-138">Ask your Teams contact to send you a request to chat.</span></span> <span data-ttu-id="bda20-139">相手からの要求を受信できない場合は、お客様のファイアウォールの設定に問題があります (相手のファイアウォールの設定が正しいことが確認済みであることが前提)。</span><span class="sxs-lookup"><span data-stu-id="bda20-139">If you don't receive their request, the problem is your firewall settings (assuming they've already confirmed their firewall settings are correct).</span></span>
    
   4. <span data-ttu-id="bda20-140">問題の原因がお客様のファイアウォールかどうかを別の方法でテストするには、ファイアウォールの外側の WiFi エリア (喫茶店など) へ行き、Teams を使用して連絡先にチャットの要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="bda20-140">Another way to test whether the problem is your firewall is to go to a wifi location not behind your firewall such as a coffee shop, and use Teams to send a request to your contact to chat.</span></span> <span data-ttu-id="bda20-141">メッセージをその場所からは送信できる一方、職場からは送信できない場合は、問題の原因は職場のファイアウォールであることが特定できます。</span><span class="sxs-lookup"><span data-stu-id="bda20-141">If the message goes through there, but not when you're at work, then you know the problem is your firewall.</span></span>

## <a name="communicate-with-users-in-a-skype-for-business-online-organization"></a><span data-ttu-id="bda20-142">Skype for Business Online の組織のユーザーとの通信</span><span class="sxs-lookup"><span data-stu-id="bda20-142">Communicate with users in a Skype for Business Online organization</span></span>

<span data-ttu-id="bda20-143">お客様の組織の Teams ユーザーが、組織のユーザーに連絡できる相手を制限している Skype for Business Online の組織のユーザーを検索して連絡できる設定になっている場合は、その組織の管理者に次の手順の実行を依頼します。</span><span class="sxs-lookup"><span data-stu-id="bda20-143">If you are setting it up to let your Teams users find and contact users that are in a Skype for Business organization that limits who can contact their users, you will ask the admin in that organization to follow these steps.</span></span>

<span data-ttu-id="bda20-144">![sfb-logo-30x30.png](media/sfb-logo-30x30.png) **Skype for Business 管理センターを使用する**</span><span class="sxs-lookup"><span data-stu-id="bda20-144">![sfb-logo-30x30.png](media/sfb-logo-30x30.png) **Using Skype for Business admin center**</span></span> 

<span data-ttu-id="bda20-145">その組織の管理者に、次の手順を実行するよう依頼します。</span><span class="sxs-lookup"><span data-stu-id="bda20-145">Have the admin in that organization do these steps:</span></span>
    
1. <span data-ttu-id="bda20-146">Office 365 管理センターで、[**管理センター**]  >  [**Teams & Skype**]  >  [**従来のポータル**] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="bda20-146">In the Office 365 admin center, go to **Admin Centers** > **Teams & Skype** > **Legacy portal**.</span></span>
  
2. <span data-ttu-id="bda20-147">**Skype for Business 管理センター**で、[**組織**]  >  [**外部通信**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="bda20-147">In the **Skype for Business admin center**, choose **Audio conferencing** > **Microsoft bridge**.</span></span>
    
3. <span data-ttu-id="bda20-148">特定の会社や別のドメインのユーザーとの通信を設定するには、ドロップダウン ボックスで [**許可したドメインに対してのみオンにする**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="bda20-148">To set up communication with a specific business or with users in another domain, in the drop-down box, choose **On only for allowed domains**.</span></span>
    
    <span data-ttu-id="bda20-149">または、Skype for Business のオープン ポリシーを使用する世界中の誰とでもユーザーが通信できるようにするには、[**禁止したドメインを除いてオンにする**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="bda20-149">OR, if they want to enable communication with everyone else in the world who has open Skype for Business policies, choose **On except for blocked domains**.</span></span> <span data-ttu-id="bda20-150">これは、既定の設定です。</span><span class="sxs-lookup"><span data-stu-id="bda20-150">This is the default setting.</span></span>
    
4. <span data-ttu-id="bda20-151">[**禁止したドメインまたは許可したドメイン**] の下で [**+**] を選択し、許可するドメイン名を追加します。</span><span class="sxs-lookup"><span data-stu-id="bda20-151">Under **Blocked or allowed domains**, choose **+** and add the name of the domain you want to allow.</span></span> <span data-ttu-id="bda20-152">相手の組織の管理者も同じ手順を実行たことを確認します。</span><span class="sxs-lookup"><span data-stu-id="bda20-152">Make sure the admin in the other organization does these same steps.</span></span> <span data-ttu-id="bda20-153">たとえば、相手の組織の管理者は、その組織の**許可されたドメイン** のリストにお客様の会社のドメインを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bda20-153">For example, in their **allowed domains** list, their admin needs to enter the domain for your business.</span></span>
    
### <a name="related-topics"></a><span data-ttu-id="bda20-154">関連トピック</span><span class="sxs-lookup"><span data-stu-id="bda20-154">Related topics</span></span>

<span data-ttu-id="bda20-155">[Microsoft Teams へのサインイン](sign-in-teams.md)
[Microsoft Teams のエンド ユーザー トレーニング](enduser-training.md)</span><span class="sxs-lookup"><span data-stu-id="bda20-155">[Sign in to Microsoft Teams](sign-in-teams.md)
[End user training for Teams](enduser-training.md)</span></span>

