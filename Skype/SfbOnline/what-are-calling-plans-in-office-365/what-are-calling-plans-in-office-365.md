---
title: "Office 365 のプランの呼び出しとは"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 3dc773b9-95e0-4448-b2f1-887c54022429
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
- Strat_SB_PSTN
- LIL_Placement
description: "どのような Office 365 Callings プラン (PSTN 通話) については、どのような地域では利用、およびそれを設定する方法の手順についてさらにします。 "
ms.openlocfilehash: fc594ce769b866d398478c324b741e81195822aa
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="what-are-calling-plans-in-office-365"></a><span data-ttu-id="98a09-103">Office 365 のプランの呼び出しとは</span><span class="sxs-lookup"><span data-stu-id="98a09-103">What are Calling Plans in Office 365?</span></span>

<span data-ttu-id="98a09-p101">通話プランをアドオン電話サービスを Office 365 で、電話システムと組み合わせることにより、組織全体で電話システムになることができます。通話プランを通常の電話番号、ビジネスで他のユーザーを提供し、組織外部の電話の発信や受信できるようにします。プランの呼び出しの 2 種類があります。**国内通話を計画**し、**国内と国際通話プラン**。詳細については、 [Office 365 のプランの呼び出し](../skype-for-business-and-microsoft-teams-add-on-licensing/calling-plans-for-office-365.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="98a09-p101">Calling Plans are an add-on telephone service that, when combined with Phone System in Office 365, can become the phone system for your entire organization. A Calling Plan provides the people in your business with a primary phone number and lets them make and receive phone calls outside of your organization. There are two types of Calling Plans: **Domestic Calling Plan** and a **Domestic and International Calling Plan**. To learn more, see [Calling Plans for Office 365](../skype-for-business-and-microsoft-teams-add-on-licensing/calling-plans-for-office-365.md).</span></span>
  
<span data-ttu-id="98a09-p102">電話番号が割り当てられているユーザーは、ビジネスのデバイスで[Skype for Business Online の取得の携帯電話](../what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online.md)コンピューター、モバイル デバイスなどのすべての Skype の音声通話を作成できます。デスクトップの電話から自分の発信をミュート/ミュート解除などの機能を使って、保留/再開、着信の転送と着信の転送できます。</span><span class="sxs-lookup"><span data-stu-id="98a09-p102">Users who are assigned phone numbers can make voice calls from all Skype for Business devices, including [Getting phones for Skype for Business Online](../what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online.md), PCs, and mobile devices. They can control their calls through desktop phones by using features such as mute/unmute, hold/resume, call transferring, and call forwarding.</span></span>
  
## <a name="start-here"></a><span data-ttu-id="98a09-110">作業の開始</span><span class="sxs-lookup"><span data-stu-id="98a09-110">Start here</span></span>

<span data-ttu-id="98a09-111">これを設定する前に質問があるため、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="98a09-111">Before you set this up, take a look at these topics for questions you might have:</span></span>
  
- <span data-ttu-id="98a09-112">かどうかは住んでいる国/地域の利用可能なプランの呼び出しにがし、分数が表示されます][国と地域の空き時間情報の電話会議とプランの呼び出し](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)、ドロップダウンから下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="98a09-112">To see if your country/region has Calling Plans available and the number of minutes you will get select the [Countries and region availability for Audio Conferencing and Calling Plans](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) from the drop down.</span></span>
    
- <span data-ttu-id="98a09-113">場合は、[組織の通信クレジットを設定する](../skype-for-business-and-microsoft-teams-add-on-licensing/set-up-communications-credits-for-your-organization.md)時間を分単位でアクセスする、考えられます。</span><span class="sxs-lookup"><span data-stu-id="98a09-113">If you think you will go over the number of minutes, [Set up Communications Credits for your organization](../skype-for-business-and-microsoft-teams-add-on-licensing/set-up-communications-credits-for-your-organization.md).</span></span>
    
- <span data-ttu-id="98a09-114">表示価格情報[次のとおり](https://go.microsoft.com/fwlink/?linkid=799761)です。</span><span class="sxs-lookup"><span data-stu-id="98a09-114">You can find pricing information [here](https://go.microsoft.com/fwlink/?linkid=799761).</span></span>
    
## <a name="setting-it-up"></a><span data-ttu-id="98a09-115">設定</span><span class="sxs-lookup"><span data-stu-id="98a09-115">Setting it up</span></span>

<span data-ttu-id="98a09-p103">プランの呼び出しを設定することは簡単です。検索、購入、および新しい電話番号をユーザーに割り当てることができます。Office 365 に、既存の番号を転送することもできます。</span><span class="sxs-lookup"><span data-stu-id="98a09-p103">Setting up Calling Plans is easy. You can search for, acquire, and assign new phone numbers to users. You can also transfer your existing numbers to Office 365.</span></span>
  
 <span data-ttu-id="98a09-119">**ステップ バイ ステップのセットアップ手順については、[プランの呼び出しを設定する](set-up-calling-plans.md)を参照してください。**</span><span class="sxs-lookup"><span data-stu-id="98a09-119">**For step-by-step setup instructions, see [Set up Calling Plans](set-up-calling-plans.md).**</span></span>
  
<span data-ttu-id="98a09-120">電話システムで、プランの呼び出し] と電話会議の詳細については、この YouTube のビデオを参照してください: [Office 365 の電話システムと Skype for Business で会議にダイヤルイン](https://www.youtube.com/watch?v=5Cxawu9mIag&amp;list=PLXtHYVsvn_b8dbRbnL19GUPcBH1UQ7c4x&amp;index=28)します。</span><span class="sxs-lookup"><span data-stu-id="98a09-120">To learn more about Phone System, Calling Plans, and audio conferencing, see this YouTube video: [Office 365 Phone System and dial-in meetings in Skype for Business](https://www.youtube.com/watch?v=5Cxawu9mIag&amp;list=PLXtHYVsvn_b8dbRbnL19GUPcBH1UQ7c4x&amp;index=28).</span></span>

> [!NOTE]
> <span data-ttu-id="98a09-121">これよりも、その他の電話番号を取得する必要がある場合は、[ビジネス製品 - 管理者向けヘルプのサポートに連絡](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)してください。</span><span class="sxs-lookup"><span data-stu-id="98a09-121">If you need to get more telephone numbers than this, please [contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span>


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]

## <a name="related-topics"></a><span data-ttu-id="98a09-122">関連トピック</span><span class="sxs-lookup"><span data-stu-id="98a09-122">Related topics</span></span>
[<span data-ttu-id="98a09-123">Skype Business および Microsoft チーム アドオン ライセンスを許可します。</span><span class="sxs-lookup"><span data-stu-id="98a09-123">Skype for Business and Microsoft Teams add-on licensing</span></span>](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)

[<span data-ttu-id="98a09-124">電話番号のよく寄せられる質問を転送します。</span><span class="sxs-lookup"><span data-stu-id="98a09-124">Transferring phone numbers common questions</span></span>](transferring-phone-numbers-common-questions.md)

[<span data-ttu-id="98a09-125">さまざまなプランの呼び出し用の電話番号</span><span class="sxs-lookup"><span data-stu-id="98a09-125">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)

<span data-ttu-id="98a09-126">[組織の電話番号を管理する](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
[緊急呼び出し条項および条件](emergency-calling-terms-and-conditions.md)</span><span class="sxs-lookup"><span data-stu-id="98a09-126">[Manage phone numbers for your organization](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
[Emergency calling terms and conditions](emergency-calling-terms-and-conditions.md)</span></span>

[<span data-ttu-id="98a09-127">Skype for Business Online: 緊急発信免責事項のラベル</span><span class="sxs-lookup"><span data-stu-id="98a09-127">Skype for Business Online: Emergency Calling disclaimer label</span></span>](https://go.microsoft.com/fwlink/?LinkID=692099)
