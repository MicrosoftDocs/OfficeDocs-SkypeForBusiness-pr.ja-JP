---
title: "Skype for Business Online をセットアップします。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 40296968-e779-4259-980b-c2de1c044c6e
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
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
description: "Skype for Business をインストールするドメイン、ユーザー、IM と、組織のプレゼンスを設定する方法を学習します。電話会議、電話システムとプランの呼び出し] と Skype 会議メディアを設定する方法を参照してください。 "
ms.openlocfilehash: 45737ce4dc37fa8c5a85f55d4c32681f96a9bbf8
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="set-up-skype-for-business-online"></a><span data-ttu-id="2e564-104">Skype for Business Online をセットアップします。</span><span class="sxs-lookup"><span data-stu-id="2e564-104">Set up Skype for Business Online</span></span>
  
<span data-ttu-id="2e564-p102">Skype for Business をセットアップする Office 365 グローバル管理者権限が必要です。Web パーツへのアクセス制限をファイアウォールまたはプロキシ サーバーがある場合は、する Skype for Business をセットアップする[Microsoft パートナー](https://go.microsoft.com/fwlink/?linkid=391089)を雇うを検討してください。</span><span class="sxs-lookup"><span data-stu-id="2e564-p102">You must have Office 365 global admin permissions to set up Skype for Business. If you have a firewall or proxy server that restricts access to parts of the web, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to set up Skype for Business for you.</span></span>
  
## <a name="setting-up-skype"></a><span data-ttu-id="2e564-107">Skype のセットアップ</span><span class="sxs-lookup"><span data-stu-id="2e564-107">Setting up Skype</span></span>

<span data-ttu-id="2e564-p103">よう、Office 365 サブスクリプションでの Skype のセットアップのヘルプが必要です。セットアップを完了するには、この記事に示す手順を実行できます。</span><span class="sxs-lookup"><span data-stu-id="2e564-p103">Looks like you need help setting up Skype with your Office 365 subscription. You can follow the steps in this article to get your setup completed.</span></span>
  
## <a name="1-plan-for-skype-for-business"></a><span data-ttu-id="2e564-110">1. Skype for Business を計画します。</span><span class="sxs-lookup"><span data-stu-id="2e564-110">1. Plan for Skype for Business</span></span>

<span data-ttu-id="2e564-p104">**[Office 365 Business Premium](https://products.office.com/en-us/business/office-365-business-premium)**または**Business Essentials**の場合は、サブスクリプションでのビジネスで他のユーザーに通話をオンラインに Skype for Business を使用することができます。たとえば、ビジネスの 10 個の連絡先ことができます[Skype for Business の IM およびオンライン会議の使用を開始](http://support.office.com/article/cc05afa6-1894-4a82-9dd9-6222061f50fd)すると[Skype for Business との会議](https://support.office.com/article/2eed8424-581a-4497-b505-c08c152e5851)が 2 ~ 6 の次の手順を実行した後に Skype for Business を使いします。. を[Skype for Business 会議を Outlook で設定](https://support.office.com/article/b8305620-d16e-4667-989d-4a977aad6556#bkmk_OWA)すると、オンライン会議を開催すぎます。</span><span class="sxs-lookup"><span data-stu-id="2e564-p104">If you have **[Office 365 Business Premium](https://products.office.com/en-us/business/office-365-business-premium)** or **Business Essentials**, you can use Skype for Business to make online calls to other people in your business who are on your subscription. For example, if your business has 10 people, you'll be able to [Start using Skype for Business for IM and online meetings](http://support.office.com/article/cc05afa6-1894-4a82-9dd9-6222061f50fd) each other, and [Meetings with Skype for Business](https://support.office.com/article/2eed8424-581a-4497-b505-c08c152e5851) using Skype for Business after performing the steps 2-6 below. And you can [Set up a Skype for Business meeting in Outlook](https://support.office.com/article/b8305620-d16e-4667-989d-4a977aad6556#bkmk_OWA) to online meetings, too!</span></span>
  
<span data-ttu-id="2e564-114">Skype for Business を使用して、作成し、ユーザーから*外部*ビジネスに**着信**を受信する場合は。</span><span class="sxs-lookup"><span data-stu-id="2e564-114">If you want to use Skype for Business to make and receive **calls** from people *external*  to your business:</span></span>
  
- <span data-ttu-id="2e564-p105">**オプション 1 です。無料の[Skype アプリ](https://www.skype.com/)を使用して**します。非常に小規模企業 (たとえば、1 と 2 人) を使っている場合は、移動する場合に適しては Skype アプリを使ってます。国内/国際通話に使用安価はできます。電話会議を押したまま、ビデオ通話、およびプレゼンテーション用にデスクトップを共有するもことができます。[単価と [お支払い方法を確認](https://secure.skype.com/en/calling-rates?wt.mc_id=legacy&amp;expo365=bundled)してください。</span><span class="sxs-lookup"><span data-stu-id="2e564-p105">**Option 1. Use the free [Skype app](https://www.skype.com/)**. If you have a very small business (for example, 1-2 people), using the Skype app is the better way to go. It's less expensive to use for domestic and international calls. You can still hold conference calls, make video calls, and share your desktop for presentations. [Check out the rates and payment options](https://secure.skype.com/en/calling-rates?wt.mc_id=legacy&amp;expo365=bundled).</span></span>
    
- <span data-ttu-id="2e564-p106">**オプション 2 です。、プランをアップグレードして、電話システムと通話プランを購入する Office 365 の**します。およびを見つけるどの程度このコストとし、切り替える、[ビジネス製品 - 管理者向けヘルプのサポートに問い合わせてください](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)には、それらを行うにはすべてのアイテムがある最も簡単な方法です。</span><span class="sxs-lookup"><span data-stu-id="2e564-p106">**Option 2. Upgrade your plan, and buy the Phone System and a Calling Plan for Office 365**. The easiest way to find out how much this costs, and then make the switch, is to [Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) and have them do everything for you.</span></span>
    
<span data-ttu-id="2e564-122">詳細については、[計画一般法人向け Office 365 の設定](https://support.office.com/article/eb926624-018b-4486-bf11-5fba6ee4d645#bkmk_skype)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e564-122">To learn more, see [Plan your setup of Office 365 for business](https://support.office.com/article/eb926624-018b-4486-bf11-5fba6ee4d645#bkmk_skype).</span></span>
  
## <a name="2-sign-in-to-office-365"></a><span data-ttu-id="2e564-123">2. へのサインインに Office 365</span><span class="sxs-lookup"><span data-stu-id="2e564-123">2. Sign in to Office 365</span></span>
<span data-ttu-id="2e564-124"><a name="bkmk_signin"> </a></span><span class="sxs-lookup"><span data-stu-id="2e564-124"></span></span>

<span data-ttu-id="2e564-p107">Skype for Business Online は、Office 365 サービスのスイートの一部です。Skype for Business Online をセットアップするには、Office 365 にサインインする必要があります。その方法を示します。</span><span class="sxs-lookup"><span data-stu-id="2e564-p107">Skype for Business Online is part of the Office 365 suite of services. To set up Skype for Business Online, you need to sign in to Office 365. Here's how you do that:</span></span>
  
1. <span data-ttu-id="2e564-p108">Office 365 ユーザー ID (たとえば、 *rob@fourthcoffee.com* ) を探します。Skype for Business Online の購入時に作成した Office 365 ユーザー ID を含む Microsoft Online Services チームからメールを受信します。メールでは、次のようなものが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2e564-p108">Locate your Office 365 user ID (for example,  *rob@fourthcoffee.com*  ). You received an email from the Microsoft Online Services Team that contains the Office 365 user ID that you created when you purchased Skype for Business Online. The mail looks something like this:</span></span>
    
    ![For Business Online Skype にサインアップした後に受信した、ようこそメールの例。Office 365 ユーザー id が含まれています。](../images/977c5c96-29c5-40c0-a4c4-1ba66ba3a1fb.png)
  
2. <span data-ttu-id="2e564-p110">Office 365 管理センターにサインインし、Office 365 ユーザー ID とパスワードを入力します。サインインした後、Office 365 管理センターが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2e564-p110">Sign in to the Office 365 admin center and enter your Office 365 user ID and password. After you sign in, you'll see the Office 365 admin center:</span></span>
    
    ![どのような Office 365 管理センターの例は次のように、ある場合は、Skype for Business Online を計画します。](../images/ed1d9906-e717-450b-81a3-ce6679bd1be1.png)
  
## <a name="3-set-up-your-domain-and-users"></a><span data-ttu-id="2e564-136">3. ドメインとユーザーを設定します。</span><span class="sxs-lookup"><span data-stu-id="2e564-136">3. Set up your domain and users</span></span>
<span data-ttu-id="2e564-137"><a name="bkmk_users"> </a></span><span class="sxs-lookup"><span data-stu-id="2e564-137"></span></span>

<span data-ttu-id="2e564-138">これで、Office 365 にサインインしている、Skype for Business Online を使用、組織のドメインとユーザーを設定できます。</span><span class="sxs-lookup"><span data-stu-id="2e564-138">Now that you're signed in to Office 365, you can set up your domain and people in your organization to use Skype for Business Online.</span></span>
  
1. <span data-ttu-id="2e564-p111">[ドメインを追加して Office 365 にユーザー](https://support.office.com/article/6383f56d-3d09-4dcb-9b41-b5f5a5efd611): Office 365 のセットアップ ウィザードを使用して、Office 365 でカスタム ドメイン (例*: fourthcoffee.com*) を設定します。**既定では、Office 365 のセットアップ ウィザードには、for Business Online の Skype の設定と Skype for Business ユーザー Id の作成が含まれています**。既に Office 365 用にドメインをセットアップするウィザードを使用した場合は、この手順を完了しました。</span><span class="sxs-lookup"><span data-stu-id="2e564-p111">[Add a domain and users to Office 365](https://support.office.com/article/6383f56d-3d09-4dcb-9b41-b5f5a5efd611): Use the Office 365 setup wizard to set up your custom domain (such as *fourthcoffee.com*) with Office 365. **By default, the Office 365 setup wizard includes setting up Skype for Business Online and creating your Skype for Business user IDs.** If you already used the wizard to set up your domain for Office 365, then you've completed this step.</span></span>
    
2. <span data-ttu-id="2e564-p112">[ドメインと DNS の接続を確認する](https://support.office.com/article/2b54e1b0-47a7-4018-a1e4-c2b924e7c5a0): ドメインと DNS の設定が正しいことを確認する - ドメインのトラブルシューティング -、ツールを使用します。これでこれを行うため、今後問題のソースとして DNS の設定を削除することができます後でセットアップの問題が発生を把握するために大きく役立ちますが移動されます。</span><span class="sxs-lookup"><span data-stu-id="2e564-p112">[Check your domain and DNS connections](https://support.office.com/article/2b54e1b0-47a7-4018-a1e4-c2b924e7c5a0): Use our tool - the domains troubleshooter - to check that your domain and DNS settings are correct. Doing this now will go a long way to helping figure out any setup issues later since you'll be able to eliminate DNS settings as the source of future issues.</span></span>
    
3. <span data-ttu-id="2e564-p113">[Office 365 の Url と IP アドレスの範囲](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2#BKMK_LYO): ほとんどの小規模企業は、この手順を実行する必要はありません。**Web パーツへのアクセスを制限しているファイアウォールまたはプロキシ サーバーがある場合**は、Skype for Business Online エンドポイント アクセスを許可するルールを作成する必要があります。これは、ファイアウォール、プロキシ サーバーの設定が発生したユーザーによって実行される最適な高度な手順です。いない場合このする前に、する Skype for Business をセットアップする[Microsoft パートナー](https://go.microsoft.com/fwlink/?linkid=391089)を雇うを検討してください。</span><span class="sxs-lookup"><span data-stu-id="2e564-p113">[Office 365 URLs and IP address ranges](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2#BKMK_LYO): Most small businesses don't need to do this step. **But if you have a firewall or proxy server that restricts access to parts of the web**, you must create rules to allow access to the Skype for Business Online endpoints. This is an advanced step best performed by someone experienced with configuring firewalls and proxy servers. If you haven't done this before, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to set up Skype for Business for you.</span></span>
    
## <a name="4-set-up-im-and-presence-in-your-organization"></a><span data-ttu-id="2e564-148">4. IM と、組織内でプレゼンスを設定します。</span><span class="sxs-lookup"><span data-stu-id="2e564-148">4. Set up IM and presence in your organization</span></span>
<span data-ttu-id="2e564-149"><a name="bkmk_IM"> </a></span><span class="sxs-lookup"><span data-stu-id="2e564-149"></span></span>

<span data-ttu-id="2e564-p114">インスタント メッセージング (IM) とプレゼンス ([Skype for Business で自分のプレゼンス情報へのアクセス制御](https://support.office.com/article/fea86e34-60cf-4dd0-bfb2-169a42afd92c)) は、Skype for Business に付属する基本的な機能です。既定では、ビジネスに相互 Skype と IM を使用できます。</span><span class="sxs-lookup"><span data-stu-id="2e564-p114">Instant Messaging (IM) and presence ([Control access to your presence information in Skype for Business](https://support.office.com/article/fea86e34-60cf-4dd0-bfb2-169a42afd92c)) are basic features included with Skype for Business. By default, the people in your business can Skype and IM with each other.</span></span>
  
1. <span data-ttu-id="2e564-152">**他の Skype for Business ユーザーと通信できるユーザーを選択します。**</span><span class="sxs-lookup"><span data-stu-id="2e564-152">**Choose who else your Skype for Business users can communicate with:**</span></span>
    
  - <span data-ttu-id="2e564-153">[ユーザーが外部の Skype for Business ユーザーに連絡できるようにします。](allow-users-to-contact-external-skype-for-business-users.md)両方する*と*その他のビジネスは、システムを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e564-153">[Allow users to contact external Skype for Business users](allow-users-to-contact-external-skype-for-business-users.md) Both you *and*  the other business will need to configure your systems.</span></span>
    
    <span data-ttu-id="2e564-154">**重要**: rob@contosowest.com ina@contosoeast.com] など、ビジネスで 2 つのドメインを持っている場合は、他のすべてのユーザー通信できるように、この手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e564-154">**IMPORTANT**: If you have two domains in your business, such as rob@contosowest.com and ina@contosoeast.com, you need to do this step so all of your users can communicate with each other.</span></span>
    
  - <span data-ttu-id="2e564-155">組織外の[、Skype for Business ユーザーが Skype の連絡先を追加します。](let-skype-for-business-users-add-skype-contacts.md)</span><span class="sxs-lookup"><span data-stu-id="2e564-155">[Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md) outside your business</span></span>
    
2. <span data-ttu-id="2e564-156">**同僚がオンラインかどうかを表示できるユーザーの選択:**オンライン状態し、は何かの空き時間情報、使用可能な取り込み中、退席中、またはプレゼンテーションなど、プレゼンス機能を示しています。</span><span class="sxs-lookup"><span data-stu-id="2e564-156">**Choose who sees whether co-workers are online:** The presence feature shows who's online and what their availability is, such as available, busy, away, or presenting.</span></span>
    
    ![個人的なメッセージをその人のオンライン状態の例です。](../images/ab6c10b4-6ad5-453c-bf0e-459b977b6e23.png)
  
    <span data-ttu-id="2e564-158">ビジネスでは、すべてのユーザーの既定の設定を選択できます。</span><span class="sxs-lookup"><span data-stu-id="2e564-158">You can choose the default settings for everyone in your business:</span></span>
    
  - <span data-ttu-id="2e564-159">組織内のすべてのユーザーにその人のオンライン プレゼンスを自動的に表示します。</span><span class="sxs-lookup"><span data-stu-id="2e564-159">Automatically display a person's online presence to everyone in the organization</span></span>
    
  - <span data-ttu-id="2e564-160">その連絡先にのみその人のオンライン プレゼンスを表示します。</span><span class="sxs-lookup"><span data-stu-id="2e564-160">Display a person's online presence only to their contacts</span></span>
    
<span data-ttu-id="2e564-161">手順については、 [Skype for Business Online でプレゼンスを設定する](configure-presence-in-skype-for-business-online.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e564-161">For instructions, see [Configure presence in Skype for Business Online](configure-presence-in-skype-for-business-online.md).</span></span>
  
## <a name="5-download-and-install-skype-for-business"></a><span data-ttu-id="2e564-162">5. ダウンロードして、Skype for Business をインストールします。</span><span class="sxs-lookup"><span data-stu-id="2e564-162">5. Download and install Skype for Business</span></span>
<span data-ttu-id="2e564-163"><a name="bkmk_download"> </a></span><span class="sxs-lookup"><span data-stu-id="2e564-163"></span></span>

<span data-ttu-id="2e564-164">使用するには Skype for Business PC、Mac、またはモバイル デバイスのして、ビジネスで他のユーザーが最初のデバイスで Skype for Business のダウンロードをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e564-164">To use Skype for Business on your PC, Mac, or mobile device, you and other people in your business have to first install the Skype for Business download on your devices.</span></span>
  
- <span data-ttu-id="2e564-165">[Skype for Business をインストールする](http://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb): は Office 365 ポータルからアプリをダウンロードして、その、PC または mac インストールする方法の手順</span><span class="sxs-lookup"><span data-stu-id="2e564-165">[Install Skype for Business](http://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb): Instructions for how to download the app from the Office 365 portal, and install it on your PC or Mac.</span></span>
    
- <span data-ttu-id="2e564-166">[Skype for Business クライアントを Office 365 の展開](deploy-the-skype-for-business-client-in-office-365.md): 大企業のアプリを展開するための手順です。</span><span class="sxs-lookup"><span data-stu-id="2e564-166">[Deploy the Skype for Business client in Office 365](deploy-the-skype-for-business-client-in-office-365.md): Instructions for deploying the app in a large enterprise.</span></span>
    
- <span data-ttu-id="2e564-167">[Skype for Business をインストールする](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb): ダウンロード、インストール、および Android デバイス、iOS デバイスでは、Windows phone で Skype for Business にサインインします。</span><span class="sxs-lookup"><span data-stu-id="2e564-167">[Install Skype for Business](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb): Download, install, and sign in to Skype for Business on Android devices, iOS devices, and Windows phones.</span></span>
    
- <span data-ttu-id="2e564-168">[携帯電話の通知を無効または有効にする](turn-on-or-off-mobile-phone-notifications.md): ビジネスでの他のユーザーとは、受信、および不在着信したインスタント メッセージに関する通知を受信できます Skype for Business のモバイル デバイスにインストールされているが、します。</span><span class="sxs-lookup"><span data-stu-id="2e564-168">[Turn on or off mobile phone notifications](turn-on-or-off-mobile-phone-notifications.md): When you have Skype for Business installed on a mobile device, you and others in your business can receive alerts about incoming and missed instant messages.</span></span>
    
## <a name="6-test-to-make-sure-everything-is-working"></a><span data-ttu-id="2e564-169">6. 動作しているかどうかを確認するテストします。</span><span class="sxs-lookup"><span data-stu-id="2e564-169">6. Test to make sure everything is working</span></span>
<span data-ttu-id="2e564-170"><a name="bkmk_test"> </a></span><span class="sxs-lookup"><span data-stu-id="2e564-170"></span></span>

<span data-ttu-id="2e564-p115">最初に、ビジネスでの他のユーザーとできるかどうかをテスト[ビデオ: 向けのサインインと Skype サインアウト](https://support.office.com/article/8abed4b3-ac48-493e-9d76-0e10140e9451)します。それぞれのプレゼンスを表示すると、クイック会議を実行するくださいとその他] に IM ができることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="2e564-p115">First, test whether you and others in your business can [Video: Sign in and out of Skype for Business](https://support.office.com/article/8abed4b3-ac48-493e-9d76-0e10140e9451). Check that you can IM each other, see each other's presence, and try a quick meeting.</span></span>
  
<span data-ttu-id="2e564-p116">問題が起きる場合次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="2e564-p116">Problems? Do the following:</span></span>
  
- <span data-ttu-id="2e564-175">[Skype for Business へのサインインのヘルプが必要ですか?](https://support.office.com/article/448b8ea7-5b33-444a-afd4-175fc9930d05)一般的なサインインの問題です。</span><span class="sxs-lookup"><span data-stu-id="2e564-175">[Need help signing in to Skype for Business?](https://support.office.com/article/448b8ea7-5b33-444a-afd4-175fc9930d05) of common sign-in problems.</span></span>
    
- <span data-ttu-id="2e564-p117">[ビジネス製品 - 管理者向けヘルプのサポートに問い合わせてください](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)。ここでは解消ためです。</span><span class="sxs-lookup"><span data-stu-id="2e564-p117">[Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b). We're here to help!</span></span>
    
## <a name="do-you-want-to-set-up-other-available-features"></a><span data-ttu-id="2e564-178">使用可能なその他の機能を設定しますか。</span><span class="sxs-lookup"><span data-stu-id="2e564-178">Do you want to set up other available features?</span></span>
<span data-ttu-id="2e564-179"><a name="bkmk_more"> </a></span><span class="sxs-lookup"><span data-stu-id="2e564-179"></span></span>

<span data-ttu-id="2e564-p118">その他の機能をセットアップする前にライセンスがあることを確認します。[Skype Business および Microsoft チーム アドオン ライセンスを許可します。](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="2e564-p118">Before setting up more features, make sure you have licenses for them. [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)</span></span>
  
### <a name="set-up-audio-conferencing"></a><span data-ttu-id="2e564-182">音声会議をセットアップします。</span><span class="sxs-lookup"><span data-stu-id="2e564-182">Set up Audio Conferencing</span></span>

<span data-ttu-id="2e564-p119">組織のユーザーは、電話を使用して、会議にコールインする必要があります。Skype for Business には、これだけの電話会議の機能が含まれています。ユーザーに Skype for Business 会議の Skype を使用して for Business アプリをモバイル デバイスや PC ではなく、電話を使用して呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="2e564-p119">Sometimes people in your organization will need to use a phone to call into a meeting. Skype for Business includes the Audio Conferencing feature for just this situation! People can call into Skype for Business meetings using a phone, instead of using the Skype for Business app on a mobile device or PC.</span></span>
  
<span data-ttu-id="2e564-186">ステップ バイ ステップのセットアップ手順については、Office 365 での[Skype for Business とチームの Microsoft の音声会議をセットアップする](../audio-conferencing-in-office-365/set-up-audio-conferencing.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e564-186">For step-by-step setup instructions, see [Set up Audio Conferencing for Skype for Business and Microsoft Teams](../audio-conferencing-in-office-365/set-up-audio-conferencing.md) in Office 365.</span></span>
  
### <a name="set-up-phone-system-and-the-calling-plans-in-office-365"></a><span data-ttu-id="2e564-187">電話システムと Office 365 での通話プランを設定します。</span><span class="sxs-lookup"><span data-stu-id="2e564-187">Set up Phone System and the Calling plans in Office 365</span></span>

<span data-ttu-id="2e564-p120">Office 365 で電話システムで機能を使用すると、ビジネス用電話システムします。組織内のビジネス ユーザーの他の skype 通話は、無料と発信者の内外から他の従業員がボイス メールを受け取ることができます。ここでは、電話システムで表示します。</span><span class="sxs-lookup"><span data-stu-id="2e564-p120">The Phone System feature in Office 365 gives you a phone system for your business. Calls to other Skype for Business people in your organization are free, and your employees can receive voicemail from each other and outside callers. Here's what you get with Phone System.</span></span>
  
<span data-ttu-id="2e564-p121">プランの呼び出しサービスを追加すると、向け Skype で主要な電話番号が表示従業員。でき、ビジネスの外部で電話をかけたり受けたりすることができます。VoIP 電話、コンピューター、モバイル デバイス間での音声通話に設定できます。また、事態した場合に備えてについて 911 を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="2e564-p121">When you add the Calling Plan service, your employees get a primary phone number in Skype for Business. They can make and receive phone calls outside of your business. They can make voice calls across VoIP phones, PCs, and mobile devices. And, in case of emergencies, they can call 911 for help.</span></span>
  
<span data-ttu-id="2e564-195">ステップ バイ ステップのセットアップ手順については、設定を参照してください。 プランの呼び出しをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="2e564-195">For step-by-step setup instructions, see Set up Calling Plans.</span></span>
  
### <a name="set-up-skype-meeting-broadcast"></a><span data-ttu-id="2e564-196">Skype 会議メディアを設定します。</span><span class="sxs-lookup"><span data-stu-id="2e564-196">Set up Skype Meeting Broadcast</span></span>

<span data-ttu-id="2e564-p122">Skype 会議メディアとは、ホストを作成して、最大 10,000 人の参加者との会議をブロードキャストする機能です。**、実際の操作の詳細については、次を参照してください[Skype 会議メディアとは何ですか?](http://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d) ** 。</span><span class="sxs-lookup"><span data-stu-id="2e564-p122">Skype Meeting Broadcast is a feature that lets you produce, host, and broadcast meetings with up to 10,000 attendees. **To learn more about how it works, see [What is a Skype Meeting Broadcast?](http://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)**</span></span>
  
<span data-ttu-id="2e564-199">Skype 会議メディアを設定する手順の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="2e564-199">Here's an overview of the steps to set up Skype Meeting Broadcast:</span></span>
  
1. <span data-ttu-id="2e564-200">[割り当てまたは一般法人向け Office 365 のライセンスを削除する](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc): すべてのユーザーは**ホスト**にブロードキャスト会議に**Skype for Business Online**または**Enterprise のプラン**のライセンスを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="2e564-200">[Assign or remove licenses for Office 365 for business](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc): Assign **Skype for Business Online** or **Enterprise Plan** licenses to everyone who is going to **host** a Broadcast meeting.</span></span>
    
2. <span data-ttu-id="2e564-p123">[Skype 会議メディアを有効にする](../set-up-your-network-for-skype-meeting-broadcast/enable-skype-meeting-broadcast.md): 既定では、この機能が有効になっています。有効にした後ことは、ユーザーは、組織内の他のユーザーとの会議をブロードキャストのホストにできるようになります。</span><span class="sxs-lookup"><span data-stu-id="2e564-p123">[Enable Skype Meeting Broadcast](../set-up-your-network-for-skype-meeting-broadcast/enable-skype-meeting-broadcast.md): By default, this feature isn't enabled. After you turn it on, your users will be able to host broadcast meetings with other people in your organization.</span></span>
    
3. <span data-ttu-id="2e564-203">[Skype 会議メディア用にネットワークを設定する](../set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast.md): 場合は、ホスト ウェビナーをブロードキャストの他の参加者と組織外部のネットワークを構成するのにはする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e564-203">[Set up your network for Skype Meeting Broadcast](../set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast.md): If you want to host webinars and other broadcasts with attendees outside of your organization, you need to configure your network.</span></span>
    
4. <span data-ttu-id="2e564-204">[スケジュールする Skype 会議メディア](http://support.office.com/article/c3995bc9-4d32-4f75-a004-3bc5c477e553)[に参加する Skype 会議メディア](http://support.office.com/article/14689da0-821d-48d4-9035-ea762de80ebe)を持っている: *https://portal.broadcast.skype.com*で Skype 会議メディアをスケジュールし、他のユーザーが作業をブロードキャスト会議に参加しようとするかどうかを確認します。会議します。</span><span class="sxs-lookup"><span data-stu-id="2e564-204">[Schedule a Skype Meeting Broadcast](http://support.office.com/article/c3995bc9-4d32-4f75-a004-3bc5c477e553) and have a [Join a Skype Meeting Broadcast](http://support.office.com/article/14689da0-821d-48d4-9035-ea762de80ebe): Make sure broadcast meetings work by scheduling a Skype Meeting Broadcast at  *https://portal.broadcast.skype.com*  and then having someone try to join the meeting.</span></span>
    
## <a name="learn-about-network-connectivity-requirements"></a><span data-ttu-id="2e564-205">ネットワーク接続の要件の詳細についてください。</span><span class="sxs-lookup"><span data-stu-id="2e564-205">Learn about network connectivity requirements</span></span>
<span data-ttu-id="2e564-206"><a name="bkmk_more"> </a></span><span class="sxs-lookup"><span data-stu-id="2e564-206"></span></span>

<span data-ttu-id="2e564-p124">音声、ビデオ、およびアプリケーション共有 Skype for Business での品質は大幅に影響を受ける-エンドツー エンド ネットワーク接続の質します。操作が最適なことが重要、会社のネットワークと Skype for Business Online の間の高品質の接続があるかどうかを確認します。ネットワークとチューニングについては、 [Skype for Business Online のパフォーマンスに微調整する](http://support.office.com/article/beec23c2-c5d6-4e84-a8af-e82aefca7802)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e564-p124">The quality of audio, video, and application sharing in Skype for Business is greatly impacted by the quality of end-to-end network connectivity. For an optimal experience, it is important to make sure there is a high-quality connection between your company network and Skype for Business Online. For network and tuning information, see [Tune Skype for Business Online performance](http://support.office.com/article/beec23c2-c5d6-4e84-a8af-e82aefca7802).</span></span>
  
## <a name="all-done-setting-up-getting-started-using-skype-for-business"></a><span data-ttu-id="2e564-p125">すべて実行セットアップよいですか。Skype for Business 使いを開始します。</span><span class="sxs-lookup"><span data-stu-id="2e564-p125">All done setting up? Getting started using Skype for Business</span></span>
<span data-ttu-id="2e564-212"><a name="bkmk_more"> </a></span><span class="sxs-lookup"><span data-stu-id="2e564-212"></span></span>

<span data-ttu-id="2e564-213">[Skype for Business のトレーニング](http://support.office.com/article/8a3491a3-c095-4718-80cf-cbbe4afe4eba): をすぐに使い始めるためのトレーニング トピックのリストを確認します。</span><span class="sxs-lookup"><span data-stu-id="2e564-213">[Skype for Business training](http://support.office.com/article/8a3491a3-c095-4718-80cf-cbbe4afe4eba): Check out this list of training topics to help you get started quickly!</span></span>
  
[<span data-ttu-id="2e564-214">Skype for Business 電話会議を開始します。</span><span class="sxs-lookup"><span data-stu-id="2e564-214">Start a Skype for Business conference call</span></span>](http://support.office.com/article/8dc8ac52-91ac-4db9-8672-11551fdaf997)
  
[<span data-ttu-id="2e564-215">Skype for Business でビデオ デバイス オプションを設定します。</span><span class="sxs-lookup"><span data-stu-id="2e564-215">Set Video Device options in Skype for Business</span></span>](http://support.office.com/article/d09017c0-deba-4f6c-a122-9eca6604f50c)
  
[<span data-ttu-id="2e564-216">Skype for Business 使い、ビデオ通話を送受信します。</span><span class="sxs-lookup"><span data-stu-id="2e564-216">Make and receive a video call using Skype for Business</span></span>](http://support.office.com/article/abf62493-670f-4b0d-b2cf-fe03b49caf42)
  
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a><span data-ttu-id="2e564-217">関連トピック</span><span class="sxs-lookup"><span data-stu-id="2e564-217">Related topics</span></span>
<span data-ttu-id="2e564-218"><a name="bkmk_more"> </a></span><span class="sxs-lookup"><span data-stu-id="2e564-218"></span></span>

[<span data-ttu-id="2e564-219">Skype for Business Server と Skype for Business Online の間のハイブリッド接続を計画します。</span><span class="sxs-lookup"><span data-stu-id="2e564-219">Plan hybrid connectivity between Skype for Business Server and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/p/?linkid=400791)
  

