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
f1.keywords:
- NOCSH
ms.custom:
- Setup
- LIL_Placement
description: '組織外のユーザーにSkype for BusinessをSkype for Businessして、連絡先の一覧に追加する方法を確認します。 '
ms.openlocfilehash: d68fc27dfb1c77935ce74e278092f6ed4ae3d7dc
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52239836"
---
# <a name="let-skype-for-business-users-add-skype-contacts"></a><span data-ttu-id="ae0b9-103">Skype for Business ユーザーが Skype の連絡先を追加できるようにする</span><span class="sxs-lookup"><span data-stu-id="ae0b9-103">Let Skype for Business users add Skype contacts</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="ae0b9-104">このSkype for Business、ユーザーは無料のアプリである Skype を使用しているすべてのユーザーと IM を検索して IM を実行できます。</span><span class="sxs-lookup"><span data-stu-id="ae0b9-104">With Skype for Business, your users can search for and IM with everyone who uses Skype, the free app!</span></span> <span data-ttu-id="ae0b9-105">この記事では、連絡先に連絡先を追加するために必要Skype説明します。</span><span class="sxs-lookup"><span data-stu-id="ae0b9-105">This article explains what you need to do so they can add Skype contacts.</span></span> 
  
<span data-ttu-id="ae0b9-106">この操作を[行うには、Microsoft 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d?ui=en-US&rs=en-US&ad=US)または Office 365アクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="ae0b9-106">You must have [admin permissions](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d?ui=en-US&rs=en-US&ad=US) in Microsoft 365 or Office 365 to do this.</span></span>

<span data-ttu-id="ae0b9-107">![Skype for Business のロゴを表示したアイコン](../images/sfb-logo-30x30.png) **Skype for Business 管理センターの使用**</span><span class="sxs-lookup"><span data-stu-id="ae0b9-107">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
  
1. <span data-ttu-id="ae0b9-108">管理者アカウント () Microsoft 365 または Office 365 でサインインします [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home#/homepage) 。</span><span class="sxs-lookup"><span data-stu-id="ae0b9-108">Sign in with your Microsoft 365 or Office 365 admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home#/homepage).</span></span>
    
2. <span data-ttu-id="ae0b9-109">管理センターで、[管理センター] に **移動Skype for Business。**  >  </span><span class="sxs-lookup"><span data-stu-id="ae0b9-109">In the admin center, go to **Admin Centers** > **Skype for Business**.</span></span> 
    
    ![管理センター Skype for Business選択します。](../images/376a7a45-e6e3-4716-be09-d2f294d885a2.png)
  
3. <span data-ttu-id="ae0b9-111">**Skype for Business 管理センター** で、[**組織**]  >  [**外部通信**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="ae0b9-111">In the **Skype for Business admin center**, choose **Organization** > **External communications**.</span></span> 
    
4. <span data-ttu-id="ae0b9-112">既定では、ユーザーは Skype for Business を使用する世界中の他のすべてのユーザーと通信できます (ファイアウォールがこれを許可するように構成されている場合)。</span><span class="sxs-lookup"><span data-stu-id="ae0b9-112">By default, your users can communicate with all other people in the world who use Skype for Business (assuming your firewall has been configured to allow this).</span></span> 
    
    ![[ユーザーが他のユーザーとSkype for Business通信を行うSkype。](../images/333789f8-2ea6-4bbd-805b-18130f427999.png)
  
    <span data-ttu-id="ae0b9-114">ユーザーが Skype ユーザーとチャットする必要があるが、Skype for Business を使用する他のユーザーとチャットしたくない場合は、[許可されているドメイン] に対して [オン] を **選択** します。</span><span class="sxs-lookup"><span data-stu-id="ae0b9-114">If you want your users to chat with Skype users, BUT you don't want them to chat with others who use Skype for Business, choose **On only for allowed domains**.</span></span> <span data-ttu-id="ae0b9-115">ユーザーとの連絡先を有効Skype、skype.com が許可されたドメインとして自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="ae0b9-115">When you enable contact with Skype users, skype.com is automatically added as an allowed domain behind the scenes.</span></span> 
    
    <span data-ttu-id="ae0b9-116">特定のドメインを除き、Skype for Business を使用して世界中の他のすべての企業からの連絡先を許可する場合は、[ブロックされているドメインを除いてオン] を選択し、それらのドメインを追加します。 **+**</span><span class="sxs-lookup"><span data-stu-id="ae0b9-116">If you want to allow contact from all other businesses in the world using Skype for Business, except specific ones, choose **On except for blocked domains**, and choose **+** to add those domains.</span></span> <span data-ttu-id="ae0b9-117">これらの特定のドメインのユーザーを除き、すべてのユーザーから連絡を受け取る可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ae0b9-117">Everyone will be able to contact you except people on those specific domains.</span></span> <span data-ttu-id="ae0b9-118">(一部の企業では、このオプションを選択する場合があります。たとえば、訴訟中で、他のビジネスとの連絡が取り合えない場合など)。</span><span class="sxs-lookup"><span data-stu-id="ae0b9-118">(Some businesses might choose this option, for example, if they are in litigation and need to ensure there's no contact with the other business.)</span></span>
    
5. <span data-ttu-id="ae0b9-119">[**組織外のユーザー Skype for Businessを使用してSkype通信する] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="ae0b9-119">Choose **Let people use Skype for Business to communicate with Skype users outside your organization**.</span></span> 
    
6.  <span data-ttu-id="ae0b9-120">ファイアウォールを使用している場合Windows必要Skype for Businessポートが自動的に開きます。</span><span class="sxs-lookup"><span data-stu-id="ae0b9-120">If you're using Windows Firewall, Skype for Business opens the required ports automatically.</span></span>
    
    <span data-ttu-id="ae0b9-121">組織で別のソリューションを使用してネットワーク上のコンピューターがインターネットに接続できない場合は、クライアント コンピューターが Skype 接続と Skype ディレクトリ検索のすべての IP アドレスと[URL](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)にアクセスできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae0b9-121">If your organization uses another solution to restrict computers on your network from connecting to the Internet, ensure client computers are able to access all of the [IP addresses and URLs](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) for Skype connectivity and Skype Directory Search.</span></span> <span data-ttu-id="ae0b9-122">これには、ファイアウォールまたはプロキシ インフラストラクチャ構成の送信許可リストに追加する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="ae0b9-122">This may require adding them to the outbound allow list in your firewall or proxy infrastructure configuration.</span></span>
    
7. <span data-ttu-id="ae0b9-123">**テストするには、最大 24 時間待機します**。</span><span class="sxs-lookup"><span data-stu-id="ae0b9-123">**WAIT UP TO 24 HOURS TO TEST**.</span></span> <span data-ttu-id="ae0b9-124">外部通信設定を変更すると、すべてのデータ センターに変更が設定されるのに最大 24 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="ae0b9-124">Any time you change the external communications settings, it can take up to 24 hours for the changes to populate across all the data centers.</span></span>
    
8. <span data-ttu-id="ae0b9-125">連絡先を見つけて追加する方法をユーザーにSkypeリストに追加する方法Skype for Businessします。</span><span class="sxs-lookup"><span data-stu-id="ae0b9-125">Show your users how to find and add Skype contacts to their list of Skype for Business contacts.</span></span> <span data-ttu-id="ae0b9-126">[ユーザーを[検索] をポイントSkype for Business。](https://support.office.com/article/b12500ef-e37f-4d22-aade-c11277e53f19)</span><span class="sxs-lookup"><span data-stu-id="ae0b9-126">Point them to [Search for people in Skype for Business](https://support.office.com/article/b12500ef-e37f-4d22-aade-c11277e53f19).</span></span>
    
## <a name="test-and-troubleshoot"></a><span data-ttu-id="ae0b9-127">テストとトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="ae0b9-127">Test and troubleshoot</span></span>

<span data-ttu-id="ae0b9-128">セットアップをテストするには、会社のファイアウォールの背後Skypeの連絡先が必要です。</span><span class="sxs-lookup"><span data-stu-id="ae0b9-128">To test your setup, you need a contact on Skype who's not behind your company firewall.</span></span> <span data-ttu-id="ae0b9-129">Gmail アカウント、Skype.com アカウント、または他の種類のメール アカウントを使用して、Outlook にサインインできます。</span><span class="sxs-lookup"><span data-stu-id="ae0b9-129">They can be signed in to Skype using a Gmail account, Outlook.com account, or other type of email account.</span></span>
  
1. <span data-ttu-id="ae0b9-130">外部通信の設定を変更した後、テスト **するまで最大 24 時間待ちます**。</span><span class="sxs-lookup"><span data-stu-id="ae0b9-130">After you change your external communications settings, **WAIT UP TO 24 HOURS TO TEST**.</span></span>
    
2. <span data-ttu-id="ae0b9-131">サインインからサインSkype for Businessし、もう一度サインインして、ディレクトリ内のディレクトリを検索Skypeします。</span><span class="sxs-lookup"><span data-stu-id="ae0b9-131">Sign out of Skype for Business and then sign in again so you see the option to search the Skype Directory.</span></span> 
    
    ![[Skype] が強調表示されている場合は、アカウントを持つユーザー Skypeできます。](../images/76ee9fab-1ac3-4f4a-9569-f5f2606dbb7a.png)
  
3. <span data-ttu-id="ae0b9-133">このSkype for Businessで連絡先を検索しSkypeチャットに要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="ae0b9-133">In Skype for Business, search for your contact in Skype, and send a request to chat.</span></span> 
    
    <span data-ttu-id="ae0b9-134">会社のポリシーが原因で送信できなかったというメッセージが表示された場合は、ファイアウォール設定 をダブルチェックする [必要があります](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)。</span><span class="sxs-lookup"><span data-stu-id="ae0b9-134">If you get the message it couldn't be sent due to company policy, you need to double-check your [firewall settings](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2).</span></span> 
    
4. <span data-ttu-id="ae0b9-135">問題がファイアウォールであるかどうかをテストするもう 1 つの方法は、コーヒー ショップなどのファイアウォールの背後ではない Wi-Fi の場所に移動し、Skype for Business を使用してチャットに Skype 連絡先に要求を送信する方法です。</span><span class="sxs-lookup"><span data-stu-id="ae0b9-135">Another way to test whether the problem is your firewall is to go to a wifi location not behind your firewall such as a coffee shop, and use Skype for Business to send a request to your Skype contact to chat.</span></span> 
    
   - <span data-ttu-id="ae0b9-136">**お客様がリクエストにSkypeし**、そのリクエストを受け取ったことがない場合は、チャットへのリクエストを送信してください。</span><span class="sxs-lookup"><span data-stu-id="ae0b9-136">**If you sent your Skype contact a request and they never received it**, ask them to send you a request to chat.</span></span> <span data-ttu-id="ae0b9-137">問題がアプリケーションとネットワークの間の接続を確立Skype場合Skype for Business、多くの場合、問題は解決します。</span><span class="sxs-lookup"><span data-stu-id="ae0b9-137">If the problem was establishing a connection between Skype and Skype for Business, that often solves it.</span></span>
    
   - <span data-ttu-id="ae0b9-138">ここで、メッセージがコーヒー ショップで送信されるが、仕事中にメッセージが送信されない場合は、ファイアウォールが問題であるのがわかっています。</span><span class="sxs-lookup"><span data-stu-id="ae0b9-138">Now if the message goes through at the coffee shop but not when you're at work, then you know the problem is your firewall.</span></span> 
    
## <a name="what-you-can-and-cant-do"></a><span data-ttu-id="ae0b9-139">実行できる操作と実行できない操作</span><span class="sxs-lookup"><span data-stu-id="ae0b9-139">What you can and can't do</span></span>

- <span data-ttu-id="ae0b9-140">**Skype for Business Mac では**、連絡先を検索して連絡を取る機能Skype行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae0b9-140">**Skype for Business on Mac** doesn't have the ability to search for and communicate with Skype contacts.</span></span>
    
- <span data-ttu-id="ae0b9-141">ディレクトリ検索が有効になっている場合は、ユーザーを検索してSkype検索Skype for Businessできます。</span><span class="sxs-lookup"><span data-stu-id="ae0b9-141">When directory search is enabled, you can search for and find Skype and Skype for Business users.</span></span> <span data-ttu-id="ae0b9-142">何らかの理由でディレクトリを検索して見つからなかった場合は、連絡先要求を送信し、Skype にサインインして承諾して、IM を送信できます。</span><span class="sxs-lookup"><span data-stu-id="ae0b9-142">If for some reason you can't find them by searching the directory, you can send them a contact request, and then have them sign in to Skype and accept it, so you can IM with them.</span></span> 
    
- <span data-ttu-id="ae0b9-143">Google や Facebook などの他の IM プロバイダーとの IM 接続を許可できない。</span><span class="sxs-lookup"><span data-stu-id="ae0b9-143">It's not possible to allow IM connectivity with other IM providers such as Google or Facebook.</span></span> <span data-ttu-id="ae0b9-144">携帯電話のテキスト メッセージSkype for Businessを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="ae0b9-144">You can't use Skype for Business to send cell phone text messages.</span></span>

- <span data-ttu-id="ae0b9-145">連絡先と連絡先の間で音声通話やビデオ通話Skype録音Skype for Businessはできません。</span><span class="sxs-lookup"><span data-stu-id="ae0b9-145">It is not possible to record audio or video calls between a Skype Contact and Skype for Business contact.</span></span>
    
## <a name="what-features-are-available-when-adding-skype-contacts"></a><span data-ttu-id="ae0b9-146">連絡先を追加するときに使用できる機能Skype?</span><span class="sxs-lookup"><span data-stu-id="ae0b9-146">What features are available when adding Skype contacts?</span></span>

<span data-ttu-id="ae0b9-147">Skype Microsoft アカウント (以前の Windows Live ID) でサインインした連絡先は、Skype for Business ユーザーと話している場合、一部の機能を取得できますが、すべてではありません。</span><span class="sxs-lookup"><span data-stu-id="ae0b9-147">Skype contacts who signed in with their Microsoft account (formerly Windows Live ID) can get some, but not all, features when they are talking to your Skype for Business users.</span></span>
  
|<span data-ttu-id="ae0b9-148">**他の連絡先Skype使用できます**</span><span class="sxs-lookup"><span data-stu-id="ae0b9-148">**Available with Skype contacts**</span></span>|<span data-ttu-id="ae0b9-149">**他の連絡先ではSkypeできません**</span><span class="sxs-lookup"><span data-stu-id="ae0b9-149">**Not available with Skype contacts**</span></span>|
|:-----|:-----|
| <span data-ttu-id="ae0b9-150">ビデオの会話</span><span class="sxs-lookup"><span data-stu-id="ae0b9-150">Video conversations</span></span> <br/>  <span data-ttu-id="ae0b9-151">ユーザー間のインスタント メッセージング</span><span class="sxs-lookup"><span data-stu-id="ae0b9-151">Person-to-person instant messaging</span></span> <br/>  <span data-ttu-id="ae0b9-152">プレゼンス</span><span class="sxs-lookup"><span data-stu-id="ae0b9-152">Presence</span></span> <br/> | <span data-ttu-id="ae0b9-153">マルチパーティ IM 会話</span><span class="sxs-lookup"><span data-stu-id="ae0b9-153">Multi-party IM conversations</span></span> <br/>  <span data-ttu-id="ae0b9-154">3 人以上のユーザーとの音声およびビデオの会話</span><span class="sxs-lookup"><span data-stu-id="ae0b9-154">Audio and video conversations with three or more people</span></span> <br/>  <span data-ttu-id="ae0b9-155">デスクトップとプログラムの共有</span><span class="sxs-lookup"><span data-stu-id="ae0b9-155">Desktop and program sharing</span></span> <br/> |
   
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a><span data-ttu-id="ae0b9-156">関連トピック</span><span class="sxs-lookup"><span data-stu-id="ae0b9-156">Related topics</span></span>

[<span data-ttu-id="ae0b9-157">外部の Skype for Business ユーザーに連絡できるようにする</span><span class="sxs-lookup"><span data-stu-id="ae0b9-157">Allow users to contact external Skype for Business users</span></span>](allow-users-to-contact-external-skype-for-business-users.md)
  
[<span data-ttu-id="ae0b9-158">Skype for Business Online のセットアップ</span><span class="sxs-lookup"><span data-stu-id="ae0b9-158">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

  
 
