---
title: Skype for Business 会議からダイヤルアウトして、他のユーザーが参加できるようにする
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 3c2db9a5-3a19-4e19-b59e-8e5587f25d31
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: Skype for Business を使用して会議の開催者が他のユーザーを呼び出せるようにするための必要事項とその方法を説明します。
ms.openlocfilehash: c0bf11f3bd6a865bcd5dea107eedb8f2d5f5951f
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164286"
---
# <a name="dialing-out-from-a-skype-for-business-meeting-so-other-people-can-join-it"></a><span data-ttu-id="bca81-103">Skype for Business 会議からダイヤルアウトして、他のユーザーが参加できるようにする</span><span class="sxs-lookup"><span data-stu-id="bca81-103">Dialing out from a Skype for Business meeting so other people can join it</span></span>

> [!NOTE]
> <span data-ttu-id="bca81-104">Teams の会議からのダイヤル アウトについての情報をお求めの場合は、「[他のユーザーが参加できるように Teams 会議からダイアル アウトする](/MicrosoftTeams/dialing-out-from-a-teams-meeting-so-other-people-can-join-it)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bca81-104">If you're looking for information about dialing out from a Teams meeting, see [Dialing out from a Teams meeting so other people can join it](/MicrosoftTeams/dialing-out-from-a-teams-meeting-so-other-people-can-join-it).</span></span>

<span data-ttu-id="bca81-105">会議の開催者である場合は、Skype for Business アプリを使ってダイヤルアウトすることで、他のユーザーが電話を使って同じ会議に参加できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="bca81-105">As the meeting organizer, you can dial out using the Skype for Business app to let other people join the same meeting using their phone.</span></span> <span data-ttu-id="bca81-106">必須ではありませんが、誰かにダイヤルアウトするときには、国/地域番号が含まれる完全な番号をダイヤルすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="bca81-106">Although it's not required, when you are dialing out to someone, it's recommended that you dial the full number, including the country/region code.</span></span> <span data-ttu-id="bca81-107">ダイヤルアウトを実行するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="bca81-107">To get dial-out to work:</span></span>
  
- <span data-ttu-id="bca81-108">ダイヤルアウトできるのは、Skype for Business アプリを使って会議に参加している場合のみです。</span><span class="sxs-lookup"><span data-stu-id="bca81-108">You can dial-out only if you join a meeting using a Skype for Business app.</span></span>
    
- <span data-ttu-id="bca81-109">会議の開催者が電話会議用に有効になっています。</span><span class="sxs-lookup"><span data-stu-id="bca81-109">You as the meeting organizer have been enabled for audio conferencing.</span></span>

<span data-ttu-id="bca81-110">組織の会議に他の参加者を追加するには、他の参加者をダイヤルアウトで追加できるようにするため、少なくとも (自分の組織の) 同じ組織のユーザーが会議に参加している必要があります。</span><span class="sxs-lookup"><span data-stu-id="bca81-110">In order to add other participants via dial-out to the meetings of your organization, at least one authenticated user from the same organization as the organizer (your organization) is required to be present in the meeting in order to allow adding other participants via dial-out.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

 <span data-ttu-id="bca81-111">**手順 1:**[会議出席依頼] で、[**他の人を招待**] オプションを使用して、電話番号にダイヤルアウトします。</span><span class="sxs-lookup"><span data-stu-id="bca81-111">**Step 1:** In the invite meeting, use the **Invite More People** option to dial out to a phone number.</span></span>
  
![Dial-out with Skype for Business.](../images/9896abec-7a6f-4148-ad09-76a1cf4b56e1.png)
  
 <span data-ttu-id="bca81-113">**手順 2:** ボックスに、国/地域コードも含めて、すべての電話番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="bca81-113">**Step 2:** Enter the full phone number, including the country/region code in the box.</span></span>
  
![Dial-out phone number in Skype for Business](../images/084b4fb5-21eb-4f10-9a1a-c92b919084b9.png)
  
## <a name="supported-countries-and-regions"></a><span data-ttu-id="bca81-115">サポートされている国と地域</span><span class="sxs-lookup"><span data-stu-id="bca81-115">Supported countries and regions</span></span>

<span data-ttu-id="bca81-116">ダイヤルアウトは一部の国と地域でのみ使用可能です。</span><span class="sxs-lookup"><span data-stu-id="bca81-116">Dial-out is only available to some countries/regions.</span></span> <span data-ttu-id="bca81-117">詳細な一覧については、「[電話会議と通話プランの国と地域の空き時間](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)情報」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bca81-117">For complete list, see [Country and region availability for Audio Conferencing and Calling Plans](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans).</span></span>
  
## <a name="want-to-know-more-about-audio-conferencing"></a><span data-ttu-id="bca81-118">電話会議について詳しく知りたいですか?</span><span class="sxs-lookup"><span data-stu-id="bca81-118">Want to know more about audio conferencing?</span></span>

[<span data-ttu-id="bca81-119">Microsoft 365 または Office 365 で電話会議を試用または購入する</span><span class="sxs-lookup"><span data-stu-id="bca81-119">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
    
- [<span data-ttu-id="bca81-120">Skype for Business アドオンのライセンス</span><span class="sxs-lookup"><span data-stu-id="bca81-120">Skype for Business add-on licensing</span></span>](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
    
## <a name="related-topics"></a><span data-ttu-id="bca81-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="bca81-121">Related topics</span></span>

[<span data-ttu-id="bca81-122">Skype for Business をインストールする</span><span class="sxs-lookup"><span data-stu-id="bca81-122">Install Skype for Business</span></span>](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb)
