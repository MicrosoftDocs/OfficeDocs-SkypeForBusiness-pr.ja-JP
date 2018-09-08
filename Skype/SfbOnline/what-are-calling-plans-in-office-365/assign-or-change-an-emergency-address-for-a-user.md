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
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: 公衆交換電話網 (PSTN) を使用して業務を行うユーザーの緊急対応の住所と電話番号を設定する方法の手順を説明します。
ms.openlocfilehash: 053e0d13109f66b4e714b69f0bc5650e20acdb69
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23885813"
---
# <a name="assign-or-change-an-emergency-address-for-a-user"></a><span data-ttu-id="83e20-103">ユーザーの緊急番号の割り当て、変更を行う</span><span class="sxs-lookup"><span data-stu-id="83e20-103">Assign or change an emergency address for a user</span></span>

<span data-ttu-id="83e20-104">Office 365 のプランの呼び出しを設定している場合は、個々 のユーザーに電話番号と緊急時のアドレスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="83e20-104">When you are setting up Calling Plans in Office 365, you will need to assign a phone number and emergency address to each of your users.</span></span> <span data-ttu-id="83e20-105">作成されていない緊急対応の住所を電話番号に関連付けることはできません。</span><span class="sxs-lookup"><span data-stu-id="83e20-105">The emergency address must be created before you can associate it with a phone number.</span></span> <span data-ttu-id="83e20-106">詳細は、「[緊急の場所、住所、通話ルーティングの概要](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83e20-106">See [What are emergency locations, addresses and call routing?](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing) for more information.</span></span>
  
<span data-ttu-id="83e20-107">Office 365 の通話プランの取得方法とプランの費用については、「[Skype for Business と Microsoft Teams アドオン ライセンス](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83e20-107">Want to know how to get Calling Plans in Office 365 and how much they cost, see [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
  
## <a name="assign-or-change-an-emergency-address"></a><span data-ttu-id="83e20-108">割り当てるか、緊急時のアドレスを変更します。</span><span class="sxs-lookup"><span data-stu-id="83e20-108">Assign or change an emergency address</span></span>

1. <span data-ttu-id="83e20-109">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="83e20-109">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="83e20-110">\*\* [Office 365 管理センター] \*\* > \*\* [Skype for Business]\*\* に移動します。</span><span class="sxs-lookup"><span data-stu-id="83e20-110">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="83e20-111">左側のナビゲーションには、 **音声**、し、 **ユーザーの音声**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="83e20-111">In the left navigation go to **Voice**, then click **Voice users**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="83e20-112">ビジネス管理センターの Skype では、左側のナビゲーションの**音声**オプションを表示するため、まず**E5 のエンタープライズ ライセンス**を少なくとも 1 つ、1 つの**電話システム**のアドオン ライセンスまたはアドオンのライセンスが 1 つの**電話会議**を購入する必要があります。</span><span class="sxs-lookup"><span data-stu-id="83e20-112">For you to see the **Voice** option in the left navigation in the Skype for Business admin center, you must first buy at least one **Enterprise E5 license**, one **Phone System** add-on license, or one **Audio Conferencing** add-on license.</span></span>
    
4. <span data-ttu-id="83e20-113">**音声ユーザー**ページで、緊急対応の住所を変更するユーザーを見つけて、選択します。</span><span class="sxs-lookup"><span data-stu-id="83e20-113">On the **Voice users** page, locate and select the user you want to change the emergency address for.</span></span>
    
5. <span data-ttu-id="83e20-114">操作ウィンドウの [ **緊急対応の場所**] で [ **変更**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="83e20-114">In the Action pane, under **Emergency location**, click **Change**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="83e20-115">既に検証が済んだ緊急対応の住所のみ変更できます。</span><span class="sxs-lookup"><span data-stu-id="83e20-115">You can only change an emergency address that has already been validated.</span></span> <span data-ttu-id="83e20-116">検証されていない緊急対応の住所を変更するには、その住所を変更して、別の緊急対応の住所を作成します。</span><span class="sxs-lookup"><span data-stu-id="83e20-116">To change an emergency address that hasn't been validated, delete it and create another emergency address.</span></span> 
  
6. <span data-ttu-id="83e20-117">**番号の割り当て**] ページで、[**場所の変更**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="83e20-117">On the **Assign number** page, click **Change location**.</span></span>
    
7. <span data-ttu-id="83e20-118">**緊急アドレスへの変更**、[市区町村の名前を入力してくださいし、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="83e20-118">Under **Change emergency address to**, enter the name of the city and click **Search**.</span></span>
    
8. <span data-ttu-id="83e20-119">アドレスのドロップダウン リストから緊急対応の住所を選択し、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="83e20-119">Select the emergency address from the address drop-down list, and then click **Save**.</span></span> 
    
## <a name="related-topics"></a><span data-ttu-id="83e20-120">関連トピック</span><span class="sxs-lookup"><span data-stu-id="83e20-120">Related topics</span></span>
[<span data-ttu-id="83e20-121">住所検証について</span><span class="sxs-lookup"><span data-stu-id="83e20-121">What is address validation?</span></span>](what-is-address-validation.md)

<span data-ttu-id="83e20-122">[[[Skype for Business 新しい電話番号の申請](/microsoftteams/manage-phone-numbers-for-your-organization)] に移動することによって、電話番号を取得するために利用できるすべてのフォームを一覧表示してダウンロードすることができます。](/microsoftteams/manage-phone-numbers-for-your-organization)</span><span class="sxs-lookup"><span data-stu-id="83e20-122">[Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization)</span></span>

[<span data-ttu-id="83e20-123">緊急通話の利用条件</span><span class="sxs-lookup"><span data-stu-id="83e20-123">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="83e20-124">[Skype for Business Online: 緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="83e20-124">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 