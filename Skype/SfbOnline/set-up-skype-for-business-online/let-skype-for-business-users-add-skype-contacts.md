---
title: "ビジネス ユーザー向けの Skype Skype の連絡先を追加できるようにします。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/23/2018
ms.topic: article
ms.assetid: 08666236-1894-42ae-8846-e49232bbc460
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
- LIL_Placement
description: "ユーザーが組織外からビジネス ユーザーのビジネス用連絡先 Skype の Skype を使用しているし、連絡先リストに追加できるようにする方法を参照してください。 "
ms.openlocfilehash: 0e74cfb8efb08da404f0fdc9be611d9a3239d90f
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="let-skype-for-business-users-add-skype-contacts"></a><span data-ttu-id="da250-103">ビジネス ユーザー向けの Skype Skype の連絡先を追加できるようにします。</span><span class="sxs-lookup"><span data-stu-id="da250-103">Let Skype for Business users add Skype contacts</span></span>

<span data-ttu-id="da250-p101">Skype for Business を使ってユーザーを検索できますと Skype、無料のアプリを使用しているすべてのユーザーとの IM を使用します。この記事では、Skype の連絡先を追加するために必要な情報について説明します。</span><span class="sxs-lookup"><span data-stu-id="da250-p101">With Skype for Business, your users can search for and IM with everyone who uses Skype, the free app! This article explains what you need to do so they can add Skype contacts.</span></span> 
  
<span data-ttu-id="da250-106">これを行う Office 365 の[管理者権限](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d?ui=en-US&rs=en-US&ad=US)が必要です。</span><span class="sxs-lookup"><span data-stu-id="da250-106">You must have [admin permissions](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d?ui=en-US&rs=en-US&ad=US) in Office 365 to do this.</span></span>
  
1. <span data-ttu-id="da250-107">[Https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home#/homepage)で Office 365 の管理者アカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="da250-107">Sign in with your Office 365 admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home#/homepage).</span></span>
    
2. <span data-ttu-id="da250-108">Office 365 管理センターで、**管理センター**に移動 > **Skype for Business**します。</span><span class="sxs-lookup"><span data-stu-id="da250-108">In the Office 365 admin center, go to **Admin Centers** > **Skype for Business**.</span></span> 
    
    ![Skype for Business 管理センター] を選びます。](../images/376a7a45-e6e3-4716-be09-d2f294d885a2.png)
  
3. <span data-ttu-id="da250-110">**Skype for Business 管理センター**で、[**組織**] を選びます > **外部通信**します。</span><span class="sxs-lookup"><span data-stu-id="da250-110">In the **Skype for Business admin center**, choose **Organization** > **External communications**.</span></span> 
    
4. <span data-ttu-id="da250-111">既定では、ユーザーは、(この操作を許可するファイアウォールが構成されている場合) 向けの Skype を使用している、世界中の他のすべてのユーザーに連絡できます。</span><span class="sxs-lookup"><span data-stu-id="da250-111">By default, your users can communicate with all other people in the world who use Skype for Business (assuming your firewall has been configured to allow this).</span></span> 
    
    ![選択できるようにユーザーが Skype との通信に Skype for Business を使用します。](../images/333789f8-2ea6-4bbd-805b-18130f427999.png)
  
    <span data-ttu-id="da250-p102">ユーザーが、Skype ユーザーとチャットする向けの Skype を使用している他のユーザーとチャットするようにしたくない場合は、 **[許可ドメインのみ**を選択します。Skype ユーザーと連絡先を有効にしたときに skype.com が行われる処理できるドメインとして自動的に追加します。</span><span class="sxs-lookup"><span data-stu-id="da250-p102">If you want your users to chat with Skype users, BUT you don't want them to chat with others who use Skype for Business, choose **On only for allowed domains**. When you enable contact with Skype users, skype.com is automatically added as an allowed domain behind the scenes.</span></span> 
    
    <span data-ttu-id="da250-p103">向け、Skype を使用して特定の送信を除く、世界中に他のすべての企業から連絡先を許可する、選択する場合**の禁止ドメイン以外**、] を選びます**+**これらのドメインを追加します。すべてのユーザーは、これらの特定のドメインでユーザーを除く連絡することはできます。(企業によっては、このオプションを選択、たとえば、訴訟では、ことを確認する必要がある場合がないとその他のビジネス用連絡先)</span><span class="sxs-lookup"><span data-stu-id="da250-p103">If you want to allow contact from all other businesses in the world using Skype for Business, except specific ones, choose **On except for blocked domains**, and choose **+** to add those domains. Everyone will be able to contact you except people on those specific domains. (Some businesses might choose this option, for example, if they are in litigation and need to ensure there's no contact with the other business.)</span></span>
    
5. <span data-ttu-id="da250-118">**Skype for Business、組織外の Skype ユーザーとやり取りする際に使用できるように**する] を選びます。</span><span class="sxs-lookup"><span data-stu-id="da250-118">Choose **Let people use Skype for Business to communicate with Skype users outside your organization**.</span></span> 
    
6.  <span data-ttu-id="da250-119">Windows ファイアウォールを使っている場合は、Skype for Business が自動的に必要なポートを開きます。</span><span class="sxs-lookup"><span data-stu-id="da250-119">If you're using Windows Firewall, Skype for Business opens the required ports automatically.</span></span>
    
    <span data-ttu-id="da250-p104">組織では、インターネットに接続するネットワーク上のコンピューターを制限するに別のソリューションを使用している場合は、クライアント コンピューターは、すべての[IP アドレスと Url](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)の Skype の接続」と「Skype ディレクトリ検索にアクセスすることを確認します。これが必要になるファイアウォールまたはプロキシ インフラストラクチャ構成] ボックスの一覧を許可する、送信に追加します。</span><span class="sxs-lookup"><span data-stu-id="da250-p104">If your organization uses another solution to restrict computers on your network from connecting to the Internet, ensure client computers are able to access all of the [IP addresses and URLs](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) for Skype connectivity and Skype Directory Search. This may require adding them to the outbound allow list in your firewall or proxy infrastructure configuration.</span></span>
    
7. <span data-ttu-id="da250-p105">**テストするのには、最大 24 時間かかる**。外部通信] 設定を変更するには、すべてのデータ センターで設定を変更するには、最大 24 時間がかかることができます。</span><span class="sxs-lookup"><span data-stu-id="da250-p105">**WAIT UP TO 24 HOURS TO TEST**. Any time you change the external communications settings, it can take up to 24 hours for the changes to populate across all the data centers.</span></span>
    
8. <span data-ttu-id="da250-p106">ユーザーの検索し、Skype のビジネス用連絡先の一覧に Skype の連絡先を追加する方法を示します。[Skype for Business で連絡先を検索](https://support.office.com/en-us/article/b12500ef-e37f-4d22-aade-c11277e53f19)するには、それらをポイントします。</span><span class="sxs-lookup"><span data-stu-id="da250-p106">Show your users how to find and add Skype contacts to their list of Skype for Business contacts. Point them to [Search for people in Skype for Business](https://support.office.com/en-us/article/b12500ef-e37f-4d22-aade-c11277e53f19).</span></span>
    
## <a name="test-and-troubleshoot"></a><span data-ttu-id="da250-126">テスト、トラブルシューティングする.</span><span class="sxs-lookup"><span data-stu-id="da250-126">Test and troubleshoot</span></span>

<span data-ttu-id="da250-p107">設定をテストするのには、会社のファイアウォールの背後にない人 Skype で連絡先を必要があります。これらは、Gmail アカウントを Outlook.com アカウント、またはその他のメール アカウントの種類を使って Skype へのサインインことができます。</span><span class="sxs-lookup"><span data-stu-id="da250-p107">To test your setup, you need a contact on Skype who's not behind your company firewall. They can be signed in to Skype using a Gmail account, Outlook.com account, or other type of email account.</span></span>
  
1. <span data-ttu-id="da250-129">した後、 **24 まで待機する時間にテスト**の外部通信設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="da250-129">After you change your external communications settings, **WAIT UP TO 24 HOURS TO TEST**.</span></span>
    
2. <span data-ttu-id="da250-130">向けに Skype をサインアウトして、もう一度サインインため、Skype ディレクトリを検索する] オプションが表示します。</span><span class="sxs-lookup"><span data-stu-id="da250-130">Sign out of Skype for Business and then sign in again so you see the option to search the Skype Directory.</span></span> 
    
    ![Skype ディレクトリを強調表示されたら、Skype アカウントを所有するユーザーを検索できます。](../images/76ee9fab-1ac3-4f4a-9569-f5f2606dbb7a.png)
  
3. <span data-ttu-id="da250-132">Skype for Business] で、Skype の連絡先を検索し、[チャット出席依頼を送信します。</span><span class="sxs-lookup"><span data-stu-id="da250-132">In Skype for Business, search for your contact in Skype, and send a request to chat.</span></span> 
    
    <span data-ttu-id="da250-133">会社のポリシーが原因でそれを送信できなかったメッセージが表示される場合は、[ファイアウォールの設定](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)を確認してくださいする必要があります。</span><span class="sxs-lookup"><span data-stu-id="da250-133">If you get the message it couldn't be sent due to company policy, you need to double-check your [firewall settings](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2).</span></span> 
    
4. <span data-ttu-id="da250-134">問題は、ファイアウォール、喫茶店など、ファイアウォールの背後にあるいない wifi 場所に移動し、Skype for Business を使って Skype に要求を送信するかどうかをテストする別の方法では、チャットにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="da250-134">Another way to test whether the problem is your firewall is to go to a wifi location not behind your firewall such as a coffee shop, and use Skype for Business to send a request to your Skype contact to chat.</span></span> 
    
  - <span data-ttu-id="da250-p108">**Skype 連絡先要求を送信して受信することがないかどうかは**、チャット、出席依頼を送信するように依頼します。問題は、Skype と Skype for Business の間の接続を確立するが、多くの場合が解決されることです。</span><span class="sxs-lookup"><span data-stu-id="da250-p108">**If you sent your Skype contact a request and they never received it**, ask them to send you a request to chat. If the problem was establishing a connection between Skype and Skype for Business, that often solves it.</span></span>
    
  - <span data-ttu-id="da250-137">今すぐメッセージ喫茶店を通過するのにいないしたら職場で、[問題の場合は、ファイアウォールです。</span><span class="sxs-lookup"><span data-stu-id="da250-137">Now if the message goes through at the coffee shop but not when you're at work, then you know the problem is your firewall.</span></span> 
    
## <a name="what-you-can-and-cant-do"></a><span data-ttu-id="da250-138">何を実行できません。</span><span class="sxs-lookup"><span data-stu-id="da250-138">What you can and can't do</span></span>

- <span data-ttu-id="da250-139">**Skype for Business Mac で**検索して、Skype の連絡先と通信する機能がありません。</span><span class="sxs-lookup"><span data-stu-id="da250-139">**Skype for Business on Mac** doesn't have the ability to search for and communicate with Skype contacts.</span></span>
    
- <span data-ttu-id="da250-p109">ディレクトリの検索を有効にすると、検索、ビジネス ユーザーの Skype と Skype を検索することができます。ディレクトリを検索することにより、それらを見つけられない何らかの理由を連絡先の依頼を送信して、[Skype にサインインし、同意してができる場合、im を送信できますにします。</span><span class="sxs-lookup"><span data-stu-id="da250-p109">When directory search is enabled, you can search for and find Skype and Skype for Business users. If for some reason you can't find them by searching the directory, you can send them a contact request, and then have them sign in to Skype and accept it, so you can IM with them.</span></span> 
    
- <span data-ttu-id="da250-p110">場合によっては、Google、Facebook などの他の IM プロバイダーとの IM 接続を許可することはできません。携帯電話のテキスト メッセージを送信するのには、Skype for Business を使うことはできません。</span><span class="sxs-lookup"><span data-stu-id="da250-p110">It's not possible to allow IM connectivity with other IM providers such as Google or Facebook. You can't use Skype for Business to send cell phone text messages.</span></span>
    
## <a name="what-features-are-available-when-adding-skype-contacts"></a><span data-ttu-id="da250-144">Skype の連絡先を追加するときに、どのような機能を使えますか。</span><span class="sxs-lookup"><span data-stu-id="da250-144">What features are available when adding Skype contacts?</span></span>

<span data-ttu-id="da250-145">Microsoft アカウント (旧 Windows Live ID) を使ってサインインした Skype の連絡先は、いくつかにアクセスできる、Skype for Business ユーザーと通信するときに、すべての機能はします。</span><span class="sxs-lookup"><span data-stu-id="da250-145">Skype contacts who signed in with their Microsoft account (formerly Windows Live ID) can get some, but not all, features when they are talking to your Skype for Business users.</span></span>
  
|<span data-ttu-id="da250-146">**Skype の連絡先との連絡可能**</span><span class="sxs-lookup"><span data-stu-id="da250-146">**Available with Skype contacts**</span></span>|<span data-ttu-id="da250-147">**Skype の連絡先では使用できません。**</span><span class="sxs-lookup"><span data-stu-id="da250-147">**Not available with Skype contacts**</span></span>|
|:-----|:-----|
| <span data-ttu-id="da250-148">ビデオ会話</span><span class="sxs-lookup"><span data-stu-id="da250-148">Video conversations</span></span> <br/>  <span data-ttu-id="da250-149">ユーザー間のインスタント メッセージング</span><span class="sxs-lookup"><span data-stu-id="da250-149">Person-to-person instant messaging</span></span> <br/>  <span data-ttu-id="da250-150">プレゼンス</span><span class="sxs-lookup"><span data-stu-id="da250-150">Presence</span></span> <br/> | <span data-ttu-id="da250-151">マルチパーティ IM での会話</span><span class="sxs-lookup"><span data-stu-id="da250-151">Multi-party IM conversations</span></span> <br/>  <span data-ttu-id="da250-152">3 つ以上のユーザーとの音声とビデオの会話</span><span class="sxs-lookup"><span data-stu-id="da250-152">Audio and video conversations with three or more people</span></span> <br/>  <span data-ttu-id="da250-153">デスクトップとプログラムの共有</span><span class="sxs-lookup"><span data-stu-id="da250-153">Desktop and program sharing</span></span> <br/> |
   
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a><span data-ttu-id="da250-154">関連トピック</span><span class="sxs-lookup"><span data-stu-id="da250-154">Related topics</span></span>

[<span data-ttu-id="da250-155">ビジネス ユーザー向けの Skype の外部の連絡先にユーザーを許可します。</span><span class="sxs-lookup"><span data-stu-id="da250-155">Allow users to contact external Skype for Business users</span></span>](allow-users-to-contact-external-skype-for-business-users.md)
  
[<span data-ttu-id="da250-156">Skype for Business Online をセットアップします。</span><span class="sxs-lookup"><span data-stu-id="da250-156">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)
