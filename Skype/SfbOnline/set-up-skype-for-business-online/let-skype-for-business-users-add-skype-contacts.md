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
description: '組織外からのビジネス ユーザー向けのビジネス用連絡先 Skype の Skype を使用しているし、連絡先の一覧に追加するユーザーをできるようにする方法を参照してください。 '
ms.openlocfilehash: 212393154cb2b730ce18f5be9b03495e747e207c
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32238034"
---
# <a name="let-skype-for-business-users-add-skype-contacts"></a><span data-ttu-id="a3369-103">Skype for Business ユーザーが Skype の連絡先を追加できるようにする</span><span class="sxs-lookup"><span data-stu-id="a3369-103">Let Skype for Business users add Skype contacts</span></span>

<span data-ttu-id="a3369-104">ビジネスの Skype で、検索でき、Skype では、無料のアプリケーションを使用して他のユーザーとの IM!</span><span class="sxs-lookup"><span data-stu-id="a3369-104">With Skype for Business, your users can search for and IM with everyone who uses Skype, the free app!</span></span> <span data-ttu-id="a3369-105">この資料では、Skype 連絡先を追加するために必要なものについて説明します。</span><span class="sxs-lookup"><span data-stu-id="a3369-105">This article explains what you need to do so they can add Skype contacts.</span></span> 
  
<span data-ttu-id="a3369-106">これを行う Office 365 の[管理者のアクセス許可](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d?ui=en-US&rs=en-US&ad=US)が必要です。</span><span class="sxs-lookup"><span data-stu-id="a3369-106">You must have [admin permissions](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d?ui=en-US&rs=en-US&ad=US) in Office 365 to do this.</span></span>

<span data-ttu-id="a3369-107">![デバイスのロゴ-30x30.png](../images/sfb-logo-30x30.png) **ビジネス管理センターの Skype を使用します。**</span><span class="sxs-lookup"><span data-stu-id="a3369-107">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
  
1. <span data-ttu-id="a3369-108">Office 365 の管理者アカウントを使用してサインイン[https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home#/homepage)。</span><span class="sxs-lookup"><span data-stu-id="a3369-108">Sign in with your Office 365 admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home#/homepage).</span></span>
    
2. <span data-ttu-id="a3369-109">Office 365 管理センターでは、**管理センター**に移動 > **ビジネス用の Skype**です。</span><span class="sxs-lookup"><span data-stu-id="a3369-109">In the Office 365 admin center, go to **Admin Centers** > **Skype for Business**.</span></span> 
    
    ![ビジネス管理センターの Skype を選択します。](../images/376a7a45-e6e3-4716-be09-d2f294d885a2.png)
  
3. <span data-ttu-id="a3369-111">**ビジネス管理センターの Skype**では、**組織**を選択します。 > **外部との連絡**。</span><span class="sxs-lookup"><span data-stu-id="a3369-111">In the **Skype for Business admin center**, choose **Organization** > **External communications**.</span></span> 
    
4. <span data-ttu-id="a3369-112">既定では、ユーザーは、(これを許可するファイアウォールが構成されていると仮定した場合)、ビジネスの Skype を使用している世界中の他のすべてのユーザーと通信できます。</span><span class="sxs-lookup"><span data-stu-id="a3369-112">By default, your users can communicate with all other people in the world who use Skype for Business (assuming your firewall has been configured to allow this).</span></span> 
    
    ![Let を選択してユーザーは、Skype で通信するためにビジネス用の Skype を使用します。](../images/333789f8-2ea6-4bbd-805b-18130f427999.png)
  
    <span data-ttu-id="a3369-114">Skype ユーザーとチャットするのには、ユーザーが、ビジネスの Skype を使用している他のユーザーとチャットすることをしない**にのみ許可されるドメイン**を選択します。</span><span class="sxs-lookup"><span data-stu-id="a3369-114">If you want your users to chat with Skype users, BUT you don't want them to chat with others who use Skype for Business, choose **On only for allowed domains**.</span></span> <span data-ttu-id="a3369-115">Skype ユーザーと連絡先を有効にすると、skype.com は自動的にバック グラウンドで許可されているドメインとして追加されます。</span><span class="sxs-lookup"><span data-stu-id="a3369-115">When you enable contact with Skype users, skype.com is automatically added as an allowed domain behind the scenes.</span></span> 
    
    <span data-ttu-id="a3369-116">特定の場合を除き、ビジネスの Skype を使用して世界中の他のすべての企業からの連絡を許可するを選択する場合は**でブロックされたドメインを除く**を選択し、**+** それらのドメインを追加するのには。</span><span class="sxs-lookup"><span data-stu-id="a3369-116">If you want to allow contact from all other businesses in the world using Skype for Business, except specific ones, choose **On except for blocked domains**, and choose **+** to add those domains.</span></span> <span data-ttu-id="a3369-117">除くこれらの特定のドメイン上のユーザーに連絡して誰もができます。</span><span class="sxs-lookup"><span data-stu-id="a3369-117">Everyone will be able to contact you except people on those specific domains.</span></span> <span data-ttu-id="a3369-118">(一部の企業は、このオプションを選択などの訴訟では、そのことを確認する必要がある場合は、他のビジネスとの接続)。</span><span class="sxs-lookup"><span data-stu-id="a3369-118">(Some businesses might choose this option, for example, if they are in litigation and need to ensure there's no contact with the other business.)</span></span>
    
5. <span data-ttu-id="a3369-119">**ユーザーが組織外の Skype ユーザーと通信するビジネス用の Skype を使用できるように**選択してください。</span><span class="sxs-lookup"><span data-stu-id="a3369-119">Choose **Let people use Skype for Business to communicate with Skype users outside your organization**.</span></span> 
    
6.  <span data-ttu-id="a3369-120">Windows ファイアウォールを使用している場合は、Skype のビジネスに必要なポートが自動的に開きます。</span><span class="sxs-lookup"><span data-stu-id="a3369-120">If you're using Windows Firewall, Skype for Business opens the required ports automatically.</span></span>
    
    <span data-ttu-id="a3369-121">組織では、インターネットへの接続をネットワーク上のコンピューターを制限するのには別のソリューションを使用している場合は、クライアント コンピューターはすべての[IP アドレスや Url](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)の Skype の接続」と「Skype ディレクトリ検索にアクセスすることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a3369-121">If your organization uses another solution to restrict computers on your network from connecting to the Internet, ensure client computers are able to access all of the [IP addresses and URLs](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) for Skype connectivity and Skype Directory Search.</span></span> <span data-ttu-id="a3369-122">これは、必要がありますファイアウォールまたはプロキシ インフラストラクチャの構成で許可リストを送信に追加します。</span><span class="sxs-lookup"><span data-stu-id="a3369-122">This may require adding them to the outbound allow list in your firewall or proxy infrastructure configuration.</span></span>
    
7. <span data-ttu-id="a3369-123">**テストするのには最大で 24 時間を待機**します。</span><span class="sxs-lookup"><span data-stu-id="a3369-123">**WAIT UP TO 24 HOURS TO TEST**.</span></span> <span data-ttu-id="a3369-124">外部通信の設定を変更するすべてのデータ センター間で設定を変更するには、最大 24 時間かかります。</span><span class="sxs-lookup"><span data-stu-id="a3369-124">Any time you change the external communications settings, it can take up to 24 hours for the changes to populate across all the data centers.</span></span>
    
8. <span data-ttu-id="a3369-125">検索し、Skype の連絡先を Skype のビジネス用連絡先の一覧に追加する方法をユーザーに表示します。</span><span class="sxs-lookup"><span data-stu-id="a3369-125">Show your users how to find and add Skype contacts to their list of Skype for Business contacts.</span></span> <span data-ttu-id="a3369-126">[ビジネス用の Skype で人を検索](https://support.office.com/en-us/article/b12500ef-e37f-4d22-aade-c11277e53f19)するには、それらをポイントします。</span><span class="sxs-lookup"><span data-stu-id="a3369-126">Point them to [Search for people in Skype for Business](https://support.office.com/en-us/article/b12500ef-e37f-4d22-aade-c11277e53f19).</span></span>
    
## <a name="test-and-troubleshoot"></a><span data-ttu-id="a3369-127">テストし、トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="a3369-127">Test and troubleshoot</span></span>

<span data-ttu-id="a3369-128">設定をテストするには、企業ファイアウォールの背後にあるではない Skype の連絡先が必要です。</span><span class="sxs-lookup"><span data-stu-id="a3369-128">To test your setup, you need a contact on Skype who's not behind your company firewall.</span></span> <span data-ttu-id="a3369-129">Gmail アカウント、Outlook.com アカウント、または他の種類の電子メール アカウントを使用して Skype に、署名できます。</span><span class="sxs-lookup"><span data-stu-id="a3369-129">They can be signed in to Skype using a Gmail account, Outlook.com account, or other type of email account.</span></span>
  
1. <span data-ttu-id="a3369-130">**24 までの待機時間をテスト**外部の通信設定を変更した場合。</span><span class="sxs-lookup"><span data-stu-id="a3369-130">After you change your external communications settings, **WAIT UP TO 24 HOURS TO TEST**.</span></span>
    
2. <span data-ttu-id="a3369-131">ビジネス用の Skype からサインアウトし、サインインし直して、Skype ディレクトリを検索するオプションを表示するようにします。</span><span class="sxs-lookup"><span data-stu-id="a3369-131">Sign out of Skype for Business and then sign in again so you see the option to search the Skype Directory.</span></span> 
    
    ![Skype ディレクトリをハイライト表示すると、Skype のアカウントを持っている人を検索できます。](../images/76ee9fab-1ac3-4f4a-9569-f5f2606dbb7a.png)
  
3. <span data-ttu-id="a3369-133">ビジネス用の Skype、Skype では、[連絡先の検索し、チャットへの要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="a3369-133">In Skype for Business, search for your contact in Skype, and send a request to chat.</span></span> 
    
    <span data-ttu-id="a3369-134">会社のポリシーのために送信できませんでした、メッセージが表示される場合は、[ファイアウォールの設定](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)を再確認してくださいする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3369-134">If you get the message it couldn't be sent due to company policy, you need to double-check your [firewall settings](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2).</span></span> 
    
4. <span data-ttu-id="a3369-135">問題は、ファイアウォールのないファイアウォールの内側に、コーヒー ショップなどの wifi の場所に移動し、ビジネスの Skype を使用して、Skype に要求を送信するかどうかをテストする別の方法では、チャットにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="a3369-135">Another way to test whether the problem is your firewall is to go to a wifi location not behind your firewall such as a coffee shop, and use Skype for Business to send a request to your Skype contact to chat.</span></span> 
    
   - <span data-ttu-id="a3369-136">**Skype 相手に要求を送信しそれを受信したことはないかどうかは**、チャットへの要求を送信するよう依頼します。</span><span class="sxs-lookup"><span data-stu-id="a3369-136">**If you sent your Skype contact a request and they never received it**, ask them to send you a request to chat.</span></span> <span data-ttu-id="a3369-137">問題は、Skype と Skype のビジネスとの間の接続を確立することが、多くの場合解決されることです。</span><span class="sxs-lookup"><span data-stu-id="a3369-137">If the problem was establishing a connection between Skype and Skype for Business, that often solves it.</span></span>
    
   - <span data-ttu-id="a3369-138">メッセージはコーヒー ショップを通過し、問題がわかっていないしたら職場場合、は、ファイアウォールです。</span><span class="sxs-lookup"><span data-stu-id="a3369-138">Now if the message goes through at the coffee shop but not when you're at work, then you know the problem is your firewall.</span></span> 
    
## <a name="what-you-can-and-cant-do"></a><span data-ttu-id="a3369-139">できるタスクとタスクを実行できません。</span><span class="sxs-lookup"><span data-stu-id="a3369-139">What you can and can't do</span></span>

- <span data-ttu-id="a3369-140">**Mac でのビジネス用の Skype**を検索し、Skype の連絡先と通信する機能がありません。</span><span class="sxs-lookup"><span data-stu-id="a3369-140">**Skype for Business on Mac** doesn't have the ability to search for and communicate with Skype contacts.</span></span>
    
- <span data-ttu-id="a3369-141">ディレクトリ検索を有効にすると、検索し、Skype と Skype をビジネス ユーザーに検索できます。</span><span class="sxs-lookup"><span data-stu-id="a3369-141">When directory search is enabled, you can search for and find Skype and Skype for Business users.</span></span> <span data-ttu-id="a3369-142">何らかの理由により、ディレクトリを検索して見つからないときにすることができます依頼、連絡先を送信し、Skype にサインインし、同意する場合は、そのためできます IM に。</span><span class="sxs-lookup"><span data-stu-id="a3369-142">If for some reason you can't find them by searching the directory, you can send them a contact request, and then have them sign in to Skype and accept it, so you can IM with them.</span></span> 
    
- <span data-ttu-id="a3369-143">Google や Facebook などの他の IM プロバイダーとの IM 接続を許可することはできません。</span><span class="sxs-lookup"><span data-stu-id="a3369-143">It's not possible to allow IM connectivity with other IM providers such as Google or Facebook.</span></span> <span data-ttu-id="a3369-144">携帯電話のテキスト メッセージを送信するビジネス用の Skype を使うことはできません。</span><span class="sxs-lookup"><span data-stu-id="a3369-144">You can't use Skype for Business to send cell phone text messages.</span></span>

- <span data-ttu-id="a3369-145">オーディオの録音またはビジネス用連絡先の連絡先を Skype と Skype との間のビデオ通話をすることはできません。</span><span class="sxs-lookup"><span data-stu-id="a3369-145">It is not possible to record audio or video calls between a Skype Contact and Skype for Business contact.</span></span>
    
## <a name="what-features-are-available-when-adding-skype-contacts"></a><span data-ttu-id="a3369-146">どのような機能は、Skype 連絡先を追加するときに使用しますか。</span><span class="sxs-lookup"><span data-stu-id="a3369-146">What features are available when adding Skype contacts?</span></span>

<span data-ttu-id="a3369-147">Microsoft アカウント (以前 Windows Live ID) を使用して署名した Skype の連絡先は、いくつかを取得できますが、Skype をビジネス ユーザー向けに、通信機能のすべてではありません。</span><span class="sxs-lookup"><span data-stu-id="a3369-147">Skype contacts who signed in with their Microsoft account (formerly Windows Live ID) can get some, but not all, features when they are talking to your Skype for Business users.</span></span>
  
|<span data-ttu-id="a3369-148">**Skype の連絡先で使用できます。**</span><span class="sxs-lookup"><span data-stu-id="a3369-148">**Available with Skype contacts**</span></span>|<span data-ttu-id="a3369-149">**Skype の連絡先では利用できません。**</span><span class="sxs-lookup"><span data-stu-id="a3369-149">**Not available with Skype contacts**</span></span>|
|:-----|:-----|
| <span data-ttu-id="a3369-150">ビデオ会話</span><span class="sxs-lookup"><span data-stu-id="a3369-150">Video conversations</span></span> <br/>  <span data-ttu-id="a3369-151">ユーザー間のインスタント メッセージング</span><span class="sxs-lookup"><span data-stu-id="a3369-151">Person-to-person instant messaging</span></span> <br/>  <span data-ttu-id="a3369-152">プレゼンス</span><span class="sxs-lookup"><span data-stu-id="a3369-152">Presence</span></span> <br/> | <span data-ttu-id="a3369-153">マルチパーティ IM 会話</span><span class="sxs-lookup"><span data-stu-id="a3369-153">Multi-party IM conversations</span></span> <br/>  <span data-ttu-id="a3369-154">3 人以上のオーディオとビデオ会話</span><span class="sxs-lookup"><span data-stu-id="a3369-154">Audio and video conversations with three or more people</span></span> <br/>  <span data-ttu-id="a3369-155">デスクトップとプログラムの共有</span><span class="sxs-lookup"><span data-stu-id="a3369-155">Desktop and program sharing</span></span> <br/> |
   
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a><span data-ttu-id="a3369-156">関連トピック</span><span class="sxs-lookup"><span data-stu-id="a3369-156">Related topics</span></span>

[<span data-ttu-id="a3369-157">外部の Skype for Business ユーザーに連絡できるようにする</span><span class="sxs-lookup"><span data-stu-id="a3369-157">Allow users to contact external Skype for Business users</span></span>](allow-users-to-contact-external-skype-for-business-users.md)
  
[<span data-ttu-id="a3369-158">Skype for Business Online のセットアップ</span><span class="sxs-lookup"><span data-stu-id="a3369-158">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

  
 
