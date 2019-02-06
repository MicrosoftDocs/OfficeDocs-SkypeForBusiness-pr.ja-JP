---
title: Microsfot Teams で招待状に含まれている電話番号を設定する
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
- Teams_ITAdmin_Help
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'マイクロソフトのチーム ミーティングに参加するのには呼び出し元の既定の電話番号を作成する手順を取得します。 '
ms.openlocfilehash: 8cbe7a88d1fcb857ce94a95b2a9af7a159ccef5a
ms.sourcegitcommit: 31827526894ffb75d64fcb0a7c76ee874ad3c269
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2019
ms.locfileid: "29754560"
---
# <a name="set-the-phone-numbers-included-on-invites-in-microsoft-teams"></a><span data-ttu-id="1e117-103">Microsfot Teams で招待状に含まれている電話番号を設定する</span><span class="sxs-lookup"><span data-stu-id="1e117-103">Set the phone numbers included on invites in Microsoft Teams</span></span>

<span data-ttu-id="1e117-104">マイクロソフト チームの会議を作成して、電話を使用してその会議にダイヤルインするユーザーを許可し、組織内のユーザーを Office 365 での音声会議に使用できます。</span><span class="sxs-lookup"><span data-stu-id="1e117-104">Audio Conferencing in Office 365 enables users in your organization to create Microsoft Teams meetings, and then allow users to dial in to those meetings using a phone.</span></span>
  
<span data-ttu-id="1e117-p101">会議ブリッジは、組織用のダイヤルイン電話番号のセットを提供します。これらの番号はすべて会議開催者が作成した会議に参加するために使用できますが、会議出席依頼にどの番号を含めるか選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="1e117-p101">A conferencing bridge gives you a set of dial-in phone numbers for your organization. All of them can be used to join the meetings that a meeting organizer has created, but you can select which ones will be included on their meeting invites.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1e117-107">会議主催者の会議出席依頼には、1 つの有料電話番号と 1 つの無料電話番号を含めることができますが、会議出席依頼の下部に、会議に参加するために使用できるダイヤルイン電話番号のすべての一覧を表示するリンクも記載されています。</span><span class="sxs-lookup"><span data-stu-id="1e117-107">There can be a maximum of one toll and one toll-free phone number on the meeting invite for a meeting organizer, but there is also a link located at the bottom of each meeting invite that opens the full list of all dial-in phone numbers that can be used to join a meeting.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="initial-assignment-of-phone-numbers-that-are-included-in-the-meeting-invites-for-new-users"></a><span data-ttu-id="1e117-108">会議に含まれている電話番号の最初の割り当ての新しいユーザーの招待します。</span><span class="sxs-lookup"><span data-stu-id="1e117-108">Initial assignment of phone numbers that are included in the meeting invites for new users</span></span>

<span data-ttu-id="1e117-109">会議にも含まれている電話番号は、オーディオ会議は、既定の会議通話の電話番号と既定会議無料電話番号のユーザーの設定で定義された有効にするユーザーの招待します。</span><span class="sxs-lookup"><span data-stu-id="1e117-109">The phone numbers that get included in the meeting invites of users enabled for Audio Conferencing are defined by the default conferencing toll phone number and the default conferencing toll-free phone number user's settings.</span></span> <span data-ttu-id="1e117-110">各設定を指定する有料電話番号と無料電話番号は、特定のユーザーの会議出席依頼に含まれます。</span><span class="sxs-lookup"><span data-stu-id="1e117-110">Each setting specifies which toll and toll-free number will be included in the meeting invite of a given user.</span></span> <span data-ttu-id="1e117-111">前述したように、各会議出席依頼には、1 つの有料電話番号が、1 つの省略可能なフリー ダイヤル番号および特定の会議に参加するのに使用できるすべてのダイヤルインの電話番号の完全な一覧を開くリンクが含まれます。</span><span class="sxs-lookup"><span data-stu-id="1e117-111">As noted above, each meeting invite contains one toll number, one optional toll-free number and a link that opens the full list of all dial-in phone numbers that can be used to join a given meeting.</span></span>

<span data-ttu-id="1e117-112">新しいユーザーの場合は、ユーザーがオーディオ会議サービスを有効にすると、ユーザーの Office 365 のプロファイルに設定されている国に基づく既定の会議の有料電話番号が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="1e117-112">For a new user, the default conferencing toll numbers is assigned based on the country that is set in the Office 365 profile of the user when the user is enabled for the Audio Conferencing service.</span></span> <span data-ttu-id="1e117-113">ユーザーの国または地域に一致する会議ブリッジに有料電話番号がある場合は、その番号がユーザーの既定の電話番号として自動的に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="1e117-113">If there is a toll number in the conference bridge that matches the country of the user, that number will be automatically assigned as the default toll number of the user.</span></span> <span data-ttu-id="1e117-114">ない場合に、ユーザーの既定の電話番号として会議ブリッジの有料電話番号が既定値として定義されている番号が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="1e117-114">If there isn't one, the number that is defined as the default toll number of the conference bridge will be assigned as the default toll number of the user.</span></span>  

<span data-ttu-id="1e117-115">オーディオ会議サービスを有効にすると、ユーザー、既定の有料電話番号とユーザーの無料電話番号はテナント管理者が各自の初期値から任意の時点で。</span><span class="sxs-lookup"><span data-stu-id="1e117-115">Once the user is enabled for the Audio Conferencing service, the default toll and toll-free phone numbers of the user can be changed by the tenant administrator from their initial values at any moment.</span></span>

## <a name="set-or-change-the-default-audio-conferencing-phone-number-for-a-meeting-organizer-or-user"></a><span data-ttu-id="1e117-116">設定または会議の開催者またはユーザーの既定の電話会議の電話番号を変更します。</span><span class="sxs-lookup"><span data-stu-id="1e117-116">Set or change the default audio conferencing phone number for a meeting organizer or user</span></span>

<span data-ttu-id="1e117-117">![チーム ・ ロゴ ・ 30x30.png](media/teams-logo-30x30.png) **、マイクロソフトのチーム管理センターを使用して**</span><span class="sxs-lookup"><span data-stu-id="1e117-117">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="1e117-118">左側のナビゲーションでは、**ユーザー**] をクリックしてで使用可能なユーザーの一覧からユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="1e117-118">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

    ![マイクロソフトのチームの管理センターでユーザーを選択することを示します](media/teamsselectusers.png)

2. <span data-ttu-id="1e117-120">ページの上部で、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1e117-120">At the top of the page, click **Edit**.</span></span>

    ![マイクロソフトのチームの管理センターで編集] をクリックします。](media/teamsedituser.png)

3. <span data-ttu-id="1e117-122">**オーディオ会議**の横にある [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1e117-122">Next to **Audio Conferencing**, click **Edit**.</span></span> 
    
    ![編集をクリックしてオーディオ会議](media/teamseditaudioconf.png)

4. <span data-ttu-id="1e117-124">**有料電話番号**や**フリー ダイヤル番号**のフィールドを使用すると、ユーザーの数を入力します。</span><span class="sxs-lookup"><span data-stu-id="1e117-124">Use the **Toll number** or **Toll-free number** fields to enter the numbers for the user.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="1e117-125">ユーザーの電話会議の設定を変更すると、マイクロソフトのチーム会議の定期的な予定と今後の更新し、出席者に送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1e117-125">When you change a user's audio conferencing settings, recurring and future Microsoft Teams meetings must be updated and sent to attendees.</span></span> 

## <a name="want-to-use-windows-powershell"></a><span data-ttu-id="1e117-126">Windows PowerShell を使用する場合</span><span class="sxs-lookup"><span data-stu-id="1e117-126">Want to use Windows PowerShell?</span></span>

<span data-ttu-id="1e117-p104">Windows PowerShell は、ユーザーと、ユーザーに許可されていることと許可されていないことを管理するためにあるということです。Windows PowerShell があれば、一元管理を使用して Office 365 を管理し、複数のタスクを抱えているときに、日常の仕事を簡素化することができます。Windows PowerShell を開始するには、これらのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1e117-p104">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="1e117-130">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="1e117-130">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="1e117-131">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="1e117-131">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="1e117-132">Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1e117-132">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span> 
  
    
## <a name="related-topics"></a><span data-ttu-id="1e117-133">関連トピック</span><span class="sxs-lookup"><span data-stu-id="1e117-133">Related topics</span></span>

[<span data-ttu-id="1e117-134">Office 365 での電話会議を使用または購入する</span><span class="sxs-lookup"><span data-stu-id="1e117-134">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
