---
title: 招待状に含まれている電話番号を設定する
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 32954439-d365-4125-872f-b37466ecb035
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
- seo-marvel-mar2020
description: Microsoft Teams 会議に参加するための既定の電話番号を作成するには、次の手順に従います。
ms.openlocfilehash: bd8ca4729a991582588f09e8c230e57983cd1a87
ms.sourcegitcommit: 4099da7b1db7663e63ef5bece16e3090c33ea207
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2020
ms.locfileid: "45021765"
---
# <a name="set-the-phone-numbers-included-on-invites-in-microsoft-teams"></a><span data-ttu-id="c6eda-103">Microsfot Teams で招待状に含まれている電話番号を設定する</span><span class="sxs-lookup"><span data-stu-id="c6eda-103">Set the phone numbers included on invites in Microsoft Teams</span></span>

<span data-ttu-id="c6eda-104">Microsoft 365 および Office 365 の電話会議では、組織内のユーザーが Microsoft Teams 会議を作成できるようになり、電話を使用してこれらの会議にダイヤルインすることができます。</span><span class="sxs-lookup"><span data-stu-id="c6eda-104">Audio Conferencing in Microsoft 365 and Office 365 enables users in your organization to create Microsoft Teams meetings, and then allow users to dial in to those meetings using a phone.</span></span>
  
<span data-ttu-id="c6eda-p101">会議ブリッジは、組織用のダイヤルイン電話番号のセットを提供します。これらの番号はすべて会議開催者が作成した会議に参加するために使用できますが、会議出席依頼にどの番号を含めるか選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="c6eda-p101">A conferencing bridge gives you a set of dial-in phone numbers for your organization. All of them can be used to join the meetings that a meeting organizer has created, but you can select which ones will be included on their meeting invites.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c6eda-107">会議主催者の会議出席依頼には、1 つの有料電話番号と 1 つの無料電話番号を含めることができますが、会議出席依頼の下部に、会議に参加するために使用できるダイヤルイン電話番号のすべての一覧を表示するリンクも記載されています。</span><span class="sxs-lookup"><span data-stu-id="c6eda-107">There can be a maximum of one toll and one toll-free phone number on the meeting invite for a meeting organizer, but there is also a link located at the bottom of each meeting invite that opens the full list of all dial-in phone numbers that can be used to join a meeting.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="initial-assignment-of-phone-numbers-that-are-included-in-the-meeting-invites-for-new-users"></a><span data-ttu-id="c6eda-108">新規ユーザー向けの会議出席依頼に記載されている電話番号の最初の割り当て</span><span class="sxs-lookup"><span data-stu-id="c6eda-108">Initial assignment of phone numbers that are included in the meeting invites for new users</span></span>

<span data-ttu-id="c6eda-109">電話会議用に有効になっているユーザーの会議の出席依頼に含まれる電話番号は、既定の電話会議の有料電話番号と、既定の電話会議無料電話番号のユーザー設定によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="c6eda-109">The phone numbers that get included in the meeting invites of users enabled for Audio Conferencing are defined by the default conferencing toll phone number and the default conferencing toll-free phone number user's settings.</span></span> <span data-ttu-id="c6eda-110">各設定では、特定のユーザーの会議出席依頼に含まれる有料電話と無料電話番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="c6eda-110">Each setting specifies which toll and toll-free number will be included in the meeting invite of a given user.</span></span> <span data-ttu-id="c6eda-111">上で説明したように、各会議出席依頼には、1つの有料電話番号、オプションの無料電話番号、および特定の会議に参加するために使用できるすべてのダイヤルイン電話番号の一覧を表示するリンクが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c6eda-111">As noted above, each meeting invite contains one toll number, one optional toll-free number and a link that opens the full list of all dial-in phone numbers that can be used to join a given meeting.</span></span>

<span data-ttu-id="c6eda-112">新規ユーザーの場合、電話会議サービスが有効になっている場合、ユーザーの Microsoft 365 管理センターで設定された使用場所に基づいて、既定の会議の有料電話番号が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="c6eda-112">For a new user, the default conferencing toll numbers is assigned based on the Usage Location that is set in the Microsoft 365 administration center of the user when the user is enabled for the Audio Conferencing service.</span></span> <span data-ttu-id="c6eda-113">電話会議でユーザーの国と一致する有料番号がある場合、その番号はユーザーの既定の有料電話番号として自動的に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="c6eda-113">If there is a toll number in the conference bridge that matches the country of the user, that number will be automatically assigned as the default toll number of the user.</span></span> <span data-ttu-id="c6eda-114">存在しない場合、電話会議ブリッジの既定の有料電話番号として定義された番号は、ユーザーの既定の有料電話番号として割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="c6eda-114">If there isn't one, the number that is defined as the default toll number of the conference bridge will be assigned as the default toll number of the user.</span></span>  

<span data-ttu-id="c6eda-115">電話会議サービスのユーザーを有効にすると、ユーザーの既定の有料電話番号と無料電話番号を初期値からいつでも変更できます。</span><span class="sxs-lookup"><span data-stu-id="c6eda-115">Once the user is enabled for the Audio Conferencing service, the default toll and toll-free phone numbers of the user can be changed by the tenant administrator from their initial values at any moment.</span></span>

## <a name="set-or-change-the-default-audio-conferencing-phone-number-for-a-meeting-organizer-or-user"></a><span data-ttu-id="c6eda-116">会議の開催者またはユーザーの既定の電話会議の電話番号を設定または変更する</span><span class="sxs-lookup"><span data-stu-id="c6eda-116">Set or change the default audio conferencing phone number for a meeting organizer or user</span></span>

<span data-ttu-id="c6eda-117">![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターを使用する**</span><span class="sxs-lookup"><span data-stu-id="c6eda-117">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

<span data-ttu-id="c6eda-118">これらの変更を行うには、管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6eda-118">You must be an admin to make these changes.</span></span>

1. <span data-ttu-id="c6eda-119">Microsoft Teams 管理センターにログインします。</span><span class="sxs-lookup"><span data-stu-id="c6eda-119">Log in to the Microsoft Teams admin center.</span></span>

2. <span data-ttu-id="c6eda-120">左側のナビゲーションで [**ユーザー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c6eda-120">In the left navigation, click **Users**.</span></span>

    ![Microsoft Teams 管理センターでのユーザーの選択を示す](media/Admin-users.png)

3. <span data-ttu-id="c6eda-122">使用可能なユーザーのリストからユーザー名をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c6eda-122">Click the user name from the list of available users.</span></span>

4. <span data-ttu-id="c6eda-123">[**電話会議**] の横の [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c6eda-123">Next to **Audio Conferencing**, click **Edit**.</span></span> 
    
    ![電話会議の横にある [編集] をクリックする](media/teams-set-phone-numbers-on-invites-image3.png)

5. <span data-ttu-id="c6eda-125">[**有料**電話番号] または [無料**電話番号**] フィールドを使用して、ユーザーの番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="c6eda-125">Use the **Toll number** or **Toll-free number** fields to enter the numbers for the user.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="c6eda-126">ユーザーの電話会議の設定を変更すると、定期的な Microsoft Teams の会議を更新して出席者に送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6eda-126">When you change a user's audio conferencing settings, recurring and future Microsoft Teams meetings must be updated and sent to attendees.</span></span> 

## <a name="want-to-use-windows-powershell"></a><span data-ttu-id="c6eda-127">Windows PowerShell を使用する場合</span><span class="sxs-lookup"><span data-stu-id="c6eda-127">Want to use Windows PowerShell?</span></span>

<span data-ttu-id="c6eda-128">Windows PowerShell では、ユーザーの管理と、許可または許可されていないユーザーの操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="c6eda-128">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="c6eda-129">Windows PowerShell を使用すると、複数のタスクがある場合に、1つの管理ポイントを使用して Microsoft 365 または Office 365 を管理し、日常的な作業を簡略化できます。</span><span class="sxs-lookup"><span data-stu-id="c6eda-129">With Windows PowerShell, you can manage Microsoft 365 or Office 365 by using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="c6eda-130">Windows PowerShell の使用を開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6eda-130">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="c6eda-131">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="c6eda-131">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="c6eda-132">Windows PowerShell を使用して Microsoft 365 または Office 365 を管理するのに最適な方法</span><span class="sxs-lookup"><span data-stu-id="c6eda-132">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="c6eda-133">Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c6eda-133">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span> 
  
    
## <a name="related-topics"></a><span data-ttu-id="c6eda-134">関連トピック</span><span class="sxs-lookup"><span data-stu-id="c6eda-134">Related topics</span></span>

[<span data-ttu-id="c6eda-135">Microsoft 365 または Office 365 で電話会議を試用または購入する</span><span class="sxs-lookup"><span data-stu-id="c6eda-135">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)

[<span data-ttu-id="c6eda-136">電話会議ブリッジの電話番号を変更する</span><span class="sxs-lookup"><span data-stu-id="c6eda-136">Change the phone numbers on your Audio Conferencing bridge</span></span>](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)
