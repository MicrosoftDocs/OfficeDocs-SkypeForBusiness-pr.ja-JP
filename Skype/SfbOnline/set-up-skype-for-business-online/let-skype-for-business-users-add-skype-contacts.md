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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
- LIL_Placement
description: 'Skype for Business を使用しているユーザーが組織外の Skype for Business ユーザーに連絡し、連絡先リストに追加できるようにする方法について説明します。 '
ms.openlocfilehash: 3ba92977fa45686a900a78cfcf231a3c0985a933
ms.sourcegitcommit: 4c041e8a7c39bd6517605ed7fc9aab18cf466596
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/18/2019
ms.locfileid: "35792145"
---
# <a name="let-skype-for-business-users-add-skype-contacts"></a><span data-ttu-id="d933c-103">Skype for Business ユーザーが Skype の連絡先を追加できるようにする</span><span class="sxs-lookup"><span data-stu-id="d933c-103">Let Skype for Business users add Skype contacts</span></span>

<span data-ttu-id="d933c-104">Skype for Business では、無料アプリの Skype を使用しているすべてのユーザーが、お客さまとの間で IM を検索して IM を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="d933c-104">With Skype for Business, your users can search for and IM with everyone who uses Skype, the free app!</span></span> <span data-ttu-id="d933c-105">この記事では、Skype の連絡先を追加できるようにするために必要な操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="d933c-105">This article explains what you need to do so they can add Skype contacts.</span></span> 
  
<span data-ttu-id="d933c-106">この操作を行うには、Office 365 の[管理者権限](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d?ui=en-US&rs=en-US&ad=US)が必要です。</span><span class="sxs-lookup"><span data-stu-id="d933c-106">You must have [admin permissions](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d?ui=en-US&rs=en-US&ad=US) in Office 365 to do this.</span></span>

<span data-ttu-id="d933c-107">![](../images/sfb-logo-30x30.png) **Skype for business 管理センターを使用し**た skype for business ロゴを示すアイコン</span><span class="sxs-lookup"><span data-stu-id="d933c-107">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
  
1. <span data-ttu-id="d933c-108">Office 365 管理者アカウントでサインイン[https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home#/homepage)します。</span><span class="sxs-lookup"><span data-stu-id="d933c-108">Sign in with your Office 365 admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home#/homepage).</span></span>
    
2. <span data-ttu-id="d933c-109">管理センターで、[**管理センター** > ]**の [Skype for business**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="d933c-109">In the admin center, go to **Admin Centers** > **Skype for Business**.</span></span> 
    
    ![Skype for Business 管理センターを選びます。](../images/376a7a45-e6e3-4716-be09-d2f294d885a2.png)
  
3. <span data-ttu-id="d933c-111">**Skype for Business 管理センター**で、[**組織**]  >  [**外部通信**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="d933c-111">In the **Skype for Business admin center**, choose **Organization** > **External communications**.</span></span> 
    
4. <span data-ttu-id="d933c-112">既定では、ユーザーは Skype for Business を使用する世界中の他のすべてのユーザーと通信できます (ファイアウォールがこれを許可するように構成されていることを前提としています)。</span><span class="sxs-lookup"><span data-stu-id="d933c-112">By default, your users can communicate with all other people in the world who use Skype for Business (assuming your firewall has been configured to allow this).</span></span> 
    
    ![[Skype for Business を使用して Skype と通信できるようにする] を選択します。](../images/333789f8-2ea6-4bbd-805b-18130f427999.png)
  
    <span data-ttu-id="d933c-114">ユーザーが Skype ユーザーとチャットする必要があるが、Skype for Business を使用している他のユーザーとチャットしたくない場合は、[許可した**ドメインに対してのみオンに**する] を選びます。</span><span class="sxs-lookup"><span data-stu-id="d933c-114">If you want your users to chat with Skype users, BUT you don't want them to chat with others who use Skype for Business, choose **On only for allowed domains**.</span></span> <span data-ttu-id="d933c-115">Skype ユーザーとの連絡を有効にすると、skype.com は、バックグラウンドで許可されたドメインとして自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="d933c-115">When you enable contact with Skype users, skype.com is automatically added as an allowed domain behind the scenes.</span></span> 
    
    <span data-ttu-id="d933c-116">Skype for Business を使って世界中の他のすべての企業の連絡先を許可する場合は、[**禁止**したドメイン**+** を除いてオンにする] を選んで、これらのドメインを追加します。</span><span class="sxs-lookup"><span data-stu-id="d933c-116">If you want to allow contact from all other businesses in the world using Skype for Business, except specific ones, choose **On except for blocked domains**, and choose **+** to add those domains.</span></span> <span data-ttu-id="d933c-117">これらの特定のドメインのユーザーを除き、すべてのユーザーがあなたに連絡できるようになります。</span><span class="sxs-lookup"><span data-stu-id="d933c-117">Everyone will be able to contact you except people on those specific domains.</span></span> <span data-ttu-id="d933c-118">(場合によっては、このオプションを選択することがあります。たとえば、訴訟の際に、他の会社との連絡が不要であることを確認する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="d933c-118">(Some businesses might choose this option, for example, if they are in litigation and need to ensure there's no contact with the other business.)</span></span>
    
5. <span data-ttu-id="d933c-119">[**ユーザーが skype For business を使って組織外の skype ユーザーと通信できるように**します] を選びます。</span><span class="sxs-lookup"><span data-stu-id="d933c-119">Choose **Let people use Skype for Business to communicate with Skype users outside your organization**.</span></span> 
    
6.  <span data-ttu-id="d933c-120">Windows ファイアウォールを使用している場合、Skype for Business は必要なポートを自動的に開きます。</span><span class="sxs-lookup"><span data-stu-id="d933c-120">If you're using Windows Firewall, Skype for Business opens the required ports automatically.</span></span>
    
    <span data-ttu-id="d933c-121">組織で別のソリューションを使用して、ネットワーク上のコンピューターがインターネットに接続されないように制限する場合は、クライアントコンピューターが Skype 接続と Skype ディレクトリ検索のすべての[IP アドレスと url](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)にアクセスできることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d933c-121">If your organization uses another solution to restrict computers on your network from connecting to the Internet, ensure client computers are able to access all of the [IP addresses and URLs](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) for Skype connectivity and Skype Directory Search.</span></span> <span data-ttu-id="d933c-122">これには、ファイアウォールまたはプロキシインフラストラクチャ構成の送信許可リストへの追加が必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="d933c-122">This may require adding them to the outbound allow list in your firewall or proxy infrastructure configuration.</span></span>
    
7. <span data-ttu-id="d933c-123">**テストに最大24時間待機**します。</span><span class="sxs-lookup"><span data-stu-id="d933c-123">**WAIT UP TO 24 HOURS TO TEST**.</span></span> <span data-ttu-id="d933c-124">外部通信設定を変更すると、すべてのデータセンターに変更が反映されるまでに最大24時間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="d933c-124">Any time you change the external communications settings, it can take up to 24 hours for the changes to populate across all the data centers.</span></span>
    
8. <span data-ttu-id="d933c-125">Skype for Business の連絡先リストに Skype の連絡先を検索して追加する方法をユーザーに示します。</span><span class="sxs-lookup"><span data-stu-id="d933c-125">Show your users how to find and add Skype contacts to their list of Skype for Business contacts.</span></span> <span data-ttu-id="d933c-126">[Skype For business で連絡先を検索](https://support.office.com/en-us/article/b12500ef-e37f-4d22-aade-c11277e53f19)するようにユーザーに伝えます。</span><span class="sxs-lookup"><span data-stu-id="d933c-126">Point them to [Search for people in Skype for Business](https://support.office.com/en-us/article/b12500ef-e37f-4d22-aade-c11277e53f19).</span></span>
    
## <a name="test-and-troubleshoot"></a><span data-ttu-id="d933c-127">テストとトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="d933c-127">Test and troubleshoot</span></span>

<span data-ttu-id="d933c-128">セットアップをテストするには、会社のファイアウォールの背後にない Skype 上の連絡先が必要です。</span><span class="sxs-lookup"><span data-stu-id="d933c-128">To test your setup, you need a contact on Skype who's not behind your company firewall.</span></span> <span data-ttu-id="d933c-129">Gmail アカウント、Outlook.com アカウント、またはその他の種類のメールアカウントを使用して、Skype にサインインできます。</span><span class="sxs-lookup"><span data-stu-id="d933c-129">They can be signed in to Skype using a Gmail account, Outlook.com account, or other type of email account.</span></span>
  
1. <span data-ttu-id="d933c-130">外部通信設定を変更したら、**最大24時間待機**してテストします。</span><span class="sxs-lookup"><span data-stu-id="d933c-130">After you change your external communications settings, **WAIT UP TO 24 HOURS TO TEST**.</span></span>
    
2. <span data-ttu-id="d933c-131">Skype for Business からサインアウトしてから、もう一度サインインすると、Skype ディレクトリを検索するオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d933c-131">Sign out of Skype for Business and then sign in again so you see the option to search the Skype Directory.</span></span> 
    
    ![Skype ディレクトリが強調表示されている場合は、Skype アカウントを持っているユーザーを検索できます。](../images/76ee9fab-1ac3-4f4a-9569-f5f2606dbb7a.png)
  
3. <span data-ttu-id="d933c-133">Skype for Business で、Skype で連絡先を検索し、チャットのリクエストを送信します。</span><span class="sxs-lookup"><span data-stu-id="d933c-133">In Skype for Business, search for your contact in Skype, and send a request to chat.</span></span> 
    
    <span data-ttu-id="d933c-134">会社のポリシーのために送信できないというメッセージが表示された場合は、[ファイアウォールの設定](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)を再確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d933c-134">If you get the message it couldn't be sent due to company policy, you need to double-check your [firewall settings](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2).</span></span> 
    
4. <span data-ttu-id="d933c-135">ファイアウォールで問題があるかどうかをテストするもう1つの方法は、喫茶店などのファイアウォールの背後にない wifi 上の場所に接続することです。 Skype for Business を使って、Skype の連絡先に要求を送信してチャットすることもできます。</span><span class="sxs-lookup"><span data-stu-id="d933c-135">Another way to test whether the problem is your firewall is to go to a wifi location not behind your firewall such as a coffee shop, and use Skype for Business to send a request to your Skype contact to chat.</span></span> 
    
   - <span data-ttu-id="d933c-136">**Skype コンタクトにリクエストを送信し**たが、それを受信したことがない場合は、チャットのリクエストを送信してください。</span><span class="sxs-lookup"><span data-stu-id="d933c-136">**If you sent your Skype contact a request and they never received it**, ask them to send you a request to chat.</span></span> <span data-ttu-id="d933c-137">問題が Skype と Skype for business の間の接続を確立していた場合は、この問題が解決されることがよくあります。</span><span class="sxs-lookup"><span data-stu-id="d933c-137">If the problem was establishing a connection between Skype and Skype for Business, that often solves it.</span></span>
    
   - <span data-ttu-id="d933c-138">メッセージがコーヒーショップで処理されているのに、仕事中にいない場合は、ファイアウォールに問題があることがわかります。</span><span class="sxs-lookup"><span data-stu-id="d933c-138">Now if the message goes through at the coffee shop but not when you're at work, then you know the problem is your firewall.</span></span> 
    
## <a name="what-you-can-and-cant-do"></a><span data-ttu-id="d933c-139">できることとできないこと</span><span class="sxs-lookup"><span data-stu-id="d933c-139">What you can and can't do</span></span>

- <span data-ttu-id="d933c-140">**Mac 版 skype For business**には、skype の連絡先を検索して通信する機能がありません。</span><span class="sxs-lookup"><span data-stu-id="d933c-140">**Skype for Business on Mac** doesn't have the ability to search for and communicate with Skype contacts.</span></span>
    
- <span data-ttu-id="d933c-141">ディレクトリ検索が有効になっている場合は、Skype と Skype for business のユーザーを検索して見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="d933c-141">When directory search is enabled, you can search for and find Skype and Skype for Business users.</span></span> <span data-ttu-id="d933c-142">何らかの理由でディレクトリを検索しても見つからない場合は、コンタクト要求を送信して、Skype にサインインして同意してもらうことができます。</span><span class="sxs-lookup"><span data-stu-id="d933c-142">If for some reason you can't find them by searching the directory, you can send them a contact request, and then have them sign in to Skype and accept it, so you can IM with them.</span></span> 
    
- <span data-ttu-id="d933c-143">Google や Facebook などの他の IM プロバイダーとの IM 接続を許可することはできません。</span><span class="sxs-lookup"><span data-stu-id="d933c-143">It's not possible to allow IM connectivity with other IM providers such as Google or Facebook.</span></span> <span data-ttu-id="d933c-144">携帯電話のテキストメッセージの送信に Skype for Business を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="d933c-144">You can't use Skype for Business to send cell phone text messages.</span></span>

- <span data-ttu-id="d933c-145">Skype コンタクトと Skype for Business の連絡先との間で音声通話やビデオ通話を録音することはできません。</span><span class="sxs-lookup"><span data-stu-id="d933c-145">It is not possible to record audio or video calls between a Skype Contact and Skype for Business contact.</span></span>
    
## <a name="what-features-are-available-when-adding-skype-contacts"></a><span data-ttu-id="d933c-146">Skype の連絡先を追加するときに使用できる機能は何ですか?</span><span class="sxs-lookup"><span data-stu-id="d933c-146">What features are available when adding Skype contacts?</span></span>

<span data-ttu-id="d933c-147">Microsoft アカウント (旧称 Windows Live ID) でサインインした skype 連絡先は、Skype for Business ユーザーと話すときに一部の機能を使用できますが、一部の機能は利用できません。</span><span class="sxs-lookup"><span data-stu-id="d933c-147">Skype contacts who signed in with their Microsoft account (formerly Windows Live ID) can get some, but not all, features when they are talking to your Skype for Business users.</span></span>
  
|<span data-ttu-id="d933c-148">**Skype の連絡先との間で利用可能**</span><span class="sxs-lookup"><span data-stu-id="d933c-148">**Available with Skype contacts**</span></span>|<span data-ttu-id="d933c-149">**Skype の連絡先との間で利用できない機能**</span><span class="sxs-lookup"><span data-stu-id="d933c-149">**Not available with Skype contacts**</span></span>|
|:-----|:-----|
| <span data-ttu-id="d933c-150">ビデオ通話</span><span class="sxs-lookup"><span data-stu-id="d933c-150">Video conversations</span></span> <br/>  <span data-ttu-id="d933c-151">個人間のインスタントメッセージング</span><span class="sxs-lookup"><span data-stu-id="d933c-151">Person-to-person instant messaging</span></span> <br/>  <span data-ttu-id="d933c-152">プレゼンス</span><span class="sxs-lookup"><span data-stu-id="d933c-152">Presence</span></span> <br/> | <span data-ttu-id="d933c-153">マルチパーティの IM 会話</span><span class="sxs-lookup"><span data-stu-id="d933c-153">Multi-party IM conversations</span></span> <br/>  <span data-ttu-id="d933c-154">3人以上のユーザーとの音声およびビデオによる会話</span><span class="sxs-lookup"><span data-stu-id="d933c-154">Audio and video conversations with three or more people</span></span> <br/>  <span data-ttu-id="d933c-155">デスクトップとプログラムの共有</span><span class="sxs-lookup"><span data-stu-id="d933c-155">Desktop and program sharing</span></span> <br/> |
   
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a><span data-ttu-id="d933c-156">関連トピック</span><span class="sxs-lookup"><span data-stu-id="d933c-156">Related topics</span></span>

[<span data-ttu-id="d933c-157">外部の Skype for Business ユーザーに連絡できるようにする</span><span class="sxs-lookup"><span data-stu-id="d933c-157">Allow users to contact external Skype for Business users</span></span>](allow-users-to-contact-external-skype-for-business-users.md)
  
[<span data-ttu-id="d933c-158">Skype for Business Online のセットアップ</span><span class="sxs-lookup"><span data-stu-id="d933c-158">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

  
 
