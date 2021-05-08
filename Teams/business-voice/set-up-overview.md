---
title: 設定Microsoft 365 Business Voice
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: 中小企業または組織でMicrosoft 365 Business Voiceを設定する方法について学習します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 534005df5161a69fd64ac94c444046508b9d7fd1
ms.sourcegitcommit: 49cdcf344c63c805bcb6365804c6f5d1393e926a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2021
ms.locfileid: "52130486"
---
# <a name="set-up-microsoft-365-business-voice"></a><span data-ttu-id="258bc-103">設定Microsoft 365 Business Voice</span><span class="sxs-lookup"><span data-stu-id="258bc-103">Set up Microsoft 365 Business Voice</span></span>

<span data-ttu-id="258bc-104">Business Voice は、既存のテレフォニー プロバイダーを置き換える完全な電話システムです。</span><span class="sxs-lookup"><span data-stu-id="258bc-104">Business Voice is a complete phone system that can replace your existing telephony provider.</span></span> <span data-ttu-id="258bc-105">新しい会社で初めて電話番号を設定する場合でも、従来のオンプレミステレフォニー プロバイダーから移行する確立されたビジネスの場合でも、これらの記事の手順は Business Voice を使い始めて実行するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="258bc-105">Whether you're a new business setting up phone numbers for the first time, or an established business moving from a legacy on-premises telephony provider, the steps in these articles can help you get up and running with Business Voice.</span></span> <span data-ttu-id="258bc-106">Business Voice の設定が完了したら、</span><span class="sxs-lookup"><span data-stu-id="258bc-106">When you're finished setting up Business Voice:</span></span>

* <span data-ttu-id="258bc-107">メインの会社の電話回線で、有料または無料の電話を受け取る事が可能です。</span><span class="sxs-lookup"><span data-stu-id="258bc-107">You'll be able to receive toll or toll-free phone calls on a main company phone line.</span></span> <span data-ttu-id="258bc-108">必要に合って通話メニューを設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="258bc-108">You can even set up a call menu if you want.</span></span>
* <span data-ttu-id="258bc-109">Business Voice でセットアップされたユーザーは、デバイスがインストールされている任意のデバイスとの間で通話を発信および受信するために使用できる独自のダイヤルTeamsされます。</span><span class="sxs-lookup"><span data-stu-id="258bc-109">Users set up with Business Voice will have their own direct-dial phone numbers that they can use to make and receive phone calls from any device with Teams installed.</span></span>
* <span data-ttu-id="258bc-110">会議の参加者は、クライアントから参加できない場合は、通常の電話を使って会議にTeamsできます。</span><span class="sxs-lookup"><span data-stu-id="258bc-110">Meeting participants will be able to call in to meetings using a regular phone if they're unable to join from a Teams client.</span></span>
* <span data-ttu-id="258bc-111">既存の電話番号がある場合は、Business Voice に移動した後も引き続き使用できます。</span><span class="sxs-lookup"><span data-stu-id="258bc-111">If you have existing phone numbers, you'll be able to continue using them after they're moved to Business Voice.</span></span>

<span data-ttu-id="258bc-112">Business Voice の詳細については、「Business Voice とは」[をMicrosoft 365 Business Voice。](whats-business-voice.md)</span><span class="sxs-lookup"><span data-stu-id="258bc-112">If you want to learn more about Business Voice, check out [What is Microsoft 365 Business Voice?](whats-business-voice.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="258bc-113">これらの記事の情報は、通話プランを使用した Business Voice **にのみ** 適用されます。</span><span class="sxs-lookup"><span data-stu-id="258bc-113">The information in these articles is applicable to Business Voice **with** Calling Plan only.</span></span> <span data-ttu-id="258bc-114">通話プラン付き Business Voice は、一部の国と地域でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="258bc-114">Business Voice with Calling Plan is available only in select countries and regions.</span></span> <span data-ttu-id="258bc-115">Business Voice のセットアップを開始する前に [、[Business Voice](country-region-availability.md) の国と地域の可用性] をオンにし、お客様の国または地域が通話プランで Business Voice をサポートするかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="258bc-115">Before you start setting up Business Voice, check [Country and region availability for Business Voice](country-region-availability.md) to see whether your country or region supports Business Voice with Calling Plan.</span></span>
>
> <span data-ttu-id="258bc-116">テナントが通話プラン付き Business Voice をサポートしていない国または地域にある場合は、「[Microsoft 販売店またはパートナーからヘルプを取得する](reseller-partner-support.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="258bc-116">If your tenant is located in a country or region that doesn't support Business Voice with Calling Plan, check out [Get help from a Microsoft reseller or partner](reseller-partner-support.md).</span></span>
>
> <span data-ttu-id="258bc-117">Microsoft Teams と Business Voice は、ユーザーのメールボックスが Microsoft 365 にある場合にのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="258bc-117">Microsoft Teams and Business Voice only work when your users' mailboxes are located in Microsoft 365.</span></span>  <span data-ttu-id="258bc-118">オンプレミスの Exchange Server 上のメールボックスはサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="258bc-118">They don't support mailboxes on on-premises Exchange Server.</span></span>
>
> <span data-ttu-id="258bc-119">このセットアップ プロセスでは、ハイブリッド デプロイSkype for Businessサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="258bc-119">This setup process doesn't support Skype for Business hybrid deployments.</span></span> <span data-ttu-id="258bc-120">Skype for Business ハイブリッド展開があり、Business Voice をセットアップする場合は、「[組織での電話システムのセットアップ](../setting-up-your-phone-system.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="258bc-120">If you have a Skype for Business hybrid deployment and want to set up Business Voice, check out [Set up Phone System in your organization](../setting-up-your-phone-system.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="258bc-121">はじめに</span><span class="sxs-lookup"><span data-stu-id="258bc-121">Before you begin</span></span>

<span data-ttu-id="258bc-122">Business Voice を設定する前に、いくつかの操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="258bc-122">Before you set up Business Voice, there are a few things you need to do.</span></span> <span data-ttu-id="258bc-123">次のタスクは、組織が Business Voice の準備ができていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="258bc-123">The following tasks will make sure your organization is ready for Business Voice.</span></span>

* <span data-ttu-id="258bc-124">**Business Voice ライセンスを購入** し、無料電話番号を取得したり、遠距離通話を行う場合は、コミュニケーション クレジットを使用します。</span><span class="sxs-lookup"><span data-stu-id="258bc-124">**Buy Business Voice licenses** and, if you want to get a toll-free number or make long-distance phone calls, Communication Credits.</span></span> <span data-ttu-id="258bc-125">詳細については、「What do I need to buy to use [Microsoft 365 Business Voice?」を参照してください](what-to-buy.md)。</span><span class="sxs-lookup"><span data-stu-id="258bc-125">For more information, see [What do I need to buy to use Microsoft 365 Business Voice?](what-to-buy.md).</span></span>
* <span data-ttu-id="258bc-126">**インターネット接続で Business Voice をサポートできる必要があります**。</span><span class="sxs-lookup"><span data-stu-id="258bc-126">**Make sure your Internet connection can support Business Voice**.</span></span> <span data-ttu-id="258bc-127">詳細については [、「Business Voice のインターネット接続を確認する」を参照してください](get-ready-internet.md)。</span><span class="sxs-lookup"><span data-stu-id="258bc-127">For more information, see [Check your Internet connection for Business Voice](get-ready-internet.md).</span></span>
* <span data-ttu-id="258bc-128">**ユーザーのデバイスTeamsを設定し**、ボイスメール応答メッセージを設定し、ユーザーがメッセージの詳細をTeams。</span><span class="sxs-lookup"><span data-stu-id="258bc-128">**Set up Teams on your users' devices**, set up voicemail greetings, and help your users learn about Teams.</span></span> <span data-ttu-id="258bc-129">詳細については、「ユーザーを作成する準備をする方法[」をMicrosoft 365 Business Voice。](prepare-users.md)</span><span class="sxs-lookup"><span data-stu-id="258bc-129">For more information, see [How do I get my users ready for Microsoft 365 Business Voice?](prepare-users.md).</span></span>

<span data-ttu-id="258bc-130">Business Voice 用に組織を準備した後、[次のステップ: Business Voice の設定を開始する] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="258bc-130">After you've prepare your organization for Business Voice, select **Next step: Start setting up Business Voice**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="258bc-131">次の手順: Business Voice の設定を開始する</span><span class="sxs-lookup"><span data-stu-id="258bc-131">Next step: Start setting up Business Voice</span></span>](set-up-emergency-locations.md)
