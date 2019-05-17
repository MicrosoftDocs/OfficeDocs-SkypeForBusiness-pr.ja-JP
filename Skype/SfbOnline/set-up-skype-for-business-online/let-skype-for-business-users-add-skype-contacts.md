---
title: Skype for Business ユーザーが Skype の連絡先を追加できるようにする
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 08666236-1894-42ae-8846-e49232bbc460
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
- LIL_Placement
description: 'Skype for Business を使用しているユーザーが、組織外の Skype for Business ユーザーと連絡を取り、連絡先の一覧に追加できるようにする方法を説明します。 '
ms.openlocfilehash: 212393154cb2b730ce18f5be9b03495e747e207c
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32238034"
---
# <a name="let-skype-for-business-users-add-skype-contacts"></a><span data-ttu-id="1bcf1-103">Skype for Business ユーザーが Skype の連絡先を追加できるようにする</span><span class="sxs-lookup"><span data-stu-id="1bcf1-103">Let Skype for Business users add Skype contacts</span></span>

<span data-ttu-id="1bcf1-104">Skype for Business では、ユーザーは無料アプリ Skype を使用するすべての人を検索し、インスタント メッセージ (IM) を送信することができます!</span><span class="sxs-lookup"><span data-stu-id="1bcf1-104">With Skype for Business, your users can search for and IM with everyone who uses Skype, the free app!</span></span> <span data-ttu-id="1bcf1-105">この記事では、Skype の連絡先を追加するために必要な操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="1bcf1-105">This article explains what you need to do so they can add Skype contacts.</span></span> 
  
<span data-ttu-id="1bcf1-106">Office 365 でこれを行うには、[管理者アクセス許可](https://support.office.com/ja-JP/article/da585eea-f576-4f55-a1e0-87090b6aaa9d?ui=en-US&rs=en-US&ad=US)が必要です。</span><span class="sxs-lookup"><span data-stu-id="1bcf1-106">You must have [admin permissions](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d?ui=en-US&rs=en-US&ad=US) in Office 365 to do this.</span></span>

<span data-ttu-id="1bcf1-107">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Skype for Business 管理センターを使用する**</span><span class="sxs-lookup"><span data-stu-id="1bcf1-107">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
  
1. <span data-ttu-id="1bcf1-108">[https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home#/homepage) で、Office 365 管理者アカウントを使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="1bcf1-108">Sign in with your Office 365 global admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home#/homepage).</span></span>
    
2. <span data-ttu-id="1bcf1-109">Office 365 管理センターから **[管理センター** > **[Skype for Business]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="1bcf1-109">In the Office 365 admin center, go to **Admin Centers** > **Skype for Business**.</span></span> 
    
    ![Skype for Business 管理センターを選択します。](../images/376a7a45-e6e3-4716-be09-d2f294d885a2.png)
  
3. <span data-ttu-id="1bcf1-111">**Skype for Business 管理センター**で、[**組織**]  >  [**外部通信**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="1bcf1-111">In the **Skype for Business admin center**, choose **Organization** > **External communications**.</span></span> 
    
4. <span data-ttu-id="1bcf1-112">既定では、ユーザーは Skype for Business を使用している世界中の他のすべてのユーザーと通信できます (ファイアウォールがこれを許可するように構成されていると仮定します)。</span><span class="sxs-lookup"><span data-stu-id="1bcf1-112">By default, your users can communicate with all other people in the world who use Skype for Business (assuming your firewall has been configured to allow this).</span></span> 
    
    ![[ユーザーが Skype for Business を使用して Skype と通信できるようにする] を選択します。](../images/333789f8-2ea6-4bbd-805b-18130f427999.png)
  
    <span data-ttu-id="1bcf1-114">ユーザーが Skype ユーザーとチャットできても、Skype for Business を使用している他のユーザーとはチャットできないようにする場合は、**[許可されたドメインに対してのみ有効にする]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1bcf1-114">If you want your users to chat with Skype users, BUT you don't want them to chat with others who use Skype for Business, choose **On only for allowed domains**.</span></span> <span data-ttu-id="1bcf1-115">Skype ユーザーとの連絡を有効にすると、skype.com が許可されたドメインとして、自動的にバックグラウンドで追加されます。</span><span class="sxs-lookup"><span data-stu-id="1bcf1-115">When you enable contact with Skype users, skype.com is automatically added as an allowed domain behind the scenes.</span></span> 
    
    <span data-ttu-id="1bcf1-116">特定の連絡先を除く、Skype For Business を使用する世界中のすべての企業からの通信を許可する場合、**[ブロックされたドメインを除く]** を選択し、**[+]** を選択して、該当するドメインを追加します。</span><span class="sxs-lookup"><span data-stu-id="1bcf1-116">If you want to allow contact from all other businesses in the world using Skype for Business, except specific ones, choose **On except for blocked domains**, and choose **+** to add those domains.</span></span> <span data-ttu-id="1bcf1-117">その特定ドメインのユーザーを除く、すべてのユーザーと通信できるようになります。</span><span class="sxs-lookup"><span data-stu-id="1bcf1-117">Everyone will be able to contact you except people on those specific domains.</span></span> <span data-ttu-id="1bcf1-118">(たとえば一部の企業では、訴訟において相手企業と接触していないことを確証する必要があるため、このオプションを選択する場合があります。)</span><span class="sxs-lookup"><span data-stu-id="1bcf1-118">(Some businesses might choose this option, for example, if they are in litigation and need to ensure there's no contact with the other business.)</span></span>
    
5. <span data-ttu-id="1bcf1-119">**[ユーザーが Skype for Business を使用して組織外の Skype と通信できるようにする]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1bcf1-119">Choose **Let people use Skype for Business to communicate with Skype users outside your organization**.</span></span> 
    
6.  <span data-ttu-id="1bcf1-120">Windows ファイアウォールを使用している場合、Skype for Business では必要なポートが自動的に開きます。</span><span class="sxs-lookup"><span data-stu-id="1bcf1-120">If you're using Windows Firewall, Skype for Business opens the required ports automatically.</span></span>
    
    <span data-ttu-id="1bcf1-121">組織が、別のソリューションを使用して、ネットワーク上のコンピューターのインターネット接続を制限している場合は、クライアント コンピューターがすべての [IP アドレスと URI](https://support.office.com/ja-JP/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) にアクセスして Skype 接続と Skype ディレクトリ検索を実行できるようにします。</span><span class="sxs-lookup"><span data-stu-id="1bcf1-121">If your organization uses another solution to restrict computers on your network from connecting to the Internet, ensure client computers are able to access all of the [IP addresses and URLs](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) for Skype connectivity and Skype Directory Search.</span></span> <span data-ttu-id="1bcf1-122">この場合、ファイアウォールまたはプロキシ インフラストラクチャ構成で、それらを送信許可リストに追加する必要がある可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1bcf1-122">This may require adding them to the outbound allow list in your firewall or proxy infrastructure configuration.</span></span>
    
7. <span data-ttu-id="1bcf1-123">**テストするため最大 24 時間待ちます**。</span><span class="sxs-lookup"><span data-stu-id="1bcf1-123">**WAIT UP TO 24 HOURS TO TEST**.</span></span> <span data-ttu-id="1bcf1-124">外部通信の設定を変更すると、すべてのデータ センターに変更が反映されるまでに最大で 24 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="1bcf1-124">Any time you change the external communications settings, it can take up to 24 hours for the changes to populate across all the data centers.</span></span>
    
8. <span data-ttu-id="1bcf1-125">ユーザーに、Skype for Business の連絡先の一覧に Skype の連絡先を検索し追加する方法を伝えます。</span><span class="sxs-lookup"><span data-stu-id="1bcf1-125">Show your users how to find and add Skype contacts to their list of Skype for Business contacts.</span></span> <span data-ttu-id="1bcf1-126">「[Skype for Business で知り合いを検索する](https://support.office.com/ja-JP/article/b12500ef-e37f-4d22-aade-c11277e53f19)」を参照してもらいます。</span><span class="sxs-lookup"><span data-stu-id="1bcf1-126">Point them to [Search for people in Skype for Business](https://support.office.com/en-us/article/b12500ef-e37f-4d22-aade-c11277e53f19).</span></span>
    
## <a name="test-and-troubleshoot"></a><span data-ttu-id="1bcf1-127">テストとトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="1bcf1-127">Test and troubleshoot</span></span>

<span data-ttu-id="1bcf1-128">設定をテストするには、会社のファイアウォールの外側にいる Skype の連絡先が必要です。</span><span class="sxs-lookup"><span data-stu-id="1bcf1-128">To test your setup, you need a Teams user who's not behind your firewall.</span></span> <span data-ttu-id="1bcf1-129">Gmail アカウント、Outlook.com アカウント、その他のメール アカウントを使用して、Skype にサインインできます。</span><span class="sxs-lookup"><span data-stu-id="1bcf1-129">They can be signed in to Skype using a Gmail account, Outlook.com account, or other type of email account.</span></span>
  
1. <span data-ttu-id="1bcf1-130">外部通信設定を変更した後、**テストするため最大 24 時間待ちます**。</span><span class="sxs-lookup"><span data-stu-id="1bcf1-130">After you change your external communications settings, **WAIT UP TO 24 HOURS TO TEST**.</span></span>
    
2. <span data-ttu-id="1bcf1-131">Skype for Business からサインアウトし、もう一度サインインすると、Skype ディレクトリの検索オプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1bcf1-131">Sign out of Skype for Business and then sign in again so you see the option to search the Skype Directory.</span></span> 
    
    ![Skype ディレクトリが強調表示されていたら、Skype アカウントを持つユーザーを検索できます。](../images/76ee9fab-1ac3-4f4a-9569-f5f2606dbb7a.png)
  
3. <span data-ttu-id="1bcf1-133">Skype for Business で、Skype の連絡先を検索し、チャットの要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="1bcf1-133">In Skype for Business, search for your contact in Skype, and send a request to chat.</span></span> 
    
    <span data-ttu-id="1bcf1-134">会社のポリシーが原因で送信できないというメッセージが表示される場合、[ファイアウォール設定](https://support.office.com/ja-JP/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)を再度確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1bcf1-134">If you get the message it couldn't be sent due to company policy, you need to double-check your [firewall settings](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2).</span></span> 
    
4. <span data-ttu-id="1bcf1-135">問題の原因がお客様のファイアウォールかどうかを別の方法でテストするには、ファイアウォールの外側の WiFi エリア (カフェなど) に行き、Skype for Business を使用して Skype の連絡先にチャットの要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="1bcf1-135">Another way to test whether the problem is your firewall is to go to a wifi location not behind your firewall such as a coffee shop, and use Teams to send a request to your contact to chat.</span></span> 
    
   - <span data-ttu-id="1bcf1-136">**Skype の連絡先にリクエストを送信したのに相手が受け取っていない場合**、チャットの要求を送信するように依頼します。</span><span class="sxs-lookup"><span data-stu-id="1bcf1-136">**If you sent your Skype contact a request and they never received it**, ask them to send you a request to chat.</span></span> <span data-ttu-id="1bcf1-137">Skype と Skype for Business 間の接続の確立に問題が発生していた場合は、たいていこれで解決します。</span><span class="sxs-lookup"><span data-stu-id="1bcf1-137">If the problem was establishing a connection between Skype and Skype for Business, that often solves it.</span></span>
    
   - <span data-ttu-id="1bcf1-138">メッセージをカフェからは送信できる一方、職場からは送信できない場合は、問題の原因は職場のファイアウォールであることが特定できます。</span><span class="sxs-lookup"><span data-stu-id="1bcf1-138">If the message goes through there, but not when you're at work, then you know the problem is your firewall.</span></span> 
    
## <a name="what-you-can-and-cant-do"></a><span data-ttu-id="1bcf1-139">実行できること、できないこと</span><span class="sxs-lookup"><span data-stu-id="1bcf1-139">What you can and can't do</span></span>

- <span data-ttu-id="1bcf1-140">**Mac 版 Skype for Business** では、Skype の連絡先を検索し通信する機能はありません。</span><span class="sxs-lookup"><span data-stu-id="1bcf1-140">**Skype for Business on Mac** doesn't have the ability to search for and communicate with Skype contacts.</span></span>
    
- <span data-ttu-id="1bcf1-141">ディレクトリの検索を有効にすると、Skype ユーザーや Skype for Business ユーザーを検索できます。</span><span class="sxs-lookup"><span data-stu-id="1bcf1-141">When directory search is enabled, you can search for and find Skype and Skype for Business users.</span></span> <span data-ttu-id="1bcf1-142">何らかの理由でディレクトリを検索しても見つからない場合は、連絡先リクエストを送信して、Skype にサインインして同意してもらうことで、インスタント メッセージ (IM) の送信が可能になります。</span><span class="sxs-lookup"><span data-stu-id="1bcf1-142">If for some reason you can't find them by searching the directory, you can send them a contact request, and then have them sign in to Skype and accept it, so you can IM with them.</span></span> 
    
- <span data-ttu-id="1bcf1-143">Google、Facebook などの他の IM プロバイダーとの IM 接続を許可することはできません。</span><span class="sxs-lookup"><span data-stu-id="1bcf1-143">It's not possible to allow IM connectivity with other IM providers such as Google or Facebook.</span></span> <span data-ttu-id="1bcf1-144">Skype for Business を使用して、携帯電話のテキスト メッセージを送信することはできません。</span><span class="sxs-lookup"><span data-stu-id="1bcf1-144">You can't use Skype for Business to send cell phone text messages.</span></span>

- <span data-ttu-id="1bcf1-145">Skype の連絡先と Skype for Business の連絡先の間でオーディオまたはビデオ通話を記録することはできません。</span><span class="sxs-lookup"><span data-stu-id="1bcf1-145">It is not possible to record audio or video calls between a Skype Contact and Skype for Business contact.</span></span>
    
## <a name="what-features-are-available-when-adding-skype-contacts"></a><span data-ttu-id="1bcf1-146">Skype の連絡先を追加すると、どんな機能を使えますか?</span><span class="sxs-lookup"><span data-stu-id="1bcf1-146">What features are available when adding Skype contacts?</span></span>

<span data-ttu-id="1bcf1-147">Microsoft アカウント (以前の Windows Live ID) でサインインしている Skype の連絡先は、Skype for Business ユーザーとの通話時に一部の機能を使えますが、すべての機能が使用できるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="1bcf1-147">Skype contacts who signed in with their Microsoft account (formerly Windows Live ID) can get some, but not all, features when they are talking to your Skype for Business users.</span></span>
  
|<span data-ttu-id="1bcf1-148">**Skype の連絡先との間で利用できる機能**</span><span class="sxs-lookup"><span data-stu-id="1bcf1-148">**Available with Skype contacts**</span></span>|<span data-ttu-id="1bcf1-149">**Skype の連絡先との間で利用できない機能**</span><span class="sxs-lookup"><span data-stu-id="1bcf1-149">**Not available with Skype contacts**</span></span>|
|:-----|:-----|
| <span data-ttu-id="1bcf1-150">ビデオ会話</span><span class="sxs-lookup"><span data-stu-id="1bcf1-150">Video conversations</span></span> <br/>  <span data-ttu-id="1bcf1-151">ユーザー間のインスタント メッセージング</span><span class="sxs-lookup"><span data-stu-id="1bcf1-151">Person-to-person instant messaging</span></span> <br/>  <span data-ttu-id="1bcf1-152">プレゼンス</span><span class="sxs-lookup"><span data-stu-id="1bcf1-152">Presence</span></span> <br/> | <span data-ttu-id="1bcf1-153">マルチ パーティの IM 会話</span><span class="sxs-lookup"><span data-stu-id="1bcf1-153">Multi-party IM conversations</span></span> <br/>  <span data-ttu-id="1bcf1-154">3 人以上でのオーディオやビデオによる会話</span><span class="sxs-lookup"><span data-stu-id="1bcf1-154">Audio and video conversations with three or more people</span></span> <br/>  <span data-ttu-id="1bcf1-155">デスクトップとプログラムの共有</span><span class="sxs-lookup"><span data-stu-id="1bcf1-155">Desktop and program sharing</span></span> <br/> |
   
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a><span data-ttu-id="1bcf1-156">関連トピック</span><span class="sxs-lookup"><span data-stu-id="1bcf1-156">Related topics</span></span>

[<span data-ttu-id="1bcf1-157">ユーザーが外部の Skype for Business ユーザーに連絡できるようにする</span><span class="sxs-lookup"><span data-stu-id="1bcf1-157">Allow users to contact external Skype for Business users</span></span>](allow-users-to-contact-external-skype-for-business-users.md)
  
[<span data-ttu-id="1bcf1-158">Skype for Business Online をセットアップする</span><span class="sxs-lookup"><span data-stu-id="1bcf1-158">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

  
 
