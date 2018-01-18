---
title: "ビジネス オンラインの Skype を設定します。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 40296968-e779-4259-980b-c2de1c044c6e
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business
localization_priority: Normal
ROBOTS: None
f1keywords:
- O365E_SkypeforBusinessON
- O365M_SkypeforBusinessON
- O365P_SkypeforBusinessON
ms.custom:
- Setup
- Alchemy
- LIL_Placement
description: "ビジネス用の Skype をインストールするのには、ドメイン、ユーザー、IM およびプレゼンスを組織の設定について説明します。 オーディオ会議、電話システムおよび計画を呼び出すには、Skype の会議のブロードキャストを設定する方法を参照してください。 "
ms.openlocfilehash: c7898122675525810c13096989b4c3863bb8223c
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/15/2017
---
# <a name="set-up-skype-for-business-online"></a><span data-ttu-id="dd3ce-104">ビジネス オンラインの Skype を設定します。</span><span class="sxs-lookup"><span data-stu-id="dd3ce-104">Set up Skype for Business Online</span></span>
  
<span data-ttu-id="dd3ce-105">ビジネス用の Skype を設定するのには Office 365 のグローバル管理者の権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="dd3ce-105">You must have Office 365 global admin permissions to set up Skype for Business.</span></span> <span data-ttu-id="dd3ce-106">Web パーツへのアクセスを制限するファイアウォールまたはプロキシ サーバーがある場合は、ビジネス用の Skype を設定するには、[マイクロソフト パートナー](https://go.microsoft.com/fwlink/?linkid=391089)の採用を検討してください。</span><span class="sxs-lookup"><span data-stu-id="dd3ce-106">If you have a firewall or proxy server that restricts access to parts of the web, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to set up Skype for Business for you.</span></span>
  
## <a name="setting-up-skype"></a><span data-ttu-id="dd3ce-107">Skype を設定します。</span><span class="sxs-lookup"><span data-stu-id="dd3ce-107">Setting up Skype</span></span>

<span data-ttu-id="dd3ce-108">Office 365 サブスクリプションの場合、Skype の設定を支援する必要があるようですね。</span><span class="sxs-lookup"><span data-stu-id="dd3ce-108">Looks like you need help setting up Skype with your Office 365 subscription.</span></span> <span data-ttu-id="dd3ce-109">セットアップを完了させるには、この資料の手順に従うことができます。</span><span class="sxs-lookup"><span data-stu-id="dd3ce-109">You can follow the steps in this article to get your setup completed.</span></span>
  
## <a name="1-plan-for-skype-for-business"></a><span data-ttu-id="dd3ce-110">1. Skype のビジネスを計画します。</span><span class="sxs-lookup"><span data-stu-id="dd3ce-110">1. Plan for Skype for Business</span></span>

<span data-ttu-id="dd3ce-111">**[Office 365 のビジネス プレミアム](https://products.office.com/en-us/business/office-365-business-premium)**または**ビジネスの基礎**があれば、お客様のビジネス ユーザーは、サブスクリプションの他のユーザーにオンラインの呼び出しを行うビジネスの Skype を使用できます。</span><span class="sxs-lookup"><span data-stu-id="dd3ce-111">If you have **[Office 365 Business Premium](https://products.office.com/en-us/business/office-365-business-premium)** or **Business Essentials**, you can use Skype for Business to make online calls to other people in your business who are on your subscription.</span></span> <span data-ttu-id="dd3ce-112">たとえば、10 人では、ことができます[IM やオンライン会議のためにビジネス用の Skype を使用](http://support.office.com/article/cc05afa6-1894-4a82-9dd9-6222061f50fd)する、および 2-6 以下の手順を実行した後、ビジネスの Skype を使用して[ビジネスの Skype での会議](https://support.office.com/article/2eed8424-581a-4497-b505-c08c152e5851)。</span><span class="sxs-lookup"><span data-stu-id="dd3ce-112">For example, if your business has 10 people, you'll be able to [Start using Skype for Business for IM and online meetings](http://support.office.com/article/cc05afa6-1894-4a82-9dd9-6222061f50fd) each other, and [Meetings with Skype for Business](https://support.office.com/article/2eed8424-581a-4497-b505-c08c152e5851) using Skype for Business after performing the steps 2-6 below.</span></span> <span data-ttu-id="dd3ce-113">[Skype の Outlook で会議を設定](https://support.office.com/article/b8305620-d16e-4667-989d-4a977aad6556#bkmk_OWA)すると、オンライン会議は、すぎます!</span><span class="sxs-lookup"><span data-stu-id="dd3ce-113">And you can [Set up a Skype for Business meeting in Outlook](https://support.office.com/article/b8305620-d16e-4667-989d-4a977aad6556#bkmk_OWA) to online meetings, too!</span></span>
  
<span data-ttu-id="dd3ce-114">ビジネス用の Skype を使用し、ビジネス ユーザーから*外部*の**呼び出し**を受信する場合はします。</span><span class="sxs-lookup"><span data-stu-id="dd3ce-114">If you want to use Skype for Business to make and receive **calls** from people *external*  to your business:</span></span>
  
- <span data-ttu-id="dd3ce-115">**オプション 1。無料の[Skype アプリ](https://www.skype.com/)を使用して**。</span><span class="sxs-lookup"><span data-stu-id="dd3ce-115">**Option 1. Use the free [Skype app](https://www.skype.com/)**.</span></span> <span data-ttu-id="dd3ce-116">非常に小規模なビジネスでは、(1-2 のユーザーなど) がある場合は、Skype のアプリケーションを使用してが移動する場合に適してします。</span><span class="sxs-lookup"><span data-stu-id="dd3ce-116">If you have a very small business (for example, 1-2 people), using the Skype app is the better way to go.</span></span> <span data-ttu-id="dd3ce-117">それは、国内および国際通話に使用する方が安価です。</span><span class="sxs-lookup"><span data-stu-id="dd3ce-117">It's less expensive to use for domestic and international calls.</span></span> <span data-ttu-id="dd3ce-118">まだ会議通話を押しながら、ビデオ通話は、してプレゼンテーション用にデスクトップを共有できます。</span><span class="sxs-lookup"><span data-stu-id="dd3ce-118">You can still hold conference calls, make video calls, and share your desktop for presentations.</span></span> <span data-ttu-id="dd3ce-119">[レートと支払オプションをチェック アウト](https://secure.skype.com/en/calling-rates?wt.mc_id=legacy&amp;expo365=bundled)します。</span><span class="sxs-lookup"><span data-stu-id="dd3ce-119">[Check out the rates and payment options](https://secure.skype.com/en/calling-rates?wt.mc_id=legacy&amp;expo365=bundled).</span></span>
    
- <span data-ttu-id="dd3ce-120">**オプション 2 です。計画をアップグレードし、Office 365 の電話システムとの呼び出しのプランを購入する**です。</span><span class="sxs-lookup"><span data-stu-id="dd3ce-120">**Option 2. Upgrade your plan, and buy the Phone System and a Calling Plan for Office 365**.</span></span> <span data-ttu-id="dd3ce-121">どれだけこのコストは、スイッチを確認、[ビジネス製品の管理のヘルプのサポートに問い合わせてください](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)するにはし、すべての処理をすることがあるを確認する最も簡単な方法です。</span><span class="sxs-lookup"><span data-stu-id="dd3ce-121">The easiest way to find out how much this costs, and then make the switch, is to [Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) and have them do everything for you.</span></span>
    
<span data-ttu-id="dd3ce-122">詳細については、[ビジネス向けの Office 365 のセットアップの計画](https://support.office.com/article/eb926624-018b-4486-bf11-5fba6ee4d645#bkmk_skype)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd3ce-122">To learn more, see [Plan your setup of Office 365 for business](https://support.office.com/article/eb926624-018b-4486-bf11-5fba6ee4d645#bkmk_skype).</span></span>
  
## <a name="2-sign-in-to-office-365"></a><span data-ttu-id="dd3ce-123">2. 記号で Office 365 に</span><span class="sxs-lookup"><span data-stu-id="dd3ce-123">2. Sign in to Office 365</span></span>
<span data-ttu-id="dd3ce-124"><a name="bkmk_signin"> </a></span><span class="sxs-lookup"><span data-stu-id="dd3ce-124"></span></span>

<span data-ttu-id="dd3ce-125">ビジネス オンラインの Skype は、Office 365 のサービス群の一部です。</span><span class="sxs-lookup"><span data-stu-id="dd3ce-125">Skype for Business Online is part of the Office 365 suite of services.</span></span> <span data-ttu-id="dd3ce-126">オンライン ビジネスでは、Skype を設定するには Office 365 にサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd3ce-126">To set up Skype for Business Online, you need to sign in to Office 365.</span></span> <span data-ttu-id="dd3ce-127">その方法を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="dd3ce-127">Here's how you do that:</span></span>
  
1. <span data-ttu-id="dd3ce-128">Office 365 ユーザー ID ( *rob@fourthcoffee.com*など) を検索します。</span><span class="sxs-lookup"><span data-stu-id="dd3ce-128">Locate your Office 365 user ID (for example,  *rob@fourthcoffee.com*  ).</span></span> <span data-ttu-id="dd3ce-129">ビジネス オンラインの Skype を購入したときに作成した Office 365 のユーザー ID を含む Microsoft Online Services チームから電子メールを受信しました。</span><span class="sxs-lookup"><span data-stu-id="dd3ce-129">You received an email from the Microsoft Online Services Team that contains the Office 365 user ID that you created when you purchased Skype for Business Online.</span></span> <span data-ttu-id="dd3ce-130">メールは、これのようになります。</span><span class="sxs-lookup"><span data-stu-id="dd3ce-130">The mail looks something like this:</span></span>
    
    ![ビジネス オンラインの Skype にサインアップした後を受信した登録完了メールの例です。](../images/977c5c96-29c5-40c0-a4c4-1ba66ba3a1fb.png)
  
2. <span data-ttu-id="dd3ce-133">Office 365 の管理センターにサインインして、Office 365 のユーザー ID とパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="dd3ce-133">Sign in to the Office 365 admin center and enter your Office 365 user ID and password.</span></span> <span data-ttu-id="dd3ce-134">サインイン後、Office 365 の管理ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="dd3ce-134">After you sign in, you'll see the Office 365 admin center:</span></span>
    
    ![Office 365 の管理の中心の例は次のように、オンライン ビジネス ・ プランは、Skype があるとします。](../images/ed1d9906-e717-450b-81a3-ce6679bd1be1.png)
  
## <a name="3-set-up-your-domain-and-users"></a><span data-ttu-id="dd3ce-136">3. ドメインおよびユーザーを設定します。</span><span class="sxs-lookup"><span data-stu-id="dd3ce-136">3. Set up your domain and users</span></span>
<span data-ttu-id="dd3ce-137"><a name="bkmk_users"> </a></span><span class="sxs-lookup"><span data-stu-id="dd3ce-137"></span></span>

<span data-ttu-id="dd3ce-138">Office 365 にサインインしていることビジネス オンラインの Skype を使用する、組織のドメインとユーザーを設定できます。</span><span class="sxs-lookup"><span data-stu-id="dd3ce-138">Now that you're signed in to Office 365, you can set up your domain and people in your organization to use Skype for Business Online.</span></span>
  
1. <span data-ttu-id="dd3ce-139">[ドメインの追加とユーザーが Office 365](https://support.office.com/article/6383f56d-3d09-4dcb-9b41-b5f5a5efd611): Office 365 のセットアップ ウィザードを使用して、Office 365 でカスタム ドメイン ( *fourthcoffee.com*) などを設定します。</span><span class="sxs-lookup"><span data-stu-id="dd3ce-139">[Add a domain and users to Office 365](https://support.office.com/article/6383f56d-3d09-4dcb-9b41-b5f5a5efd611): Use the Office 365 setup wizard to set up your custom domain (such as *fourthcoffee.com*) with Office 365.</span></span> <span data-ttu-id="dd3ce-140">**既定では、Office 365 のセットアップ ウィザードには、ビジネス オンラインの Skype を設定し、Skype をビジネス ユーザー Id の作成が含まれています。**</span><span class="sxs-lookup"><span data-stu-id="dd3ce-140">**By default, the Office 365 setup wizard includes setting up Skype for Business Online and creating your Skype for Business user IDs.**</span></span> <span data-ttu-id="dd3ce-141">既に Office 365 のドメインを設定するウィザードを使用した場合は、この手順を完了しました。</span><span class="sxs-lookup"><span data-stu-id="dd3ce-141">If you already used the wizard to set up your domain for Office 365, then you've completed this step.</span></span>
    
2. <span data-ttu-id="dd3ce-142">[ドメインと DNS の接続を確認する](https://support.office.com/article/2b54e1b0-47a7-4018-a1e4-c2b924e7c5a0): ドメインと DNS の設定が正しいことを確認するのには、ツール ・ ドメインのトラブルシューティング ツールでを使用します。</span><span class="sxs-lookup"><span data-stu-id="dd3ce-142">[Check your domain and DNS connections](https://support.office.com/article/2b54e1b0-47a7-4018-a1e4-c2b924e7c5a0): Use our tool - the domains troubleshooter - to check that your domain and DNS settings are correct.</span></span> <span data-ttu-id="dd3ce-143">ようになりましたこれで、将来の問題の原因として、DNS の設定を排除することができますので後で、セットアップの問題を把握するためにずっとを移動します。</span><span class="sxs-lookup"><span data-stu-id="dd3ce-143">Doing this now will go a long way to helping figure out any setup issues later since you'll be able to eliminate DNS settings as the source of future issues.</span></span>
    
3. <span data-ttu-id="dd3ce-144">[Office 365 の Url と IP アドレスの範囲](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2#BKMK_LYO): ほとんどの小規模企業はこの手順を行う必要はありません。</span><span class="sxs-lookup"><span data-stu-id="dd3ce-144">[Office 365 URLs and IP address ranges](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2#BKMK_LYO): Most small businesses don't need to do this step.</span></span> <span data-ttu-id="dd3ce-145">**Web パーツへのアクセスを制限しているファイアウォールまたはプロキシ サーバーがある場合は**、オンライン ビジネスのエンドポイントに対して、Skype へのアクセスを許可する規則を作成してください。</span><span class="sxs-lookup"><span data-stu-id="dd3ce-145">**But if you have a firewall or proxy server that restricts access to parts of the web**, you must create rules to allow access to the Skype for Business Online endpoints.</span></span> <span data-ttu-id="dd3ce-146">これは、数々 のファイアウォールやプロキシ サーバーを構成する他のユーザーによって実行される最適な高度な手順です。</span><span class="sxs-lookup"><span data-stu-id="dd3ce-146">This is an advanced step best performed by someone experienced with configuring firewalls and proxy servers.</span></span> <span data-ttu-id="dd3ce-147">いない場合はこれまで、ビジネス用の Skype を設定するには、[マイクロソフト パートナー](https://go.microsoft.com/fwlink/?linkid=391089)の採用を検討してください。</span><span class="sxs-lookup"><span data-stu-id="dd3ce-147">If you haven't done this before, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to set up Skype for Business for you.</span></span>
    
## <a name="4-set-up-im-and-presence-in-your-organization"></a><span data-ttu-id="dd3ce-148">4. IM およびプレゼンスを、組織内の場合に設定します。</span><span class="sxs-lookup"><span data-stu-id="dd3ce-148">4. Set up IM and presence in your organization</span></span>
<span data-ttu-id="dd3ce-149"><a name="bkmk_IM"> </a></span><span class="sxs-lookup"><span data-stu-id="dd3ce-149"></span></span>

<span data-ttu-id="dd3ce-150">インスタント メッセージング (IM) とプレゼンス ([ビジネス用の Skype で自分のプレゼンス情報へのアクセス制御](https://support.office.com/article/fea86e34-60cf-4dd0-bfb2-169a42afd92c)) は、ビジネスの Skype に含まれている、基本的な機能です。</span><span class="sxs-lookup"><span data-stu-id="dd3ce-150">Instant Messaging (IM) and presence ([Control access to your presence information in Skype for Business](https://support.office.com/article/fea86e34-60cf-4dd0-bfb2-169a42afd92c)) are basic features included with Skype for Business.</span></span> <span data-ttu-id="dd3ce-151">既定では、自社内のユーザーは、互いに Skype や IM をできます。</span><span class="sxs-lookup"><span data-stu-id="dd3ce-151">By default, the people in your business can Skype and IM with each other.</span></span>
  
1. <span data-ttu-id="dd3ce-152">**他のビジネス ユーザー向けに、Skype 通信できるメンバーを選択します。**</span><span class="sxs-lookup"><span data-stu-id="dd3ce-152">**Choose who else your Skype for Business users can communicate with:**</span></span>
    
  - <span data-ttu-id="dd3ce-153">[ビジネス ユーザー向けの外部の Skype に連絡を許可します。](allow-users-to-contact-external-skype-for-business-users.md)両方*および*その他のビジネス システムを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd3ce-153">[Allow users to contact external Skype for Business users](allow-users-to-contact-external-skype-for-business-users.md) Both you *and*  the other business will need to configure your systems.</span></span>
    
    <span data-ttu-id="dd3ce-154">**重要**: rob@contosowest.com、ina@contosoeast.com など、お客様のビジネスに 2 つのドメインがある場合は、すべてのユーザーが相互に通信できるように、この手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd3ce-154">**IMPORTANT**: If you have two domains in your business, such as rob@contosowest.com and ina@contosoeast.com, you need to do this step so all of your users can communicate with each other.</span></span>
    
  - <span data-ttu-id="dd3ce-155">お客様のビジネスの外の[ビジネス ユーザー向けの Skype は、Skype 連絡先を追加します。](let-skype-for-business-users-add-skype-contacts.md)</span><span class="sxs-lookup"><span data-stu-id="dd3ce-155">[Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md) outside your business</span></span>
    
2. <span data-ttu-id="dd3ce-156">**を同僚がオンラインかどうかを確認を選択してください:**プレゼンス機能は、オンラインになっていると、利用可能時間は、使用可能な使用中、退席中、またはプレゼンテーションなどを示しています。</span><span class="sxs-lookup"><span data-stu-id="dd3ce-156">**Choose who sees whether co-workers are online:** The presence feature shows who's online and what their availability is, such as available, busy, away, or presenting.</span></span>
    
    ![個人的なメッセージを持つ人のオンラインの状態の例です。](../images/ab6c10b4-6ad5-453c-bf0e-459b977b6e23.png)
  
    <span data-ttu-id="dd3ce-158">お客様のビジネスでは、すべてのユーザーの既定の設定を選択できます。</span><span class="sxs-lookup"><span data-stu-id="dd3ce-158">You can choose the default settings for everyone in your business:</span></span>
    
  - <span data-ttu-id="dd3ce-159">組織内のすべてのユーザーに、ユーザーのオンライン プレゼンスを自動的に表示します。</span><span class="sxs-lookup"><span data-stu-id="dd3ce-159">Automatically display a person's online presence to everyone in the organization</span></span>
    
  - <span data-ttu-id="dd3ce-160">そのメンバーにのみ、ユーザーのオンライン プレゼンスを表示します。</span><span class="sxs-lookup"><span data-stu-id="dd3ce-160">Display a person's online presence only to their contacts</span></span>
    
<span data-ttu-id="dd3ce-161">手順については、[ビジネス オンラインの Skype のプレゼンスを構成する](configure-presence-in-skype-for-business-online.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd3ce-161">For instructions, see [Configure presence in Skype for Business Online](configure-presence-in-skype-for-business-online.md).</span></span>
  
## <a name="5-download-and-install-skype-for-business"></a><span data-ttu-id="dd3ce-162">5. ダウンロードし、ビジネスの Skype をインストール</span><span class="sxs-lookup"><span data-stu-id="dd3ce-162">5. Download and install Skype for Business</span></span>
<span data-ttu-id="dd3ce-163"><a name="bkmk_download"> </a></span><span class="sxs-lookup"><span data-stu-id="dd3ce-163"></span></span>

<span data-ttu-id="dd3ce-164">ビジネス、PC、Mac、またはモバイル デバイス上の Skype を使用するにし、お客様のビジネスの他のユーザーは、ビジネス ダウンロード Skype をデバイスにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd3ce-164">To use Skype for Business on your PC, Mac, or mobile device, you and other people in your business have to first install the Skype for Business download on your devices.</span></span>
  
- <span data-ttu-id="dd3ce-165">[ビジネス用の Skype のインストール](http://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb): Office 365 ポータルからアプリケーションをダウンロードし、ファルダ、PC にインストールする方法について</span><span class="sxs-lookup"><span data-stu-id="dd3ce-165">[Install Skype for Business](http://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb): Instructions for how to download the app from the Office 365 portal, and install it on your PC or Mac.</span></span>
    
- <span data-ttu-id="dd3ce-166">[ビジネス クライアントを Office 365 での Skype の展開](deploy-the-skype-for-business-client-in-office-365.md): 大規模な企業でアプリケーションを展開する手順について。</span><span class="sxs-lookup"><span data-stu-id="dd3ce-166">[Deploy the Skype for Business client in Office 365](deploy-the-skype-for-business-client-in-office-365.md): Instructions for deploying the app in a large enterprise.</span></span>
    
- <span data-ttu-id="dd3ce-167">[ビジネス用の Skype のインストール](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb): ダウンロード、インストール、および Android デバイス、iOS デバイス、および Windows の電話でビジネス用の Skype にサインインします。</span><span class="sxs-lookup"><span data-stu-id="dd3ce-167">[Install Skype for Business](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb): Download, install, and sign in to Skype for Business on Android devices, iOS devices, and Windows phones.</span></span>
    
- <span data-ttu-id="dd3ce-168">[オンまたはオフ、携帯電話の通知](turn-on-or-off-mobile-phone-notifications.md): とお客様のビジネスがインスタント メッセージを受信および失敗したに関する警告を表示することができますモバイル デバイスにインストールされているビジネス用の Skype を使用すると、します。</span><span class="sxs-lookup"><span data-stu-id="dd3ce-168">[Turn on or off mobile phone notifications](turn-on-or-off-mobile-phone-notifications.md): When you have Skype for Business installed on a mobile device, you and others in your business can receive alerts about incoming and missed instant messages.</span></span>
    
## <a name="6-test-to-make-sure-everything-is-working"></a><span data-ttu-id="dd3ce-169">6. すべてが動作しているかどうかを確認するテストします。</span><span class="sxs-lookup"><span data-stu-id="dd3ce-169">6. Test to make sure everything is working</span></span>
<span data-ttu-id="dd3ce-170"><a name="bkmk_test"> </a></span><span class="sxs-lookup"><span data-stu-id="dd3ce-170"></span></span>

<span data-ttu-id="dd3ce-171">ほかのユーザーがお客様のビジネスができるかどうかを最初に、テスト[ビデオ: ビジネスの Skype との間で署名を](https://support.office.com/article/8abed4b3-ac48-493e-9d76-0e10140e9451)。</span><span class="sxs-lookup"><span data-stu-id="dd3ce-171">First, test whether you and others in your business can [Video: Sign in and out of Skype for Business](https://support.office.com/article/8abed4b3-ac48-493e-9d76-0e10140e9451).</span></span> <span data-ttu-id="dd3ce-172">互いの存在を参照するくださいと、短時間のミーティングを実行するくださいと、その他の IM をすることができますを確認します。</span><span class="sxs-lookup"><span data-stu-id="dd3ce-172">Check that you can IM each other, see each other's presence, and try a quick meeting.</span></span>
  
<span data-ttu-id="dd3ce-173">問題でしょうか。</span><span class="sxs-lookup"><span data-stu-id="dd3ce-173">Problems?</span></span> <span data-ttu-id="dd3ce-174">次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="dd3ce-174">Do the following:</span></span>
  
- <span data-ttu-id="dd3ce-175">[ビジネス用の Skype にサインインのヘルプが必要ですか?](https://support.office.com/article/448b8ea7-5b33-444a-afd4-175fc9930d05)一般的な記号に問題があります。</span><span class="sxs-lookup"><span data-stu-id="dd3ce-175">[Need help signing in to Skype for Business?](https://support.office.com/article/448b8ea7-5b33-444a-afd4-175fc9930d05) of common sign-in problems.</span></span>
    
- <span data-ttu-id="dd3ce-176">[ビジネス製品 - 管理者ヘルプのサポートに問い合わせてください](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)。</span><span class="sxs-lookup"><span data-stu-id="dd3ce-176">[Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span> <span data-ttu-id="dd3ce-177">私たちはここに役立つ!</span><span class="sxs-lookup"><span data-stu-id="dd3ce-177">We're here to help!</span></span>
    
## <a name="do-you-want-to-set-up-other-available-features"></a><span data-ttu-id="dd3ce-178">使用可能なその他の機能を設定しますか。</span><span class="sxs-lookup"><span data-stu-id="dd3ce-178">Do you want to set up other available features?</span></span>
<span data-ttu-id="dd3ce-179"><a name="bkmk_more"> </a></span><span class="sxs-lookup"><span data-stu-id="dd3ce-179"></span></span>

<span data-ttu-id="dd3ce-180">多くの機能をセットアップする前にそれらのライセンスを持っていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="dd3ce-180">Before setting up more features, make sure you have licenses for them.</span></span> [<span data-ttu-id="dd3ce-181">Skype for Business と Microsoft Teams のアドオン ライセンス</span><span class="sxs-lookup"><span data-stu-id="dd3ce-181">Skype for Business and Microsoft Teams add-on licensing</span></span>](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
### <a name="set-up-audio-conferencing"></a><span data-ttu-id="dd3ce-182">電話会議をセットアップする</span><span class="sxs-lookup"><span data-stu-id="dd3ce-182">Set up Audio Conferencing</span></span>

<span data-ttu-id="dd3ce-183">組織内のユーザーは、会議への呼び出しを携帯電話を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd3ce-183">Sometimes people in your organization will need to use a phone to call into a meeting.</span></span> <span data-ttu-id="dd3ce-184">ビジネス用の Skype には、これだけの電話会議機能が含まれています!</span><span class="sxs-lookup"><span data-stu-id="dd3ce-184">Skype for Business includes the Audio Conferencing feature for just this situation!</span></span> <span data-ttu-id="dd3ce-185">ユーザーは、モバイル デバイスまたは PC 上のアプリケーションをビジネス用の Skype を使用する代わりに、電話を使用してビジネス ・ ミーティングの Skype を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="dd3ce-185">People can call into Skype for Business meetings using a phone, instead of using the Skype for Business app on a mobile device or PC.</span></span>
  
<span data-ttu-id="dd3ce-186">ステップ バイ ステップのセットアップ手順については、Office 365 の[ビジネスおよびマイクロソフトのチームに Skype の電話会議の設定](../audio-conferencing-in-office-365/set-up-audio-conferencing.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd3ce-186">For step-by-step setup instructions, see [Set up Audio Conferencing for Skype for Business and Microsoft Teams](../audio-conferencing-in-office-365/set-up-audio-conferencing.md) in Office 365.</span></span>
  
### <a name="set-up-phone-system-and-the-calling-plans-in-office-365"></a><span data-ttu-id="dd3ce-187">電話システムと Office 365 の通話プランを設定します。</span><span class="sxs-lookup"><span data-stu-id="dd3ce-187">Set up Phone System and the Calling plans in Office 365</span></span>

<span data-ttu-id="dd3ce-188">Office 365 の電話システムの機能を使用すると、お客様のビジネス電話システムです。</span><span class="sxs-lookup"><span data-stu-id="dd3ce-188">The Phone System feature in Office 365 gives you a phone system for your business.</span></span> <span data-ttu-id="dd3ce-189">ビジネスに携わる人々、組織内の他の Skype への呼び出しは、自由、および呼び出し元の内外から他の従業員がボイスメールを受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="dd3ce-189">Calls to other Skype for Business people in your organization are free, and your employees can receive voicemail from each other and outside callers.</span></span> <span data-ttu-id="dd3ce-190">電話システムで取得するにはここです。</span><span class="sxs-lookup"><span data-stu-id="dd3ce-190">Here's what you get with Phone System.</span></span>
  
<span data-ttu-id="dd3ce-191">計画を呼び出してサービスを追加すると、従業員は、ビジネスの Skype で基本の電話番号を取得します。</span><span class="sxs-lookup"><span data-stu-id="dd3ce-191">When you add the Calling Plan service, your employees get a primary phone number in Skype for Business.</span></span> <span data-ttu-id="dd3ce-192">組織外からの電話呼び出しを受信できます。</span><span class="sxs-lookup"><span data-stu-id="dd3ce-192">They can make and receive phone calls outside of your business.</span></span> <span data-ttu-id="dd3ce-193">VoIP 電話、Pc、およびモバイル デバイスの間で音声通話をようにします。</span><span class="sxs-lookup"><span data-stu-id="dd3ce-193">They can make voice calls across VoIP phones, PCs, and mobile devices.</span></span> <span data-ttu-id="dd3ce-194">事態が発生した場合については 911 を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="dd3ce-194">And, in case of emergencies, they can call 911 for help.</span></span>
  
<span data-ttu-id="dd3ce-195">ステップ バイ ステップのセットアップ手順については、表示を呼び出すことを計画します。</span><span class="sxs-lookup"><span data-stu-id="dd3ce-195">For step-by-step setup instructions, see Set up Calling Plans.</span></span>
  
### <a name="set-up-skype-meeting-broadcast"></a><span data-ttu-id="dd3ce-196">Skype 会議のブロードキャストの設定します。</span><span class="sxs-lookup"><span data-stu-id="dd3ce-196">Set up Skype Meeting Broadcast</span></span>

<span data-ttu-id="dd3ce-197">Skype の会議のブロードキャストは、ホストを作成して、最大 10000 個までの参加者との会議をブロードキャストできるようにする機能です。</span><span class="sxs-lookup"><span data-stu-id="dd3ce-197">Skype Meeting Broadcast is a feature that lets you produce, host, and broadcast meetings with up to 10,000 attendees.</span></span> <span data-ttu-id="dd3ce-198">**そのしくみの詳細についてを参照してください[Skype の会議のブロードキャストとは何ですか?](http://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)**</span><span class="sxs-lookup"><span data-stu-id="dd3ce-198">**To learn more about how it works, see [What is a Skype Meeting Broadcast?](http://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)**</span></span>
  
<span data-ttu-id="dd3ce-199">Skype 会議のブロードキャストを設定する手順の概要を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="dd3ce-199">Here's an overview of the steps to set up Skype Meeting Broadcast:</span></span>
  
1. <span data-ttu-id="dd3ce-200">[割り当てまたはビジネスのための Office 365 のライセンスを削除する](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc): すべてのブロードキャストの会議**のホスト**にいる人に**Skype** 、または**エンタープライズ**のライセンスを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="dd3ce-200">[Assign or remove licenses for Office 365 for business](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc): Assign **Skype for Business Online** or **Enterprise Plan** licenses to everyone who is going to **host** a Broadcast meeting.</span></span>
    
2. <span data-ttu-id="dd3ce-201">[Skype 会議のブロードキャストを有効にする](../set-up-your-network-for-skype-meeting-broadcast/enable-skype-meeting-broadcast.md): 既定では、この機能が有効になっています。</span><span class="sxs-lookup"><span data-stu-id="dd3ce-201">[Enable Skype Meeting Broadcast](../set-up-your-network-for-skype-meeting-broadcast/enable-skype-meeting-broadcast.md): By default, this feature isn't enabled.</span></span> <span data-ttu-id="dd3ce-202">有効にした後ことをユーザーは、組織内の他のユーザーと会議をブロードキャストをホストすることになります。</span><span class="sxs-lookup"><span data-stu-id="dd3ce-202">After you turn it on, your users will be able to host broadcast meetings with other people in your organization.</span></span>
    
3. <span data-ttu-id="dd3ce-203">[Skype 会議をブロードキャストするためにネットワークを設定します](../set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast.md): ウェビナーをホストし、他の放送参加者と別の組織をする場合、ネットワークを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd3ce-203">[Set up your network for Skype Meeting Broadcast](../set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast.md): If you want to host webinars and other broadcasts with attendees outside of your organization, you need to configure your network.</span></span>
    
4. <span data-ttu-id="dd3ce-204">[Skype 会議のブロードキャストのスケジュール](http://support.office.com/article/c3995bc9-4d32-4f75-a004-3bc5c477e553) [Skype の会議のブロードキャストの結合](http://support.office.com/article/14689da0-821d-48d4-9035-ea762de80ebe): *https://portal.broadcast.skype.com*で、Skype の会議のブロードキャストをスケジュールし、他の会議のブロードキャストの作業に参加しようとするかどうかを確認、会議。</span><span class="sxs-lookup"><span data-stu-id="dd3ce-204">[Schedule a Skype Meeting Broadcast](http://support.office.com/article/c3995bc9-4d32-4f75-a004-3bc5c477e553) and have a [Join a Skype Meeting Broadcast](http://support.office.com/article/14689da0-821d-48d4-9035-ea762de80ebe): Make sure broadcast meetings work by scheduling a Skype Meeting Broadcast at  *https://portal.broadcast.skype.com*  and then having someone try to join the meeting.</span></span>
    
## <a name="learn-about-network-connectivity-requirements"></a><span data-ttu-id="dd3ce-205">ネットワーク接続の要件についてください。</span><span class="sxs-lookup"><span data-stu-id="dd3ce-205">Learn about network connectivity requirements</span></span>
<span data-ttu-id="dd3ce-206"><a name="bkmk_more"> </a></span><span class="sxs-lookup"><span data-stu-id="dd3ce-206"></span></span>

<span data-ttu-id="dd3ce-207">品質のオーディオ、ビデオ、およびアプリケーション共有のビジネス用の Skype では、エンド ・ ツー ・ エンドのネットワーク接続の品質が大幅に影響があります。</span><span class="sxs-lookup"><span data-stu-id="dd3ce-207">The quality of audio, video, and application sharing in Skype for Business is greatly impacted by the quality of end-to-end network connectivity.</span></span> <span data-ttu-id="dd3ce-208">最適なエクスペリエンスでは、ことが会社のネットワークとオンライン ビジネスの Skype の高品質の接続があるかどうかを確認するのには重要です。</span><span class="sxs-lookup"><span data-stu-id="dd3ce-208">For an optimal experience, it is important to make sure there is a high-quality connection between your company network and Skype for Business Online.</span></span> <span data-ttu-id="dd3ce-209">ネットワークとチューニングについては、[オンライン ビジネスのパフォーマンスのための Skype のチューニング](http://support.office.com/article/beec23c2-c5d6-4e84-a8af-e82aefca7802)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd3ce-209">For network and tuning information, see [Tune Skype for Business Online performance](http://support.office.com/article/beec23c2-c5d6-4e84-a8af-e82aefca7802).</span></span>
  
## <a name="all-done-setting-up-getting-started-using-skype-for-business"></a><span data-ttu-id="dd3ce-210">すべて実行を設定しますか。</span><span class="sxs-lookup"><span data-stu-id="dd3ce-210">All done setting up?</span></span> <span data-ttu-id="dd3ce-211">ビジネスの Skype を使用して作業の開始</span><span class="sxs-lookup"><span data-stu-id="dd3ce-211">Getting started using Skype for Business</span></span>
<span data-ttu-id="dd3ce-212"><a name="bkmk_more"> </a></span><span class="sxs-lookup"><span data-stu-id="dd3ce-212"></span></span>

<span data-ttu-id="dd3ce-213">[業務トレーニング用 Skype](http://support.office.com/article/8a3491a3-c095-4718-80cf-cbbe4afe4eba): 簡単に開始するためのトレーニング ・ トピックの一覧をチェック!</span><span class="sxs-lookup"><span data-stu-id="dd3ce-213">[Skype for Business training](http://support.office.com/article/8a3491a3-c095-4718-80cf-cbbe4afe4eba): Check out this list of training topics to help you get started quickly!</span></span>
  
[<span data-ttu-id="dd3ce-214">Skype の電話会議のビジネスを開始します。</span><span class="sxs-lookup"><span data-stu-id="dd3ce-214">Start a Skype for Business conference call</span></span>](http://support.office.com/article/8dc8ac52-91ac-4db9-8672-11551fdaf997)
  
[<span data-ttu-id="dd3ce-215">ビジネス用の Skype でビデオ デバイス オプションを設定します。</span><span class="sxs-lookup"><span data-stu-id="dd3ce-215">Set Video Device options in Skype for Business</span></span>](http://support.office.com/article/d09017c0-deba-4f6c-a122-9eca6604f50c)
  
[<span data-ttu-id="dd3ce-216">ビジネスの Skype を使用してビデオ通話を受信し、</span><span class="sxs-lookup"><span data-stu-id="dd3ce-216">Make and receive a video call using Skype for Business</span></span>](http://support.office.com/article/abf62493-670f-4b0d-b2cf-fe03b49caf42)
  
[!INCLUDE [LinkedIn Learning Info](../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a><span data-ttu-id="dd3ce-217">関連トピック</span><span class="sxs-lookup"><span data-stu-id="dd3ce-217">Related topics</span></span>
<span data-ttu-id="dd3ce-218"><a name="bkmk_more"> </a></span><span class="sxs-lookup"><span data-stu-id="dd3ce-218"></span></span>

[<span data-ttu-id="dd3ce-219">Skype ビジネス サーバーとビジネス オンラインの Skype との間のハイブリッド接続を計画します。</span><span class="sxs-lookup"><span data-stu-id="dd3ce-219">Plan hybrid connectivity between Skype for Business Server and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/p/?linkid=400791)
  

