---
title: ユーザー用の緊急対応の場所を変更する
ms.author: tonysmit
author: tonysmit
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
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: 'ユーザー用の緊急対応の場所を変更する方法を説明します。無制限の数の場所を利用して、従業員がフロアや建物を移動するときの緊急対応の場所を変更できます。 '
ms.openlocfilehash: 7ebec7ca6a2180702eec9e24b3165eb501d4a097
ms.sourcegitcommit: 19fb0279985251c00cd507a8d13b8499b19e2808
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/28/2018
ms.locfileid: "25347113"
---
# <a name="change-the-emergency-location-for-a-user"></a><span data-ttu-id="83741-104">ユーザー用の緊急対応の場所を変更する</span><span class="sxs-lookup"><span data-stu-id="83741-104">Change the emergency location for a user</span></span>

<span data-ttu-id="83741-105">ユーザーに電話番号が割り当てられるときに、有効な各電話番号には、緊急対応の住所が関連付けられなければなりません (Office 365 から電話番号を取得するとき、または電話番号を転送するときに、緊急対応の住所が電話番号と関連付けられます)。</span><span class="sxs-lookup"><span data-stu-id="83741-105">Each active phone number must have an emergency address (associated when you get a phone number in Office 365 or when you transfer a phone number) when the phone number is assigned to the user.</span></span> <span data-ttu-id="83741-106">電話番号を緊急対応の住所と関連付けるときに、緊急対応の場所も追加して、物理的な場所のより正確な位置を示すことができます。</span><span class="sxs-lookup"><span data-stu-id="83741-106">When you associate the number with an emergency address, you can also add an emergency location to provide a more exact location within a physical location.</span></span> <span data-ttu-id="83741-107">緊急の場所は、床、建物の翼やオフィスの番号は、ユーザーを指定できます。</span><span class="sxs-lookup"><span data-stu-id="83741-107">An emergency location can be the floor, building wing, or office number where the user is located.</span></span> <span data-ttu-id="83741-108">特定の緊急対応の住所に対して無制限の数の緊急対応の場所を指定できます。また、ユーザーが別のオフィスや建物に移動する場合 (例えば、ユーザーが 34 階から 35 階に移動した場合)、緊急対応の場所を変更できます。</span><span class="sxs-lookup"><span data-stu-id="83741-108">You can have an unlimited number of locations for a given emergency address, and you can change the emergency location if the user moves to a different office or building—for example, if the user moves from floor 34 to floor 35.</span></span>
  
<span data-ttu-id="83741-109">Office 365 の通話プランの取得方法とかかる費用については、「[Skype for Business と Microsoft Teams アドオン ライセンシング](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83741-109">To learn how to get Calling Plans in Office 365 and how much they cost, see [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
  
## <a name="change-the-emergency-location-for-a-user"></a><span data-ttu-id="83741-110">ユーザー用の緊急対応の場所を変更する</span><span class="sxs-lookup"><span data-stu-id="83741-110">Change the emergency location for a user</span></span>

1. <span data-ttu-id="83741-111">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="83741-111">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="83741-112">移動、**マイクロソフトのチームとビジネス管理センターの Skype** > **従来のポータル**です。</span><span class="sxs-lookup"><span data-stu-id="83741-112">Go to the **Microsoft Teams and Skype for Business Admin Center** > **Legacy portal**.</span></span>
    
3. <span data-ttu-id="83741-113">左側のナビゲーションでは、**音声**に移動 > **音声ユーザー**です。</span><span class="sxs-lookup"><span data-stu-id="83741-113">In the left navigation go to **Voice** > **Voice users**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="83741-114">ビジネス管理センターの Skype では、左側のナビゲーションの**音声**オプションを表示するため、まず**E5 のエンタープライズ ライセンス**を少なくとも 1 つ、1 つの**電話システム**のアドオン ライセンスまたはアドオンのライセンスが 1 つの**電話会議**を購入する必要があります。</span><span class="sxs-lookup"><span data-stu-id="83741-114">For you to see the **Voice** option in the left navigation in the Skype for Business admin center, you must first buy at least one **Enterprise E5 license**, one **Phone System** add-on license, or one **Audio Conferencing** add-on license.</span></span>
    
4. <span data-ttu-id="83741-115">**音声ユーザー**ページで、緊急対応の場所を変更するユーザーを見つけて、選択します。</span><span class="sxs-lookup"><span data-stu-id="83741-115">On the **Voice users** page, locate and select the user you want to change the emergency location for.</span></span>
    
5. <span data-ttu-id="83741-116">操作ウィンドウの [ **緊急対応の場所**] で [ **変更**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="83741-116">In the Action pane, under **Emergency location**, click **Change**.</span></span>
    
6. <span data-ttu-id="83741-117">**番号の割り当て**] ページで、[**場所の変更**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="83741-117">On the **Assign number** page, click **Change location**.</span></span> 
    
7. <span data-ttu-id="83741-118">[**緊急時のアドレスの変更**を都市の名前をボックスに入力し、**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="83741-118">Under **Change emergency address to**, enter the name of the city in the box and click **Search**.</span></span>
    
8. <span data-ttu-id="83741-119">リストから緊急対応の場所を選択し、[ **保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="83741-119">Select the emergency location from the list, and then click **Save**.</span></span>
    
    <span data-ttu-id="83741-120">新しい緊急対応の場所を追加する場合は、「[組織の緊急対応の場所を追加、変更、削除する](add-change-or-remove-an-emergency-location-for-your-organization.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83741-120">If you want to add a new emergency location, see [Add, change, or remove an emergency location for your organization](add-change-or-remove-an-emergency-location-for-your-organization.md).</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="83741-121">関連トピック</span><span class="sxs-lookup"><span data-stu-id="83741-121">Related topics</span></span>
[<span data-ttu-id="83741-122">組織の緊急対応の住所を追加または削除する</span><span class="sxs-lookup"><span data-stu-id="83741-122">Add or remove an emergency address for your organization</span></span>](add-or-remove-an-emergency-address-for-your-organization.md)

[<span data-ttu-id="83741-123">組織の緊急対応の場所を追加、変更、削除する</span><span class="sxs-lookup"><span data-stu-id="83741-123">Add, change, or remove an emergency location for your organization</span></span>](add-change-or-remove-an-emergency-location-for-your-organization.md)

[<span data-ttu-id="83741-124">住所検証について</span><span class="sxs-lookup"><span data-stu-id="83741-124">What is address validation?</span></span>](what-is-address-validation.md)

<span data-ttu-id="83741-125">[[[Skype for Business 新しい電話番号の申請](/microsoftteams/manage-phone-numbers-for-your-organization)] に移動することによって、電話番号を取得するために利用できるすべてのフォームを一覧表示してダウンロードすることができます。](/microsoftteams/manage-phone-numbers-for-your-organization)</span><span class="sxs-lookup"><span data-stu-id="83741-125">[Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization)</span></span>

[<span data-ttu-id="83741-126">緊急通話の利用条件</span><span class="sxs-lookup"><span data-stu-id="83741-126">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="83741-127">[Skype for Business Online: 緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="83741-127">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 