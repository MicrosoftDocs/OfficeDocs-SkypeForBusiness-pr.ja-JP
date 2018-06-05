---
title: Skype for Business ユーザーが Skype 連絡先を追加できるようにする
ms.author: tonysmit
author: tonysmit
manager: serdars
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
description: 'See how to  let people who are using Skype for Business contact Skype for Business users from outside your organization and add them to their list of contacts. '
ms.openlocfilehash: 37f028c6a7347f13c6f41d88bfdb23907dfa92c3
ms.sourcegitcommit: a5b8b0a1e5ae5eb718e296ca6df6687368ee9174
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/05/2018
ms.locfileid: "19500617"
---
# <a name="let-skype-for-business-users-add-skype-contacts"></a><span data-ttu-id="fa2ac-103">Skype for Business ユーザーが Skype 連絡先を追加できるようにする</span><span class="sxs-lookup"><span data-stu-id="fa2ac-103">Let Skype for Business users add Skype contacts</span></span>

<span data-ttu-id="fa2ac-p101">[] Skype for Business では、ユーザーは無料アプリの Skype を使用しているすべての人に対して検索したり、IM で連絡することもできます。この記事では、Skype の連絡先を追加するために必要なことを説明します。</span><span class="sxs-lookup"><span data-stu-id="fa2ac-p101">With Skype for Business, your users can search for and IM with everyone who uses Skype, the free app! This article explains what you need to do so they can add Skype contacts.</span></span> 
  
<span data-ttu-id="fa2ac-106">Office 365 でこれを行うには、[Office 365 の管理者ロールについて](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d?ui=en-US&rs=en-US&ad=US)が必要です。</span><span class="sxs-lookup"><span data-stu-id="fa2ac-106">You must have [admin permissions](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d?ui=en-US&rs=en-US&ad=US) in Office 365 to do this.</span></span>

<span data-ttu-id="fa2ac-107">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Skype for Business の管理センターを使用する**</span><span class="sxs-lookup"><span data-stu-id="fa2ac-107">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
  
1. <span data-ttu-id="fa2ac-108">Office 365 の管理者アカウントを使用してサインイン[https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home#/homepage)。</span><span class="sxs-lookup"><span data-stu-id="fa2ac-108">Sign in with your Office 365 admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home#/homepage).</span></span>
    
2. <span data-ttu-id="fa2ac-109">Office 365 管理センターで、[**管理センター**]  >  [**Skype for Business**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="fa2ac-109">In the Office 365 admin center, go to **Admin Centers** > **Skype for Business**.</span></span> 
    
    ![Choose the Skype for Business admin center.](../images/376a7a45-e6e3-4716-be09-d2f294d885a2.png)
  
3. <span data-ttu-id="fa2ac-111">[**Skype for Business 管理センター**] で、[**組織**]  >  [**外部通信**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="fa2ac-111">In the **Skype for Business admin center**, choose **Organization** > **External communications**.</span></span> 
    
4. <span data-ttu-id="fa2ac-112">既定では、自分の組織のユーザーは Skype for Business を使用する世界中の他のユーザーと通信することができます (お使いのファイアウォールが通信を許可するよう構成されていることが前提です)。</span><span class="sxs-lookup"><span data-stu-id="fa2ac-112">By default, your users can communicate with all other people in the world who use Skype for Business (assuming your firewall has been configured to allow this).</span></span> 
    
    ![Choose Let people use Skype for Business to communicate with Skype.](../images/333789f8-2ea6-4bbd-805b-18130f427999.png)
  
    <span data-ttu-id="fa2ac-p102">自分の組織のユーザーが Skype ユーザーとチャットするようにして、Skype for Business を使用する他のユーザーとはチャットしないようにする場合は、[ **許可したドメインに対してのみオンにする**] を選択します。Skype ユーザーとの連絡を有効にすると、skype.com はバックグラウンドで許可されたドメインとして自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="fa2ac-p102">If you want your users to chat with Skype users, BUT you don't want them to chat with others who use Skype for Business, choose **On only for allowed domains**. When you enable contact with Skype users, skype.com is automatically added as an allowed domain behind the scenes.</span></span> 
    
    <span data-ttu-id="fa2ac-p103">Skype for Business を使用する世界中の他のすべての企業からの連絡を許可する場合は、[ **禁止したドメインを除いてオンにする**] を選び、[ **+**] を選んで該当するドメインを追加します。これらの特定のドメイン上のユーザーを除くすべてのユーザーが自分に連絡できるようになります。(企業によっては、訴訟中で他の企業と連絡を取ることがないようにする必要がある場合などに、このオプションを選択する可能性があります。)</span><span class="sxs-lookup"><span data-stu-id="fa2ac-p103">If you want to allow contact from all other businesses in the world using Skype for Business, except specific ones, choose **On except for blocked domains**, and choose **+** to add those domains. Everyone will be able to contact you except people on those specific domains. (Some businesses might choose this option, for example, if they are in litigation and need to ensure there's no contact with the other business.)</span></span>
    
5. <span data-ttu-id="fa2ac-119">[ **他のユーザーに Skype for Business の使用を許可して、組織外の Skype ユーザーと通信します**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="fa2ac-119">Choose **Let people use Skype for Business to communicate with Skype users outside your organization**.</span></span> 
    
6.  <span data-ttu-id="fa2ac-120">Windows Firewall を使用している場合は、Skype for Business が必要なポートを自動的に開きます。</span><span class="sxs-lookup"><span data-stu-id="fa2ac-120">If you're using Windows Firewall, Skype for Business opens the required ports automatically.</span></span>
    
    <span data-ttu-id="fa2ac-p104">組織でネットワーク上のコンピューターがインターネットに接続するのを制限するために別のソリューションを使用している場合は、お使いのクライアント コンピューターが Skype 接続と Skype ディレクトリ検索用のすべての [Office 365 URL および IP アドレス範囲](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) にアクセスできることを確認してください。これにより、ファイアウォールまたはプロキシのインフラストラクチャ構成の発信許可リストに、これらの IP アドレスと URL を追加する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="fa2ac-p104">If your organization uses another solution to restrict computers on your network from connecting to the Internet, ensure client computers are able to access all of the [IP addresses and URLs](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) for Skype connectivity and Skype Directory Search. This may require adding them to the outbound allow list in your firewall or proxy infrastructure configuration.</span></span>
    
7. <span data-ttu-id="fa2ac-p105">**テストのために最大 24 時間待機します** 。外部通信設定を変更したときはいつでも、変更がデータ　センター全体に行き渡るまでに最大 24 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="fa2ac-p105">**WAIT UP TO 24 HOURS TO TEST**. Any time you change the external communications settings, it can take up to 24 hours for the changes to populate across all the data centers.</span></span>
    
8. <span data-ttu-id="fa2ac-p106">Skype 連絡先を見つけて Skype for Business 連絡先の一覧に追加する方法をユーザーに示します。ユーザーに、「[Skype for Business で知り合いを検索する](https://support.office.com/en-us/article/b12500ef-e37f-4d22-aade-c11277e53f19)」を参照するよう指示します。</span><span class="sxs-lookup"><span data-stu-id="fa2ac-p106">Show your users how to find and add Skype contacts to their list of Skype for Business contacts. Point them to [Search for people in Skype for Business](https://support.office.com/en-us/article/b12500ef-e37f-4d22-aade-c11277e53f19).</span></span>
    
## <a name="test-and-troubleshoot"></a><span data-ttu-id="fa2ac-127">テストとトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="fa2ac-127">Test and troubleshoot</span></span>

<span data-ttu-id="fa2ac-p107">セットアップをテストするには、会社のファイアウォールの背後にない Skype 上の連絡先が必要です。Gmail アカウント、Outlook.com アカウント、またはその他の種類の電子メール アカウントを使用して Skype にサインインできます。</span><span class="sxs-lookup"><span data-stu-id="fa2ac-p107">To test your setup, you need a contact on Skype who's not behind your company firewall. They can be signed in to Skype using a Gmail account, Outlook.com account, or other type of email account.</span></span>
  
1. <span data-ttu-id="fa2ac-130">外部通信設定を変更した後、 **テストのために最大 24 時間待機** します。</span><span class="sxs-lookup"><span data-stu-id="fa2ac-130">After you change your external communications settings, **WAIT UP TO 24 HOURS TO TEST**.</span></span>
    
2. <span data-ttu-id="fa2ac-131">Skype for Business からサイン アウトして、再びサイン インすると、Skype ディレクトリを検索するオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fa2ac-131">Sign out of Skype for Business and then sign in again so you see the option to search the Skype Directory.</span></span> 
    
    ![When Skype Directory is highlighted, you can search for people who have Skype accounts.](../images/76ee9fab-1ac3-4f4a-9569-f5f2606dbb7a.png)
  
3. <span data-ttu-id="fa2ac-133">Skype for Business で、Skype の連絡先を検索し、チャットのリクエストを送信します。</span><span class="sxs-lookup"><span data-stu-id="fa2ac-133">In Skype for Business, search for your contact in Skype, and send a request to chat.</span></span> 
    
    <span data-ttu-id="fa2ac-134">会社のポリシーのために送信できなかったというメッセージを受信する場合は、お使いの[Office 365 URL および IP アドレス範囲](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)をダブルチェックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa2ac-134">If you get the message it couldn't be sent due to company policy, you need to double-check your [firewall settings](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2).</span></span> 
    
4. <span data-ttu-id="fa2ac-135">問題がファイアウォールであるかどうかをテストするもう 1 つの方法は、お使いのファイアウォールの背後ではないコーヒー ショップなどの wifi の場所に移動して、Skype for Business を使用して Skype 連絡先にチャットするリクエストを送信します。</span><span class="sxs-lookup"><span data-stu-id="fa2ac-135">Another way to test whether the problem is your firewall is to go to a wifi location not behind your firewall such as a coffee shop, and use Skype for Business to send a request to your Skype contact to chat.</span></span> 
    
  - <span data-ttu-id="fa2ac-p108">**Skype 連絡先にリクエストを送信したのに、受信されていない場合** は、チャットするためのリクエストを自分宛てに送信してもらいます。Skype と Skype for Business との間の接続に問題がある場合は、これにより問題が解決する可能性が高いです。</span><span class="sxs-lookup"><span data-stu-id="fa2ac-p108">**If you sent your Skype contact a request and they never received it**, ask them to send you a request to chat. If the problem was establishing a connection between Skype and Skype for Business, that often solves it.</span></span>
    
  - <span data-ttu-id="fa2ac-138">メッセージがコーヒー ショップでは送られるのに職場では送られない場合は、ファイアウォールが問題であることが分かります。</span><span class="sxs-lookup"><span data-stu-id="fa2ac-138">Now if the message goes through at the coffee shop but not when you're at work, then you know the problem is your firewall.</span></span> 
    
## <a name="what-you-can-and-cant-do"></a><span data-ttu-id="fa2ac-139">できることとできないこと</span><span class="sxs-lookup"><span data-stu-id="fa2ac-139">What you can and can't do</span></span>

- <span data-ttu-id="fa2ac-140">**Skype for BusinessMac 版** には Skype の連絡先を検索して通信相手とする機能がありません。</span><span class="sxs-lookup"><span data-stu-id="fa2ac-140">**Skype for Business on Mac** doesn't have the ability to search for and communicate with Skype contacts.</span></span>
    
- <span data-ttu-id="fa2ac-p109">Skype ユーザーを検索して見つけることはできますが、Skype for Business ユーザーの検索はできません。彼らと IM で連絡できるようにするには、連絡先追加のリクエストを彼らに送信し、彼らは Skype にサインインしてリクエストを承諾する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa2ac-p109">When directory search is enabled, you can search for and find Skype and Skype for Business users. If for some reason you can't find them by searching the directory, you can send them a contact request, and then have them sign in to Skype and accept it, so you can IM with them.</span></span> 
    
- <span data-ttu-id="fa2ac-p110">Google や Facebook などの他の IM プロバイダーとの IM の接続を許可することはできません。Skype for Business を使用して携帯電話のテキスト メッセージを送信することはできません。</span><span class="sxs-lookup"><span data-stu-id="fa2ac-p110">It's not possible to allow IM connectivity with other IM providers such as Google or Facebook. You can't use Skype for Business to send cell phone text messages.</span></span>

- <span data-ttu-id="fa2ac-145">Skype 連絡先を追加するときに、どの機能を使用できますか。</span><span class="sxs-lookup"><span data-stu-id="fa2ac-145">It is not possible to record audio or video calls between a Skype Contact and Skype for Business contact.</span></span>
    
## <a name="what-features-are-available-when-adding-skype-contacts"></a><span data-ttu-id="fa2ac-146">Microsoft アカウント (旧称 Windows Live ID) でサインインした Skype 連絡先は、Skype for Business ユーザーと話すときに一部の機能を使用できますが、すべての機能を使用できるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="fa2ac-146">What features are available when adding Skype contacts?</span></span>

<span data-ttu-id="fa2ac-147">Microsoft アカウント (旧称 Windows Live ID) でサインインした Skype 連絡先は、Skype for Business ユーザーと話すときに一部の機能を使用できますが、すべての機能を使用できるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="fa2ac-147">Skype contacts who signed in with their Microsoft account (formerly Windows Live ID) can get some, but not all, features when they are talking to your Skype for Business users.</span></span>
  
|<span data-ttu-id="fa2ac-148">**Skype 連絡先との間では使用不可**</span><span class="sxs-lookup"><span data-stu-id="fa2ac-148">**Available with Skype contacts**</span></span>|<span data-ttu-id="fa2ac-149">ビデオ会話</span><span class="sxs-lookup"><span data-stu-id="fa2ac-149">**Not available with Skype contacts**</span></span>|
|:-----|:-----|
| <span data-ttu-id="fa2ac-150">ユーザー間のインスタント メッセージング</span><span class="sxs-lookup"><span data-stu-id="fa2ac-150">Video conversations</span></span> <br/>  <span data-ttu-id="fa2ac-151">プレゼンス</span><span class="sxs-lookup"><span data-stu-id="fa2ac-151">Person-to-person instant messaging</span></span> <br/>  <span data-ttu-id="fa2ac-152">マルチパーティの IM での会話</span><span class="sxs-lookup"><span data-stu-id="fa2ac-152">Presence</span></span> <br/> | <span data-ttu-id="fa2ac-153">3 人以上での音声会話やビデオ会話</span><span class="sxs-lookup"><span data-stu-id="fa2ac-153">Multi-party IM conversations</span></span> <br/>  <span data-ttu-id="fa2ac-154">デスクトップとプログラムの共有</span><span class="sxs-lookup"><span data-stu-id="fa2ac-154">Audio and video conversations with three or more people</span></span> <br/>  <span data-ttu-id="fa2ac-155">デスクトップおよびプログラムの共有</span><span class="sxs-lookup"><span data-stu-id="fa2ac-155">Desktop and program sharing</span></span> <br/> |
   
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a><span data-ttu-id="fa2ac-156">See also</span><span class="sxs-lookup"><span data-stu-id="fa2ac-156">Related topics</span></span>

[<span data-ttu-id="fa2ac-157">外部の Skype for Business ユーザーに連絡できるようにする</span><span class="sxs-lookup"><span data-stu-id="fa2ac-157">Allow users to contact external Skype for Business users</span></span>](allow-users-to-contact-external-skype-for-business-users.md)
  
[<span data-ttu-id="fa2ac-158">Skype for Business Online のセットアップ</span><span class="sxs-lookup"><span data-stu-id="fa2ac-158">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

  
 