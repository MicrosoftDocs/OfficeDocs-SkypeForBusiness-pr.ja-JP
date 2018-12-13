---
title: 別の組織内のチームのユーザーとの通信します。
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 09/12/2018
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.audience: Admin
search.appverid: MET150
appliesto:
- Microsoft Teams
localization_priority: Normal
description: ユーザーが別の組織内のユーザーと通信できるようにするのにはチームを構成する方法を参照してください。
ms.openlocfilehash: 6fb71e4c9e1461ca920d480336288b06e3111eb2
ms.sourcegitcommit: 1ad4120af98240f1b54c0ca18286598b289a97f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/12/2018
ms.locfileid: "27240841"
---
# <a name="let-your-teams-users-chat-and-communicate-with-users-in-another-teams-organization"></a><span data-ttu-id="e68a8-103">チームのユーザーのチャットを使用し、チームの別の組織内のユーザーとの通信</span><span class="sxs-lookup"><span data-stu-id="e68a8-103">Let your Teams users chat and communicate with users in another Teams organization</span></span>

<span data-ttu-id="e68a8-104">記事の場合この手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="e68a8-104">Use the steps in this article when:</span></span>
  
- <span data-ttu-id="e68a8-105">お客様のビジネスの別のドメインにユーザーがあります。</span><span class="sxs-lookup"><span data-stu-id="e68a8-105">You have users in different domains in your business.</span></span> <span data-ttu-id="e68a8-106">たとえば、Rob@ContosoEast.com と Ann@ContosoWest.com です。</span><span class="sxs-lookup"><span data-stu-id="e68a8-106">For example, Rob@ContosoEast.com and Ann@ContosoWest.com.</span></span>
    
- <span data-ttu-id="e68a8-107">チームを使用して特定の企業、組織外の人に連絡するのには、組織内には、人をします。</span><span class="sxs-lookup"><span data-stu-id="e68a8-107">You want the people in your organization to use Teams to contact people in specific businesses outside of your organization.</span></span>
    
- <span data-ttu-id="e68a8-108">他のユーザーを検索し、連絡先、電子メール アドレスを使用することができるチームを使用している世界で。</span><span class="sxs-lookup"><span data-stu-id="e68a8-108">You want anyone else in the world who uses Teams to be able to find and contact you, using your email address.</span></span> <span data-ttu-id="e68a8-109">他のユーザーは、外部アクセスを有効にして、他方のドメインを許可する、これは動作します。</span><span class="sxs-lookup"><span data-stu-id="e68a8-109">If you and another user both enable External Access and allow each other's domains, this will work.</span></span> <span data-ttu-id="e68a8-110">動作しない場合は、他のユーザーを確認してください彼または彼女の構成は、ドメインをブロックされていません。</span><span class="sxs-lookup"><span data-stu-id="e68a8-110">If it doesn't work, the other user should make sure his or her configuration isn't blocking your domain.</span></span>

<span data-ttu-id="e68a8-111">これによって、ユーザーは検索、呼び出し、インスタント メッセージを送信するとあなたとの会議を設定します。</span><span class="sxs-lookup"><span data-stu-id="e68a8-111">This will allow users to find, call, and send you instant messages, as well as set up meetings with you.</span></span> <span data-ttu-id="e68a8-112">チームとのチャネルにアクセスする外部のユーザーを実行する場合に、ゲスト アクセスに優れた方法で可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e68a8-112">If you want external users to have access to teams and channels, guest access might be a better way to go.</span></span> <span data-ttu-id="e68a8-113">手順を確認してくださいこの記事で[ゲスト アクセスを有効に](set-up-guests.md)するのにはユーザーが通信できるようにします。</span><span class="sxs-lookup"><span data-stu-id="e68a8-113">Follow the steps in this article and make sure to [turn on guest access](set-up-guests.md) so that users can communicate.</span></span>

## <a name="let-your-teams-users-chat-and-communicate-with-users-in-another-teams-organization"></a><span data-ttu-id="e68a8-114">チームのユーザーのチャットを使用し、チームの別の組織内のユーザーとの通信</span><span class="sxs-lookup"><span data-stu-id="e68a8-114">Let your Teams users chat and communicate with users in another Teams organization</span></span>

<span data-ttu-id="e68a8-115">これらの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="e68a8-115">Follow these steps.</span></span>

### <a name="step-1---make-sure-to-set-up-the-ports-and-urls-that-are-needed"></a><span data-ttu-id="e68a8-116">手順 1 - ポートおよび必要な Url を設定することを確認します。</span><span class="sxs-lookup"><span data-stu-id="e68a8-116">Step 1 - Make sure to set up the ports and URLs that are needed.</span></span>

<span data-ttu-id="e68a8-117">**企業間の通信を設定する際に発生する最も一般的な問題は、取得[Office 365 の Url と IP アドレスの範囲](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges)右です。**</span><span class="sxs-lookup"><span data-stu-id="e68a8-117">**The most common issue people encounter when setting up business-to-business communication is getting their [Office 365 URLs and IP address ranges](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges) right.**</span></span>

### <a name="step-2---enable-your-organization-to-communicate-with-another-teams-organization"></a><span data-ttu-id="e68a8-118">手順 2 - 別のチームの組織と通信するために組織を有効にします。</span><span class="sxs-lookup"><span data-stu-id="e68a8-118">Step 2 - Enable your organization to communicate with another Teams organization</span></span>

<span data-ttu-id="e68a8-119">![チーム ・ ロゴ ・ 30x30.png](media/teams-logo-30x30.png) **、マイクロソフトのチームとビジネス管理センターの Skype を使用します。**</span><span class="sxs-lookup"><span data-stu-id="e68a8-119">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

   1. <span data-ttu-id="e68a8-120">左側のナビゲーションでは、**組織全体の設定**に移動 > **外部からアクセス**します。</span><span class="sxs-lookup"><span data-stu-id="e68a8-120">In the left navigation, go to **Org-wide settings** > **External access**.</span></span> 

   2. <span data-ttu-id="e68a8-121">**外部アクセス**] ページの上部には、**上**に**外部からのアクセス**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e68a8-121">At the top of the **External access** page, click **External access** to **On**.</span></span> 

   3. <span data-ttu-id="e68a8-122">チームのすべての組織、組織内のユーザーとの通信を許可する場合は、手順 5 に進んでください。</span><span class="sxs-lookup"><span data-stu-id="e68a8-122">If you want to allow all Teams organizations to communicate with users in your organization, skip to step 5.</span></span> 
   
   4. <span data-ttu-id="e68a8-123">制限するのどの組織が通信できるユーザーと組織の場合、すべてが、いくつかのドメインを許可するか、特定の組織のみを許可します。</span><span class="sxs-lookup"><span data-stu-id="e68a8-123">If you want to limit which organizations can communicate with users in your organization you can either allow all but some domains, or only allow specific organizations.</span></span> <span data-ttu-id="e68a8-124">すべてが、いくつかのドメインを許可するには、**ドメインの追加**] をクリックしてブロックするドメインを追加します。</span><span class="sxs-lookup"><span data-stu-id="e68a8-124">To allow all but some domains, add the domains you want to block by clicking **Add domain**.</span></span> <span data-ttu-id="e68a8-125">**ドメインの追加**ウィンドウで、ドメイン名に**ブロック**し、**実行**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e68a8-125">In the **Add a domain** pane, put in the domain name, click **Blocked** and then **Done**.</span></span> <span data-ttu-id="e68a8-126">特定の organizatioins への通信を制限するためには、 **Alowed**の状態でリストにそれらのドメインを追加します。</span><span class="sxs-lookup"><span data-stu-id="e68a8-126">To limit communications to specific organizatioins, add those domains to the list with a status of **Alowed**.</span></span> <span data-ttu-id="e68a8-127">許可リストに任意のドメインを追加すると他の組織への通信は許可リストには、そのドメインの組織だけに制限されます。</span><span class="sxs-lookup"><span data-stu-id="e68a8-127">Once you have added any domain to the Allow list, communications to other organizations will be limited to only those organizations whose domains are in the Allow list.</span></span> 
   
   5. <span data-ttu-id="e68a8-128">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e68a8-128">Click **Save**.</span></span> 

   6. <span data-ttu-id="e68a8-129">その他のチームの組織の管理者は、同じ手順を確認します。</span><span class="sxs-lookup"><span data-stu-id="e68a8-129">Then make sure the admin in the other Teams  organization does these same steps.</span></span> <span data-ttu-id="e68a8-130">などの**ドメインを許可する**ボックスの一覧で、管理者が組織は、そのユーザーと通信できますが制限される場合、お客様のビジネスのドメインを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e68a8-130">For example, in their **allowed domains** list, their admin needs to enter the domain for your business if they limit which organizations can communicate with their users.</span></span> 

### <a name="step-3---test-it"></a><span data-ttu-id="e68a8-131">手順 3 - テスト</span><span class="sxs-lookup"><span data-stu-id="e68a8-131">Step 3 - Test it</span></span>
<span data-ttu-id="e68a8-132">セットアップをテストするには、チームないユーザーが、ファイアウォールの背後にある必要があります。</span><span class="sxs-lookup"><span data-stu-id="e68a8-132">To test your setup, you need a Teams user who's not behind your firewall.</span></span>
  
   1. <span data-ttu-id="e68a8-133">組織の管理者が、**外部アクセス**の設定を変更された後に適切なはずです。</span><span class="sxs-lookup"><span data-stu-id="e68a8-133">After you and the admin from the organization have changed the **External access** settings, you should be good to go.</span></span>
    
   2. <span data-ttu-id="e68a8-134">チーム アプリケーションでは、電子メール アドレス、ユーザーの検索し、チャットするのには要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="e68a8-134">In the Teams app, search for the person by email address, and send a request to chat.</span></span>
    
   3. <span data-ttu-id="e68a8-135">チャットへの要求を送信するチーム メンバーに依頼します。</span><span class="sxs-lookup"><span data-stu-id="e68a8-135">Ask your Teams contact to send you a request to chat.</span></span> <span data-ttu-id="e68a8-136">要求の場合、問題は、ファイアウォールの設定 (ファイアウォール設定が正しいことが既にわかっていると仮定した場合) です。</span><span class="sxs-lookup"><span data-stu-id="e68a8-136">If you don't receive their request, the problem is your firewall settings (assuming they've already confirmed their firewall settings are correct).</span></span>
    
   4. <span data-ttu-id="e68a8-137">問題がお使いのファイアウォールであるかどうかをテストする別の方法ではないファイアウォールの内側に、コーヒー ショップなどの wifi の場所に移動し、チャットする相手に要求を送信するチームを使用します。</span><span class="sxs-lookup"><span data-stu-id="e68a8-137">Another way to test whether the problem is your firewall is to go to a wifi location not behind your firewall such as a coffee shop, and use Teams to send a request to your contact to chat.</span></span> <span data-ttu-id="e68a8-138">メッセージは、そこを通過し、問題がわかっていないしたら職場場合、は、お使いのファイアウォールです。</span><span class="sxs-lookup"><span data-stu-id="e68a8-138">If the message goes through there, but not when you're at work, then you know the problem is your firewall.</span></span>

## <a name="communicate-with-users-in-a-skype-for-business-online-organization"></a><span data-ttu-id="e68a8-139">Skype のオンライン ビジネスの組織内のユーザーとの通信します。</span><span class="sxs-lookup"><span data-stu-id="e68a8-139">Communicate with users in a Skype for Business Online organization</span></span>

<span data-ttu-id="e68a8-140">設定すると、チームのユーザーの検索と組織を制限することができます、ユーザーに連絡するため、Skype では、連絡先のユーザーをできるように場合、は、以下の手順には、その組織の管理を求められます。</span><span class="sxs-lookup"><span data-stu-id="e68a8-140">If you are setting it up to let your Teams users find and contact users that are in a Skype for Business organization that limits who can contact their users, you will ask the admin in that organization to follow these steps.</span></span>

<span data-ttu-id="e68a8-141">![デバイスのロゴ-30x30.png](media/sfb-logo-30x30.png) **ビジネス管理センターの Skype を使用します。**</span><span class="sxs-lookup"><span data-stu-id="e68a8-141">![sfb-logo-30x30.png](media/sfb-logo-30x30.png) **Using Skype for Business admin center**</span></span> 

<span data-ttu-id="e68a8-142">組織は、次の手順を行うことで、管理者があります。</span><span class="sxs-lookup"><span data-stu-id="e68a8-142">Have the admin in that organization do these steps:</span></span>
    
1. <span data-ttu-id="e68a8-143">**管理センター**には、Office 365 管理センターで、 > **のチームと Skype** > **従来のポータル**です。</span><span class="sxs-lookup"><span data-stu-id="e68a8-143">In the Office 365 admin center, go to **Admin Centers** > **Teams & Skype** > **Legacy portal**.</span></span>
  
2. <span data-ttu-id="e68a8-144">[**Skype for Business 管理センター**] で、[**組織**]  >  [**外部通信**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="e68a8-144">In the **Skype for Business admin center**, choose **Organization** > **External communications**.</span></span>
    
3. <span data-ttu-id="e68a8-145">設定するには、特定のビジネスで、または、ドロップ ダウン ボックスで、別のドメイン内のユーザーとの通信**にのみ許可されるドメイン**を選択します。</span><span class="sxs-lookup"><span data-stu-id="e68a8-145">To set up communication with a specific business or with users in another domain, in the drop-down box, choose **On only for allowed domains**.</span></span>
    
    <span data-ttu-id="e68a8-146">ビジネス ポリシーでは、Skype の選択を開くには世界中の他のすべてとの通信を有効にするかどうかは、**でブロックされているドメイン以外**。</span><span class="sxs-lookup"><span data-stu-id="e68a8-146">OR, if they want to enable communication with everyone else in the world who has open Skype for Business policies, choose **On except for blocked domains**.</span></span> <span data-ttu-id="e68a8-147">これは既定の設定です。</span><span class="sxs-lookup"><span data-stu-id="e68a8-147">This is the default setting.</span></span>
    
4. <span data-ttu-id="e68a8-148">[**ブロックまたは許可するドメイン**] を選択して**+** を許可するドメインの名前を追加します。</span><span class="sxs-lookup"><span data-stu-id="e68a8-148">Under **Blocked or allowed domains**, choose **+** and add the name of the domain you want to allow.</span></span> <span data-ttu-id="e68a8-149">他の組織内の管理者は、同じ手順を確認します。</span><span class="sxs-lookup"><span data-stu-id="e68a8-149">Make sure the admin in the other organization does these same steps.</span></span> <span data-ttu-id="e68a8-150">などの**ドメインを許可する**ボックスの一覧で、管理者が自社のドメインを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e68a8-150">For example, in their **allowed domains** list, their admin needs to enter the domain for your business.</span></span>
    
### <a name="related-topics"></a><span data-ttu-id="e68a8-151">関連トピック</span><span class="sxs-lookup"><span data-stu-id="e68a8-151">Related topics</span></span>

<span data-ttu-id="e68a8-152">[マイクロソフトのチームへのサインイン](sign-in-teams.md)
[エンド ・ ユーザーは、チームのトレーニング](enduser-training.md)</span><span class="sxs-lookup"><span data-stu-id="e68a8-152">[Sign in to Microsoft Teams](sign-in-teams.md)
[End user training for Teams](enduser-training.md)</span></span>

