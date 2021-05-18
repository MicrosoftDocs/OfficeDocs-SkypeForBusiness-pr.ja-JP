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
description: '組織のドメイン、ユーザー、IM、プレゼンスをセットアップして、組織がドメインをインストールSkype for Business。 また、電話会議、通話プランと通話プラン電話システム会議ブロードキャストを設定するSkypeを参照してください。 '
ms.openlocfilehash: fcca1a3181ca0f5753fd53811290d710e8030064
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52239809"
---
# <a name="set-up-skype-for-business-online"></a><span data-ttu-id="2cb7b-104">Skype for Business Online をセットアップする</span><span class="sxs-lookup"><span data-stu-id="2cb7b-104">Set up Skype for Business Online</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="2cb7b-105">アカウントを設定するには、グローバル管理者のアクセス許可がSkype for Business。</span><span class="sxs-lookup"><span data-stu-id="2cb7b-105">You must have global admin permissions to set up Skype for Business.</span></span> <span data-ttu-id="2cb7b-106">Web の一部へのアクセスを制限するファイアウォールまたはプロキシ サーバーがある場合は[、Microsoft](https://go.microsoft.com/fwlink/?linkid=391089)パートナーに問い合Skype for Businessを検討してください。</span><span class="sxs-lookup"><span data-stu-id="2cb7b-106">If you have a firewall or proxy server that restricts access to parts of the web, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to set up Skype for Business for you.</span></span>

## <a name="setting-up-skype"></a><span data-ttu-id="2cb7b-107">設定Skype</span><span class="sxs-lookup"><span data-stu-id="2cb7b-107">Setting up Skype</span></span>

<span data-ttu-id="2cb7b-108">サブスクリプションまたはサブスクリプションを使用してSkypeを設定Microsoft 365必要Office 365します。</span><span class="sxs-lookup"><span data-stu-id="2cb7b-108">Looks like you need help setting up Skype with your Microsoft 365 or Office 365 subscription.</span></span> <span data-ttu-id="2cb7b-109">この記事の手順に従って、セットアップを完了できます。</span><span class="sxs-lookup"><span data-stu-id="2cb7b-109">You can follow the steps in this article to get your setup completed.</span></span>

## <a name="1-plan-for-skype-for-business"></a><span data-ttu-id="2cb7b-110">1. プランのSkype for Business</span><span class="sxs-lookup"><span data-stu-id="2cb7b-110">1. Plan for Skype for Business</span></span>

<span data-ttu-id="2cb7b-111">Standard または **Business Essentials** **[Microsoft 365 Business Premiumを](https://products.office.com/business/office-365-business-premium)** 使用している場合は、Skype for Business を使用して、サブスクリプションを利用している企業内の他のユーザーにオンライン通話を行います。</span><span class="sxs-lookup"><span data-stu-id="2cb7b-111">If you have **[Microsoft 365 Business Premium Standard](https://products.office.com/business/office-365-business-premium)** or **Business Essentials**, you can use Skype for Business to make online calls to other people in your business who are on your subscription.</span></span> <span data-ttu-id="2cb7b-112">たとえば、ビジネスに 10 人の人がいて[、IM](https://support.office.com/article/cc05afa6-1894-4a82-9dd9-6222061f50fd)会議とオンライン会議に Skype for Business を使い始め、次の手順 2 から 6 を実行した後に Skype for Business を使用して[Skype for Business](https://support.office.com/article/2eed8424-581a-4497-b505-c08c152e5851)で会議を開始できます。</span><span class="sxs-lookup"><span data-stu-id="2cb7b-112">For example, if your business has 10 people, you'll be able to [Start using Skype for Business for IM and online meetings](https://support.office.com/article/cc05afa6-1894-4a82-9dd9-6222061f50fd) each other, and [Meetings with Skype for Business](https://support.office.com/article/2eed8424-581a-4497-b505-c08c152e5851) using Skype for Business after performing the steps 2-6 below.</span></span> <span data-ttu-id="2cb7b-113">また、[オンライン会議Skype for Business会議Outlook](https://support.office.com/article/b8305620-d16e-4667-989d-4a977aad6556#bkmk_OWA)会議を設定できます。</span><span class="sxs-lookup"><span data-stu-id="2cb7b-113">And you can [Set up a Skype for Business meeting in Outlook](https://support.office.com/article/b8305620-d16e-4667-989d-4a977aad6556#bkmk_OWA) to online meetings, too!</span></span>

<span data-ttu-id="2cb7b-114">このサービスを使用してSkype for Business外部のユーザーとの通話を送受信する場合は、次 *の方法を* 実行します。</span><span class="sxs-lookup"><span data-stu-id="2cb7b-114">If you want to use Skype for Business to make and receive **calls** from people *external*  to your business:</span></span>

- <span data-ttu-id="2cb7b-115">**オプション 1。無料の [Skype アプリ](https://www.skype.com/)** を使用します。</span><span class="sxs-lookup"><span data-stu-id="2cb7b-115">**Option 1. Use the free [Skype app](https://www.skype.com/)**.</span></span> <span data-ttu-id="2cb7b-116">小規模な企業 (1 ~ 2 人など) がある場合は、Skype アプリを使用する方が便利です。</span><span class="sxs-lookup"><span data-stu-id="2cb7b-116">If you have a very small business (for example, 1-2 people), using the Skype app is the better way to go.</span></span> <span data-ttu-id="2cb7b-117">国内通話と国際通話で利用する場合は、より安価な手段となります。</span><span class="sxs-lookup"><span data-stu-id="2cb7b-117">It's less expensive to use for domestic and international calls.</span></span> <span data-ttu-id="2cb7b-118">電話会議を開催し、ビデオ通話を行い、プレゼンテーション用にデスクトップを共有することができます。</span><span class="sxs-lookup"><span data-stu-id="2cb7b-118">You can still hold conference calls, make video calls, and share your desktop for presentations.</span></span> <span data-ttu-id="2cb7b-119">[料金と支払オプションを確認](https://secure.skype.com/en/calling-rates?wt.mc_id=legacy&amp;expo365=bundled)してください。</span><span class="sxs-lookup"><span data-stu-id="2cb7b-119">[Check out the rates and payment options](https://secure.skype.com/en/calling-rates?wt.mc_id=legacy&amp;expo365=bundled).</span></span>

- <span data-ttu-id="2cb7b-120">**オプション 2.プランをアップグレードし、プランと 電話システム 通話プランを購入Office 365。**</span><span class="sxs-lookup"><span data-stu-id="2cb7b-120">**Option 2. Upgrade your plan, and buy the Phone System and a Calling Plan for Office 365**.</span></span> <span data-ttu-id="2cb7b-121">このコストを確認し、切り替える最も簡単な方法は、ビジネス製品のサポートに問い合わせ [- 管理者](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) 向けヘルプを使用して、すべての操作を行う方法です。</span><span class="sxs-lookup"><span data-stu-id="2cb7b-121">The easiest way to find out how much this costs, and then make the switch, is to [Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) and have them do everything for you.</span></span>

<span data-ttu-id="2cb7b-122">詳細については、「一Office 365[のセットアップを計画する」を参照してください](https://support.office.com/article/eb926624-018b-4486-bf11-5fba6ee4d645#bkmk_skype)。</span><span class="sxs-lookup"><span data-stu-id="2cb7b-122">To learn more, see [Plan your setup of Office 365 for business](https://support.office.com/article/eb926624-018b-4486-bf11-5fba6ee4d645#bkmk_skype).</span></span>

## <a name="2-sign-in-to-office-365"></a><span data-ttu-id="2cb7b-123">2. サインインして Office 365</span><span class="sxs-lookup"><span data-stu-id="2cb7b-123">2. Sign in to Office 365</span></span>
<span data-ttu-id="2cb7b-124"><a name="bkmk_signin"> </a></span><span class="sxs-lookup"><span data-stu-id="2cb7b-124"><a name="bkmk_signin"> </a></span></span>

<span data-ttu-id="2cb7b-125">Skype for Businessオンラインは、サービスのOffice 365の一部です。</span><span class="sxs-lookup"><span data-stu-id="2cb7b-125">Skype for Business Online is part of the Office 365 suite of services.</span></span> <span data-ttu-id="2cb7b-126">Skype for Business Online を設定するには、アカウントにサインインOffice 365。</span><span class="sxs-lookup"><span data-stu-id="2cb7b-126">To set up Skype for Business Online, you need to sign in to Office 365.</span></span> <span data-ttu-id="2cb7b-127">その方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2cb7b-127">Here's how you do that:</span></span>

1. <span data-ttu-id="2cb7b-128">ユーザー ID Microsoft 365またはOffice 365を見つける (例: <em>rob@fourthcoffee.com)。</em></span><span class="sxs-lookup"><span data-stu-id="2cb7b-128">Locate your Microsoft 365 or Office 365 user ID (for example,  <em>rob@fourthcoffee.com</em>  ).</span></span> <span data-ttu-id="2cb7b-129">Microsoft Online Services Online の購入時に作成した Microsoft 365 または Office 365 ユーザー ID を含むメールが Skype for Business されました。</span><span class="sxs-lookup"><span data-stu-id="2cb7b-129">You received an email from the Microsoft Online Services Team that contains the Microsoft 365 or Office 365 user ID that you created when you purchased Skype for Business Online.</span></span> <span data-ttu-id="2cb7b-130">メールは次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="2cb7b-130">The mail looks something like this:</span></span>

    ![Skype for Business Online にサインアップした後に受信したウェルカム メールの例。](../images/977c5c96-29c5-40c0-a4c4-1ba66ba3a1fb.png)

2. <span data-ttu-id="2cb7b-133">管理センターに[サインインし、](https://admin.microsoft.com)ユーザー ID とパスワードMicrosoft 365またはOffice 365を入力します。</span><span class="sxs-lookup"><span data-stu-id="2cb7b-133">Sign in to the [admin center](https://admin.microsoft.com) and enter your Microsoft 365 or Office 365 user ID and password.</span></span> 

## <a name="3-set-up-your-domain-and-users"></a><span data-ttu-id="2cb7b-134">3. ドメインとユーザーを設定する</span><span class="sxs-lookup"><span data-stu-id="2cb7b-134">3. Set up your domain and users</span></span>
<span data-ttu-id="2cb7b-135"><a name="bkmk_users"> </a></span><span class="sxs-lookup"><span data-stu-id="2cb7b-135"><a name="bkmk_users"> </a></span></span>

<span data-ttu-id="2cb7b-136">Office 365 にサインインすると、ドメインと組織内のユーザーが Skype for Business Online を使用Skype for Businessできます。</span><span class="sxs-lookup"><span data-stu-id="2cb7b-136">Now that you're signed in to Office 365, you can set up your domain and people in your organization to use Skype for Business Online.</span></span>

1. <span data-ttu-id="2cb7b-137">[ドメインとユーザー](https://support.office.com/article/6383f56d-3d09-4dcb-9b41-b5f5a5efd611)を Office 365 に追加する: Office 365 セットアップ ウィザードを使用して、カスタム ドメイン (fourthcoffee.com *など)* を Office 365 で設定します。</span><span class="sxs-lookup"><span data-stu-id="2cb7b-137">[Add a domain and users to Office 365](https://support.office.com/article/6383f56d-3d09-4dcb-9b41-b5f5a5efd611): Use the Office 365 setup wizard to set up your custom domain (such as *fourthcoffee.com*) with Office 365.</span></span> <span data-ttu-id="2cb7b-138">**既定では、Office 365 セットアップ ウィザードには、Skype for Business Online のセットアップとユーザー ID Skype for Businessが含まれています。**</span><span class="sxs-lookup"><span data-stu-id="2cb7b-138">**By default, the Office 365 setup wizard includes setting up Skype for Business Online and creating your Skype for Business user IDs.**</span></span> <span data-ttu-id="2cb7b-139">既にウィザードを使用してドメインをセットアップしている場合はOffice 365、この手順は完了しています。</span><span class="sxs-lookup"><span data-stu-id="2cb7b-139">If you already used the wizard to set up your domain for Office 365, then you've completed this step.</span></span>

2. <span data-ttu-id="2cb7b-140">[ドメインと DNS 接続を確認する](https://support.office.com/article/2b54e1b0-47a7-4018-a1e4-c2b924e7c5a0): ドメインのトラブルシューティング ツールを使用して、ドメインと DNS の設定が正しいか確認します。</span><span class="sxs-lookup"><span data-stu-id="2cb7b-140">[Check your domain and DNS connections](https://support.office.com/article/2b54e1b0-47a7-4018-a1e4-c2b924e7c5a0): Use our tool - the domains troubleshooter - to check that your domain and DNS settings are correct.</span></span> <span data-ttu-id="2cb7b-141">今後の問題のソースとして DNS 設定を排除できるので、セットアップの問題を後で把握するには、この作業が長い道のりになります。</span><span class="sxs-lookup"><span data-stu-id="2cb7b-141">Doing this now will go a long way to helping figure out any setup issues later since you'll be able to eliminate DNS settings as the source of future issues.</span></span>

3. <span data-ttu-id="2cb7b-142">[Office 365 URL](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2#BKMK_LYO)と IP アドレス範囲: ほとんどの小規模企業は、この手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2cb7b-142">[Office 365 URLs and IP address ranges](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2#BKMK_LYO): Most small businesses don't need to do this step.</span></span> <span data-ttu-id="2cb7b-143">**ただし、Web の一** 部へのアクセスを制限するファイアウォールまたはプロキシ サーバーがある場合は、Skype for Business Online エンドポイントへのアクセスを許可するルールを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2cb7b-143">**But if you have a firewall or proxy server that restricts access to parts of the web**, you must create rules to allow access to the Skype for Business Online endpoints.</span></span> <span data-ttu-id="2cb7b-144">これは、ファイアウォールとプロキシ サーバーの構成経験のあるユーザーが実行する高度な手順です。</span><span class="sxs-lookup"><span data-stu-id="2cb7b-144">This is an advanced step best performed by someone experienced with configuring firewalls and proxy servers.</span></span> <span data-ttu-id="2cb7b-145">この設定をまだ行ったことがない場合は[、Microsoft](https://go.microsoft.com/fwlink/?linkid=391089)パートナーを採用してユーザーにSkype for Businessを検討してください。</span><span class="sxs-lookup"><span data-stu-id="2cb7b-145">If you haven't done this before, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to set up Skype for Business for you.</span></span>

## <a name="4-set-up-im-and-presence-in-your-organization"></a><span data-ttu-id="2cb7b-146">4. 組織内で IM とプレゼンスを設定する</span><span class="sxs-lookup"><span data-stu-id="2cb7b-146">4. Set up IM and presence in your organization</span></span>
<span data-ttu-id="2cb7b-147"><a name="bkmk_IM"> </a></span><span class="sxs-lookup"><span data-stu-id="2cb7b-147"><a name="bkmk_IM"> </a></span></span>

<span data-ttu-id="2cb7b-148">インスタント メッセージング (IM) とプレゼンス ( Skype for Business でのプレゼンス[情報](https://support.office.com/article/fea86e34-60cf-4dd0-bfb2-169a42afd92c)へのアクセスの制御) は、Skype for Business に含まれている基本的な機能です。</span><span class="sxs-lookup"><span data-stu-id="2cb7b-148">Instant Messaging (IM) and presence ([Control access to your presence information in Skype for Business](https://support.office.com/article/fea86e34-60cf-4dd0-bfb2-169a42afd92c)) are basic features included with Skype for Business.</span></span> <span data-ttu-id="2cb7b-149">既定では、ビジネスのユーザーは、Skype IM を使用できます。</span><span class="sxs-lookup"><span data-stu-id="2cb7b-149">By default, the people in your business can Skype and IM with each other.</span></span>

1. <span data-ttu-id="2cb7b-150">**ユーザーが通信できる他Skype for Businessを選択します。**</span><span class="sxs-lookup"><span data-stu-id="2cb7b-150">**Choose who else your Skype for Business users can communicate with:**</span></span>

   - <span data-ttu-id="2cb7b-151">[ユーザーが外部ユーザーに連絡Skype for Business許可する](allow-users-to-contact-external-skype-for-business-users.md)自分と *他のビジネス* の両方が、システムを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2cb7b-151">[Allow users to contact external Skype for Business users](allow-users-to-contact-external-skype-for-business-users.md) Both you *and*  the other business will need to configure your systems.</span></span>

     <span data-ttu-id="2cb7b-152">**重要**: rob@contosowest.com と ina@contosoeast.com など、ビジネスに 2 つのドメインがある場合は、すべてのユーザーが相互に通信できるよう、この手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2cb7b-152">**IMPORTANT**: If you have two domains in your business, such as rob@contosowest.com and ina@contosoeast.com, you need to do this step so all of your users can communicate with each other.</span></span>

   - <span data-ttu-id="2cb7b-153">[ユーザーがSkype for Business外部のSkypeを追加](let-skype-for-business-users-add-skype-contacts.md)する</span><span class="sxs-lookup"><span data-stu-id="2cb7b-153">[Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md) outside your business</span></span>

2. <span data-ttu-id="2cb7b-154">**同僚がオンラインかどうかを確認するユーザーを選択します。** プレゼンス機能では、オンラインのユーザーと、空き時間情報、取り込み中、空き時間情報、発表中など、そのユーザーの空き時間情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2cb7b-154">**Choose who sees whether co-workers are online:** The presence feature shows who's online and what their availability is, such as available, busy, away, or presenting.</span></span>

    ![個人のメッセージを含むユーザーのオンライン状態の例。](../images/ab6c10b4-6ad5-453c-bf0e-459b977b6e23.png)

    <span data-ttu-id="2cb7b-156">ビジネスのすべてのユーザーの既定の設定を選択できます。</span><span class="sxs-lookup"><span data-stu-id="2cb7b-156">You can choose the default settings for everyone in your business:</span></span>

   - <span data-ttu-id="2cb7b-157">組織内のすべてのユーザーにユーザーのオンライン プレゼンスを自動的に表示する</span><span class="sxs-lookup"><span data-stu-id="2cb7b-157">Automatically display a person's online presence to everyone in the organization</span></span>

   - <span data-ttu-id="2cb7b-158">連絡先にのみユーザーのオンライン プレゼンスを表示する</span><span class="sxs-lookup"><span data-stu-id="2cb7b-158">Display a person's online presence only to their contacts</span></span>

<span data-ttu-id="2cb7b-159">手順については、「Skype for Business Online でのプレゼンス[の構成」を参照してください](configure-presence-in-skype-for-business-online.md)。</span><span class="sxs-lookup"><span data-stu-id="2cb7b-159">For instructions, see [Configure presence in Skype for Business Online](configure-presence-in-skype-for-business-online.md).</span></span>

## <a name="5-download-and-install-skype-for-business"></a><span data-ttu-id="2cb7b-160">5. ダウンロードしてインストールSkype for Business</span><span class="sxs-lookup"><span data-stu-id="2cb7b-160">5. Download and install Skype for Business</span></span>
<span data-ttu-id="2cb7b-161"><a name="bkmk_download"> </a></span><span class="sxs-lookup"><span data-stu-id="2cb7b-161"><a name="bkmk_download"> </a></span></span>

<span data-ttu-id="2cb7b-162">PC Skype for Business Mac、またはモバイル デバイスでアプリを使用するには、ユーザーと他のユーザーが最初にデバイスに Skype for Business をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2cb7b-162">To use Skype for Business on your PC, Mac, or mobile device, you and other people in your business have to first install the Skype for Business download on your devices.</span></span>

- <span data-ttu-id="2cb7b-163">[インストールSkype for Business:](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb)Microsoft 365 管理センターからアプリをダウンロードし、PC または Mac にインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2cb7b-163">[Install Skype for Business](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb): Instructions for how to download the app from the Microsoft 365 admin center, and install it on your PC or Mac.</span></span>

- <span data-ttu-id="2cb7b-164">[大規模なSkype for Businessにアプリ](deploy-the-skype-for-business-client-in-office-365.md)Office 365デプロイする手順に関するページで、クライアントをデプロイします。</span><span class="sxs-lookup"><span data-stu-id="2cb7b-164">[Deploy the Skype for Business client in Office 365](deploy-the-skype-for-business-client-in-office-365.md): Instructions for deploying the app in a large enterprise.</span></span>

- <span data-ttu-id="2cb7b-165">[インストールSkype for Business:](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb)Android デバイス、iOS デバイス、およびスマートフォンSkype for Businessにダウンロード、インストール、サインインWindowsします。</span><span class="sxs-lookup"><span data-stu-id="2cb7b-165">[Install Skype for Business](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb): Download, install, and sign in to Skype for Business on Android devices, iOS devices, and Windows phones.</span></span>

- <span data-ttu-id="2cb7b-166">[携帯電話の通知](turn-on-or-off-mobile-phone-notifications.md)をオンまたはオフにする: モバイル デバイスに Skype for Business をインストールすると、受信したインスタント メッセージと見逃したインスタント メッセージに関する通知を受信できます。</span><span class="sxs-lookup"><span data-stu-id="2cb7b-166">[Turn on or off mobile phone notifications](turn-on-or-off-mobile-phone-notifications.md): When you have Skype for Business installed on a mobile device, you and others in your business can receive alerts about incoming and missed instant messages.</span></span>

## <a name="6-test-to-make-sure-everything-is-working"></a><span data-ttu-id="2cb7b-167">6. テストして、すべてが動作している</span><span class="sxs-lookup"><span data-stu-id="2cb7b-167">6. Test to make sure everything is working</span></span>
<span data-ttu-id="2cb7b-168"><a name="bkmk_test"> </a></span><span class="sxs-lookup"><span data-stu-id="2cb7b-168"><a name="bkmk_test"> </a></span></span>

<span data-ttu-id="2cb7b-169">まず、自分とビジネスの他のユーザーがビデオ: サインインとサインアウトを実行できるかどうか[をテスト](https://support.office.com/article/8abed4b3-ac48-493e-9d76-0e10140e9451)Skype for Business。</span><span class="sxs-lookup"><span data-stu-id="2cb7b-169">First, test whether you and others in your business can [Video: Sign in and out of Skype for Business](https://support.office.com/article/8abed4b3-ac48-493e-9d76-0e10140e9451).</span></span> <span data-ttu-id="2cb7b-170">互いに IM を取り合い、互いにプレゼンスを確認し、簡単な会議を試みる。</span><span class="sxs-lookup"><span data-stu-id="2cb7b-170">Check that you can IM each other, see each other's presence, and try a quick meeting.</span></span>

<span data-ttu-id="2cb7b-171">問題がある場合</span><span class="sxs-lookup"><span data-stu-id="2cb7b-171">Problems?</span></span> <span data-ttu-id="2cb7b-172">以下の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="2cb7b-172">Do the following:</span></span>

- <span data-ttu-id="2cb7b-173">[サインインに関するヘルプがSkype for Business?](https://support.office.com/article/448b8ea7-5b33-444a-afd4-175fc9930d05)サインインに関する一般的な問題の一部です。</span><span class="sxs-lookup"><span data-stu-id="2cb7b-173">[Need help signing in to Skype for Business?](https://support.office.com/article/448b8ea7-5b33-444a-afd4-175fc9930d05) of common sign-in problems.</span></span>

- <span data-ttu-id="2cb7b-174">[ビジネス製品のサポートに問い合わせ - 管理者向けヘルプ](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)。</span><span class="sxs-lookup"><span data-stu-id="2cb7b-174">[Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span> <span data-ttu-id="2cb7b-175">お手伝いします。</span><span class="sxs-lookup"><span data-stu-id="2cb7b-175">We're here to help!</span></span>

## <a name="do-you-want-to-set-up-other-available-features"></a><span data-ttu-id="2cb7b-176">その他の利用可能な機能を設定しますか?</span><span class="sxs-lookup"><span data-stu-id="2cb7b-176">Do you want to set up other available features?</span></span>
<span data-ttu-id="2cb7b-177"><a name="bkmk_more"> </a></span><span class="sxs-lookup"><span data-stu-id="2cb7b-177"><a name="bkmk_more"> </a></span></span>

<span data-ttu-id="2cb7b-178">その他の機能を設定する前に、その機能のライセンスを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="2cb7b-178">Before setting up more features, make sure you have licenses for them.</span></span> [<span data-ttu-id="2cb7b-179">Skype for Business と Microsoft Teams のアドオン ライセンス</span><span class="sxs-lookup"><span data-stu-id="2cb7b-179">Skype for Business and Microsoft Teams add-on licensing</span></span>](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)

### <a name="set-up-audio-conferencing"></a><span data-ttu-id="2cb7b-180">電話会議をセットアップする</span><span class="sxs-lookup"><span data-stu-id="2cb7b-180">Set up Audio Conferencing</span></span>

<span data-ttu-id="2cb7b-181">組織内のユーザーは電話を使って会議に参加する必要が生じることがあります。</span><span class="sxs-lookup"><span data-stu-id="2cb7b-181">Sometimes people in your organization will need to use a phone to call into a meeting.</span></span> <span data-ttu-id="2cb7b-182">Skype for Business、この状況だけの電話会議機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="2cb7b-182">Skype for Business includes the Audio Conferencing feature for just this situation!</span></span> <span data-ttu-id="2cb7b-183">参加者は、モバイル デバイスや PC で Skype for Business アプリを使用する代わりに、電話を使って Skype for Business 会議にコールインできます。</span><span class="sxs-lookup"><span data-stu-id="2cb7b-183">People can call into Skype for Business meetings using a phone, instead of using the Skype for Business app on a mobile device or PC.</span></span>

### <a name="set-up-phone-system-and-the-calling-plans-in-office-365"></a><span data-ttu-id="2cb7b-184">通話プラン電話システム通話プランを設定Office 365</span><span class="sxs-lookup"><span data-stu-id="2cb7b-184">Set up Phone System and the Calling plans in Office 365</span></span>

<span data-ttu-id="2cb7b-185">この電話システム機能Office 365、ビジネス用の電話システムを提供します。</span><span class="sxs-lookup"><span data-stu-id="2cb7b-185">The Phone System feature in Office 365 gives you a phone system for your business.</span></span> <span data-ttu-id="2cb7b-186">組織内のユーザー Skype for Business他のユーザーへの呼び出しは無料で、従業員は互いにボイスメールを受け取り、外部の発信者を受け取る可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2cb7b-186">Calls to other Skype for Business people in your organization are free, and your employees can receive voicemail from each other and outside callers.</span></span> <span data-ttu-id="2cb7b-187">次に示すのは、電話システム。</span><span class="sxs-lookup"><span data-stu-id="2cb7b-187">Here's what you get with Phone System.</span></span>

<span data-ttu-id="2cb7b-188">通話プラン サービスを追加すると、従業員は通話プランにプライマリ電話番号Skype for Business。</span><span class="sxs-lookup"><span data-stu-id="2cb7b-188">When you add the Calling Plan service, your employees get a primary phone number in Skype for Business.</span></span> <span data-ttu-id="2cb7b-189">外部のユーザーは、業務外で電話を行い、受信できます。</span><span class="sxs-lookup"><span data-stu-id="2cb7b-189">They can make and receive phone calls outside of your business.</span></span> <span data-ttu-id="2cb7b-190">VoIP 電話、PC、モバイル デバイス間で音声通話を行えます。</span><span class="sxs-lookup"><span data-stu-id="2cb7b-190">They can make voice calls across VoIP phones, PCs, and mobile devices.</span></span> <span data-ttu-id="2cb7b-191">また、緊急対応の場合は、911 に電話してサポートを受け取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="2cb7b-191">And, in case of emergencies, they can call 911 for help.</span></span>

<span data-ttu-id="2cb7b-192">詳細なセットアップ手順については、「通話プランを設定する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2cb7b-192">For step-by-step setup instructions, see Set up Calling Plans.</span></span>

### <a name="set-up-skype-meeting-broadcast"></a><span data-ttu-id="2cb7b-193">会議ブロードキャストSkype設定する</span><span class="sxs-lookup"><span data-stu-id="2cb7b-193">Set up Skype Meeting Broadcast</span></span>

<span data-ttu-id="2cb7b-194">Skype会議ブロードキャストは、最大 10,000 人の出席者を含む会議を作成、ホスト、およびブロードキャストできる機能です。</span><span class="sxs-lookup"><span data-stu-id="2cb7b-194">Skype Meeting Broadcast is a feature that lets you produce, host, and broadcast meetings with up to 10,000 attendees.</span></span> <span data-ttu-id="2cb7b-195">**機能の詳細については、「会議ブロードキャストの概要 [」Skypeしてください。](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)**</span><span class="sxs-lookup"><span data-stu-id="2cb7b-195">**To learn more about how it works, see [What is a Skype Meeting Broadcast?](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)**</span></span>

<span data-ttu-id="2cb7b-196">会議ブロードキャストを設定する手順の概要をSkypeします。</span><span class="sxs-lookup"><span data-stu-id="2cb7b-196">Here's an overview of the steps to set up Skype Meeting Broadcast:</span></span>

1. <span data-ttu-id="2cb7b-197">[一Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)のライセンスの割り当てまたは削除: ブロードキャスト会議を開催する全員に **Skype for Business Online** または **Enterprise プラン** ライセンスを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="2cb7b-197">[Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc): Assign **Skype for Business Online** or **Enterprise Plan** licenses to everyone who is going to **host** a Broadcast meeting.</span></span>

2. <span data-ttu-id="2cb7b-198">[会議Skype有効](../set-up-your-network-for-skype-meeting-broadcast/enable-skype-meeting-broadcast.md)にする: 既定では、この機能は有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="2cb7b-198">[Enable Skype Meeting Broadcast](../set-up-your-network-for-skype-meeting-broadcast/enable-skype-meeting-broadcast.md): By default, this feature isn't enabled.</span></span> <span data-ttu-id="2cb7b-199">有効にした後、ユーザーは組織内の他のユーザーとのブロードキャスト会議をホストできます。</span><span class="sxs-lookup"><span data-stu-id="2cb7b-199">After you turn it on, your users will be able to host broadcast meetings with other people in your organization.</span></span>

3. <span data-ttu-id="2cb7b-200">[Skype 会議](../set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast.md)ブロードキャスト用にネットワークを設定する: 組織外の出席者とウェビナーや他のブロードキャストをホストする場合は、ネットワークを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2cb7b-200">[Set up your network for Skype Meeting Broadcast](../set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast.md): If you want to host webinars and other broadcasts with attendees outside of your organization, you need to configure your network.</span></span>

4. <span data-ttu-id="2cb7b-201">[](https://support.office.com/article/c3995bc9-4d32-4f75-a004-3bc5c477e553) Skype 会議ブロードキャストをスケジュールし [、Skype](https://support.office.com/article/14689da0-821d-48d4-9035-ea762de80ebe)会議ブロードキャストに参加する : Skype 会議ブロードキャストをスケジュール設定し、他のユーザーに会議への参加を試みて、ブロードキャスト会議が機能します。 *https://portal.broadcast.skype.com*</span><span class="sxs-lookup"><span data-stu-id="2cb7b-201">[Schedule a Skype Meeting Broadcast](https://support.office.com/article/c3995bc9-4d32-4f75-a004-3bc5c477e553) and have a [Join a Skype Meeting Broadcast](https://support.office.com/article/14689da0-821d-48d4-9035-ea762de80ebe): Make sure broadcast meetings work by scheduling a Skype Meeting Broadcast at  *https://portal.broadcast.skype.com*  and then having someone try to join the meeting.</span></span>

## <a name="learn-about-network-connectivity-requirements"></a><span data-ttu-id="2cb7b-202">ネットワーク接続の要件について学習する</span><span class="sxs-lookup"><span data-stu-id="2cb7b-202">Learn about network connectivity requirements</span></span>
<span data-ttu-id="2cb7b-203"><a name="bkmk_more"> </a></span><span class="sxs-lookup"><span data-stu-id="2cb7b-203"><a name="bkmk_more"> </a></span></span>

<span data-ttu-id="2cb7b-204">Skype for Business でのオーディオ、ビデオ、およびアプリケーション共有の品質は、エンドツーエンドのネットワーク接続の品質の影響を大きく受け取っています。</span><span class="sxs-lookup"><span data-stu-id="2cb7b-204">The quality of audio, video, and application sharing in Skype for Business is greatly impacted by the quality of end-to-end network connectivity.</span></span> <span data-ttu-id="2cb7b-205">最適なエクスペリエンスを実現するには、会社のネットワークと Skype for Business Online の間に高品質の接続が確立Skype for Businessです。</span><span class="sxs-lookup"><span data-stu-id="2cb7b-205">For an optimal experience, it is important to make sure there is a high-quality connection between your company network and Skype for Business Online.</span></span> <span data-ttu-id="2cb7b-206">ネットワークとチューニングの情報については、「Tune Skype for Business Online performance 」[を参照してください](https://support.office.com/article/beec23c2-c5d6-4e84-a8af-e82aefca7802)。</span><span class="sxs-lookup"><span data-stu-id="2cb7b-206">For network and tuning information, see [Tune Skype for Business Online performance](https://support.office.com/article/beec23c2-c5d6-4e84-a8af-e82aefca7802).</span></span>

## <a name="all-done-setting-up-getting-started-using-skype-for-business"></a><span data-ttu-id="2cb7b-207">セットアップが完了しましたか?</span><span class="sxs-lookup"><span data-stu-id="2cb7b-207">All done setting up?</span></span> <span data-ttu-id="2cb7b-208">Skype for Business の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="2cb7b-208">Getting started using Skype for Business</span></span>
<span data-ttu-id="2cb7b-209"><a name="bkmk_more"> </a></span><span class="sxs-lookup"><span data-stu-id="2cb7b-209"><a name="bkmk_more"> </a></span></span>

<span data-ttu-id="2cb7b-210">[Skype for Businessトレーニング](https://support.office.com/article/8a3491a3-c095-4718-80cf-cbbe4afe4eba): すぐに始めるのに役立つトレーニング トピックの一覧をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2cb7b-210">[Skype for Business training](https://support.office.com/article/8a3491a3-c095-4718-80cf-cbbe4afe4eba): Check out this list of training topics to help you get started quickly!</span></span>

[<span data-ttu-id="2cb7b-211">電話会議Skype for Business開始する</span><span class="sxs-lookup"><span data-stu-id="2cb7b-211">Start a Skype for Business conference call</span></span>](https://support.office.com/article/8dc8ac52-91ac-4db9-8672-11551fdaf997)

<span data-ttu-id="2cb7b-212">[[ビデオ デバイス] オプションを [Skype for Business](https://support.office.com/article/d09017c0-deba-4f6c-a122-9eca6604f50c)</span><span class="sxs-lookup"><span data-stu-id="2cb7b-212">[Set Video Device options in Skype for Business](https://support.office.com/article/d09017c0-deba-4f6c-a122-9eca6604f50c)</span></span>

[<span data-ttu-id="2cb7b-213">ビデオ通話を行い、ビデオ通話を受信Skype for Business</span><span class="sxs-lookup"><span data-stu-id="2cb7b-213">Make and receive a video call using Skype for Business</span></span>](https://support.office.com/article/abf62493-670f-4b0d-b2cf-fe03b49caf42)

[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]

## <a name="related-topics"></a><span data-ttu-id="2cb7b-214">関連項目</span><span class="sxs-lookup"><span data-stu-id="2cb7b-214">Related topics</span></span>
<span data-ttu-id="2cb7b-215"><a name="bkmk_more"> </a></span><span class="sxs-lookup"><span data-stu-id="2cb7b-215"><a name="bkmk_more"> </a></span></span>

[<span data-ttu-id="2cb7b-216">Skype for Business Server と Skype for Business Online 間のハイブリッド接続を計画する</span><span class="sxs-lookup"><span data-stu-id="2cb7b-216">Plan hybrid connectivity between Skype for Business Server and Skype for Business Online</span></span>](../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)
