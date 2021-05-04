---
title: 緊急の場所Microsoft 365 Business Voice設定する
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
description: ユーザーの緊急の場所を設定する方法Microsoft 365 Business Voice。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 531d1b747a86c84e99c2b6f06a83ae405527f3ba
ms.sourcegitcommit: 49cdcf344c63c805bcb6365804c6f5d1393e926a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2021
ms.locfileid: "52130485"
---
# <a name="step-1-set-up-a-business-voice-emergency-location"></a><span data-ttu-id="5dde1-103">手順 1: Business Voice の緊急場所を設定する</span><span class="sxs-lookup"><span data-stu-id="5dde1-103">Step 1: Set up a Business Voice emergency location</span></span>

<span data-ttu-id="5dde1-104">緊急時の場所は、組織内の誰かが火災、警察、救急車などの緊急サービスを呼び出す場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="5dde1-104">An emergency location is used when someone in your organization calls emergency services such as fire, police, or ambulance.</span></span> <span data-ttu-id="5dde1-105">ユーザーが緊急サービスを呼び出す場合、組織の緊急住所として構成されているアドレスがサービスに送信されます。</span><span class="sxs-lookup"><span data-stu-id="5dde1-105">When a person calls an emergency service, the address that's configured as your organization's emergency address is sent to the service.</span></span> <span data-ttu-id="5dde1-106">この手順では、組織の主要な緊急対応場所を設定します。</span><span class="sxs-lookup"><span data-stu-id="5dde1-106">This step sets up the primary emergency location for your organization.</span></span> <span data-ttu-id="5dde1-107">この場所は、後の手順で会社の主要電話番号に関連付けられる予定です。</span><span class="sxs-lookup"><span data-stu-id="5dde1-107">This location will be associated with your company's main phone number in a later step.</span></span>

<span data-ttu-id="5dde1-108">他の都市のホーム オフィスやオフィスなど、複数の場所にユーザーを持っている場合は、追加の緊急の場所を構成できます。</span><span class="sxs-lookup"><span data-stu-id="5dde1-108">If you have users in multiple locations, such as home offices or offices in other cities, you can configure additional emergency locations.</span></span> <span data-ttu-id="5dde1-109">また、場所内の特定の場所を構成できます。</span><span class="sxs-lookup"><span data-stu-id="5dde1-109">You can even configure specific places within a location.</span></span> <span data-ttu-id="5dde1-110">場所は、異なる建物、フロア、オフィス、またはユーザーが場所にある可能性があるその他の場所を指定できます。</span><span class="sxs-lookup"><span data-stu-id="5dde1-110">Places can be different buildings, floors, offices, or other places where users may be at a location.</span></span> <span data-ttu-id="5dde1-111">Business Voice の初期セットアップを完了した後、追加の場所と場所を追加できます。</span><span class="sxs-lookup"><span data-stu-id="5dde1-111">Additional locations and places can be added after you complete your initial setup of Business Voice.</span></span>

## <a name="add-an-emergency-location"></a><span data-ttu-id="5dde1-112">緊急の場所を追加する</span><span class="sxs-lookup"><span data-stu-id="5dde1-112">Add an emergency location</span></span>

1. <span data-ttu-id="5dde1-113">管理者センター [Microsoft Teams開](https://admin.teams.microsoft.com)き、グローバル管理者であるユーザーでログインします (通常は、管理者のサインアップに使用Microsoft 365)。</span><span class="sxs-lookup"><span data-stu-id="5dde1-113">Open the [Microsoft Teams admin center](https://admin.teams.microsoft.com) and log in with a user that is a Global admin (this is usually the account you used to sign up for Microsoft 365).</span></span>
1. <span data-ttu-id="5dde1-114">管理センターの左側のナビゲーションで、[Microsoft Teams **緊急対応アドレス]**  >  **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="5dde1-114">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
1. <span data-ttu-id="5dde1-115">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5dde1-115">Click **Add**.</span></span>
1. <span data-ttu-id="5dde1-116">場所の名前と説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="5dde1-116">Enter a name and description for the location.</span></span>
1. <span data-ttu-id="5dde1-117">国または地域を選択し、住所を入力します。</span><span class="sxs-lookup"><span data-stu-id="5dde1-117">Select the country or region, and then enter the address.</span></span>

   > [!NOTE]
   > <span data-ttu-id="5dde1-118">ベルギー、フランス、ドイツ、アイルランド、オランダ、スペインでは、Microsoft 365 または Office 365 で電話番号を正常にアクティブ化するには、電話番号の取得に使用される緊急の場所に設定された住所が電話番号の市中コードと一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5dde1-118">In Belgium, France, Germany, Ireland, Netherlands, and Spain, it's important to understand that to successfully activate a phone number in Microsoft 365 or Office 365, the address set up in the emergency location, which is used to acquire the number, must match the phone number's area code.</span></span>

1. <span data-ttu-id="5dde1-119">アドレスが見つからない場合に、アドレスを手動で編集する場合は、[手動でアドレスを編集する **] をオンにしてください**。</span><span class="sxs-lookup"><span data-stu-id="5dde1-119">If the address isn't found and you want to manually edit the address, turn on **Edit the address manually**.</span></span>
1. <span data-ttu-id="5dde1-120">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5dde1-120">Click **Save**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="5dde1-121">次の手順: 電話番号を設定する</span><span class="sxs-lookup"><span data-stu-id="5dde1-121">Next step: Set up phone numbers</span></span>](set-up-phone-numbers.md)
