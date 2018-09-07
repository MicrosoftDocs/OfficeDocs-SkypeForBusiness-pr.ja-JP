---
title: ユーザーの緊急番号の割り当て、変更を行う
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 1411b594-1e88-44c9-9f60-2202f9bb8553
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
description: 公衆交換電話網 (PSTN) を使用して業務を行うユーザーの緊急対応の住所と電話番号を設定する方法の手順を説明します。
ms.openlocfilehash: e4ca1934ddb604c5efd81fd6a21b6f18d39b144b
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23854869"
---
# <a name="assign-or-change-an-emergency-address-for-a-user"></a><span data-ttu-id="c267d-103">ユーザーの緊急番号の割り当て、変更を行う</span><span class="sxs-lookup"><span data-stu-id="c267d-103">Assign or change an emergency address for a user</span></span>

<span data-ttu-id="c267d-104">Office 365 の通話プランを設定している場合、電話番号と緊急対応の住所をユーザーごとに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="c267d-104">When you set up Calling Plans in Office 365, you will need to assign a phone number and emergency address to each of your users.</span></span> <span data-ttu-id="c267d-105">作成されていない緊急対応の住所を電話番号に関連付けることはできません。</span><span class="sxs-lookup"><span data-stu-id="c267d-105">The emergency address must be created before you can associate it with a phone number.</span></span> <span data-ttu-id="c267d-106">詳細は、「[緊急の場所、住所、通話ルーティングの概要](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c267d-106">See [What are emergency locations, addresses and call routing?](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing) for more information.</span></span>
  
<span data-ttu-id="c267d-107">Office 365 の通話プランの取得方法とプランの費用については、「[Skype for Business と Microsoft Teams アドオン ライセンス](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c267d-107">Want to know how to get Calling Plans in Office 365 and how much they cost, see [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
  
## <a name="assign-or-change-an-emergency-address"></a><span data-ttu-id="c267d-108">ユーザーの緊急対応の住所の割り当てまたは変更を行う</span><span class="sxs-lookup"><span data-stu-id="c267d-108">Assign or change an emergency address for a user</span></span>

1. <span data-ttu-id="c267d-109">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="c267d-109">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="c267d-110">|||UNTRANSLATED_CONTENT_START|||Go to the **Office 365 admin center** > **Skype for Business**.|||UNTRANSLATED_CONTENT_END|||</span><span class="sxs-lookup"><span data-stu-id="c267d-110">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="c267d-111">左側のナビゲーションには、 **音声**、し、 **ユーザーの音声**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c267d-111">In the left navigation go to **Voice**, then click **Voice users**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="c267d-112">Skype for Business 管理センターの左にあるナビゲーションで [**音声**] オプションが表示される場合、最初に少なくとも 1 つの **Enterprise E5 ライセンス**、1 つの**電話システム** アドオン ライセンス、または 1 つの**電話会議**アドオン ライセンスを購入する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c267d-112">IMPORTANT: For you to see the **Voice** option in the left navigation in the Skype for Business admin center, you must first buy at least one **Enterprise E5 license**, one **Phone System** add-on license, or one **Audio Conferencing** add-on license.</span></span>
    
4. <span data-ttu-id="c267d-113">**音声ユーザー**ページで、緊急対応の住所を変更するユーザーを見つけて、選択します。</span><span class="sxs-lookup"><span data-stu-id="c267d-113">On the **Voice users** page, locate and select the user you want to change the emergency address for.</span></span>
    
5. <span data-ttu-id="c267d-114">操作ウィンドウの [ **緊急対応の場所**] で [ **変更**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c267d-114">In the Action pane, under **Emergency location**, click **Change**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c267d-115">既に検証が済んだ緊急対応の住所のみ変更できます。</span><span class="sxs-lookup"><span data-stu-id="c267d-115">You can only change an emergency address that has already been validated.</span></span> <span data-ttu-id="c267d-116">検証されていない緊急対応の住所を変更するには、その住所を変更して、別の緊急対応の住所を作成します。</span><span class="sxs-lookup"><span data-stu-id="c267d-116">To change an emergency address that hasn't been validated, delete it and create another emergency address.</span></span> 
  
6. <span data-ttu-id="c267d-117">**番号の割り当て**ページで、[**場所の変更**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c267d-117">On the **Assign number** page, under Emergency location click **Change location**.</span></span>
    
7. <span data-ttu-id="c267d-118">[**緊急対応の住所を次に変更**] で都市の名前を入力し、[ **検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c267d-118">Under **Change emergency address to**, in the Find City box, enter the name of the city and click **Search**.</span></span>
    
8. <span data-ttu-id="c267d-119">アドレスのドロップダウン リストから緊急対応の住所を選択し、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c267d-119">Select the emergency address from the address drop-down list, and then click **Save**.</span></span> 
    
## <a name="related-topics"></a><span data-ttu-id="c267d-120">このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「Skype for Business Online 用 Windows PowerShell モジュール」からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="c267d-120">Related topics</span></span>
[<span data-ttu-id="c267d-121">住所検証について</span><span class="sxs-lookup"><span data-stu-id="c267d-121">What is address validation?</span></span>](what-is-address-validation.md)

[<span data-ttu-id="c267d-122">|||UNTRANSLATED_CONTENT_START|||Manage phone numbers for your organization|||UNTRANSLATED_CONTENT_END|||</span><span class="sxs-lookup"><span data-stu-id="c267d-122">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="c267d-123">緊急通話の利用条件</span><span class="sxs-lookup"><span data-stu-id="c267d-123">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="c267d-124">[Skype for Business Online: 緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="c267d-124">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 