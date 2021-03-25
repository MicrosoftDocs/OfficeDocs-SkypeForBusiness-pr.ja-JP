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
f1.keywords:
- CSH
ms.custom:
- Setup
- Alchemy
- LIL_Placement
- O365E_SkypeforBusinessON
- O365M_SkypeforBusinessON
- O365P_SkypeforBusinessON
description: 'Skype for Business をインストールするために組織のドメイン、ユーザー、IM、プレゼンスを設定する方法について学習します。 また、電話会議、電話システムと通話プラン、Skype 会議ブロードキャストを設定する方法も参照してください。 '
ms.openlocfilehash: 0c357c1dbe5b91c06b385562bf31d5f1307bd240
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109963"
---
# <a name="set-up-skype-for-business-online"></a><span data-ttu-id="08b4d-104">Skype for Business Online をセットアップする</span><span class="sxs-lookup"><span data-stu-id="08b4d-104">Set up Skype for Business Online</span></span>

<span data-ttu-id="08b4d-105">Skype for Business をセットアップするには、グローバル管理者権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="08b4d-105">You must have global admin permissions to set up Skype for Business.</span></span> <span data-ttu-id="08b4d-106">Web の一部へのアクセスを制限するファイアウォールまたはプロキシ サーバーがある場合は [、Skype](https://go.microsoft.com/fwlink/?linkid=391089) for Business をセットアップするために Microsoft パートナーを採用する方法を検討してください。</span><span class="sxs-lookup"><span data-stu-id="08b4d-106">If you have a firewall or proxy server that restricts access to parts of the web, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to set up Skype for Business for you.</span></span>

## <a name="setting-up-skype"></a><span data-ttu-id="08b4d-107">Skype のセットアップ</span><span class="sxs-lookup"><span data-stu-id="08b4d-107">Setting up Skype</span></span>

<span data-ttu-id="08b4d-108">Microsoft 365 または Office 365 サブスクリプションを使用して Skype をセットアップする方法をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="08b4d-108">Looks like you need help setting up Skype with your Microsoft 365 or Office 365 subscription.</span></span> <span data-ttu-id="08b4d-109">この記事の手順に従って、セットアップを完了できます。</span><span class="sxs-lookup"><span data-stu-id="08b4d-109">You can follow the steps in this article to get your setup completed.</span></span>

## <a name="1-plan-for-skype-for-business"></a><span data-ttu-id="08b4d-110">1. Skype for Business のプラン</span><span class="sxs-lookup"><span data-stu-id="08b4d-110">1. Plan for Skype for Business</span></span>

<span data-ttu-id="08b4d-111">**[Microsoft 365 Business Premium Standard](https://products.office.com/business/office-365-business-premium)** または Business **Essentials** をお持ちである場合は、Skype for Business を使用して、サブスクリプションを利用している他のユーザーにオンライン通話を行います。</span><span class="sxs-lookup"><span data-stu-id="08b4d-111">If you have **[Microsoft 365 Business Premium Standard](https://products.office.com/business/office-365-business-premium)** or **Business Essentials**, you can use Skype for Business to make online calls to other people in your business who are on your subscription.</span></span> <span data-ttu-id="08b4d-112">たとえば、ビジネスに 10 人のユーザーがいて、IM 会議やオンライン会議で [Skype for Business](https://support.office.com/article/cc05afa6-1894-4a82-9dd9-6222061f50fd) を使い始め、Skype for [Business](https://support.office.com/article/2eed8424-581a-4497-b505-c08c152e5851) を使った会議は、以下の手順 2 ~ 6 を実行した後で開始できます。</span><span class="sxs-lookup"><span data-stu-id="08b4d-112">For example, if your business has 10 people, you'll be able to [Start using Skype for Business for IM and online meetings](https://support.office.com/article/cc05afa6-1894-4a82-9dd9-6222061f50fd) each other, and [Meetings with Skype for Business](https://support.office.com/article/2eed8424-581a-4497-b505-c08c152e5851) using Skype for Business after performing the steps 2-6 below.</span></span> <span data-ttu-id="08b4d-113">また [、Outlook で Skype for Business 会議をオンライン](https://support.office.com/article/b8305620-d16e-4667-989d-4a977aad6556#bkmk_OWA) 会議に設定できます。</span><span class="sxs-lookup"><span data-stu-id="08b4d-113">And you can [Set up a Skype for Business meeting in Outlook](https://support.office.com/article/b8305620-d16e-4667-989d-4a977aad6556#bkmk_OWA) to online meetings, too!</span></span>

<span data-ttu-id="08b4d-114">Skype for Business を使用して、社外のユーザーとの通話の送受信 *を* 行う場合:</span><span class="sxs-lookup"><span data-stu-id="08b4d-114">If you want to use Skype for Business to make and receive **calls** from people *external*  to your business:</span></span>

- <span data-ttu-id="08b4d-115">**オプション 1。無料の [Skype アプリ](https://www.skype.com/)** を使用します。</span><span class="sxs-lookup"><span data-stu-id="08b4d-115">**Option 1. Use the free [Skype app](https://www.skype.com/)**.</span></span> <span data-ttu-id="08b4d-116">小規模な企業 (1 ~ 2 人など) の場合は、Skype アプリを使う方が良い方法です。</span><span class="sxs-lookup"><span data-stu-id="08b4d-116">If you have a very small business (for example, 1-2 people), using the Skype app is the better way to go.</span></span> <span data-ttu-id="08b4d-117">国内通話と国際通話で利用する場合は、より安価な手段となります。</span><span class="sxs-lookup"><span data-stu-id="08b4d-117">It's less expensive to use for domestic and international calls.</span></span> <span data-ttu-id="08b4d-118">電話会議を開催し、ビデオ通話を行い、プレゼンテーション用にデスクトップを共有することができます。</span><span class="sxs-lookup"><span data-stu-id="08b4d-118">You can still hold conference calls, make video calls, and share your desktop for presentations.</span></span> <span data-ttu-id="08b4d-119">[料金と支払オプションを確認](https://secure.skype.com/en/calling-rates?wt.mc_id=legacy&amp;expo365=bundled)してください。</span><span class="sxs-lookup"><span data-stu-id="08b4d-119">[Check out the rates and payment options](https://secure.skype.com/en/calling-rates?wt.mc_id=legacy&amp;expo365=bundled).</span></span>

- <span data-ttu-id="08b4d-120">**オプション 2。プランをアップグレードし、365** 用の電話システムと通話Officeします。</span><span class="sxs-lookup"><span data-stu-id="08b4d-120">**Option 2. Upgrade your plan, and buy the Phone System and a Calling Plan for Office 365**.</span></span> <span data-ttu-id="08b4d-121">このコストを確認し、切り替える最も簡単な方法は、ビジネス製品のサポートへのお問い合わせ [-](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) 管理者向けヘルプを使用して、すべてを実行させる方法です。</span><span class="sxs-lookup"><span data-stu-id="08b4d-121">The easiest way to find out how much this costs, and then make the switch, is to [Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) and have them do everything for you.</span></span>

<span data-ttu-id="08b4d-122">詳細については、「一Office [365 のセットアップを計画する」を参照してください](https://support.office.com/article/eb926624-018b-4486-bf11-5fba6ee4d645#bkmk_skype)。</span><span class="sxs-lookup"><span data-stu-id="08b4d-122">To learn more, see [Plan your setup of Office 365 for business](https://support.office.com/article/eb926624-018b-4486-bf11-5fba6ee4d645#bkmk_skype).</span></span>

## <a name="2-sign-in-to-office-365"></a><span data-ttu-id="08b4d-123">2. Office 365 にサインインする</span><span class="sxs-lookup"><span data-stu-id="08b4d-123">2. Sign in to Office 365</span></span>
<span data-ttu-id="08b4d-124"><a name="bkmk_signin"> </a></span><span class="sxs-lookup"><span data-stu-id="08b4d-124"><a name="bkmk_signin"> </a></span></span>

<span data-ttu-id="08b4d-125">Skype for Business Online は、365 Officeサービスの一部です。</span><span class="sxs-lookup"><span data-stu-id="08b4d-125">Skype for Business Online is part of the Office 365 suite of services.</span></span> <span data-ttu-id="08b4d-126">Skype for Business Online をセットアップするには、365 から Officeする必要があります。</span><span class="sxs-lookup"><span data-stu-id="08b4d-126">To set up Skype for Business Online, you need to sign in to Office 365.</span></span> <span data-ttu-id="08b4d-127">この操作を行うには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="08b4d-127">Here's how you do that:</span></span>

1. <span data-ttu-id="08b4d-128">Microsoft 365 または Office 365 のユーザー ID を見<em>rob@fourthcoffee.com。</em></span><span class="sxs-lookup"><span data-stu-id="08b4d-128">Locate your Microsoft 365 or Office 365 user ID (for example,  <em>rob@fourthcoffee.com</em>  ).</span></span> <span data-ttu-id="08b4d-129">Skype for Business Online の購入時に作成した Microsoft 365 または Office 365 ユーザー ID を含むメールを Microsoft Online Services チームから受け取った。</span><span class="sxs-lookup"><span data-stu-id="08b4d-129">You received an email from the Microsoft Online Services Team that contains the Microsoft 365 or Office 365 user ID that you created when you purchased Skype for Business Online.</span></span> <span data-ttu-id="08b4d-130">メールは次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="08b4d-130">The mail looks something like this:</span></span>

    ![Skype for Business Online にサインアップした後に受信したウェルカム メールの例。](../images/977c5c96-29c5-40c0-a4c4-1ba66ba3a1fb.png)

2. <span data-ttu-id="08b4d-133">管理センターに [サインインし](https://admin.microsoft.com) 、Microsoft 365 または Office 365 のユーザー ID とパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="08b4d-133">Sign in to the [admin center](https://admin.microsoft.com) and enter your Microsoft 365 or Office 365 user ID and password.</span></span> 

## <a name="3-set-up-your-domain-and-users"></a><span data-ttu-id="08b4d-134">3. ドメインとユーザーをセットアップする</span><span class="sxs-lookup"><span data-stu-id="08b4d-134">3. Set up your domain and users</span></span>
<span data-ttu-id="08b4d-135"><a name="bkmk_users"> </a></span><span class="sxs-lookup"><span data-stu-id="08b4d-135"><a name="bkmk_users"> </a></span></span>

<span data-ttu-id="08b4d-136">Office 365 にサインインしたので、Skype for Business Online を使用するドメインと組織内のユーザーを設定できます。</span><span class="sxs-lookup"><span data-stu-id="08b4d-136">Now that you're signed in to Office 365, you can set up your domain and people in your organization to use Skype for Business Online.</span></span>

1. <span data-ttu-id="08b4d-137">[Office 365](https://support.office.com/article/6383f56d-3d09-4dcb-9b41-b5f5a5efd611)にドメインとユーザーを追加する: Office 365 セットアップ ウィザードを使用して、fourthcoffee.com 365 でカスタム ドメイン *(fourthcoffee.com* など) をセットアップOfficeします。</span><span class="sxs-lookup"><span data-stu-id="08b4d-137">[Add a domain and users to Office 365](https://support.office.com/article/6383f56d-3d09-4dcb-9b41-b5f5a5efd611): Use the Office 365 setup wizard to set up your custom domain (such as *fourthcoffee.com*) with Office 365.</span></span> <span data-ttu-id="08b4d-138">**既定では、Office 365 セットアップ ウィザードには、Skype for Business Online のセットアップと Skype for Business ユーザー ID の作成が含まれます。**</span><span class="sxs-lookup"><span data-stu-id="08b4d-138">**By default, the Office 365 setup wizard includes setting up Skype for Business Online and creating your Skype for Business user IDs.**</span></span> <span data-ttu-id="08b4d-139">ウィザードを使用して Office 365 のドメインをセットアップした場合は、この手順を完了します。</span><span class="sxs-lookup"><span data-stu-id="08b4d-139">If you already used the wizard to set up your domain for Office 365, then you've completed this step.</span></span>

2. <span data-ttu-id="08b4d-140">[ドメインと DNS](https://support.office.com/article/2b54e1b0-47a7-4018-a1e4-c2b924e7c5a0)接続を確認する: ドメインのトラブルシューティング ツールであるツールを使用して、ドメインと DNS の設定が正しいか確認します。</span><span class="sxs-lookup"><span data-stu-id="08b4d-140">[Check your domain and DNS connections](https://support.office.com/article/2b54e1b0-47a7-4018-a1e4-c2b924e7c5a0): Use our tool - the domains troubleshooter - to check that your domain and DNS settings are correct.</span></span> <span data-ttu-id="08b4d-141">今後の問題のソースとして DNS 設定を排除できるので、この作業は後でセットアップの問題を把握する上で大きな助けになります。</span><span class="sxs-lookup"><span data-stu-id="08b4d-141">Doing this now will go a long way to helping figure out any setup issues later since you'll be able to eliminate DNS settings as the source of future issues.</span></span>

3. <span data-ttu-id="08b4d-142">[Office 365 URL](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2#BKMK_LYO)と IP アドレス範囲を使用する: ほとんどの中小企業は、この手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="08b4d-142">[Office 365 URLs and IP address ranges](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2#BKMK_LYO): Most small businesses don't need to do this step.</span></span> <span data-ttu-id="08b4d-143">**ただし、Web の** 一部へのアクセスを制限するファイアウォールまたはプロキシ サーバーがある場合は、Skype for Business Online エンドポイントへのアクセスを許可するルールを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="08b4d-143">**But if you have a firewall or proxy server that restricts access to parts of the web**, you must create rules to allow access to the Skype for Business Online endpoints.</span></span> <span data-ttu-id="08b4d-144">これは、ファイアウォールとプロキシ サーバーの構成経験があるユーザーが実行する高度な手順です。</span><span class="sxs-lookup"><span data-stu-id="08b4d-144">This is an advanced step best performed by someone experienced with configuring firewalls and proxy servers.</span></span> <span data-ttu-id="08b4d-145">以前にこの設定を行ったことが見当たらない場合は [、Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) パートナーに Skype for Business のセットアップを採用する方法を検討してください。</span><span class="sxs-lookup"><span data-stu-id="08b4d-145">If you haven't done this before, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to set up Skype for Business for you.</span></span>

## <a name="4-set-up-im-and-presence-in-your-organization"></a><span data-ttu-id="08b4d-146">4. 組織内で IM とプレゼンスを設定する</span><span class="sxs-lookup"><span data-stu-id="08b4d-146">4. Set up IM and presence in your organization</span></span>
<span data-ttu-id="08b4d-147"><a name="bkmk_IM"> </a></span><span class="sxs-lookup"><span data-stu-id="08b4d-147"><a name="bkmk_IM"> </a></span></span>

<span data-ttu-id="08b4d-148">インスタント メッセージング (IM) とプレゼンス[(Skype for Business](https://support.office.com/article/fea86e34-60cf-4dd0-bfb2-169a42afd92c)のプレゼンス情報へのアクセスを制御する) は、Skype for Business に含まれる基本的な機能です。</span><span class="sxs-lookup"><span data-stu-id="08b4d-148">Instant Messaging (IM) and presence ([Control access to your presence information in Skype for Business](https://support.office.com/article/fea86e34-60cf-4dd0-bfb2-169a42afd92c)) are basic features included with Skype for Business.</span></span> <span data-ttu-id="08b4d-149">既定では、お客様のビジネスのユーザーは、互いに Skype と IM を使用できます。</span><span class="sxs-lookup"><span data-stu-id="08b4d-149">By default, the people in your business can Skype and IM with each other.</span></span>

1. <span data-ttu-id="08b4d-150">**Skype for Business ユーザーが通信できる他のユーザーを選択します。**</span><span class="sxs-lookup"><span data-stu-id="08b4d-150">**Choose who else your Skype for Business users can communicate with:**</span></span>

   - <span data-ttu-id="08b4d-151">[ユーザーが外部の Skype for Business ユーザーと連絡を取り合うのを許可する](allow-users-to-contact-external-skype-for-business-users.md) お客様と *他*  の企業の両方がシステムを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="08b4d-151">[Allow users to contact external Skype for Business users](allow-users-to-contact-external-skype-for-business-users.md) Both you *and*  the other business will need to configure your systems.</span></span>

     <span data-ttu-id="08b4d-152">**重要**: rob@contosowest.com と ina@contosoeast.com など、ビジネスに 2 つのドメインがある場合は、すべてのユーザーが互いに通信できるよう、この手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="08b4d-152">**IMPORTANT**: If you have two domains in your business, such as rob@contosowest.com and ina@contosoeast.com, you need to do this step so all of your users can communicate with each other.</span></span>

   - <span data-ttu-id="08b4d-153">[Skype for Business ユーザーが社外の Skype 連絡先を](let-skype-for-business-users-add-skype-contacts.md) 追加する</span><span class="sxs-lookup"><span data-stu-id="08b4d-153">[Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md) outside your business</span></span>

2. <span data-ttu-id="08b4d-154">**同僚がオンラインかどうかを確認するユーザーを選択します。** プレゼンス機能では、オンライン状態のユーザーと空き時間情報 (空き時間情報、取り込み中、離れた場所、発表中など) が表示されます。</span><span class="sxs-lookup"><span data-stu-id="08b4d-154">**Choose who sees whether co-workers are online:** The presence feature shows who's online and what their availability is, such as available, busy, away, or presenting.</span></span>

    ![個人メッセージを含むユーザーのオンライン状態の例。](../images/ab6c10b4-6ad5-453c-bf0e-459b977b6e23.png)

    <span data-ttu-id="08b4d-156">ビジネスのすべてのユーザーに対して既定の設定を選択できます。</span><span class="sxs-lookup"><span data-stu-id="08b4d-156">You can choose the default settings for everyone in your business:</span></span>

   - <span data-ttu-id="08b4d-157">組織内のすべてのユーザーにユーザーのオンライン プレゼンスを自動的に表示する</span><span class="sxs-lookup"><span data-stu-id="08b4d-157">Automatically display a person's online presence to everyone in the organization</span></span>

   - <span data-ttu-id="08b4d-158">ユーザーのオンライン プレゼンスを連絡先にのみ表示する</span><span class="sxs-lookup"><span data-stu-id="08b4d-158">Display a person's online presence only to their contacts</span></span>

<span data-ttu-id="08b4d-159">手順については [、「Skype for Business Online でプレゼンスを構成する」を参照してください](configure-presence-in-skype-for-business-online.md)。</span><span class="sxs-lookup"><span data-stu-id="08b4d-159">For instructions, see [Configure presence in Skype for Business Online](configure-presence-in-skype-for-business-online.md).</span></span>

## <a name="5-download-and-install-skype-for-business"></a><span data-ttu-id="08b4d-160">5. Skype for Business をダウンロードしてインストールする</span><span class="sxs-lookup"><span data-stu-id="08b4d-160">5. Download and install Skype for Business</span></span>
<span data-ttu-id="08b4d-161"><a name="bkmk_download"> </a></span><span class="sxs-lookup"><span data-stu-id="08b4d-161"><a name="bkmk_download"> </a></span></span>

<span data-ttu-id="08b4d-162">お使いの PC、Mac、またはモバイル デバイスで Skype for Business を使用するには、お客様と他のユーザーが最初に Skype for Business ダウンロードをデバイスにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="08b4d-162">To use Skype for Business on your PC, Mac, or mobile device, you and other people in your business have to first install the Skype for Business download on your devices.</span></span>

- <span data-ttu-id="08b4d-163">[Skype for Business をインストール](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb)する: Microsoft 365 管理センターからアプリをダウンロードして、PC または Mac にインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="08b4d-163">[Install Skype for Business](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb): Instructions for how to download the app from the Microsoft 365 admin center, and install it on your PC or Mac.</span></span>

- <span data-ttu-id="08b4d-164">[Office 365](deploy-the-skype-for-business-client-in-office-365.md)で Skype for Business クライアントを展開する: 大企業にアプリを展開する手順。</span><span class="sxs-lookup"><span data-stu-id="08b4d-164">[Deploy the Skype for Business client in Office 365](deploy-the-skype-for-business-client-in-office-365.md): Instructions for deploying the app in a large enterprise.</span></span>

- <span data-ttu-id="08b4d-165">[Skype for Business のインストール](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb): Android デバイス、iOS デバイス、Windows Phone で Skype for Business をダウンロード、インストール、サインインします。</span><span class="sxs-lookup"><span data-stu-id="08b4d-165">[Install Skype for Business](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb): Download, install, and sign in to Skype for Business on Android devices, iOS devices, and Windows phones.</span></span>

- <span data-ttu-id="08b4d-166">[携帯電話の](turn-on-or-off-mobile-phone-notifications.md)通知のオンとオフを切り替えます: モバイル デバイスに Skype for Business がインストールされている場合、自分と他のユーザーが受信したインスタント メッセージと見逃したインスタント メッセージに関する通知を受信できます。</span><span class="sxs-lookup"><span data-stu-id="08b4d-166">[Turn on or off mobile phone notifications](turn-on-or-off-mobile-phone-notifications.md): When you have Skype for Business installed on a mobile device, you and others in your business can receive alerts about incoming and missed instant messages.</span></span>

## <a name="6-test-to-make-sure-everything-is-working"></a><span data-ttu-id="08b4d-167">6. すべての機能が動作しているテストを行う</span><span class="sxs-lookup"><span data-stu-id="08b4d-167">6. Test to make sure everything is working</span></span>
<span data-ttu-id="08b4d-168"><a name="bkmk_test"> </a></span><span class="sxs-lookup"><span data-stu-id="08b4d-168"><a name="bkmk_test"> </a></span></span>

<span data-ttu-id="08b4d-169">まず、自分と他のユーザーがビデオ: Skype for Business にサインインおよびサインアウトできるかどうか [をテストします](https://support.office.com/article/8abed4b3-ac48-493e-9d76-0e10140e9451)。</span><span class="sxs-lookup"><span data-stu-id="08b4d-169">First, test whether you and others in your business can [Video: Sign in and out of Skype for Business](https://support.office.com/article/8abed4b3-ac48-493e-9d76-0e10140e9451).</span></span> <span data-ttu-id="08b4d-170">IM で互いに IM をやり取りし、互いにプレゼンスを確認し、簡単な会議を試す。</span><span class="sxs-lookup"><span data-stu-id="08b4d-170">Check that you can IM each other, see each other's presence, and try a quick meeting.</span></span>

<span data-ttu-id="08b4d-171">問題がある場合</span><span class="sxs-lookup"><span data-stu-id="08b4d-171">Problems?</span></span> <span data-ttu-id="08b4d-172">以下の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="08b4d-172">Do the following:</span></span>

- <span data-ttu-id="08b4d-173">[Skype for Business へのサインインでヘルプが必要ですか?](https://support.office.com/article/448b8ea7-5b33-444a-afd4-175fc9930d05) サインインに関する一般的な問題について確認してください。</span><span class="sxs-lookup"><span data-stu-id="08b4d-173">[Need help signing in to Skype for Business?](https://support.office.com/article/448b8ea7-5b33-444a-afd4-175fc9930d05) of common sign-in problems.</span></span>

- <span data-ttu-id="08b4d-174">[ビジネス製品のサポートへのお問い合わせ - 管理者向けヘルプ](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)。</span><span class="sxs-lookup"><span data-stu-id="08b4d-174">[Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span> <span data-ttu-id="08b4d-175">お手伝いします!</span><span class="sxs-lookup"><span data-stu-id="08b4d-175">We're here to help!</span></span>

## <a name="do-you-want-to-set-up-other-available-features"></a><span data-ttu-id="08b4d-176">その他の利用可能な機能を設定しますか?</span><span class="sxs-lookup"><span data-stu-id="08b4d-176">Do you want to set up other available features?</span></span>
<span data-ttu-id="08b4d-177"><a name="bkmk_more"> </a></span><span class="sxs-lookup"><span data-stu-id="08b4d-177"><a name="bkmk_more"> </a></span></span>

<span data-ttu-id="08b4d-178">その他の機能を設定する前に、その機能のライセンスを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="08b4d-178">Before setting up more features, make sure you have licenses for them.</span></span> [<span data-ttu-id="08b4d-179">Skype for Business と Microsoft Teams のアドオン ライセンス</span><span class="sxs-lookup"><span data-stu-id="08b4d-179">Skype for Business and Microsoft Teams add-on licensing</span></span>](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)

### <a name="set-up-audio-conferencing"></a><span data-ttu-id="08b4d-180">電話会議をセットアップする</span><span class="sxs-lookup"><span data-stu-id="08b4d-180">Set up Audio Conferencing</span></span>

<span data-ttu-id="08b4d-181">組織内のユーザーは電話を使って会議に参加する必要が生じることがあります。</span><span class="sxs-lookup"><span data-stu-id="08b4d-181">Sometimes people in your organization will need to use a phone to call into a meeting.</span></span> <span data-ttu-id="08b4d-182">Skype for Business には、このような状況専用の電話会議機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="08b4d-182">Skype for Business includes the Audio Conferencing feature for just this situation!</span></span> <span data-ttu-id="08b4d-183">参加者は、モバイル デバイスや PC で Skype for Business アプリを使用する代わりに、電話を使って Skype for Business 会議にコールインできます。</span><span class="sxs-lookup"><span data-stu-id="08b4d-183">People can call into Skype for Business meetings using a phone, instead of using the Skype for Business app on a mobile device or PC.</span></span>

### <a name="set-up-phone-system-and-the-calling-plans-in-office-365"></a><span data-ttu-id="08b4d-184">Office 365 で電話システムと通話プランをセットアップする</span><span class="sxs-lookup"><span data-stu-id="08b4d-184">Set up Phone System and the Calling plans in Office 365</span></span>

<span data-ttu-id="08b4d-185">Office 365 の電話システム機能は、業務用の電話システムを提供します。</span><span class="sxs-lookup"><span data-stu-id="08b4d-185">The Phone System feature in Office 365 gives you a phone system for your business.</span></span> <span data-ttu-id="08b4d-186">組織内の他の Skype for Business ユーザーへの通話は無料で、従業員は互いにボイスメールを受け取り、外部の発信者も受け取ります。</span><span class="sxs-lookup"><span data-stu-id="08b4d-186">Calls to other Skype for Business people in your organization are free, and your employees can receive voicemail from each other and outside callers.</span></span> <span data-ttu-id="08b4d-187">電話システムでは次の機能を利用できます。</span><span class="sxs-lookup"><span data-stu-id="08b4d-187">Here's what you get with Phone System.</span></span>

<span data-ttu-id="08b4d-188">通話プラン サービスを追加すると、従業員は Skype for Business の主要電話番号を取得します。</span><span class="sxs-lookup"><span data-stu-id="08b4d-188">When you add the Calling Plan service, your employees get a primary phone number in Skype for Business.</span></span> <span data-ttu-id="08b4d-189">社外からの電話の送受信が可能です。</span><span class="sxs-lookup"><span data-stu-id="08b4d-189">They can make and receive phone calls outside of your business.</span></span> <span data-ttu-id="08b4d-190">VoIP 電話、PC、モバイル デバイス間で音声通話を行えます。</span><span class="sxs-lookup"><span data-stu-id="08b4d-190">They can make voice calls across VoIP phones, PCs, and mobile devices.</span></span> <span data-ttu-id="08b4d-191">また、緊急時に 911 に電話でサポートを受け取る場合があります。</span><span class="sxs-lookup"><span data-stu-id="08b4d-191">And, in case of emergencies, they can call 911 for help.</span></span>

<span data-ttu-id="08b4d-192">詳しいセットアップ手順については、「通話プランをセットアップする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="08b4d-192">For step-by-step setup instructions, see Set up Calling Plans.</span></span>

### <a name="set-up-skype-meeting-broadcast"></a><span data-ttu-id="08b4d-193">Skype 会議ブロードキャストをセットアップする</span><span class="sxs-lookup"><span data-stu-id="08b4d-193">Set up Skype Meeting Broadcast</span></span>

<span data-ttu-id="08b4d-194">Skype 会議ブロードキャストは、最大 10,000 人の出席者を含む会議を作成、ホスト、ブロードキャストできる機能です。</span><span class="sxs-lookup"><span data-stu-id="08b4d-194">Skype Meeting Broadcast is a feature that lets you produce, host, and broadcast meetings with up to 10,000 attendees.</span></span> <span data-ttu-id="08b4d-195">**機能の詳細については、「Skype 会議ブロードキャストとは [」を参照してください。](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)**</span><span class="sxs-lookup"><span data-stu-id="08b4d-195">**To learn more about how it works, see [What is a Skype Meeting Broadcast?](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)**</span></span>

<span data-ttu-id="08b4d-196">Skype 会議ブロードキャストをセットアップする手順の概要を次に示します。</span><span class="sxs-lookup"><span data-stu-id="08b4d-196">Here's an overview of the steps to set up Skype Meeting Broadcast:</span></span>

1. <span data-ttu-id="08b4d-197">[Office 365 for Business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)のライセンスの割り当てまたは削除: ブロードキャスト会議を開催する予定のユーザー全員に Skype for **Business Online** または **エンタープライズ** プランのライセンスを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="08b4d-197">[Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc): Assign **Skype for Business Online** or **Enterprise Plan** licenses to everyone who is going to **host** a Broadcast meeting.</span></span>

2. <span data-ttu-id="08b4d-198">[Skype 会議ブロードキャストを有効](../set-up-your-network-for-skype-meeting-broadcast/enable-skype-meeting-broadcast.md)にする: 既定では、この機能は有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="08b4d-198">[Enable Skype Meeting Broadcast](../set-up-your-network-for-skype-meeting-broadcast/enable-skype-meeting-broadcast.md): By default, this feature isn't enabled.</span></span> <span data-ttu-id="08b4d-199">有効にした後、ユーザーは組織内の他のユーザーとのブロードキャスト会議を開催できます。</span><span class="sxs-lookup"><span data-stu-id="08b4d-199">After you turn it on, your users will be able to host broadcast meetings with other people in your organization.</span></span>

3. <span data-ttu-id="08b4d-200">[Skype 会議ブロードキャスト](../set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast.md)用にネットワークをセットアップする: 組織外の出席者とウェビナーや他のブロードキャストを開催する場合は、ネットワークを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="08b4d-200">[Set up your network for Skype Meeting Broadcast](../set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast.md): If you want to host webinars and other broadcasts with attendees outside of your organization, you need to configure your network.</span></span>

4. <span data-ttu-id="08b4d-201">[Skype 会議ブロードキャストを](https://support.office.com/article/c3995bc9-4d32-4f75-a004-3bc5c477e553) スケジュールし [、Skype](https://support.office.com/article/14689da0-821d-48d4-9035-ea762de80ebe)会議ブロードキャストに参加する: Skype 会議ブロードキャストをスケジュールして、他のユーザーが会議に参加しようとして、ブロードキャスト会議が機能します  *https://portal.broadcast.skype.com*  。</span><span class="sxs-lookup"><span data-stu-id="08b4d-201">[Schedule a Skype Meeting Broadcast](https://support.office.com/article/c3995bc9-4d32-4f75-a004-3bc5c477e553) and have a [Join a Skype Meeting Broadcast](https://support.office.com/article/14689da0-821d-48d4-9035-ea762de80ebe): Make sure broadcast meetings work by scheduling a Skype Meeting Broadcast at  *https://portal.broadcast.skype.com*  and then having someone try to join the meeting.</span></span>

## <a name="learn-about-network-connectivity-requirements"></a><span data-ttu-id="08b4d-202">ネットワーク接続の要件について</span><span class="sxs-lookup"><span data-stu-id="08b4d-202">Learn about network connectivity requirements</span></span>
<span data-ttu-id="08b4d-203"><a name="bkmk_more"> </a></span><span class="sxs-lookup"><span data-stu-id="08b4d-203"><a name="bkmk_more"> </a></span></span>

<span data-ttu-id="08b4d-204">Skype for Business でのオーディオ、ビデオ、アプリケーション共有の品質は、エンドツーエンドのネットワーク接続の品質に大きく影響されます。</span><span class="sxs-lookup"><span data-stu-id="08b4d-204">The quality of audio, video, and application sharing in Skype for Business is greatly impacted by the quality of end-to-end network connectivity.</span></span> <span data-ttu-id="08b4d-205">最適なエクスペリエンスを得る場合は、会社のネットワークと Skype for Business Online の間に高品質の接続を確立することが重要です。</span><span class="sxs-lookup"><span data-stu-id="08b4d-205">For an optimal experience, it is important to make sure there is a high-quality connection between your company network and Skype for Business Online.</span></span> <span data-ttu-id="08b4d-206">ネットワークとチューニングに関する情報については、「Skype for Business Online のパフォーマンス [をチューニングする」を参照してください](https://support.office.com/article/beec23c2-c5d6-4e84-a8af-e82aefca7802)。</span><span class="sxs-lookup"><span data-stu-id="08b4d-206">For network and tuning information, see [Tune Skype for Business Online performance](https://support.office.com/article/beec23c2-c5d6-4e84-a8af-e82aefca7802).</span></span>

## <a name="all-done-setting-up-getting-started-using-skype-for-business"></a><span data-ttu-id="08b4d-207">セットアップが完了しましたか?</span><span class="sxs-lookup"><span data-stu-id="08b4d-207">All done setting up?</span></span> <span data-ttu-id="08b4d-208">Skype for Business の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="08b4d-208">Getting started using Skype for Business</span></span>
<span data-ttu-id="08b4d-209"><a name="bkmk_more"> </a></span><span class="sxs-lookup"><span data-stu-id="08b4d-209"><a name="bkmk_more"> </a></span></span>

<span data-ttu-id="08b4d-210">[Skype for Business のトレーニング](https://support.office.com/article/8a3491a3-c095-4718-80cf-cbbe4afe4eba): すぐに始めるのに役立つトレーニング トピックの一覧をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="08b4d-210">[Skype for Business training](https://support.office.com/article/8a3491a3-c095-4718-80cf-cbbe4afe4eba): Check out this list of training topics to help you get started quickly!</span></span>

[<span data-ttu-id="08b4d-211">Skype for Business 電話会議を開始する</span><span class="sxs-lookup"><span data-stu-id="08b4d-211">Start a Skype for Business conference call</span></span>](https://support.office.com/article/8dc8ac52-91ac-4db9-8672-11551fdaf997)

[<span data-ttu-id="08b4d-212">Skype for Business のビデオ デバイス オプションを設定する</span><span class="sxs-lookup"><span data-stu-id="08b4d-212">Set Video Device options in Skype for Business</span></span>](https://support.office.com/article/d09017c0-deba-4f6c-a122-9eca6604f50c)

[<span data-ttu-id="08b4d-213">Skype for Business を使用してビデオ通話を送受信する</span><span class="sxs-lookup"><span data-stu-id="08b4d-213">Make and receive a video call using Skype for Business</span></span>](https://support.office.com/article/abf62493-670f-4b0d-b2cf-fe03b49caf42)

[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]

## <a name="related-topics"></a><span data-ttu-id="08b4d-214">関連項目</span><span class="sxs-lookup"><span data-stu-id="08b4d-214">Related topics</span></span>
<span data-ttu-id="08b4d-215"><a name="bkmk_more"> </a></span><span class="sxs-lookup"><span data-stu-id="08b4d-215"><a name="bkmk_more"> </a></span></span>

[<span data-ttu-id="08b4d-216">Skype for Business Server と Skype for Business Online 間のハイブリッド接続を計画する</span><span class="sxs-lookup"><span data-stu-id="08b4d-216">Plan hybrid connectivity between Skype for Business Server and Skype for Business Online</span></span>](../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)