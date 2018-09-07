---
title: ユーザーの緊急対応の住所を変更する
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 5412636c-ad0e-48a5-b199-5925156abee4
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Calling Plans
description: '米国とヨーロッパで公衆交換電話網 (PSTN) を使用して業務を行うユーザーの緊急対応の住所を変更する方法の手順を参照してください。 '
ms.openlocfilehash: 5f08e7503e95028e5045404dc4a0ba294addd481
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23860551"
---
# <a name="change-the-emergency-address-for-a-user"></a><span data-ttu-id="74618-103">ユーザーの緊急対応の住所を変更する</span><span class="sxs-lookup"><span data-stu-id="74618-103">Change the emergency address for a user</span></span>

<span data-ttu-id="74618-104">Office 365 の通話プランを設定している場合、電話番号またはユーザーごとに緊急対応の住所を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="74618-104">When you are setting up Calling Plans in Office 365, you will need to assign an emergency address to each phone number or user.</span></span> <span data-ttu-id="74618-105">欧州諸国では、Office 365 から電話番号を取得するとき、または Office 365 に電話番号を転送するときに、緊急対応の住所が電話番号と関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="74618-105">In European countries, the emergency address is associated with the phone number when you get it from Office 365 or when you transfer a phone number over to Office 365.</span></span> <span data-ttu-id="74618-106">米国では、電話番号がユーザーに割り当てられるときに、緊急対応の住所が電話番号と関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="74618-106">In the United States, the emergency address is associated with the phone number when it is assigned to the user.</span></span> <span data-ttu-id="74618-107">緊急対応の住所が割り当てられたユーザーが新しい場所に引っ越す場合、緊急対応の住所は変更できます。</span><span class="sxs-lookup"><span data-stu-id="74618-107">The emergency address can be changed if the user it is assigned to moves to a new location.</span></span> <span data-ttu-id="74618-108">緊急対応の場所および住所の詳細については、「[緊急対応の場所、アドレス、通話ルーティングの概要](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="74618-108">For more about emergency addresses and locations, see [What are emergency locations, addresses and call routing?](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing)</span></span>
  
<span data-ttu-id="74618-109">Office 365 の通話プランの取得方法とかかる費用については、「[Skype for Business と Microsoft Teams アドオン ライセンシング](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="74618-109">To learn how to get Calling Plans in Office 365 and how much they cost, see [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
  
## <a name="change-the-emergency-address-for-a-user"></a><span data-ttu-id="74618-110">ユーザーの緊急対応の住所を変更する</span><span class="sxs-lookup"><span data-stu-id="74618-110">Change the emergency address for a user</span></span>

<span data-ttu-id="74618-111">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Skype for Business の管理センターを使用する**</span><span class="sxs-lookup"><span data-stu-id="74618-111">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="74618-112">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="74618-112">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="74618-113">**[Office 365 管理センター]** > **[Skype for Business]** に進みます。</span><span class="sxs-lookup"><span data-stu-id="74618-113">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="74618-114">左側のナビゲーションで、**[音声]** > **[音声ユーザー]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="74618-114">In the left navigation, click **Voice** > **Voice users**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="74618-115">Skype for Business 管理センターの左にあるナビゲーションで [**音声**] オプションが表示される場合、最初に少なくとも 1 つの **Enterprise E5 ライセンス**、1 つの**電話システム** アドオン ライセンス、または 1 つの**電話会議**アドオン ライセンスを購入する必要があります。</span><span class="sxs-lookup"><span data-stu-id="74618-115">IMPORTANT: For you to see the **Voice** option in the left navigation in the Skype for Business admin center, you must first buy at least one **Enterprise E5 license**, one **Phone System** add-on license, or one **Audio Conferencing** add-on license.</span></span>
    
4. <span data-ttu-id="74618-116">**音声ユーザー**ページで、緊急対応の住所を変更するユーザーを見つけて、選択します。</span><span class="sxs-lookup"><span data-stu-id="74618-116">On the **Voice users** page, locate and select the user you want to change the emergency address for.</span></span>
    
5. <span data-ttu-id="74618-117">操作ウィンドウの [**緊急対応の場所**] で [**変更**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="74618-117">In the Action pane, under **Emergency location**, click **Change**.</span></span>
    
6. <span data-ttu-id="74618-118">**番号の割り当て**ページで、**[場所の変更]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="74618-118">On the **Assign number** page, under Emergency location click **Change location**.</span></span> 
    
7. <span data-ttu-id="74618-119">[**緊急対応の住所を次に変更**] のボックスに都市の名前を入力し、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="74618-119">Under **Change emergency address to**, in the Find City box, enter the name of the city and click **Search**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="74618-120">既に検証されている緊急対応の住所のみ変更できます。</span><span class="sxs-lookup"><span data-stu-id="74618-120">You can only change an emergency address that has already been validated.</span></span> <span data-ttu-id="74618-121">検証されていない緊急対応の住所を変更するには、その住所を変更して、別の緊急対応の住所を作成します。</span><span class="sxs-lookup"><span data-stu-id="74618-121">To change an emergency address that hasn't been validated, delete it and create another emergency address.</span></span> 
  
8. <span data-ttu-id="74618-122">リストから新しい緊急対応の住所を選択し、[ **保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="74618-122">Select a new emergency address from the list, and then click **Save**.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="74618-123">関連トピック</span><span class="sxs-lookup"><span data-stu-id="74618-123">Related topics</span></span>
[<span data-ttu-id="74618-124">組織の緊急対応の住所を追加または削除する</span><span class="sxs-lookup"><span data-stu-id="74618-124">Add or remove an emergency address for your organization</span></span>](add-or-remove-an-emergency-address-for-your-organization.md)

[<span data-ttu-id="74618-125">組織の緊急対応の場所を追加、変更、削除する</span><span class="sxs-lookup"><span data-stu-id="74618-125">Add, change, or remove an emergency location for your organization</span></span>](add-change-or-remove-an-emergency-location-for-your-organization.md)

[<span data-ttu-id="74618-126">住所検証について</span><span class="sxs-lookup"><span data-stu-id="74618-126">What is address validation?</span></span>](what-is-address-validation.md)

[<span data-ttu-id="74618-127">組織の電話番号を管理する</span><span class="sxs-lookup"><span data-stu-id="74618-127">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="74618-128">緊急通話の利用条件</span><span class="sxs-lookup"><span data-stu-id="74618-128">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="74618-129">[Skype for Business Online: 緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="74618-129">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 