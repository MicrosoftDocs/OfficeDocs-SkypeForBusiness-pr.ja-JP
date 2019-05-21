---
title: ユーザーの緊急対応の場所の割り当てまたは変更
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 2d5d3c87-af1e-487e-b86c-261f2e5a0661
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: 'Learn how to change the emergency location for your users. With an unlimited number of locations, you can change emergency locations as employees move floors or buildings. '
ms.openlocfilehash: 49410b0ba98e6d193749b558e479d98de1f4ef29
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303836"
---
# <a name="assign-or-change-the-emergency-location-for-a-user"></a><span data-ttu-id="6f6bd-104">ユーザーの緊急対応の場所の割り当てまたは変更</span><span class="sxs-lookup"><span data-stu-id="6f6bd-104">Assign or change the emergency location for a user</span></span>

<span data-ttu-id="6f6bd-105">電話番号をユーザーに割り当てるときは、有効な電話番号ごとに対応する緊急対応の住所が必要です。</span><span class="sxs-lookup"><span data-stu-id="6f6bd-105">Each active phone number must have an associated emergency address when you assign the phone number to a user.</span></span> <span data-ttu-id="6f6bd-106">(住所は、Office 365 で電話番号を取得する場合、または電話番号を移行する場合に関連付けます)。電話番号を緊急対応の住所に関連付けている場合は、緊急対応の場所を追加して、物理的な場所でより正確な位置情報を提供することもできます。</span><span class="sxs-lookup"><span data-stu-id="6f6bd-106">(You associate the address when you get a phone number in Office 365 or when you transfer a phone number.) When you associate the number with an emergency address, you can also add an emergency location to provide a more exact location within a physical location.</span></span> <span data-ttu-id="6f6bd-107">An emergency location can be the floor, building wing, or office number where the user is located.</span><span class="sxs-lookup"><span data-stu-id="6f6bd-107">An emergency location can be the floor, building wing, or office number where the user is located.</span></span> <span data-ttu-id="6f6bd-108">特定の緊急対応の住所には無制限の場所を含めることができます。また、ユーザーがフロア34からフロア35に移動した場合など、ユーザーが別のオフィスや建物に移動した場合は、緊急対応の場所を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="6f6bd-108">You can have an unlimited number of locations for a given emergency address, and you can change the emergency location if the user moves to a different office or building—for example, if the user moves from floor 34 to floor 35.</span></span>
  
<span data-ttu-id="6f6bd-109">Office 365 の通話プランの取得方法とかかる費用については、「[Skype for Business と Microsoft Teams アドオン ライセンシング](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6f6bd-109">To learn how to get Calling Plans in Office 365 and how much they cost, see [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
  
## <a name="assign-or-change-the-emergency-location"></a><span data-ttu-id="6f6bd-110">緊急対応の場所を割り当てる、または変更する</span><span class="sxs-lookup"><span data-stu-id="6f6bd-110">Assign or change the emergency location</span></span>

1. <span data-ttu-id="6f6bd-111">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="6f6bd-111">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="6f6bd-112">**Microsoft Teams 管理センター** > の**従来のポータル**に移動します。</span><span class="sxs-lookup"><span data-stu-id="6f6bd-112">Go to the **Microsoft Teams admin center** > **Legacy portal**.</span></span>
    
3. <span data-ttu-id="6f6bd-113">左のナビゲーションで、[**音声** > **音声ユーザー**に移動します。</span><span class="sxs-lookup"><span data-stu-id="6f6bd-113">In the left navigation go to **Voice** > **Voice users**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="6f6bd-114">Skype for Business 管理センターの左のナビゲーションに [**音声**] オプションが表示されるようにするには、最初に **Enterprise E5 ライセンス**、**電話システム**アドオン ライセンス、または**電話会議**アドオン ライセンスを少なくとも 1 件購入する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f6bd-114">For you to see the **Voice** option in the left navigation in the Skype for Business admin center, you must first buy at least one **Enterprise E5 license**, one **Phone System** add-on license, or one **Audio Conferencing** add-on license.</span></span>
    
4. <span data-ttu-id="6f6bd-115">[**音声ユーザー** ] ページで、緊急対応の場所を変更するユーザーを探して選びます。</span><span class="sxs-lookup"><span data-stu-id="6f6bd-115">On the **Voice users** page, locate and select the user you want to change the emergency location for.</span></span>
    
5. <span data-ttu-id="6f6bd-116">操作ウィンドウの [ **緊急対応の場所**] で [ **変更**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6f6bd-116">In the Action pane, under **Emergency location**, click **Change**.</span></span>
    
6. <span data-ttu-id="6f6bd-117">[**番号を割り当てる**] ページで、[**場所の変更**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6f6bd-117">On the **Assign number** page, click **Change location**.</span></span> 
    
7. <span data-ttu-id="6f6bd-118">[**緊急対応の住所の変更先**] で、ボックスに市区町村の名前を入力し、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6f6bd-118">Under **Change emergency address to**, enter the name of the city in the box and click **Search**.</span></span>

8. <span data-ttu-id="6f6bd-119">ドロップダウンリストから [**場所で検索**] を選択し、場所の部分名 (「**床面**」など) を入力して、「**検索**」をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6f6bd-119">Select **Search by location** from the drop-down list, enter a partial name for the location (for example, enter **floor**), and then click **Search**.</span></span> 
    
8. <span data-ttu-id="6f6bd-120">リストから緊急対応の場所を選択し、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6f6bd-120">Select the emergency location from the list, and then click **Save**.</span></span>
    
    <span data-ttu-id="6f6bd-121">リストに表示される新しい緊急対応の場所を追加する場合は、「[組織の緊急対応の場所を追加、変更、削除](add-change-or-remove-an-emergency-location-for-your-organization.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6f6bd-121">If you want to add a new emergency location that will appear on the list, see [Add, change, or remove an emergency location for your organization](add-change-or-remove-an-emergency-location-for-your-organization.md).</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="6f6bd-122">関連トピック</span><span class="sxs-lookup"><span data-stu-id="6f6bd-122">Related topics</span></span>

[<span data-ttu-id="6f6bd-123">Powershell を使用して緊急対応の場所を割り当てる</span><span class="sxs-lookup"><span data-stu-id="6f6bd-123">Assign an emergency response locations via powershell</span></span>](https://github.com/MicrosoftDocs/office-docs-powershell/blob/master/skype/skype-ps/skype/Set-CsOnlineVoiceUser.md)

[<span data-ttu-id="6f6bd-124">組織の緊急対応の住所を追加または削除する</span><span class="sxs-lookup"><span data-stu-id="6f6bd-124">Add or remove an emergency address for your organization</span></span>](add-or-remove-an-emergency-address-for-your-organization.md)

[<span data-ttu-id="6f6bd-125">組織の緊急対応の場所を追加、変更、削除する</span><span class="sxs-lookup"><span data-stu-id="6f6bd-125">Add, change, or remove an emergency location for your organization</span></span>](add-change-or-remove-an-emergency-location-for-your-organization.md)

[<span data-ttu-id="6f6bd-126">住所検証とは何ですか?</span><span class="sxs-lookup"><span data-stu-id="6f6bd-126">What is address validation?</span></span>](what-is-address-validation.md)

<span data-ttu-id="6f6bd-127">[[[Skype for Business 新しい電話番号の申請](/microsoftteams/manage-phone-numbers-for-your-organization)] に移動することによって、電話番号を取得するために利用できるすべてのフォームを一覧表示してダウンロードすることができます。](/microsoftteams/manage-phone-numbers-for-your-organization)</span><span class="sxs-lookup"><span data-stu-id="6f6bd-127">[Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization)</span></span>

[<span data-ttu-id="6f6bd-128">緊急通話の利用条件</span><span class="sxs-lookup"><span data-stu-id="6f6bd-128">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="6f6bd-129">[Skype for Business Online: 緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="6f6bd-129">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

[<span data-ttu-id="6f6bd-130">CsOnlineVoiceUser コマンドレット</span><span class="sxs-lookup"><span data-stu-id="6f6bd-130">Set-CsOnlineVoiceUser cmdlet</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/set-csonlinevoiceuser?view=skype-ps)

  
 
