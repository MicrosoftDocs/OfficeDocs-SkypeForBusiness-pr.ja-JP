---
title: Office 365 の通話プランについて
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 3dc773b9-95e0-4448-b2f1-887c54022429
ms.tgt.pltfrm: cloud
ms.service:
- skype-for-business-online
- msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
- LIL_Placement
description: 'どのような Office 365 Callings 計画 (PSTN 通話) については、どのような領域では使用、およびそれを設定する方法の手順に移動する場所です。 '
ms.openlocfilehash: 032527a0d2244d0121329220a9ef45491ec19017
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2018
ms.locfileid: "25013596"
---
# <a name="what-are-calling-plans-in-office-365"></a><span data-ttu-id="77f9e-103">Office 365 の通話プランについて</span><span class="sxs-lookup"><span data-stu-id="77f9e-103">What are Calling Plans in Office 365?</span></span>

<span data-ttu-id="77f9e-104">通話プランは、アドオンの電話サービスを Office 365 の電話システムと組み合わせることにより、組織全体の電話システムになることができます。</span><span class="sxs-lookup"><span data-stu-id="77f9e-104">Calling Plans are an add-on telephone service that, when combined with Phone System in Office 365, can become the phone system for your entire organization.</span></span> <span data-ttu-id="77f9e-105">呼び出す計画基本の電話番号とお客様のビジネスの人が用意されていて、組織外の電話通話を送受信することができます。</span><span class="sxs-lookup"><span data-stu-id="77f9e-105">A Calling Plan provides the people in your business with a primary phone number and lets them make and receive phone calls outside of your organization.</span></span> <span data-ttu-id="77f9e-106">プランの呼び出しの 2 種類があります: 国内を呼び出すことを**計画**し**国内および国際の計画を呼び出します**。</span><span class="sxs-lookup"><span data-stu-id="77f9e-106">There are two types of Calling Plans: **Domestic Calling Plan** and a **Domestic and International Calling Plan**.</span></span> <span data-ttu-id="77f9e-107">詳細については、 [Office 365 のプランを呼び出す](calling-plans-for-office-365.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77f9e-107">To learn more, see [Calling Plans for Office 365](calling-plans-for-office-365.md).</span></span>
  
<span data-ttu-id="77f9e-108">電話番号が割り当てられているユーザーはビジネスのデバイスは、[オンライン ビジネスの Skype を得る電話](/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online)Pc、およびモバイル デバイスを含む、すべての Skype からの音声通話を行えます。</span><span class="sxs-lookup"><span data-stu-id="77f9e-108">Users who are assigned phone numbers can make voice calls from all Skype for Business devices, including [Getting phones for Skype for Business Online](/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online), PCs, and mobile devices.</span></span> <span data-ttu-id="77f9e-109">ことができますミュート/ミュート解除などの機能を使用してデスクトップ電話経由での呼び出しを制御、保留/再開、呼び出しの転送、および着信の転送します。</span><span class="sxs-lookup"><span data-stu-id="77f9e-109">They can control their calls through desktop phones by using features such as mute/unmute, hold/resume, call transferring, and call forwarding.</span></span>
  
## <a name="start-here"></a><span data-ttu-id="77f9e-110">ここから開始</span><span class="sxs-lookup"><span data-stu-id="77f9e-110">Start here</span></span>

<span data-ttu-id="77f9e-111">この設定をして、前に質問があるこれらのトピックを見てください。</span><span class="sxs-lookup"><span data-stu-id="77f9e-111">Before you set this up, take a look at these topics for questions you might have:</span></span>
  
- <span data-ttu-id="77f9e-112">かどうかに、国/地域では、利用可能なプランを呼び出すことは、表示される時間を分単位を選択、[オーディオ会議や予定を呼び出すことで利用可能な地域の国や](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)ドロップ ダウンします。</span><span class="sxs-lookup"><span data-stu-id="77f9e-112">To see if your country/region has Calling Plans available and the number of minutes you will get select the [Countries and region availability for Audio Conferencing and Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) from the drop down.</span></span>
    
- <span data-ttu-id="77f9e-113">場合は[、組織の通信のクレジットを設定](set-up-communications-credits-for-your-organization.md)、時間を分単位で移動しますと思います。</span><span class="sxs-lookup"><span data-stu-id="77f9e-113">If you think you will go over the number of minutes, [Set up Communications Credits for your organization](set-up-communications-credits-for-your-organization.md).</span></span>
    
- <span data-ttu-id="77f9e-114">表示価格情報[は、ここ](https://go.microsoft.com/fwlink/?linkid=799761)です。</span><span class="sxs-lookup"><span data-stu-id="77f9e-114">You can find pricing information [here](https://go.microsoft.com/fwlink/?linkid=799761).</span></span>
    
## <a name="setting-it-up"></a><span data-ttu-id="77f9e-115">設定時に</span><span class="sxs-lookup"><span data-stu-id="77f9e-115">Setting it up</span></span>

<span data-ttu-id="77f9e-116">プランの呼び出しを設定することは簡単です。</span><span class="sxs-lookup"><span data-stu-id="77f9e-116">Setting up Calling Plans is easy.</span></span> <span data-ttu-id="77f9e-117">検索、購入、および新しい電話番号をユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="77f9e-117">You can search for, acquire, and assign new phone numbers to users.</span></span> <span data-ttu-id="77f9e-118">Office 365 に、既存の番号を転送することもできます。</span><span class="sxs-lookup"><span data-stu-id="77f9e-118">You can also transfer your existing numbers to Office 365.</span></span>
  
 <span data-ttu-id="77f9e-119">**ステップ バイ ステップのセットアップ手順については、[計画を呼び出す設定](set-up-calling-plans.md)を参照してください。**</span><span class="sxs-lookup"><span data-stu-id="77f9e-119">**For step-by-step setup instructions, see [Set up Calling Plans](set-up-calling-plans.md).**</span></span>
  
<span data-ttu-id="77f9e-120">電話システム、計画を呼び出すこと、および音声会議の詳細については、この YouTube のビデオを参照してください: [Office 365 の電話システムとビジネスの Skype でダイヤルイン会議](https://www.youtube.com/watch?v=5Cxawu9mIag&amp;list=PLXtHYVsvn_b8dbRbnL19GUPcBH1UQ7c4x&amp;index=28)。</span><span class="sxs-lookup"><span data-stu-id="77f9e-120">To learn more about Phone System, Calling Plans, and audio conferencing, see this YouTube video: [Office 365 Phone System and dial-in meetings in Skype for Business](https://www.youtube.com/watch?v=5Cxawu9mIag&amp;list=PLXtHYVsvn_b8dbRbnL19GUPcBH1UQ7c4x&amp;index=28).</span></span>

> [!NOTE]
> <span data-ttu-id="77f9e-121">さらに追加で電話番号が必要な場合は、「[一般法人向け Office 365 のサポートへのお問い合わせ - 管理者向けヘルプ](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="77f9e-121">If you need to get more telephone numbers than this, please [contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span>


## <a name="related-topics"></a><span data-ttu-id="77f9e-122">関連トピック</span><span class="sxs-lookup"><span data-stu-id="77f9e-122">Related topics</span></span>
[<span data-ttu-id="77f9e-123">Skype for Business と Microsoft Teams のアドオン ライセンス</span><span class="sxs-lookup"><span data-stu-id="77f9e-123">Skype for Business and Microsoft Teams add-on licensing</span></span>](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing)

[<span data-ttu-id="77f9e-124">電話番号の移行に関するよくある質問</span><span class="sxs-lookup"><span data-stu-id="77f9e-124">Transferring phone numbers common questions</span></span>](transferring-phone-numbers-common-questions.md)

[<span data-ttu-id="77f9e-125">通話プランで使用されるさまざまな種類の電話番号</span><span class="sxs-lookup"><span data-stu-id="77f9e-125">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)

<span data-ttu-id="77f9e-126">[組織のために電話番号を管理する](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
[緊急通話の利用条件](emergency-calling-terms-and-conditions.md)</span><span class="sxs-lookup"><span data-stu-id="77f9e-126">[Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
[Emergency calling terms and conditions](emergency-calling-terms-and-conditions.md)</span></span>

<span data-ttu-id="77f9e-127">[Skype for Business Online: 緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="77f9e-127">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 