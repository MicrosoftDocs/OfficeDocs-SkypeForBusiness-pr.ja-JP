---
title: 組織の緊急対応の住所を追加、変更、削除する
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: f954c67c-b73c-4473-b6cd-a0fbcd0fd4c9
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
description: 'Skype for Business のアカウントに緊急対応の住所を追加する方法を学びます。 '
ms.openlocfilehash: 5c22875873d2164c14d690523404481a514ef388
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34293737"
---
# <a name="add-change-or-remove-an-emergency-address-for-your-organization"></a><span data-ttu-id="0abe6-103">組織の緊急対応の住所を追加、変更、削除する</span><span class="sxs-lookup"><span data-stu-id="0abe6-103">Add, change, or remove an emergency address for your organization</span></span>

<span data-ttu-id="0abe6-104">緊急対応の住所は電話番号と関連付けられている必要がありますが、このような状況は国/地域によって異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="0abe6-104">An emergency address must be associated with a phone number, but when this happens can vary between country/regions.</span></span> <span data-ttu-id="0abe6-105">例えば米国では、電話番号をユーザーに割り当てるときに、緊急対応の住所を関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="0abe6-105">For example, in the United States, you need to associate an emergency address when you assign the phone number to the user.</span></span> <span data-ttu-id="0abe6-106">英国では、Office 365 から電話番号を取得するか、現在のサービス プロバイダーから電話番号を移すときに、緊急対応の住所をその電話番号に関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="0abe6-106">In the United Kingdom, you need to associate an emergency address to the phone number when you are getting the phone numbers from Office 365 or transferring phone numbers from your current service provider.</span></span>
  
<span data-ttu-id="0abe6-107">どの国や地域であっても、緊急対応の住所に 1 つ以上の場所を追加すること、また、緊急対応の住所を削除することができます。</span><span class="sxs-lookup"><span data-stu-id="0abe6-107">No matter which country/region you are in, it's possible to add a location or locations to an emergency address or remove an emergency address.</span></span> <span data-ttu-id="0abe6-108">組織内の物理的な場所の数に応じて、建物、フロア、オフィスの場所を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="0abe6-108">Depending on the number of physical locations in your organization, you can create them for buildings, floors, and offices.</span></span> <span data-ttu-id="0abe6-109">詳細については、「[緊急対応の場所、住所、通話のルーティングの概要](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing)」 をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0abe6-109">See [What are emergency locations, addresses, and call routing?](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing) for some details.</span></span>
  
<span data-ttu-id="0abe6-110">Office 365 の通話プランの取得方法とプランの費用については、「[Skype for Business と Microsoft Teams アドオン ライセンス](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0abe6-110">To learn how to get a Calling Plan and how much it costs, see [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
  
## <a name="add-an-emergency-address"></a><span data-ttu-id="0abe6-111">緊急対応の住所を追加する</span><span class="sxs-lookup"><span data-stu-id="0abe6-111">Add an emergency address</span></span>

1. <span data-ttu-id="0abe6-112">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="0abe6-112">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="0abe6-113">**Microsoft Teams 管理センター** > の**従来のポータル**に移動します。</span><span class="sxs-lookup"><span data-stu-id="0abe6-113">Go to the **Microsoft Teams admin center** > **Legacy portal**.</span></span>
    
3. <span data-ttu-id="0abe6-114">左側のナビゲーションで、[**音声**][ > **緊急対応の場所**] に移動し、[**新しい住所を追加** ] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="0abe6-114">In the left navigation, go to **Voice** > **Emergency locations**, and then click the **Add new address** button.</span></span>
    
    > [!Important]
    > <span data-ttu-id="0abe6-115">Skype for Business 管理センターの左のナビゲーションに [**音声**] オプションが表示されるようにするには、最初に **Enterprise E5 ライセンス**、**電話システム**アドオン ライセンス、または**電話会議**アドオン ライセンスを少なくとも 1 件購入する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0abe6-115">For you to see the **Voice** option in the left navigation in the Skype for Business admin center, you must first buy at least one **Enterprise E5 license**, one **Phone System** add-on license, or one **Audio Conferencing** add-on license.</span></span>
    
4. <span data-ttu-id="0abe6-116">アクション ウィンドウで、[**新しい住所**] の下のボックスに必要な情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="0abe6-116">In the Action pane, under **New Address**, enter the required information in the boxes.</span></span>
    
5. <span data-ttu-id="0abe6-117">住所の情報をすべて入力したら、[**検証**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0abe6-117">After you enter all of the information for the address, click **Validate**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="0abe6-p103">住所や番地を確認できるよう、正当な住所が正しい形式で入力されている必要があります。部分的に正しい緊急対応用の住所 (たとえば、市名の綴りが間違っていたなど) でも住所確認が取れる場合があります。綴りに間違いがあっても住所確認が取れた場合は、綴りの間違った市名と住所情報の他の部分を組み合わせることで、通話を適切な緊急出動センターにルーティングするのに十分な情報があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="0abe6-p103">Validating a street or civic address involves making sure that it is legitimate and correctly formatted. It is possible that a partially correct emergency address, such as if you mistyped the name of the city, may still pass validation. Even though it's misspelled and passed validation, the combination of the misspelled name of city along with the other correct parts of the address are enough information to route the call to the appropriate emergency dispatch center.</span></span> 
    
    > <span data-ttu-id="0abe6-121">注: ベルギー、フランス、ドイツ、アイルランド、オランダ、およびスペインでは、Office 365 で電話番号を有効にするには、電話番号を取得するために使用される緊急対応の場所の住所の設定を確認する必要があることを理解しておくことが重要です。電話番号の市外局番。</span><span class="sxs-lookup"><span data-stu-id="0abe6-121">NOTE: In Belgium, France, Germany, Ireland, Netherlands, and Spain it is important to understand that in order to successfully activate a phone number in Office 365 the address setup in the Emergency Location, which will be used to acquire the number, must match the phone number’s area code.</span></span>
  
    <span data-ttu-id="0abe6-122">住所の確認ができないとき、米国の住所を確認しようとする場合は、[**確認要求を送信** ] をクリックし、米国外の場合は、[**住所の確認についてのヘルプを表示するためのサービス  リクエストを開く** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0abe6-122">If the address can't be validated, you can send a manual validation request by clicking **Send a validation request** if you are trying to validate a U.S. address, or click **Open a service request to get help with address validation** if you are outside the United States.</span></span>
    
6. <span data-ttu-id="0abe6-123">住所が検証されたら、[ **保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0abe6-123">After the address is validated, click **Save**.</span></span>
    
## <a name="change-an-emergency-address"></a><span data-ttu-id="0abe6-124">緊急対応の住所を変更する</span><span class="sxs-lookup"><span data-stu-id="0abe6-124">Change an emergency address</span></span>

1. <span data-ttu-id="0abe6-125">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="0abe6-125">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="0abe6-126">**Microsoft Teams 管理センター** > の**従来のポータル**に移動します。</span><span class="sxs-lookup"><span data-stu-id="0abe6-126">Go to the **Microsoft Teams admin center** > **Legacy portal**.</span></span>
    
3. <span data-ttu-id="0abe6-127">左側のナビゲーションで、[**音声** > の緊急対応の**場所**] に移動し、変更する住所を選択して、操作ウィンドウで [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0abe6-127">In the left navigation, go to **Voice** > **Emergency locations**, select the address you want to change, and in the Action pane click **Edit**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="0abe6-128">Skype for Business 管理センターの左のナビゲーションに [**音声**] オプションが表示されるようにするには、最初に **Enterprise E5 ライセンス**、**電話システム**アドオン ライセンス、または**電話会議**アドオン ライセンスを少なくとも 1 件購入する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0abe6-128">For you to see the **Voice** option in the left navigation in the Skype for Business admin center, you must first buy at least one **Enterprise E5 license**, one **Phone System** add-on license, or one **Audio Conferencing** add-on license.</span></span>

4. <span data-ttu-id="0abe6-129">必要な変更を行い、[**検証**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0abe6-129">Make your changes, and then click **Validate**.</span></span>

5. <span data-ttu-id="0abe6-130">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0abe6-130">Click **Save**.</span></span>

## <a name="remove-an-emergency-address"></a><span data-ttu-id="0abe6-131">緊急対応の住所を削除する</span><span class="sxs-lookup"><span data-stu-id="0abe6-131">Remove an emergency address</span></span>

1. <span data-ttu-id="0abe6-132">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="0abe6-132">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="0abe6-133">**Microsoft Teams 管理センター** > の**従来のポータル**に移動します。</span><span class="sxs-lookup"><span data-stu-id="0abe6-133">Go to the **Microsoft Teams admin center** > **Legacy portal**.</span></span>
    
3. <span data-ttu-id="0abe6-134">左側のナビゲーションで、[**音声** > の緊急対応の**場所**] に移動し、削除する住所を選択して、操作ウィンドウで [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0abe6-134">In the left navigation, go to **Voice** > **Emergency locations**, select the address you want to delete, and in the Action pane click **Delete**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="0abe6-135">Skype for Business 管理センターの左のナビゲーションに [**音声**] オプションが表示されるようにするには、最初に **Enterprise E5 ライセンス**、**電話システム**アドオン ライセンス、または**電話会議**アドオン ライセンスを少なくとも 1 件購入する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0abe6-135">For you to see the **Voice** option in the left navigation in the Skype for Business admin center, you must first buy at least one **Enterprise E5 license**, one **Phone System** add-on license, or one **Audio Conferencing** add-on license.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="0abe6-136">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="0abe6-136">Troubleshooting</span></span>

<span data-ttu-id="0abe6-137">**"失敗" 状態の数値。**</span><span class="sxs-lookup"><span data-stu-id="0abe6-137">**Number in “Failed” state.**</span></span>

<span data-ttu-id="0abe6-138">Office 365 ポータルから番号を取得した後、状態が **"プロビジョニング中"** から **"失敗"** に変わります。</span><span class="sxs-lookup"><span data-stu-id="0abe6-138">After acquiring a number from the Office 365 portal, the status changed from **“Provisioning”** to **“Failed”**.</span></span>

<span data-ttu-id="0abe6-139">この問題は、電話の市外局番と一致しない場所を指す緊急対応の住所を使って、ポータルから番号が追加された場合によく発生します。</span><span class="sxs-lookup"><span data-stu-id="0abe6-139">This issue often occurs when a number is added from the portal, using an emergency address pointing to a location which is not matching the phone’s area code.</span></span>

<span data-ttu-id="0abe6-140">正しくライセンス認証されていない電話番号に関する詳細情報を入手するには、次の Powershell を実行します。</span><span class="sxs-lookup"><span data-stu-id="0abe6-140">To obtain more information about the number(s) which wasn't activated properly, run the following Powershell :</span></span>
 
> [!構文]<span data-ttu-id="0abe6-141"> Get-CsOnlineTelephoneNumber |ここで、オブジェクト {$ _ を指定します。ActivationState-cnotcontains "有効" と表示されます。 |fl</span><span class="sxs-lookup"><span data-stu-id="0abe6-141"> Get-CsOnlineTelephoneNumber | Where-Object {$_.ActivationState -cnotcontains “Activated”} | fl *</span></span>

<span data-ttu-id="0abe6-142">その結果、region、id、ActivationState などの他の情報にも、CityCode が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="0abe6-142">The result, aside other information like region, id and ActivationState, should also contain the CityCode.</span></span>

<span data-ttu-id="0abe6-143">**たとえば**、マドリッド番号の場合、返される CityCode は "EMEA-ES-M_MA" になります。</span><span class="sxs-lookup"><span data-stu-id="0abe6-143">**Example**, for a Madrid number, the CityCode returned will be "EMEA-ES-ALL-M_MA".</span></span>

<span data-ttu-id="0abe6-144">実際に間違った緊急対応の住所が使用されている場合は、番号の市外局番に対応する新しい緊急対応の住所を作成していることを確認してから、番号を割り当ててください。</span><span class="sxs-lookup"><span data-stu-id="0abe6-144">If indeed a wrong emergency address has been used, make sure you have created a new emergency address corresponding to the number’s area code and assign it to the number.</span></span>

1. <span data-ttu-id="0abe6-145">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="0abe6-145">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="0abe6-146">**Microsoft Teams 管理センター** > の**従来のポータル**に移動します。</span><span class="sxs-lookup"><span data-stu-id="0abe6-146">Go to the **Microsoft Teams admin center** > **Legacy portal**.</span></span>
    
3. <span data-ttu-id="0abe6-147">左側のナビゲーションで [**音声** > **電話番号**] に移動し、[**失敗]** 状態の番号をダブルクリックして、右側の [サイト] メニューから**新しい緊急対応の住所**を選択します。</span><span class="sxs-lookup"><span data-stu-id="0abe6-147">In the left navigation, go to **Voice** > **Phone Numbers**, and then double-click on the number in **“Failed”** State and from the right hand site menu, select the **new Emergency Address**.</span></span>


<span data-ttu-id="0abe6-148">緊急対応の住所を変更した後は、番号の状態は **「割り当ての保留」** に変わり、正常にライセンス認証されるまで最長で24時間かかる場合がありますので、ご了承ください。</span><span class="sxs-lookup"><span data-stu-id="0abe6-148">Please note that after changing the emergency address, the number’s status will change to **“Assignment Pending”** and it can take up to 24 hours for successfully activating.</span></span>

## <a name="related-topics"></a><span data-ttu-id="0abe6-149">関連トピック</span><span class="sxs-lookup"><span data-stu-id="0abe6-149">Related topics</span></span>
[<span data-ttu-id="0abe6-150">緊急対応の場所、アドレス、通話ルーティングの概要</span><span class="sxs-lookup"><span data-stu-id="0abe6-150">What are emergency locations, addresses, and call routing?</span></span>](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing)

<span data-ttu-id="0abe6-151">[[[Skype for Business 新しい電話番号の申請](/microsoftteams/manage-phone-numbers-for-your-organization)] に移動することによって、電話番号を取得するために利用できるすべてのフォームを一覧表示してダウンロードすることができます。](/microsoftteams/manage-phone-numbers-for-your-organization)</span><span class="sxs-lookup"><span data-stu-id="0abe6-151">[Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization)</span></span>

[<span data-ttu-id="0abe6-152">緊急通話の利用条件</span><span class="sxs-lookup"><span data-stu-id="0abe6-152">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="0abe6-153">[Skype for Business Online: 緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="0abe6-153">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 
