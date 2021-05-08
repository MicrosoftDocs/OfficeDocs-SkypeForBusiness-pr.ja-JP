---
title: 他のユーザーが参加Skype for Business会議からダイヤルアウトする
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
ms.openlocfilehash: 814d753570fd2337a8e443f93c3d58748711b964
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238502"
---
# <a name="dialing-out-from-a-skype-for-business-meeting-so-other-people-can-join-it"></a><span data-ttu-id="d5ad7-103">他のユーザーが参加Skype for Business会議からダイヤルアウトする</span><span class="sxs-lookup"><span data-stu-id="d5ad7-103">Dialing out from a Skype for Business meeting so other people can join it</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!NOTE]
> <span data-ttu-id="d5ad7-104">Teams の会議からのダイヤル アウトについての情報をお求めの場合は、「[他のユーザーが参加できるように Teams 会議からダイアル アウトする](/MicrosoftTeams/dialing-out-from-a-teams-meeting-so-other-people-can-join-it)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d5ad7-104">If you're looking for information about dialing out from a Teams meeting, see [Dialing out from a Teams meeting so other people can join it](/MicrosoftTeams/dialing-out-from-a-teams-meeting-so-other-people-can-join-it).</span></span>

<span data-ttu-id="d5ad7-105">会議の開催者は、Skype for Business アプリを使用してダイヤルアウトして、他のユーザーが自分の電話を使って同じ会議に参加することができます。</span><span class="sxs-lookup"><span data-stu-id="d5ad7-105">As the meeting organizer, you can dial out using the Skype for Business app to let other people join the same meeting using their phone.</span></span> <span data-ttu-id="d5ad7-106">必須ではありませんが、誰かにダイヤルアウトするときには、国/地域番号が含まれる完全な番号をダイヤルすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d5ad7-106">Although it's not required, when you are dialing out to someone, it's recommended that you dial the full number, including the country/region code.</span></span> <span data-ttu-id="d5ad7-107">ダイヤルアウトを実行するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="d5ad7-107">To get dial-out to work:</span></span>
  
- <span data-ttu-id="d5ad7-108">ダイヤルアウトできるのは、新しいアプリを使用して会議に参加Skype for Businessです。</span><span class="sxs-lookup"><span data-stu-id="d5ad7-108">You can dial-out only if you join a meeting using a Skype for Business app.</span></span>
    
- <span data-ttu-id="d5ad7-109">会議の開催者として電話会議を有効にしました。</span><span class="sxs-lookup"><span data-stu-id="d5ad7-109">You as the meeting organizer have been enabled for audio conferencing.</span></span>

<span data-ttu-id="d5ad7-110">ダイヤルアウトを介して他の参加者を組織の会議に追加するには、ダイヤルアウトを介して他の参加者を追加するために、開催者 (組織) と同じ組織の認証されたユーザーが少なくとも 1 人会議に参加している必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5ad7-110">In order to add other participants via dial-out to the meetings of your organization, at least one authenticated user from the same organization as the organizer (your organization) is required to be present in the meeting in order to allow adding other participants via dial-out.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

 <span data-ttu-id="d5ad7-111">**手順 1:** 招待会議で、[他のユーザーを招待 **]** オプションを使用して、電話番号にダイヤルアウトします。</span><span class="sxs-lookup"><span data-stu-id="d5ad7-111">**Step 1:** In the invite meeting, use the **Invite More People** option to dial out to a phone number.</span></span>
  
![Dial-out with Skype for Business.](../images/9896abec-7a6f-4148-ad09-76a1cf4b56e1.png)
  
 <span data-ttu-id="d5ad7-113">**手順 2:** ボックスに国/地域コードを含む完全な電話番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="d5ad7-113">**Step 2:** Enter the full phone number, including the country/region code in the box.</span></span>
  
![Dial-out phone number in Skype for Business](../images/084b4fb5-21eb-4f10-9a1a-c92b919084b9.png)
  
## <a name="supported-countries-and-regions"></a><span data-ttu-id="d5ad7-115">サポートされている国と地域</span><span class="sxs-lookup"><span data-stu-id="d5ad7-115">Supported countries and regions</span></span>

<span data-ttu-id="d5ad7-116">ダイヤルアウトは一部の国と地域でのみ使用可能です。</span><span class="sxs-lookup"><span data-stu-id="d5ad7-116">Dial-out is only available to some countries/regions.</span></span> <span data-ttu-id="d5ad7-117">完全な一覧については、「電話会議と通話プランの国と地域の可用性 [」を参照してください](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)。</span><span class="sxs-lookup"><span data-stu-id="d5ad7-117">For complete list, see [Country and region availability for Audio Conferencing and Calling Plans](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans).</span></span>
  
## <a name="want-to-know-more-about-audio-conferencing"></a><span data-ttu-id="d5ad7-118">電話会議の詳細については、次のページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d5ad7-118">Want to know more about audio conferencing?</span></span>

[<span data-ttu-id="d5ad7-119">電話会議を試用または購入するには、Microsoft 365またはOffice 365</span><span class="sxs-lookup"><span data-stu-id="d5ad7-119">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
    
- [<span data-ttu-id="d5ad7-120">Skype for Business アドオンのライセンス</span><span class="sxs-lookup"><span data-stu-id="d5ad7-120">Skype for Business add-on licensing</span></span>](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
    
## <a name="related-topics"></a><span data-ttu-id="d5ad7-121">関連トピック</span><span class="sxs-lookup"><span data-stu-id="d5ad7-121">Related topics</span></span>

[<span data-ttu-id="d5ad7-122">Skype for Business をインストールする</span><span class="sxs-lookup"><span data-stu-id="d5ad7-122">Install Skype for Business</span></span>](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb)
