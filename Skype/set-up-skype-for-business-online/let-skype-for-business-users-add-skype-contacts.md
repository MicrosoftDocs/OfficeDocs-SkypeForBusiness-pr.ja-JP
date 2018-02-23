---
title: "Skype for Business ユーザーが Skype 連絡先を追加できるようにする"
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
description: "Skype for Business を使用しているユーザーが、組織外部の Skype for Business ユーザーに連絡したり、それらを連絡先のリストに追加したりできるようになる方法を確認します。 "
ms.openlocfilehash: 8f6ca948434d9b5a63788cbb5bc54ad6297843e2
ms.sourcegitcommit: 46ca433590a4c3aefbe2fb777542bb0b332563bf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2018
---
# <a name="let-skype-for-business-users-add-skype-contacts"></a><span data-ttu-id="18662-103">Skype for Business ユーザーが Skype 連絡先を追加できるようにする</span><span class="sxs-lookup"><span data-stu-id="18662-103">Let Skype for Business users add Skype contacts</span></span>

<span data-ttu-id="18662-104">Skype for Business では、自分の組織のユーザーは無料の Skype を使用しているあらゆるユーザーを検索したり、それらのユーザーにインスタント メッセージを送信したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="18662-104">With Skype for Business, your users can search for and IM with everyone who uses Skype, the free app!</span></span> <span data-ttu-id="18662-105">この記事では、ユーザーが Skype 連絡先を追加できるようになるために何を行う必要があるかについて説明します。</span><span class="sxs-lookup"><span data-stu-id="18662-105">This article explains what you need to do so they can add Skype contacts.</span></span> 
  
<span data-ttu-id="18662-106">この操作を行うには Office 365 での[管理者のアクセス許可](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d?ui=en-US&rs=en-US&ad=US)を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="18662-106">You must have [admin permissions](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d?ui=en-US&rs=en-US&ad=US) in Office 365 to do this.</span></span>
  
1. <span data-ttu-id="18662-107">[https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home#/homepage)で Office 365 の管理者アカウントを使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="18662-107">Sign in with your Office 365 global admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home#/homepage).</span></span>
    
2. <span data-ttu-id="18662-108">Office 365 管理センターで、[**管理センター**]  >  [**Skype for Business**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="18662-108">In the Office 365 admin center, go to **Admin Centers** > **Skype for Business**.</span></span> 
    
    ![Skype for Business 管理センターを選択します。](../images/376a7a45-e6e3-4716-be09-d2f294d885a2.png)
  
3. <span data-ttu-id="18662-110">[**Skype for Business 管理センター**] で、[**組織**]  >  [**外部通信**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="18662-110">In the **Skype for Business admin center**, choose **Audio conferencing**.</span></span> 
    
4. <span data-ttu-id="18662-111">既定では、自分の組織のユーザーは Skype for Business を使用する世界中の他のユーザーと通信することができます (お使いのファイアウォールが通信を許可するよう構成されていることが前提です)。</span><span class="sxs-lookup"><span data-stu-id="18662-111">By default, your users can communicate with all other people in the world who use Skype for Business (assuming your firewall has been configured to allow this).</span></span> 
    
    ![[Skype for Business を使って組織外の Skype ユーザーと通信できるようにします] を選択します。](../images/333789f8-2ea6-4bbd-805b-18130f427999.png)
  
    <span data-ttu-id="18662-113">自分の組織のユーザーが Skype ユーザーとチャットするようにして、Skype for Business を使用する他のユーザーとはチャットしないようにする場合は、[**許可したドメインに対してのみオンにする**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="18662-113">If you want your users to chat with Skype users, BUT you don't want them to chat with others who use Skype for Business, choose **On only for allowed domains**.</span></span> <span data-ttu-id="18662-114">Skype ユーザーとの連絡を有効にすると、skype.com はバックグラウンドで許可されたドメインとして自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="18662-114">When you enable contact with Skype users, skype.com is automatically added as an allowed domain behind the scenes.</span></span> 
    
    <span data-ttu-id="18662-115">特定の企業を除く、Skype fo Business を使用する世界中のすべての企業からの連絡を許可する場合は、[**禁止したドメインを除いてオンにする**] を選び、[**+**] を選んで該当するドメインを追加します。</span><span class="sxs-lookup"><span data-stu-id="18662-115">If you want to allow contact from all other businesses in the world using Skype for Business, except specific ones, choose **On except for blocked domains**, and choose **+** to add those domains.</span></span> <span data-ttu-id="18662-116">これらの特定のドメイン上のユーザーを除くすべてのユーザーが自分に連絡できるようになります。</span><span class="sxs-lookup"><span data-stu-id="18662-116">Everyone will be able to contact you except people on those specific domains.</span></span> <span data-ttu-id="18662-117">(企業によっては、訴訟中で他の企業と連絡を取ることがないようにする必要がある場合などに、このオプションを選択する可能性があります。)</span><span class="sxs-lookup"><span data-stu-id="18662-117">(Some businesses might choose this option, for example, if they are in litigation and need to ensure there's no contact with the other business.)</span></span>
    
5. <span data-ttu-id="18662-118">[**他のユーザーに Skype for Business の使用を許可して、組織外の Skype ユーザーと通信します**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="18662-118">Choose **Let people use Skype for Business to communicate with Skype users outside your organization**.</span></span> 
    
6.  <span data-ttu-id="18662-119">Windows Firewall を使用している場合、Skype for Business は必要なポートを自動的に開きます。</span><span class="sxs-lookup"><span data-stu-id="18662-119">If you're using Windows Firewall, Skype for Business opens the required ports automatically.</span></span>
    
    <span data-ttu-id="18662-120">組織でネットワーク上のコンピューターがインターネットに接続するのを制限するために別のソリューションを使用している場合は、クライアント コンピューターが Skype 接続および Skype ディレクトリ検索のためにすべての [IP アドレスと URL](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)  にアクセスできることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="18662-120">If your organization uses another solution to restrict computers on your network from connecting to the Internet, ensure client computers are able to access all of the [IP addresses and URLs](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) for Skype connectivity and Skype Directory Search.</span></span> <span data-ttu-id="18662-121">これにより、ファイアウォールまたはプロキシのインフラストラクチャ構成の発信許可リストに、これらの IP アドレスと URL を追加する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="18662-121">This may require adding them to the outbound allow list in your firewall or proxy infrastructure configuration.</span></span>
    
7. <span data-ttu-id="18662-122">**テストのために最大 24 時間待機します**。</span><span class="sxs-lookup"><span data-stu-id="18662-122">**WAIT UP TO 24 HOURS TO TEST**.</span></span> <span data-ttu-id="18662-123">外部通信設定を変更したときはいつでも、変更がデータ センター全体に行き渡るまでに最大 24 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="18662-123">Any time you change the external communications settings, it can take up to 24 hours for the changes to populate across all the data centers.</span></span>
    
8. <span data-ttu-id="18662-124">自分の組織のユーザーに Skype 連絡先を検索して Skype for Business 連絡先のリストに追加する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="18662-124">Show your users how to find and add Skype contacts to their list of Skype for Business contacts.</span></span> <span data-ttu-id="18662-125">それらのユーザーに対して、[Skype for Business で知り合いを検索する](https://support.office.com/en-us/article/b12500ef-e37f-4d22-aade-c11277e53f19)ように仕向けます。</span><span class="sxs-lookup"><span data-stu-id="18662-125">Point them to [Search for people in Skype for Business](https://support.office.com/en-us/article/b12500ef-e37f-4d22-aade-c11277e53f19).</span></span>
    
## <a name="test-and-troubleshoot"></a><span data-ttu-id="18662-126">テストとトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="18662-126">Test and troubleshoot</span></span>

<span data-ttu-id="18662-127">セットアップをテストするには、会社のファイアウォールの背後にいない、Skype 上の連絡先が必要です。</span><span class="sxs-lookup"><span data-stu-id="18662-127">To test your setup, you need a contact on Skype who's not behind your company firewall.</span></span> <span data-ttu-id="18662-128">Gmail アカウント、Outlook.com アカウント、またはその他の種類の電子メール アカウントを使用して Skype にサインインできます。</span><span class="sxs-lookup"><span data-stu-id="18662-128">They can be signed in to Skype using a Gmail account, Outlook.com account, or other type of email account.</span></span>
  
1. <span data-ttu-id="18662-129">外部通信設定を変更した後、**テストのために最大 24 時間待機します**。</span><span class="sxs-lookup"><span data-stu-id="18662-129">After you change your external communications settings, **WAIT UP TO 24 HOURS TO TEST**.</span></span>
    
2. <span data-ttu-id="18662-130">Skype for Business をサインアウトして、再びサインインすると、Skype ディレクトリを検索するオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="18662-130">Sign out of Skype for Business and then sign in again so you see the option to search the Skype Directory.</span></span> 
    
    ![Skype ディレクトリが強調表示されている場合、Skype アカウントを持つユーザーを検索できます。](../images/76ee9fab-1ac3-4f4a-9569-f5f2606dbb7a.png)
  
3. <span data-ttu-id="18662-132">Skype for Business で、Skype の連絡先を検索し、チャットのリクエストを送信します。</span><span class="sxs-lookup"><span data-stu-id="18662-132">In Skype for Business, search for your contact in Skype, and send a request to chat.</span></span> 
    
    <span data-ttu-id="18662-133">会社のポリシーのためにリクエストを送信できなかったというメッセージを受け取る場合は、[ファイアウォールの設定](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)をダブルチェックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="18662-133">If you get the message it couldn't be sent due to company policy, you need to double-check your [firewall settings](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2).</span></span> 
    
4. <span data-ttu-id="18662-134">問題がファイアウォールであるかどうかをテストする別の手段として、お使いのファイアウォールの背後ではないコーヒー ショップなどの WiFi を利用できる場所で Skype for Business を使用して Skype 連絡先にチャットのリクエストを送信する方法があります。</span><span class="sxs-lookup"><span data-stu-id="18662-134">Another way to test whether the problem is your firewall is to go to a wifi location not behind your firewall such as a coffee shop, and use Skype for Business to send a request to your Skype contact to chat.</span></span> 
    
  - <span data-ttu-id="18662-135">**Skype 連絡先にリクエストを送信したのに**、受信されていない場合は、チャットするためのリクエストを自分宛てに送信してもらいます。</span><span class="sxs-lookup"><span data-stu-id="18662-135">**If you sent your Skype contact a request and they never received it**, ask them to send you a request to chat.</span></span> <span data-ttu-id="18662-136">Skype と Skype for Business との間の接続に問題がある場合は、これにより問題が解決する可能性が高いです。</span><span class="sxs-lookup"><span data-stu-id="18662-136">If the problem was establishing a connection between Skype and Skype for Business, that often solves it.</span></span>
    
  - <span data-ttu-id="18662-137">メッセージがコーヒー ショップでは送られるのに職場では送られない場合は、ファイアウォールが問題であることがわかります。</span><span class="sxs-lookup"><span data-stu-id="18662-137">Now if the message goes through at the coffee shop but not when you're at work, then you know the problem is your firewall.</span></span> 
    
## <a name="what-you-can-and-cant-do"></a><span data-ttu-id="18662-138">実行できる操作と実行できない操作</span><span class="sxs-lookup"><span data-stu-id="18662-138">What you can and can't do</span></span>

- <span data-ttu-id="18662-139">**Mac 版 Skype for Business** には Skype の連絡先を検索して通信相手とする機能がありません。</span><span class="sxs-lookup"><span data-stu-id="18662-139">**Skype for Business on Mac** doesn't have the ability to search for and communicate with Skype contacts.</span></span>
    
- <span data-ttu-id="18662-140">ディレクトリ検索が有効になっている場合、Skype および Skype for Business のユーザーを検索して見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="18662-140">When directory search is enabled, you can search for and find Skype and Skype for Business users.</span></span> <span data-ttu-id="18662-141">何らかの理由によりディレクトリを検索してもユーザーを見つけられない場合は、連絡先追加のリクエストをそれらのユーザーに送信して、Skype にサインインしてリクエストを承諾してもらい、インスタント メッセージを送ることができます。</span><span class="sxs-lookup"><span data-stu-id="18662-141">If for some reason you can't find them by searching the directory, you can send them a contact request, and then have them sign in to Skype and accept it, so you can IM with them.</span></span> 
    
- <span data-ttu-id="18662-142">Google や Facebook などのインスタント メッセージ プロバイダーとのインスタント メッセージによる接続を許可することはできません。</span><span class="sxs-lookup"><span data-stu-id="18662-142">It's not possible to allow IM connectivity with other IM providers such as Google or Facebook.</span></span> <span data-ttu-id="18662-143">Skype for Business を使用して携帯電話のテキストメッセージを送信することはできません。</span><span class="sxs-lookup"><span data-stu-id="18662-143">You can't use Skype for Business to send cell phone text messages.</span></span>

- <span data-ttu-id="18662-144">Skype 連絡先と Skype for Business 連絡先との間の音声通話やビデオ通話を記録することはできません。</span><span class="sxs-lookup"><span data-stu-id="18662-144">It is not possible to record audio or video calls between a Skype Contact and Skype for Business contact.</span></span>
    
## <a name="what-features-are-available-when-adding-skype-contacts"></a><span data-ttu-id="18662-145">Skype 連絡先を追加すると利用できるようになる機能を教えてください。</span><span class="sxs-lookup"><span data-stu-id="18662-145">What features are available when adding Skype contacts?</span></span>

<span data-ttu-id="18662-146">Microsoft アカウント (旧称 Windows Live ID) でサインインした Skype 連絡先は、Skype for Business ユーザーと話すときに一部の機能を使用できますが、すべての機能を使用できるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="18662-146">Skype contacts who signed in with their Microsoft account (formerly Windows Live ID) can get some, but not all, features when they are talking to your Skype for Business users.</span></span>
  
|<span data-ttu-id="18662-147">**Skype 連絡先との間で使用可能**</span><span class="sxs-lookup"><span data-stu-id="18662-147">**Available with Skype contacts**</span></span>|<span data-ttu-id="18662-148">**Skype 連絡先との間では使用不可**</span><span class="sxs-lookup"><span data-stu-id="18662-148">**Not available with Skype contacts**</span></span>|
|:-----|:-----|
| <span data-ttu-id="18662-149">ビデオ会話</span><span class="sxs-lookup"><span data-stu-id="18662-149">Video conversations</span></span> <br/>  <span data-ttu-id="18662-150">ユーザー間のインスタント メッセージング</span><span class="sxs-lookup"><span data-stu-id="18662-150">Person-to-person instant messaging</span></span> <br/>  <span data-ttu-id="18662-151">プレゼンス</span><span class="sxs-lookup"><span data-stu-id="18662-151">Presence</span></span> <br/> | <span data-ttu-id="18662-152">マルチパーティの IM 会話</span><span class="sxs-lookup"><span data-stu-id="18662-152">Multi-party IM conversations</span></span> <br/>  <span data-ttu-id="18662-153">3 人以上のユーザーでの音声およびビデオでの会話</span><span class="sxs-lookup"><span data-stu-id="18662-153">Audio and video conversations with three or more people</span></span> <br/>  <span data-ttu-id="18662-154">デスクトップおよびプログラムの共有</span><span class="sxs-lookup"><span data-stu-id="18662-154">Desktop and program sharing</span></span> <br/> |
   
[!INCLUDE [LinkedIn Learning Info](../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a><span data-ttu-id="18662-155">関連トピック</span><span class="sxs-lookup"><span data-stu-id="18662-155">Related topics</span></span>

[<span data-ttu-id="18662-156">外部の Skype for Business ユーザーに連絡できるようにする</span><span class="sxs-lookup"><span data-stu-id="18662-156">Allow users to contact external Skype for Business users</span></span>](allow-users-to-contact-external-skype-for-business-users.md)
  
[<span data-ttu-id="18662-157">Skype for Business Online のセットアップ</span><span class="sxs-lookup"><span data-stu-id="18662-157">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)
