---
title: Skype for Business Online をセットアップする
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 40296968-e779-4259-980b-c2de1c044c6e
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords:
- O365E_SkypeforBusinessON
- O365M_SkypeforBusinessON
- O365P_SkypeforBusinessON
ms.custom:
- Setup
- Alchemy
- LIL_Placement
description: 'Skype for Business をインストールするために、ドメイン、ユーザー、IM、プレゼンスを組織用にセットアップする方法について説明します。 「電話会議、電話システム、通話プラン、Skype 会議ブロードキャストを設定する」もご覧ください。 '
ms.openlocfilehash: fb31a2affa1507f043244fbe6f1988040cfec4ba
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34285256"
---
# <a name="set-up-skype-for-business-online"></a><span data-ttu-id="5a0ce-104">Skype for Business Online をセットアップする</span><span class="sxs-lookup"><span data-stu-id="5a0ce-104">Set up Skype for Business Online</span></span>

<span data-ttu-id="5a0ce-105">Skype for Business をセットアップするには、Office 365 グローバル管理者の権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="5a0ce-105">You must have Office 365 global admin permissions to set up Skype for Business.</span></span> <span data-ttu-id="5a0ce-106">Web パーツへのアクセスを制限するファイアウォールまたはプロキシサーバーがある場合は、 [Microsoft パートナー](https://go.microsoft.com/fwlink/?linkid=391089)を採用して Skype for business をセットアップすることを検討してください。</span><span class="sxs-lookup"><span data-stu-id="5a0ce-106">If you have a firewall or proxy server that restricts access to parts of the web, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to set up Skype for Business for you.</span></span>

## <a name="setting-up-skype"></a><span data-ttu-id="5a0ce-107">Skype のセットアップ</span><span class="sxs-lookup"><span data-stu-id="5a0ce-107">Setting up Skype</span></span>

<span data-ttu-id="5a0ce-108">Office 365 サブスクリプションでの Skype のセットアップに関するヘルプが必要なようです。</span><span class="sxs-lookup"><span data-stu-id="5a0ce-108">Looks like you need help setting up Skype with your Office 365 subscription.</span></span> <span data-ttu-id="5a0ce-109">この記事の手順に従って、セットアップを完了することができます。</span><span class="sxs-lookup"><span data-stu-id="5a0ce-109">You can follow the steps in this article to get your setup completed.</span></span>

## <a name="1-plan-for-skype-for-business"></a><span data-ttu-id="5a0ce-110">1. Skype for Business を計画する</span><span class="sxs-lookup"><span data-stu-id="5a0ce-110">1. Plan for Skype for Business</span></span>

<span data-ttu-id="5a0ce-111">**[Office 365 Business Premium](https://products.office.com/en-us/business/office-365-business-premium)** または**business Essentials**を使用している場合は、Skype for business を使用して、サブスクリプションに参加している組織内の他のユーザーとオンラインで通話を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="5a0ce-111">If you have **[Office 365 Business Premium](https://products.office.com/en-us/business/office-365-business-premium)** or **Business Essentials**, you can use Skype for Business to make online calls to other people in your business who are on your subscription.</span></span> <span data-ttu-id="5a0ce-112">たとえば、ユーザーが10人いる組織では、以下の手順2-6 を実行した後に skype for business を使用して skype [](https://support.office.com/article/2eed8424-581a-4497-b505-c08c152e5851) for business を使用して通話を[開始](https://support.office.com/article/cc05afa6-1894-4a82-9dd9-6222061f50fd)することができます。</span><span class="sxs-lookup"><span data-stu-id="5a0ce-112">For example, if your business has 10 people, you'll be able to [Start using Skype for Business for IM and online meetings](https://support.office.com/article/cc05afa6-1894-4a82-9dd9-6222061f50fd) each other, and [Meetings with Skype for Business](https://support.office.com/article/2eed8424-581a-4497-b505-c08c152e5851) using Skype for Business after performing the steps 2-6 below.</span></span> <span data-ttu-id="5a0ce-113">また、 [Outlook で Skype For business 会議を設定](https://support.office.com/article/b8305620-d16e-4667-989d-4a977aad6556#bkmk_OWA)することもできます。</span><span class="sxs-lookup"><span data-stu-id="5a0ce-113">And you can [Set up a Skype for Business meeting in Outlook](https://support.office.com/article/b8305620-d16e-4667-989d-4a977aad6556#bkmk_OWA) to online meetings, too!</span></span>

<span data-ttu-id="5a0ce-114">Skype for Business を使用して*社外*のユーザーとの**通話を発信**および受信するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="5a0ce-114">If you want to use Skype for Business to make and receive **calls** from people *external*  to your business:</span></span>

- <span data-ttu-id="5a0ce-115">**オプション 1。無料の [Skype アプリ](https://www.skype.com/)** を使用します。</span><span class="sxs-lookup"><span data-stu-id="5a0ce-115">**Option 1. Use the free [Skype app](https://www.skype.com/)**.</span></span> <span data-ttu-id="5a0ce-116">非常に小さなビジネス (1-2 ユーザーなど) を使用している場合は、Skype アプリを使う方が便利です。</span><span class="sxs-lookup"><span data-stu-id="5a0ce-116">If you have a very small business (for example, 1-2 people), using the Skype app is the better way to go.</span></span> <span data-ttu-id="5a0ce-117">国内通話と国際通話で利用する場合は、より安価な手段となります。</span><span class="sxs-lookup"><span data-stu-id="5a0ce-117">It's less expensive to use for domestic and international calls.</span></span> <span data-ttu-id="5a0ce-118">会議通話を保留したり、ビデオ通話を発信したり、デスクトップを共有してプレゼンテーションを行ったりすることができます。</span><span class="sxs-lookup"><span data-stu-id="5a0ce-118">You can still hold conference calls, make video calls, and share your desktop for presentations.</span></span> <span data-ttu-id="5a0ce-119">[料金と支払オプションを確認](https://secure.skype.com/en/calling-rates?wt.mc_id=legacy&amp;expo365=bundled)してください。</span><span class="sxs-lookup"><span data-stu-id="5a0ce-119">[Check out the rates and payment options](https://secure.skype.com/en/calling-rates?wt.mc_id=legacy&amp;expo365=bundled).</span></span>

- <span data-ttu-id="5a0ce-120">**オプション2。プランをアップグレードし、電話システムと、Office 365 の通話プランを購入**します。</span><span class="sxs-lookup"><span data-stu-id="5a0ce-120">**Option 2. Upgrade your plan, and buy the Phone System and a Calling Plan for Office 365**.</span></span> <span data-ttu-id="5a0ce-121">このコストを確認してから、切り替えを行う最も簡単な方法は、[ビジネス製品のサポートにお問い合わせください。管理者向けヘルプ](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)。</span><span class="sxs-lookup"><span data-stu-id="5a0ce-121">The easiest way to find out how much this costs, and then make the switch, is to [Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) and have them do everything for you.</span></span>

<span data-ttu-id="5a0ce-122">詳細については、「一般[法人向け Office 365 のセットアップを計画](https://support.office.com/article/eb926624-018b-4486-bf11-5fba6ee4d645#bkmk_skype)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a0ce-122">To learn more, see [Plan your setup of Office 365 for business](https://support.office.com/article/eb926624-018b-4486-bf11-5fba6ee4d645#bkmk_skype).</span></span>

## <a name="2-sign-in-to-office-365"></a><span data-ttu-id="5a0ce-123">2. Office 365 にサインインする</span><span class="sxs-lookup"><span data-stu-id="5a0ce-123">2. Sign in to Office 365</span></span>
<span data-ttu-id="5a0ce-124"><a name="bkmk_signin"> </a></span><span class="sxs-lookup"><span data-stu-id="5a0ce-124"></span></span>

<span data-ttu-id="5a0ce-125">Skype for Business Online は、Office 365 スイートのサービスの一部です。</span><span class="sxs-lookup"><span data-stu-id="5a0ce-125">Skype for Business Online is part of the Office 365 suite of services.</span></span> <span data-ttu-id="5a0ce-126">Skype for Business Online をセットアップするには、Office 365 にサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a0ce-126">To set up Skype for Business Online, you need to sign in to Office 365.</span></span> <span data-ttu-id="5a0ce-127">その方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5a0ce-127">Here's how you do that:</span></span>

1. <span data-ttu-id="5a0ce-128">使用している Office 365 のユーザー ID ( <em>rob@fourthcoffee.com</em>など) を探します。</span><span class="sxs-lookup"><span data-stu-id="5a0ce-128">Locate your Office 365 user ID (for example,  <em>rob@fourthcoffee.com</em>  ).</span></span> <span data-ttu-id="5a0ce-129">Skype for Business Online を購入したときに作成した Office 365 ユーザー ID が含まれている Microsoft Online Services チームからメールを受信しました。</span><span class="sxs-lookup"><span data-stu-id="5a0ce-129">You received an email from the Microsoft Online Services Team that contains the Office 365 user ID that you created when you purchased Skype for Business Online.</span></span> <span data-ttu-id="5a0ce-130">次のようなメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5a0ce-130">The mail looks something like this:</span></span>

    ![Skype for Business Online にサインアップした後に受信したようこそメールの例です。](../images/977c5c96-29c5-40c0-a4c4-1ba66ba3a1fb.png)

2. <span data-ttu-id="5a0ce-133">Office 365 管理センターにサインインして、Office 365 のユーザー ID とパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="5a0ce-133">Sign in to the Office 365 admin center and enter your Office 365 user ID and password.</span></span> <span data-ttu-id="5a0ce-134">サインインすると、Office 365 管理センターが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5a0ce-134">After you sign in, you'll see the Office 365 admin center:</span></span>

    ![Skype for Business Online プランを使用している場合、Office 365 管理センターの外観はどのように表示されますか。](../images/ed1d9906-e717-450b-81a3-ce6679bd1be1.png)

## <a name="3-set-up-your-domain-and-users"></a><span data-ttu-id="5a0ce-136">3. ドメインとユーザーをセットアップする</span><span class="sxs-lookup"><span data-stu-id="5a0ce-136">3. Set up your domain and users</span></span>
<span data-ttu-id="5a0ce-137"><a name="bkmk_users"> </a></span><span class="sxs-lookup"><span data-stu-id="5a0ce-137"></span></span>

<span data-ttu-id="5a0ce-138">Office 365 にサインインしたら、ドメインと組織内のユーザーが Skype for Business Online を使用するようにセットアップすることができます。</span><span class="sxs-lookup"><span data-stu-id="5a0ce-138">Now that you're signed in to Office 365, you can set up your domain and people in your organization to use Skype for Business Online.</span></span>

1. <span data-ttu-id="5a0ce-139">[Office 365 にドメインとユーザーを追加](https://support.office.com/article/6383f56d-3d09-4dcb-9b41-b5f5a5efd611)する: office 365 セットアップウィザードを使用して、office 365 でカスタムドメイン ( *fourthcoffee.com*など) をセットアップします。</span><span class="sxs-lookup"><span data-stu-id="5a0ce-139">[Add a domain and users to Office 365](https://support.office.com/article/6383f56d-3d09-4dcb-9b41-b5f5a5efd611): Use the Office 365 setup wizard to set up your custom domain (such as *fourthcoffee.com*) with Office 365.</span></span> <span data-ttu-id="5a0ce-140">**既定では、Office 365 セットアップウィザードには、Skype for business Online のセットアップと Skype for Business のユーザー Id の作成が含まれています。**</span><span class="sxs-lookup"><span data-stu-id="5a0ce-140">**By default, the Office 365 setup wizard includes setting up Skype for Business Online and creating your Skype for Business user IDs.**</span></span> <span data-ttu-id="5a0ce-141">既にウィザードを使用して Office 365 用にドメインをセットアップした場合は、この手順を完了します。</span><span class="sxs-lookup"><span data-stu-id="5a0ce-141">If you already used the wizard to set up your domain for Office 365, then you've completed this step.</span></span>

2. <span data-ttu-id="5a0ce-142">[ドメインと dns の接続を確認](https://support.office.com/article/2b54e1b0-47a7-4018-a1e4-c2b924e7c5a0)します。「ツール」「ドメインのトラブルシューティング-ドメインと dns の設定が正しいことを確認する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a0ce-142">[Check your domain and DNS connections](https://support.office.com/article/2b54e1b0-47a7-4018-a1e4-c2b924e7c5a0): Use our tool - the domains troubleshooter - to check that your domain and DNS settings are correct.</span></span> <span data-ttu-id="5a0ce-143">これを行うと、今後の問題のソースとして DNS 設定を削除できるため、後でセットアップの問題を簡単に解決できるようになります。</span><span class="sxs-lookup"><span data-stu-id="5a0ce-143">Doing this now will go a long way to helping figure out any setup issues later since you'll be able to eliminate DNS settings as the source of future issues.</span></span>

3. <span data-ttu-id="5a0ce-144">[Office 365 の url と IP アドレスの範囲](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2#BKMK_LYO): ほとんどの小規模企業は、この手順を実行する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="5a0ce-144">[Office 365 URLs and IP address ranges](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2#BKMK_LYO): Most small businesses don't need to do this step.</span></span> <span data-ttu-id="5a0ce-145">**ただし、web の一部へのアクセスを制限するファイアウォールまたはプロキシサーバーがある場合**は、そのルールを作成して、Skype For business Online エンドポイントへのアクセスを許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a0ce-145">**But if you have a firewall or proxy server that restricts access to parts of the web**, you must create rules to allow access to the Skype for Business Online endpoints.</span></span> <span data-ttu-id="5a0ce-146">これは、ファイアウォールとプロキシサーバーの構成で経験したユーザーによって実行される高度な手順です。</span><span class="sxs-lookup"><span data-stu-id="5a0ce-146">This is an advanced step best performed by someone experienced with configuring firewalls and proxy servers.</span></span> <span data-ttu-id="5a0ce-147">この作業をまだ行っていない場合は、 [Microsoft パートナー](https://go.microsoft.com/fwlink/?linkid=391089)を雇用して Skype for business をセットアップすることを検討してください。</span><span class="sxs-lookup"><span data-stu-id="5a0ce-147">If you haven't done this before, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to set up Skype for Business for you.</span></span>

## <a name="4-set-up-im-and-presence-in-your-organization"></a><span data-ttu-id="5a0ce-148">4. 組織で IM とプレゼンスを設定する</span><span class="sxs-lookup"><span data-stu-id="5a0ce-148">4. Set up IM and presence in your organization</span></span>
<span data-ttu-id="5a0ce-149"><a name="bkmk_IM"> </a></span><span class="sxs-lookup"><span data-stu-id="5a0ce-149"></span></span>

<span data-ttu-id="5a0ce-150">インスタントメッセージング (IM) とプレゼンス ([skype For business のプレゼンス情報へのアクセスの制御](https://support.office.com/article/fea86e34-60cf-4dd0-bfb2-169a42afd92c)) は、skype for business に組み込まれている基本的な機能です。</span><span class="sxs-lookup"><span data-stu-id="5a0ce-150">Instant Messaging (IM) and presence ([Control access to your presence information in Skype for Business](https://support.office.com/article/fea86e34-60cf-4dd0-bfb2-169a42afd92c)) are basic features included with Skype for Business.</span></span> <span data-ttu-id="5a0ce-151">既定では、会社内のユーザーは互いに Skype と IM を使用できます。</span><span class="sxs-lookup"><span data-stu-id="5a0ce-151">By default, the people in your business can Skype and IM with each other.</span></span>

1. <span data-ttu-id="5a0ce-152">**Skype for Business ユーザーが通信できるユーザーを次の中から選びます。**</span><span class="sxs-lookup"><span data-stu-id="5a0ce-152">**Choose who else your Skype for Business users can communicate with:**</span></span>

   - <span data-ttu-id="5a0ce-153">[ユーザーが外部の Skype For business ユーザーに連絡できるように](allow-users-to-contact-external-skype-for-business-users.md)する自分*と*その両方のビジネスがシステムを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a0ce-153">[Allow users to contact external Skype for Business users](allow-users-to-contact-external-skype-for-business-users.md) Both you *and*  the other business will need to configure your systems.</span></span>

     <span data-ttu-id="5a0ce-154">**重要**: rob@contosowest.com や ina@contosoeast.com などの2つのドメインがある場合は、この手順を実行して、すべてのユーザーが相互に通信できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a0ce-154">**IMPORTANT**: If you have two domains in your business, such as rob@contosowest.com and ina@contosoeast.com, you need to do this step so all of your users can communicate with each other.</span></span>

   - <span data-ttu-id="5a0ce-155">[Skype For business ユーザーが社外の skype 連絡先を追加できる](let-skype-for-business-users-add-skype-contacts.md)ようにする</span><span class="sxs-lookup"><span data-stu-id="5a0ce-155">[Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md) outside your business</span></span>

2. <span data-ttu-id="5a0ce-156">**同僚がオンラインであるかどうかを確認できるユーザーを選択します。** プレゼンス機能は、誰がオンライン状態かを表示し、連絡可能、取り込み中、退席中、プレゼンテーション中などの状態を示します。</span><span class="sxs-lookup"><span data-stu-id="5a0ce-156">**Choose who sees whether co-workers are online:** The presence feature shows who's online and what their availability is, such as available, busy, away, or presenting.</span></span>

    ![個人メッセージによる個人のオンライン状態の例。](../images/ab6c10b4-6ad5-453c-bf0e-459b977b6e23.png)

    <span data-ttu-id="5a0ce-158">組織内のすべてのユーザーに対して既定の設定を選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="5a0ce-158">You can choose the default settings for everyone in your business:</span></span>

   - <span data-ttu-id="5a0ce-159">組織内のすべてのユーザーにオンラインプレゼンスを自動的に表示する</span><span class="sxs-lookup"><span data-stu-id="5a0ce-159">Automatically display a person's online presence to everyone in the organization</span></span>

   - <span data-ttu-id="5a0ce-160">連絡先に対してのみ自分のオンラインプレゼンスを表示する</span><span class="sxs-lookup"><span data-stu-id="5a0ce-160">Display a person's online presence only to their contacts</span></span>

<span data-ttu-id="5a0ce-161">手順については、「 [Skype For Business Online でプレゼンスを設定する](configure-presence-in-skype-for-business-online.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a0ce-161">For instructions, see [Configure presence in Skype for Business Online](configure-presence-in-skype-for-business-online.md).</span></span>

## <a name="5-download-and-install-skype-for-business"></a><span data-ttu-id="5a0ce-162">5. Skype for Business をダウンロードしてインストールする</span><span class="sxs-lookup"><span data-stu-id="5a0ce-162">5. Download and install Skype for Business</span></span>
<span data-ttu-id="5a0ce-163"><a name="bkmk_download"> </a></span><span class="sxs-lookup"><span data-stu-id="5a0ce-163"></span></span>

<span data-ttu-id="5a0ce-164">Skype for Business を PC、Mac、またはモバイルデバイスで使用するには、組織内の自分または他のユーザーがまず、デバイスに Skype for Business ダウンロードをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a0ce-164">To use Skype for Business on your PC, Mac, or mobile device, you and other people in your business have to first install the Skype for Business download on your devices.</span></span>

- <span data-ttu-id="5a0ce-165">[Skype For business をインストール](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb)する: Office 365 ポータルからアプリをダウンロードして、PC または Mac にインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5a0ce-165">[Install Skype for Business](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb): Instructions for how to download the app from the Office 365 portal, and install it on your PC or Mac.</span></span>

- <span data-ttu-id="5a0ce-166">[Office 365 で Skype For business クライアントを展開](deploy-the-skype-for-business-client-in-office-365.md)する: 大企業でアプリを展開するための手順。</span><span class="sxs-lookup"><span data-stu-id="5a0ce-166">[Deploy the Skype for Business client in Office 365](deploy-the-skype-for-business-client-in-office-365.md): Instructions for deploying the app in a large enterprise.</span></span>

- <span data-ttu-id="5a0ce-167">[Skype For business をインストール](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb)する: Android デバイス、iOS デバイス、Windows Phone で Skype for business をダウンロードしてインストールし、サインインします。</span><span class="sxs-lookup"><span data-stu-id="5a0ce-167">[Install Skype for Business](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb): Download, install, and sign in to Skype for Business on Android devices, iOS devices, and Windows phones.</span></span>

- <span data-ttu-id="5a0ce-168">[携帯電話の通知をオンまたはオフ](turn-on-or-off-mobile-phone-notifications.md)にする: モバイルデバイスに Skype for business がインストールされている場合、組織内の他のユーザーが、受信または不在着信したインスタントメッセージに関する通知を受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="5a0ce-168">[Turn on or off mobile phone notifications](turn-on-or-off-mobile-phone-notifications.md): When you have Skype for Business installed on a mobile device, you and others in your business can receive alerts about incoming and missed instant messages.</span></span>

## <a name="6-test-to-make-sure-everything-is-working"></a><span data-ttu-id="5a0ce-169">6. すべての機能が動作していることをテストして確認する</span><span class="sxs-lookup"><span data-stu-id="5a0ce-169">6. Test to make sure everything is working</span></span>
<span data-ttu-id="5a0ce-170"><a name="bkmk_test"> </a></span><span class="sxs-lookup"><span data-stu-id="5a0ce-170"></span></span>

<span data-ttu-id="5a0ce-171">まず、自分とビジネス上の他のユーザーがビデオを利用できるかどうかをテストし[ます。 Skype For business のサインインとサインアウト](https://support.office.com/article/8abed4b3-ac48-493e-9d76-0e10140e9451)。</span><span class="sxs-lookup"><span data-stu-id="5a0ce-171">First, test whether you and others in your business can [Video: Sign in and out of Skype for Business](https://support.office.com/article/8abed4b3-ac48-493e-9d76-0e10140e9451).</span></span> <span data-ttu-id="5a0ce-172">お互いに IM を送信して、お互いのプレゼンスを確認して、簡単に会議を試すことができることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5a0ce-172">Check that you can IM each other, see each other's presence, and try a quick meeting.</span></span>

<span data-ttu-id="5a0ce-173">問題?</span><span class="sxs-lookup"><span data-stu-id="5a0ce-173">Problems?</span></span> <span data-ttu-id="5a0ce-174">次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="5a0ce-174">Do the following:</span></span>

- <span data-ttu-id="5a0ce-175">[Skype For business のサインインでヘルプが必要ですか?](https://support.office.com/article/448b8ea7-5b33-444a-afd4-175fc9930d05)サインインに関する一般的な問題の場合。</span><span class="sxs-lookup"><span data-stu-id="5a0ce-175">[Need help signing in to Skype for Business?](https://support.office.com/article/448b8ea7-5b33-444a-afd4-175fc9930d05) of common sign-in problems.</span></span>

- <span data-ttu-id="5a0ce-176">[ビジネス製品のサポートについては、「管理者向けヘルプ」を参照してください](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)。</span><span class="sxs-lookup"><span data-stu-id="5a0ce-176">[Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span> <span data-ttu-id="5a0ce-177">ここでは、ご意見をお待ちしています。</span><span class="sxs-lookup"><span data-stu-id="5a0ce-177">We're here to help!</span></span>

## <a name="do-you-want-to-set-up-other-available-features"></a><span data-ttu-id="5a0ce-178">他の機能をセットアップしますか?</span><span class="sxs-lookup"><span data-stu-id="5a0ce-178">Do you want to set up other available features?</span></span>
<span data-ttu-id="5a0ce-179"><a name="bkmk_more"> </a></span><span class="sxs-lookup"><span data-stu-id="5a0ce-179"></span></span>

<span data-ttu-id="5a0ce-180">その他の機能を設定する前に、ライセンスがあることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="5a0ce-180">Before setting up more features, make sure you have licenses for them.</span></span> [<span data-ttu-id="5a0ce-181">Skype for Business と Microsoft Teams のアドオン ライセンス</span><span class="sxs-lookup"><span data-stu-id="5a0ce-181">Skype for Business and Microsoft Teams add-on licensing</span></span>](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)

### <a name="set-up-audio-conferencing"></a><span data-ttu-id="5a0ce-182">電話会議をセットアップする</span><span class="sxs-lookup"><span data-stu-id="5a0ce-182">Set up Audio Conferencing</span></span>

<span data-ttu-id="5a0ce-183">組織内のユーザーは電話を使って会議に参加する必要が生じることがあります。</span><span class="sxs-lookup"><span data-stu-id="5a0ce-183">Sometimes people in your organization will need to use a phone to call into a meeting.</span></span> <span data-ttu-id="5a0ce-184">Skype for Business には、このような状況での電話会議機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="5a0ce-184">Skype for Business includes the Audio Conferencing feature for just this situation!</span></span> <span data-ttu-id="5a0ce-185">参加者は、モバイル デバイスや PC で Skype for Business アプリを使用する代わりに、電話を使って Skype for Business 会議にコールインできます。</span><span class="sxs-lookup"><span data-stu-id="5a0ce-185">People can call into Skype for Business meetings using a phone, instead of using the Skype for Business app on a mobile device or PC.</span></span>

### <a name="set-up-phone-system-and-the-calling-plans-in-office-365"></a><span data-ttu-id="5a0ce-186">Office 365 で電話システムと通話プランをセットアップする</span><span class="sxs-lookup"><span data-stu-id="5a0ce-186">Set up Phone System and the Calling plans in Office 365</span></span>

<span data-ttu-id="5a0ce-187">Office 365 の電話システム機能により、ビジネス用の電話システムが提供されます。</span><span class="sxs-lookup"><span data-stu-id="5a0ce-187">The Phone System feature in Office 365 gives you a phone system for your business.</span></span> <span data-ttu-id="5a0ce-188">組織内の他の Skype for Business ユーザーへの通話は無料であり、従業員はお互いの発信者や外部からのボイスメールを受信することができます。</span><span class="sxs-lookup"><span data-stu-id="5a0ce-188">Calls to other Skype for Business people in your organization are free, and your employees can receive voicemail from each other and outside callers.</span></span> <span data-ttu-id="5a0ce-189">電話システムで利用できる機能は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5a0ce-189">Here's what you get with Phone System.</span></span>

<span data-ttu-id="5a0ce-190">通話プランサービスを追加すると、従業員は Skype for Business で主要な電話番号を取得できます。</span><span class="sxs-lookup"><span data-stu-id="5a0ce-190">When you add the Calling Plan service, your employees get a primary phone number in Skype for Business.</span></span> <span data-ttu-id="5a0ce-191">組織外での通話の発信と受信を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="5a0ce-191">They can make and receive phone calls outside of your business.</span></span> <span data-ttu-id="5a0ce-192">VoIP 電話、Pc、モバイルデバイスを介して音声通話を発信できます。</span><span class="sxs-lookup"><span data-stu-id="5a0ce-192">They can make voice calls across VoIP phones, PCs, and mobile devices.</span></span> <span data-ttu-id="5a0ce-193">緊急事態が発生した場合は、911に連絡してサポートを受けてください。</span><span class="sxs-lookup"><span data-stu-id="5a0ce-193">And, in case of emergencies, they can call 911 for help.</span></span>

<span data-ttu-id="5a0ce-194">詳細な手順については、「通話プランのセットアップ」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="5a0ce-194">For step-by-step setup instructions, see Set up Calling Plans.</span></span>

### <a name="set-up-skype-meeting-broadcast"></a><span data-ttu-id="5a0ce-195">Skype 会議ブロードキャストをセットアップする</span><span class="sxs-lookup"><span data-stu-id="5a0ce-195">Set up Skype Meeting Broadcast</span></span>

<span data-ttu-id="5a0ce-196">Skype 会議ブロードキャストは、最大1万人の出席者との会議を作成、主催、ブロードキャストできる機能です。</span><span class="sxs-lookup"><span data-stu-id="5a0ce-196">Skype Meeting Broadcast is a feature that lets you produce, host, and broadcast meetings with up to 10,000 attendees.</span></span> <span data-ttu-id="5a0ce-197">**機能の詳細については、「 [Skype 会議ブロードキャストとは](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)」を参照してください。**</span><span class="sxs-lookup"><span data-stu-id="5a0ce-197">**To learn more about how it works, see [What is a Skype Meeting Broadcast?](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)**</span></span>

<span data-ttu-id="5a0ce-198">次に、Skype 会議ブロードキャストをセットアップする手順の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="5a0ce-198">Here's an overview of the steps to set up Skype Meeting Broadcast:</span></span>

1. <span data-ttu-id="5a0ce-199">一般[法人向け Office 365 のライセンスの割り当てまたは削除](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc): ブロードキャスト会議を**開催**するすべてのユーザーに、 **Skype For Business Online**または**Enterprise プラン**のライセンスを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="5a0ce-199">[Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc): Assign **Skype for Business Online** or **Enterprise Plan** licenses to everyone who is going to **host** a Broadcast meeting.</span></span>

2. <span data-ttu-id="5a0ce-200">[Skype 会議ブロードキャストを有効にする](../set-up-your-network-for-skype-meeting-broadcast/enable-skype-meeting-broadcast.md): 既定では、この機能は有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="5a0ce-200">[Enable Skype Meeting Broadcast](../set-up-your-network-for-skype-meeting-broadcast/enable-skype-meeting-broadcast.md): By default, this feature isn't enabled.</span></span> <span data-ttu-id="5a0ce-201">有効にすると、ユーザーは、組織内の他のユーザーとブロードキャスト会議をホストできるようになります。</span><span class="sxs-lookup"><span data-stu-id="5a0ce-201">After you turn it on, your users will be able to host broadcast meetings with other people in your organization.</span></span>

3. <span data-ttu-id="5a0ce-202">[Skype 会議ブロードキャスト用にネットワーク](../set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast.md)をセットアップする: 組織外の出席者とウェビナーやその他のブロードキャストをホストする場合は、ネットワークを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a0ce-202">[Set up your network for Skype Meeting Broadcast](../set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast.md): If you want to host webinars and other broadcasts with attendees outside of your organization, you need to configure your network.</span></span>

4. <span data-ttu-id="5a0ce-203">Skype[会議ブロードキャストをスケジュール](https://support.office.com/article/c3995bc9-4d32-4f75-a004-3bc5c477e553)して、 [skype 会議ブロードキャストに参加](https://support.office.com/article/14689da0-821d-48d4-9035-ea762de80ebe)します。ブロードキャスト会議が有効になっていることを*https://portal.broadcast.skype.com*確認するには、skype 会議ブロードキャストをスケジュールして、他のユーザーに会議への参加を試みます。</span><span class="sxs-lookup"><span data-stu-id="5a0ce-203">[Schedule a Skype Meeting Broadcast](https://support.office.com/article/c3995bc9-4d32-4f75-a004-3bc5c477e553) and have a [Join a Skype Meeting Broadcast](https://support.office.com/article/14689da0-821d-48d4-9035-ea762de80ebe): Make sure broadcast meetings work by scheduling a Skype Meeting Broadcast at  *https://portal.broadcast.skype.com*  and then having someone try to join the meeting.</span></span>

## <a name="learn-about-network-connectivity-requirements"></a><span data-ttu-id="5a0ce-204">ネットワーク接続要件について</span><span class="sxs-lookup"><span data-stu-id="5a0ce-204">Learn about network connectivity requirements</span></span>
<span data-ttu-id="5a0ce-205"><a name="bkmk_more"> </a></span><span class="sxs-lookup"><span data-stu-id="5a0ce-205"></span></span>

<span data-ttu-id="5a0ce-206">Skype for Business の音声、ビデオ、およびアプリケーション共有の品質は、エンドツーエンドのネットワーク接続の品質に大きく影響されます。</span><span class="sxs-lookup"><span data-stu-id="5a0ce-206">The quality of audio, video, and application sharing in Skype for Business is greatly impacted by the quality of end-to-end network connectivity.</span></span> <span data-ttu-id="5a0ce-207">最適なエクスペリエンスを実現するには、会社のネットワークと Skype for Business Online の間に高品質の接続があることを確認することが重要です。</span><span class="sxs-lookup"><span data-stu-id="5a0ce-207">For an optimal experience, it is important to make sure there is a high-quality connection between your company network and Skype for Business Online.</span></span> <span data-ttu-id="5a0ce-208">ネットワークとチューニングに関する情報については、「 [Skype For Business Online のパフォーマンスのチューニング](https://support.office.com/article/beec23c2-c5d6-4e84-a8af-e82aefca7802)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a0ce-208">For network and tuning information, see [Tune Skype for Business Online performance](https://support.office.com/article/beec23c2-c5d6-4e84-a8af-e82aefca7802).</span></span>

## <a name="all-done-setting-up-getting-started-using-skype-for-business"></a><span data-ttu-id="5a0ce-209">すべての設定が完了しましたか?</span><span class="sxs-lookup"><span data-stu-id="5a0ce-209">All done setting up?</span></span> <span data-ttu-id="5a0ce-210">Skype for Business の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="5a0ce-210">Getting started using Skype for Business</span></span>
<span data-ttu-id="5a0ce-211"><a name="bkmk_more"> </a></span><span class="sxs-lookup"><span data-stu-id="5a0ce-211"></span></span>

<span data-ttu-id="5a0ce-212">[Skype For business のトレーニング](https://support.office.com/article/8a3491a3-c095-4718-80cf-cbbe4afe4eba): このトレーニングトピックの一覧を確認して、すぐに使い始めることができます。</span><span class="sxs-lookup"><span data-stu-id="5a0ce-212">[Skype for Business training](https://support.office.com/article/8a3491a3-c095-4718-80cf-cbbe4afe4eba): Check out this list of training topics to help you get started quickly!</span></span>

[<span data-ttu-id="5a0ce-213">Skype for Business 電話会議を開始する</span><span class="sxs-lookup"><span data-stu-id="5a0ce-213">Start a Skype for Business conference call</span></span>](https://support.office.com/article/8dc8ac52-91ac-4db9-8672-11551fdaf997)

[<span data-ttu-id="5a0ce-214">Skype for Business のビデオデバイスオプションを設定する</span><span class="sxs-lookup"><span data-stu-id="5a0ce-214">Set Video Device options in Skype for Business</span></span>](https://support.office.com/article/d09017c0-deba-4f6c-a122-9eca6604f50c)

[<span data-ttu-id="5a0ce-215">Skype for Business を使ってビデオ通話の発信と受信を行う</span><span class="sxs-lookup"><span data-stu-id="5a0ce-215">Make and receive a video call using Skype for Business</span></span>](https://support.office.com/article/abf62493-670f-4b0d-b2cf-fe03b49caf42)

[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]

## <a name="related-topics"></a><span data-ttu-id="5a0ce-216">関連トピック</span><span class="sxs-lookup"><span data-stu-id="5a0ce-216">Related topics</span></span>
<span data-ttu-id="5a0ce-217"><a name="bkmk_more"> </a></span><span class="sxs-lookup"><span data-stu-id="5a0ce-217"></span></span>

[<span data-ttu-id="5a0ce-218">Skype for Business Server と Skype for Business Online 間のハイブリッド接続を計画する</span><span class="sxs-lookup"><span data-stu-id="5a0ce-218">Plan hybrid connectivity between Skype for Business Server and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/p/?linkid=400791)



