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
description: 'ユーザー用の緊急対応の場所を変更する方法を説明します。無制限の数の場所を利用して、従業員がフロアや建物を移動するときの緊急対応の場所を変更できます。 '
ms.openlocfilehash: 6f554a4233f6b3c60711281978212e1cbec35c10
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2018
ms.locfileid: "23779280"
---
# <a name="change-the-emergency-location-for-a-user"></a><span data-ttu-id="68f6c-104">ユーザー用の緊急対応の場所を変更する</span><span class="sxs-lookup"><span data-stu-id="68f6c-104">Change the emergency location for a user</span></span>

<span data-ttu-id="68f6c-105">ユーザーに電話番号が割り当てられるときに、有効な各電話番号には、緊急対応の住所が関連付けられなければなりません (Office 365 から電話番号を取得するとき、または電話番号を転送するときに、緊急対応の住所が電話番号と関連付けられます)。</span><span class="sxs-lookup"><span data-stu-id="68f6c-105">Each active phone number must have an emergency address (associated when you get a phone number in Office 365 or when you transfer a phone number) when the phone number is assigned to the user.</span></span> <span data-ttu-id="68f6c-106">電話番号を緊急対応の住所と関連付けるときに、緊急対応の場所も追加して、物理的な場所のより正確な位置を示すことができます。</span><span class="sxs-lookup"><span data-stu-id="68f6c-106">When you associate the number with an emergency address, you can also add an emergency location to provide a more exact location within a physical location.</span></span> <span data-ttu-id="68f6c-107">緊急対応の場所には、ユーザーがいる場所の階数、建物の棟、オフィスの番号などを使用できます。</span><span class="sxs-lookup"><span data-stu-id="68f6c-107">An emergency location is typically a floor, building wing, or office number where the user is located.</span></span> <span data-ttu-id="68f6c-108">特定の緊急対応の住所に対して無制限の数の緊急対応の場所を指定できます。また、ユーザーが別のオフィスや建物に移動する場合 (例えば、ユーザーが 34 階から 35 階に移動した場合)、緊急対応の場所を変更できます。</span><span class="sxs-lookup"><span data-stu-id="68f6c-108">You can have an unlimited number of locations for a given emergency address, and you can change the emergency location if the user moves to a different office or building—for example, if the user moves from floor 34 to floor 35.</span></span>
  
<span data-ttu-id="68f6c-109">Office 365 の通話プランの取得方法とかかる費用については、「[Skype for Business と Microsoft Teams アドオン ライセンシング](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="68f6c-109">To learn how to get Calling Plans in Office 365 and how much they cost, see [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
  
## <a name="change-the-emergency-location-for-a-user"></a><span data-ttu-id="68f6c-110">ユーザー用の緊急対応の場所を変更する</span><span class="sxs-lookup"><span data-stu-id="68f6c-110">Change the emergency location for a user</span></span>

1. <span data-ttu-id="68f6c-111">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="68f6c-111">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="68f6c-112">[**Office 365 管理センター** ] >  [**Skype for Business**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="68f6c-112">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="68f6c-113">左側のナビゲーションで、**[音声]** > **[音声ユーザー]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="68f6c-113">In the left navigation, go to **Voice** > **Phone numbers**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="68f6c-114">Skype for Business 管理センターの左にあるナビゲーションで [**音声**] オプションが表示される場合、最初に少なくとも 1 つの **Enterprise E5 ライセンス**、1 つの**電話システム** アドオン ライセンス、または 1 つの**電話会議**アドオン ライセンスを購入する必要があります。</span><span class="sxs-lookup"><span data-stu-id="68f6c-114">IMPORTANT: For you to see the **Voice** option in the left navigation in the Skype for Business admin center, you must first buy at least one **Enterprise E5 license**, one **Phone System** add-on license, or one **Audio Conferencing** add-on license.</span></span>
    
4. <span data-ttu-id="68f6c-115">**音声ユーザー**ページで、緊急対応の場所を変更するユーザーを見つけて、選択します。</span><span class="sxs-lookup"><span data-stu-id="68f6c-115">On the **Voice users** page, locate and select the user you want to change the emergency location for.</span></span>
    
5. <span data-ttu-id="68f6c-116">[操作] ウィンドウの [ **緊急対応の場所**] で、[ **変更**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="68f6c-116">In the Action pane, under **Emergency location**, click **Change**.</span></span>
    
6. <span data-ttu-id="68f6c-117">**番号の割り当て**ページで、**[場所の変更]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="68f6c-117">On the **Assign number** page, under Emergency location click **Change location**.</span></span> 
    
7. <span data-ttu-id="68f6c-118">[ **緊急対応の住所を次に変更**] の [ 市区町村の検索] ボックスで、市区町村の名前を入力し、[ **検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="68f6c-118">Under **Change emergency address to**, in the Find City box, enter the name of the city and click **Search**.</span></span>
    
8. <span data-ttu-id="68f6c-119">リストから緊急対応の場所を選択し、[ **保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="68f6c-119">Select the emergency location from the list, and then click **Save**.</span></span>
    
    <span data-ttu-id="68f6c-120">新しい緊急対応の場所を追加する場合は、「[組織の緊急対応の場所を追加、変更、削除する](add-change-or-remove-an-emergency-location-for-your-organization.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="68f6c-120">If you want to add a new emergency location, see [Add, change, or remove an emergency location for your organization](add-change-or-remove-an-emergency-location-for-your-organization.md).</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="68f6c-121">関連トピック</span><span class="sxs-lookup"><span data-stu-id="68f6c-121">Related topics</span></span>
[<span data-ttu-id="68f6c-122">組織の緊急対応の住所を追加または削除する</span><span class="sxs-lookup"><span data-stu-id="68f6c-122">Add or remove an emergency address for your organization</span></span>](add-or-remove-an-emergency-address-for-your-organization.md)

[<span data-ttu-id="68f6c-123">組織の緊急対応の場所を追加、変更、削除する</span><span class="sxs-lookup"><span data-stu-id="68f6c-123">Add, change, or remove an emergency location for your organization</span></span>](add-change-or-remove-an-emergency-location-for-your-organization.md)

[<span data-ttu-id="68f6c-124">住所検証について</span><span class="sxs-lookup"><span data-stu-id="68f6c-124">What is address validation?</span></span>](what-is-address-validation.md)

[<span data-ttu-id="68f6c-125">組織の電話番号を管理する</span><span class="sxs-lookup"><span data-stu-id="68f6c-125">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="68f6c-126">緊急通話の利用条件</span><span class="sxs-lookup"><span data-stu-id="68f6c-126">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="68f6c-127">[Skype for Business Online: 緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="68f6c-127">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 