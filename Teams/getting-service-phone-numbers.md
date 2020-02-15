---
title: サービス電話番号を取得する
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, jastark, oscarr, makolomi
ms.topic: article
ms.assetid: e434aeb2-af99-40e7-981e-a474f0383734
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
description: Office 365 からユーザーの電話番号を取得することに加えて、電話会議 (会議ブリッジの場合)、自動応答、通話キュー (サービス番号とも呼ばれます) などのサービスの有料または無料の電話番号を検索して取得することができます。 サービス用電話番号の同時通話容量は、ユーザーまたは登録者の電話番号より大きくなります。
ms.openlocfilehash: a8cd5582cdcbddff1a6c6375230864e569111a0e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42031051"
---
# <a name="getting-service-phone-numbers"></a><span data-ttu-id="1eb00-104">サービス電話番号を取得する</span><span class="sxs-lookup"><span data-stu-id="1eb00-104">Getting service phone numbers</span></span>

<span data-ttu-id="1eb00-p102">Office 365 ユーザー用の電話番号の取得に加え、電話会議 (会議ブリッジ用)、自動応答、通話キュー (別名: サービス番号) などのサービス用に、有料または無料電話番号を検索し、取得できます。ユーザーまたはサブスクライバーの電話番号に比べて、サービス電話番号はより高い同時通話の処理能力を持ちます。たとえば、ユーザーの電話番号 1 つが同時に取り扱える通話数はごく少数なのに対して、1 つのサービス番号は何百もの通話を同時に取り扱えます。</span><span class="sxs-lookup"><span data-stu-id="1eb00-p102">In addition to getting phone numbers for your users from Office 365, you can search and acquire toll or toll-free phone numbers for services such as audio conferencing (for conference bridges), auto attendants, and call queues (also called service numbers). Service phone numbers have a higher concurrent calling capacity than user or subscriber phone numbers. For example, a service number can handle 100s of calls simultaneously, whereas a user's phone number can only handle a few calls simultaneously.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1eb00-108">Office 365 コミュニケーション クレジットは、フリー ダイヤル番号を取得できるように、最初にセットアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1eb00-108">Office 365 Communications Credits must be set up first in order to acquire toll-free numbers.</span></span> <span data-ttu-id="1eb00-109">「[組織のためにコミュニケーションクレジットを設定する](/microsoftteams/set-up-communications-credits-for-your-organization)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1eb00-109">See [Set up Communications Credits for your organization](/microsoftteams/set-up-communications-credits-for-your-organization).</span></span> 
  
<span data-ttu-id="1eb00-110">サービス番号を取得して、Skype for Business および Microsoft Teams で使用できるようにするには、次の2つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="1eb00-110">You have two ways of getting service numbers so you can use them with Skype for Business and Microsoft Teams:</span></span>
  
- <span data-ttu-id="1eb00-111">Office 365 から新しい番号を取得します。</span><span class="sxs-lookup"><span data-stu-id="1eb00-111">Get new numbers from Office 365.</span></span>
    
- <span data-ttu-id="1eb00-112">サービスプロバイダーまたは電話会社から Office 365 に既存の番号を移行する。</span><span class="sxs-lookup"><span data-stu-id="1eb00-112">Port or transfer your existing numbers from your service provider or phone carrier to Office 365.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1eb00-113">サービス番号を転送する場合は、同時通話容量が優先され、正しく構成されていることを確認するために、 [Microsoft サポート](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)に連絡することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1eb00-113">When you transfer your service numbers, it is highly recommended that you contact [Microsoft support](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) to ensure that the higher concurrent calling capacity is considered and configured correctly.</span></span>
  
## <a name="get-new-service-numbers"></a><span data-ttu-id="1eb00-114">新しいサービス番号を取得する</span><span class="sxs-lookup"><span data-stu-id="1eb00-114">Get new service numbers</span></span>

<span data-ttu-id="1eb00-115">![Skype for Business のロゴを表示したアイコン](media/sfb-logo-30x30.png) **Skype for Business 管理センターの使用**</span><span class="sxs-lookup"><span data-stu-id="1eb00-115">![An icon showing the Skype for Business logo](media/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="1eb00-116">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="1eb00-116">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="1eb00-117">**管理センター** > **チームと skype** > **skype 従来の管理者**にお進みください。</span><span class="sxs-lookup"><span data-stu-id="1eb00-117">Go to the **Admin center** > **Teams and Skype** > **Skype Legacy Admin**.</span></span>
    
3. <span data-ttu-id="1eb00-118">In the left navigation go to **Voice** > **Phone numbers** > **Add** then click **New service numbers**.</span><span class="sxs-lookup"><span data-stu-id="1eb00-118">In the left navigation go to **Voice** > **Phone numbers** > **Add new number**, and then click **New service numbers**.</span></span>
    
    > [!IMPORTANT] 
    > <span data-ttu-id="1eb00-119">Skype for Business 管理センターの左のナビゲーションに [**音声**] オプションが表示されるようにするには、最初に **Enterprise E5 ライセンス**、**電話システム**アドオン ライセンス、または**電話会議**アドオン ライセンスを少なくとも 1 件購入する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1eb00-119">For you to see the **Voice** option in the left navigation in the Skype for Business admin center, you must first buy at least one **Enterprise E5 license**, one **Phone System** add-on license, or one **Audio Conferencing** add-on license.</span></span>
    
4. <span data-ttu-id="1eb00-120">[**新しいサービス番号の追加**] ページで、次を選択します。</span><span class="sxs-lookup"><span data-stu-id="1eb00-120">On the **Add new service numbers** page, choose the following:</span></span>
    
   - <span data-ttu-id="1eb00-121">**国/地域**</span><span class="sxs-lookup"><span data-stu-id="1eb00-121">**Country/Region**</span></span>
    
   - <span data-ttu-id="1eb00-122">**都道府県/地域**</span><span class="sxs-lookup"><span data-stu-id="1eb00-122">**State/Region**</span></span>
    
   - <span data-ttu-id="1eb00-123">**市区町村**</span><span class="sxs-lookup"><span data-stu-id="1eb00-123">**City**</span></span>
    
5. <span data-ttu-id="1eb00-124">[ **数量**] の下に、組織に必要な電話番号の数を入力し、[ **追加**] をクリックして、予約を作成します。</span><span class="sxs-lookup"><span data-stu-id="1eb00-124">Under **Quantity**, enter the number of phone numbers that you want for your organization and click **Add** to create a reservation.</span></span> <span data-ttu-id="1eb00-125">電話番号を選択するには、10分間かかります。10分以上かかる場合は、電話番号のプールに電話番号が返されます。</span><span class="sxs-lookup"><span data-stu-id="1eb00-125">You have 10 minutes to select your phone numbers; if you take more than 10 minutes, the phone numbers will be returned to the pool of phone numbers.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1eb00-126">[**取得可能なサービスの合計**数] の横に表示されるライセンス数に基づいて、電話番号の数を確認できます。</span><span class="sxs-lookup"><span data-stu-id="1eb00-126">You can see the number of phone numbers, which is based on the number of licenses, listed next to **Total Service numbers your can acquire**.</span></span> <span data-ttu-id="1eb00-127">詳細については、「[取得できる電話番号の数](/microsoftteams/how-many-phone-numbers-can-you-get)を確認する方法」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1eb00-127">For details, see [How many phone numbers can you get?](/microsoftteams/how-many-phone-numbers-can-you-get)</span></span>
  
6. <span data-ttu-id="1eb00-128">[ **番号を表示**] をクリックすると、電話番号の完全なリストを表示できます。</span><span class="sxs-lookup"><span data-stu-id="1eb00-128">You can click **Show numbers** to see the full list of phone numbers.</span></span> <span data-ttu-id="1eb00-129">これは、リスト内の特定の電話番号を選択しない場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="1eb00-129">This is helpful if you don't want to select a specific phone number in the list.</span></span>
    
7. <span data-ttu-id="1eb00-130">目的の電話番号を選んでから、[ **番号の入手**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="1eb00-130">Select the phone numbers you want, and then click **Acquire numbers**.</span></span>
    
### <a name="assign-service-numbers"></a><span data-ttu-id="1eb00-131">サービス番号を割り当てる</span><span class="sxs-lookup"><span data-stu-id="1eb00-131">Assign service numbers</span></span>

<span data-ttu-id="1eb00-132">サービス番号を取得すると、電話会議ブリッジに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="1eb00-132">Once you have your service numbers, they can then be assigned to an audio conferencing bridge.</span></span> <span data-ttu-id="1eb00-133">これを行う場合は、「[電話会議ブリッジの有料または無料の電話番号を変更する](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1eb00-133">To do this, see [Change the toll or toll free numbers on your Audio Conferencing bridge](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).</span></span>
  
### <a name="port-or-transfer-existing-service-numbers"></a><span data-ttu-id="1eb00-134">既存のサービス番号を移行または転送する</span><span class="sxs-lookup"><span data-stu-id="1eb00-134">Port or transfer existing service numbers</span></span>

<span data-ttu-id="1eb00-p108">現在のサービス プロバイダーまたは通信事業者からサービス番号を移動する場合は、ポートの注文を手動で Microsoft に送信する必要があります。承認状 (LOA) を使用して、移動するサービス番号の種類 (有料電話番号または無料電話番号) ごとに別々のポート注文を送信する必要があります。承認状 (LOA) では、適切な種類のサービス番号が選択されている必要があります。Microsoft サポートに連絡する際は、移動する番号は*ユーザーまたはサブスクライバーの番号ではなく*、サービス番号であることを必ず指定してください。これを指定しない場合、実際の通話件数を処理するには同時通話処理能力が不十分なものになる可能性があります。電話番号の移動や電話番号に関するその他の手続きを行うには、「[組織の電話番号を管理する](/microsoftteams/manage-phone-numbers-for-your-organization)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1eb00-p108">If you want to transfer service numbers from your current service provider or carrier, you need to manually submit a port order to Microsoft. You have to submit separate port orders for each type of service number (toll vs. toll-free) that you will be transferring using a Letter of Authorization (LOA). In the Letter of Authorization (LOA), you must select the correct type of service number. When contacting Microsoft support, please make sure you specify that you are transferring a service number (*and not a user or subscriber number*), or the concurrent calling capacity may not be enough to handle call volumes. If you want to transfer phone numbers or do other things with your phone numbers, see [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization).</span></span>

> [!NOTE]
> <span data-ttu-id="1eb00-140">さらに多くの電話番号を取得する必要がある場合は、 [ビジネス製品に関するサポート (管理者向けヘルプ) に問い合わせる](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="1eb00-140">If you need to get more telephone numbers than this, please [contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="1eb00-141">関連トピック</span><span class="sxs-lookup"><span data-stu-id="1eb00-141">Related topics</span></span>
[<span data-ttu-id="1eb00-142">Office 365 の電話システムでできること</span><span class="sxs-lookup"><span data-stu-id="1eb00-142">Here's what you get with Phone System in Office 365</span></span>](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[<span data-ttu-id="1eb00-143">国および地域ごとの電話会議および通話プランの利用可能性</span><span class="sxs-lookup"><span data-stu-id="1eb00-143">Country and region availability for Audio Conferencing and Calling Plans</span></span>](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

  
 