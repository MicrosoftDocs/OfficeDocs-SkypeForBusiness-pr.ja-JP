---
title: 緊急対応Microsoft 365 Business Voiceを設定する
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: 緊急対応の場所を設定する方法についてMicrosoft 365 Business Voice。
appliesto:
- Microsoft Teams
ms.openlocfilehash: e8f740034a67e1f2199b5a18aa34d67e16df43e2
ms.sourcegitcommit: 2419348e964cfe97b72d533f267c5d7055d5366f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/11/2021
ms.locfileid: "52907763"
---
# <a name="step-1-set-up-a-business-voice-emergency-location"></a><span data-ttu-id="758b9-103">手順 1: Business Voice の緊急対応の場所を設定する</span><span class="sxs-lookup"><span data-stu-id="758b9-103">Step 1: Set up a Business Voice emergency location</span></span>

<span data-ttu-id="758b9-104">緊急対応の場所は、組織内の誰かが火災、警察、または緊急対応のサービスを呼び出す場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="758b9-104">An emergency location is used when someone in your organization calls emergency services such as fire, police, or ambulance.</span></span> <span data-ttu-id="758b9-105">ユーザーが緊急サービスに電話すると、組織の緊急対応の住所として構成された住所がサービスに送信されます。</span><span class="sxs-lookup"><span data-stu-id="758b9-105">When a person calls an emergency service, the address that's configured as your organization's emergency address is sent to the service.</span></span> <span data-ttu-id="758b9-106">この手順では、組織の主要な緊急対応の場所を設定します。</span><span class="sxs-lookup"><span data-stu-id="758b9-106">This step sets up the primary emergency location for your organization.</span></span> <span data-ttu-id="758b9-107">この場所は、後の手順で会社のメイン電話番号に関連付けられる予定です。</span><span class="sxs-lookup"><span data-stu-id="758b9-107">This location will be associated with your company's main phone number in a later step.</span></span>

<span data-ttu-id="758b9-108">ホーム オフィスや他の都市のオフィスなど、複数の場所にユーザーがある場合は、追加の緊急対応の場所を構成できます。</span><span class="sxs-lookup"><span data-stu-id="758b9-108">If you have users in multiple locations, such as home offices or offices in other cities, you can configure additional emergency locations.</span></span> <span data-ttu-id="758b9-109">また、場所内の特定の場所を構成できます。</span><span class="sxs-lookup"><span data-stu-id="758b9-109">You can even configure specific places within a location.</span></span> <span data-ttu-id="758b9-110">場所には、異なる建物、フロア、オフィス、またはユーザーが場所にある可能性があるその他の場所を指定できます。</span><span class="sxs-lookup"><span data-stu-id="758b9-110">Places can be different buildings, floors, offices, or other places where users may be at a location.</span></span> <span data-ttu-id="758b9-111">Business Voice の初期セットアップを完了すると、追加の場所と場所を追加できます。</span><span class="sxs-lookup"><span data-stu-id="758b9-111">Additional locations and places can be added after you complete your initial setup of Business Voice.</span></span>

<span data-ttu-id="758b9-112">次のビデオでは、管理センターでこれらの手順を完了Teams示します。</span><span class="sxs-lookup"><span data-stu-id="758b9-112">The following video shows you how to complete these steps in the Teams admin center.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWEZGE]

## <a name="add-an-emergency-location"></a><span data-ttu-id="758b9-113">緊急対応の場所を追加する</span><span class="sxs-lookup"><span data-stu-id="758b9-113">Add an emergency location</span></span>

1. <span data-ttu-id="758b9-114">Microsoft Teams 管理センターを開き、グローバル管理者であるユーザー (通常は、管理者のサインアップに使用したアカウント) でログインMicrosoft 365。</span><span class="sxs-lookup"><span data-stu-id="758b9-114">Open the Microsoft Teams admin center and log in with a user that is a Global admin (this is usually the account you used to sign up for Microsoft 365).</span></span>
1. <span data-ttu-id="758b9-115">左側のナビゲーション ウィンドウで、[場所] [緊急対応の住所 <a href="https://admin.teams.microsoft.com/locations" target="_blank">**]**  >  **に移動します**</a>。</span><span class="sxs-lookup"><span data-stu-id="758b9-115">In the left navigation pane, go to <a href="https://admin.teams.microsoft.com/locations" target="_blank">**Locations** > **Emergency addresses**</a>.</span></span>
1. <span data-ttu-id="758b9-116">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="758b9-116">Click **Add**.</span></span>
1. <span data-ttu-id="758b9-117">場所の名前と説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="758b9-117">Enter a name and description for the location.</span></span>
1. <span data-ttu-id="758b9-118">国または地域を選択し、アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="758b9-118">Select the country or region, and then enter the address.</span></span>

   > [!NOTE]
   > <span data-ttu-id="758b9-119">ベルギー、フランス、ドイツ、アイルランド、オランダ、スペインでは、Microsoft 365 または Office 365 で電話番号を正常にアクティブ化するには、緊急対応の場所に設定された住所 (番号の取得に使用) が電話番号の市番と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="758b9-119">In Belgium, France, Germany, Ireland, Netherlands, and Spain, it's important to understand that to successfully activate a phone number in Microsoft 365 or Office 365, the address set up in the emergency location, which is used to acquire the number, must match the phone number's area code.</span></span>

1. <span data-ttu-id="758b9-120">住所が見つからない場合に、アドレスを手動で編集する場合は、[アドレスを手動で編集する **] をオンにしてください**。</span><span class="sxs-lookup"><span data-stu-id="758b9-120">If the address isn't found and you want to manually edit the address, turn on **Edit the address manually**.</span></span>
1. <span data-ttu-id="758b9-121">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="758b9-121">Click **Save**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="758b9-122">次の手順: 電話番号を設定する</span><span class="sxs-lookup"><span data-stu-id="758b9-122">Next step: Set up phone numbers</span></span>](set-up-phone-numbers.md)
