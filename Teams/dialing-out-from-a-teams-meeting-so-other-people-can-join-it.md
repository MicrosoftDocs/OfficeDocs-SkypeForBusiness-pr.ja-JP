---
title: 他のユーザーが参加できるよう会議からダイヤルアウトする
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 3c2db9a5-3a19-4e19-b59e-8e5587f25d31
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-apr2020
description: 会議の開催者は、Teams アプリを使用してダイヤルアウトして、他のユーザーが自分の電話を使用して同じ会議に参加する方法を学習できます。
ms.openlocfilehash: 55cbd5ccc9e9c364bcb829d9a392f61cbdd2f7f8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119286"
---
# <a name="dialing-out-from-a-microsoft-teams-meeting-so-other-people-can-join-it"></a><span data-ttu-id="cec3e-103">他のユーザーが参加できるように Microsoft Teams 会議からダイヤル アウトする</span><span class="sxs-lookup"><span data-stu-id="cec3e-103">Dialing out from a Microsoft Teams meeting so other people can join it</span></span>

<span data-ttu-id="cec3e-104">会議の開催者は、Teams アプリを使用してダイヤルアウトし、他のユーザーが自分の電話を使用して同じ会議に参加することができます。</span><span class="sxs-lookup"><span data-stu-id="cec3e-104">As the meeting organizer, you can dial out using the Teams app to let other people join the same meeting using their phones.</span></span>

<span data-ttu-id="cec3e-105">他のユーザーにダイヤルアウトする場合は、完全な電話番号 (国/地域コードを含む - E.164 形式) を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="cec3e-105">When you dial out to someone, we recommend that you do so using their full phone numbers (including the country/region code - E.164 format).</span></span>
  
  <span data-ttu-id="cec3e-106">次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="cec3e-106">Please note that:</span></span>

- <span data-ttu-id="cec3e-107">Teams を使用して会議に参加する場合にのみダイヤルアウトできます。</span><span class="sxs-lookup"><span data-stu-id="cec3e-107">You can dial out only if you join a meeting using Teams.</span></span>
- <span data-ttu-id="cec3e-108">会議の開催者が電話会議に対して有効になっているか、または、電話会議ライセンスが割り当てられていない場合、オンライン通話プランまたは直接ルーティングを介して公衆交換電話網に通話を発信することができます。</span><span class="sxs-lookup"><span data-stu-id="cec3e-108">The meeting organizer, has been enabled for audio conferencing, OR, in the case no audio conferencing license is assigned, is allowed to make calls to the public switched telephone network via online calling plans or direct routing.</span></span>
- <span data-ttu-id="cec3e-109">会議の開催者 [に、会議からのダイヤルアウトを有効にするオンライン ダイヤルアウト ポリシーが付与される](/powershell/module/skype/grant-csdialoutpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="cec3e-109">The meeting organizer is [Granted an online dial out policy that enables dial out from conferencing enabled](/powershell/module/skype/grant-csdialoutpolicy?view=skype-ps)</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="cec3e-110">ダイヤルアウトを使用するには、次の方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="cec3e-110">Here's how to get dial out to work:</span></span>

 <span data-ttu-id="cec3e-111">**手順 1:** 会議で、[ユーザーの追加] **ボタン** オプションの [ユーザーの追加] スクリーンショットを使用して、電話番号 ![ ](media/add-people-button.png) にダイヤルアウトします。</span><span class="sxs-lookup"><span data-stu-id="cec3e-111">**Step 1:** In the meeting, use the **Add people** ![Screenshot of the Add people button](media/add-people-button.png) option to dial out to a phone number.</span></span>
 <span data-ttu-id="cec3e-112">**手順 2:** [ユーザーの招待] ボックスに国/地域コードを含む完全な電話番号 **を入力** します。</span><span class="sxs-lookup"><span data-stu-id="cec3e-112">**Step 2:** Enter the full phone number, including the country/region code in the **Invite someone or dial a number** box.</span></span>
  
![[他のユーザーを招待するか、番号をダイヤルする] ボックスのスクリーンショット](media/invite-someone-box.png)
    
## <a name="supported-countries-and-regions"></a><span data-ttu-id="cec3e-114">サポートされている国と地域</span><span class="sxs-lookup"><span data-stu-id="cec3e-114">Supported countries and regions</span></span>

<span data-ttu-id="cec3e-115">ダイヤルアウトは一部の国と地域でのみ使用可能です。</span><span class="sxs-lookup"><span data-stu-id="cec3e-115">Dial-out is only available to some countries/regions.</span></span> <span data-ttu-id="cec3e-116">詳細な一覧については、「電話 [会議と通話プランの国と地域の可用性」を参照してください](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="cec3e-116">For complete list, see [Country and region availability for Audio Conferencing and Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span></span>

## <a name="allow-users-to-dial-in"></a><span data-ttu-id="cec3e-117">ユーザーにダイヤルインを許可する</span><span class="sxs-lookup"><span data-stu-id="cec3e-117">Allow users to dial in</span></span>

<span data-ttu-id="cec3e-118">ユーザーが Teams 会議にダイヤルインする方法については、Microsoft Teams の電話会議の電話番号を [参照してください](phone-numbers-for-audio-conferencing-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="cec3e-118">If you are looking for instructions on how to let your users dial in to a Teams meeting, please see [Phone numbers for Audio Conferencing in Microsoft Teams](phone-numbers-for-audio-conferencing-in-teams.md).</span></span>

## <a name="want-to-know-more-about-audio-conferencing"></a><span data-ttu-id="cec3e-119">電話会議について詳しくは、次のリンクを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cec3e-119">Want to know more about audio conferencing?</span></span>

[<span data-ttu-id="cec3e-120">電話会議を試用または購入する</span><span class="sxs-lookup"><span data-stu-id="cec3e-120">Try or purchase Audio Conferencing</span></span>](try-or-purchase-audio-conferencing-in-office-365-for-teams.md)
    
[<span data-ttu-id="cec3e-121">Microsoft Teams アドオン ライセンス</span><span class="sxs-lookup"><span data-stu-id="cec3e-121">Microsoft Teams add-on licensing</span></span>](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)