---
title: 電話番号を Business Voice にポートする
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
localization_priority: Priority
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: ''
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8959b335d695630f991017c789916bfd2fcf697c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102913"
---
# <a name="move-port-phone-numbers-to-business-voice"></a><span data-ttu-id="53fd5-102">電話番号を Business Voice に移行 (ポート) する</span><span class="sxs-lookup"><span data-stu-id="53fd5-102">Move (port) phone numbers to Business Voice</span></span>

> [!IMPORTANT]
> <span data-ttu-id="53fd5-103">この記事の情報は、通話プラン **付き** Business Voice のみに適用されます。</span><span class="sxs-lookup"><span data-stu-id="53fd5-103">The information in this article is applicable to Business Voice **with** Calling Plan only.</span></span> <span data-ttu-id="53fd5-104">通話プラン付き Business Voice は、一部の国と地域でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="53fd5-104">Business Voice with Calling Plan is available only in select countries and regions.</span></span> <span data-ttu-id="53fd5-105">この記事を読む前に、「[Business Voice を利用できる国と地域](country-region-availability.md)」で、お住まいの国または地域が通話プラン付き Business Voice をサポートしているかどうかを確認してください。</span><span class="sxs-lookup"><span data-stu-id="53fd5-105">Before reading this article, check [Country and region availability for Business Voice](country-region-availability.md) to see whether your country or region supports Business Voice with Calling Plan.</span></span>
>
> <span data-ttu-id="53fd5-106">テナントが通話プラン付き Business Voice をサポートしていない国または地域にある場合は、「[Microsoft 販売店またはパートナーからヘルプを取得する](reseller-partner-support.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="53fd5-106">If your tenant is located in a country or region that doesn't support Business Voice with Calling Plan, check out [Get help from a Microsoft reseller or partner](reseller-partner-support.md).</span></span>

<span data-ttu-id="53fd5-107">[作業の開始] ウィザードで Business Voice をセットアップすると、メインの会社の回線と、Business Voice ライセンスを割り当てたユーザーに電話番号が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="53fd5-107">When the Getting Started wizard helps you set up Business Voice, it assigns phone numbers for the main company line and for any users that you've assigned a Business Voice license to.</span></span> <span data-ttu-id="53fd5-108">Business Voice に移行するときに保持したい電話番号が既にある場合は、電話番号ポータビリティと呼ばれるプロセスを使用して、それらを Business Voice に引き継ぎ、移行することができます。</span><span class="sxs-lookup"><span data-stu-id="53fd5-108">If you already have phone numbers that you want to keep when you move to Business Voice, you can bring them with you by using a process called phone number porting to bring them over to Business Voice.</span></span> <span data-ttu-id="53fd5-109">電話番号を Business Voice にポートした後、ユーザーとサービスに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="53fd5-109">After you port your phone numbers to Business Voice, you assign them to users and services.</span></span> <span data-ttu-id="53fd5-110">以前の番号は、[作業の開始] ウィザードが割り当てた一時的な数字と置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="53fd5-110">The old numbers replace the temporary numbers that the Getting Started wizard assigned.</span></span>

<span data-ttu-id="53fd5-111">番号を Business Voice に移動する前に、「[電話番号の移行に関するよくある質問](../phone-number-calling-plans/port-order-overview.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="53fd5-111">Before you move numbers to Business Voice, take a look at [Transferring phone numbers common questions](../phone-number-calling-plans/port-order-overview.md).</span></span> <span data-ttu-id="53fd5-112">この記事には、サポートされている国や地域、転送できる番号と転送できない番号、必要な情報を含む質問への回答が含まれています。</span><span class="sxs-lookup"><span data-stu-id="53fd5-112">This article includes answers to questions including what countries and regions are supported, what numbers can and can't be transferred, and what information you'll need.</span></span>

<span data-ttu-id="53fd5-113">電話番号を Business Voice に移動する準備ができたら、「[Office 365 に電話番号を転送する](../phone-number-calling-plans/transfer-phone-numbers-to-teams.md)」の手順に従って番号移行注文を作成します。</span><span class="sxs-lookup"><span data-stu-id="53fd5-113">When you're ready to move your phone numbers to Business Voice, follow the steps in [Transfer phone numbers to Office 365](../phone-number-calling-plans/transfer-phone-numbers-to-teams.md) to create a port order.</span></span> <span data-ttu-id="53fd5-114">注文には、現在の電話サービス キャリアから Business Voice に番号を移動するために必要な情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="53fd5-114">The order includes the information that's needed to move your numbers from your current phone service carrier to Business Voice.</span></span>

<span data-ttu-id="53fd5-115">電話番号を Business Voice に移動した後、それらをユーザーに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="53fd5-115">After your phone numbers have been moved to Business Voice, you need to assign them to people.</span></span> <span data-ttu-id="53fd5-116">これを行うには、「[ユーザーの電話番号を変更する](../assign-change-or-remove-a-phone-number-for-a-user.md#change-a-phone-number-for-a-user)」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="53fd5-116">To do that, follow the steps in [Change a phone number for a user](../assign-change-or-remove-a-phone-number-for-a-user.md#change-a-phone-number-for-a-user).</span></span> <span data-ttu-id="53fd5-117">これらの手順を実行すると、ユーザーに一時的に割り当てられた電話番号がポートした元の電話番号に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="53fd5-117">When you follow these steps, you'll replace the phone number that was temporarily assigned to the user with their original phone number that you ported over.</span></span>

<span data-ttu-id="53fd5-118">サポートが必要な場合は、お知らせください。</span><span class="sxs-lookup"><span data-stu-id="53fd5-118">If you need help, let us know!</span></span> <span data-ttu-id="53fd5-119">電話番号をできるだけ簡単に Business Voice に移行できるようにお手伝いします。</span><span class="sxs-lookup"><span data-stu-id="53fd5-119">We're here to help you get your phone numbers moved to Business Voice as easy as possible.</span></span> <span data-ttu-id="53fd5-120">以下の情報が含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="53fd5-120">Be sure to include the following information:</span></span>
- <span data-ttu-id="53fd5-121">組織の ID (例えば、***contoso***.onmicrosoft.com)</span><span class="sxs-lookup"><span data-stu-id="53fd5-121">Your organization ID (such as ***contoso***.onmicrosoft.com)</span></span>
- <span data-ttu-id="53fd5-122">ヘルプが必要なデータの種類と数</span><span class="sxs-lookup"><span data-stu-id="53fd5-122">What types and how many numbers you need help with</span></span>
- <span data-ttu-id="53fd5-123">アカウントで承認を行うユーザー</span><span class="sxs-lookup"><span data-stu-id="53fd5-123">The authorizing person on your account</span></span>
- <span data-ttu-id="53fd5-124">問題または質問の説明</span><span class="sxs-lookup"><span data-stu-id="53fd5-124">A description of the issue or question that you have</span></span>

<span data-ttu-id="53fd5-125">カナダおよび米国の電話番号については、[ptn@microsoft.com](mailto:ptn@microsoft.com) にリクエストを送信してください。</span><span class="sxs-lookup"><span data-stu-id="53fd5-125">For help with phone numbers in Canada and the United States, send your request to [ptn@microsoft.com](mailto:ptn@microsoft.com).</span></span>

<span data-ttu-id="53fd5-126">ヨーロッパの電話番号については、[ptneu@microsoft.com](mailto:ptneu@microsoft.com) にリクエストを送信してください。</span><span class="sxs-lookup"><span data-stu-id="53fd5-126">For help with phone numbers in Europe, send your request to [ptneu@microsoft.com](mailto:ptneu@microsoft.com).</span></span>