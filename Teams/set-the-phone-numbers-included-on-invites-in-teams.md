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
description: 発信者が会議に参加するための既定の電話番号を作成するには、次のMicrosoft Teamsします。
ms.openlocfilehash: 476075ccf5e261695564b78ec084605af9e6898c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117175"
---
# <a name="set-the-phone-numbers-included-on-invites-in-microsoft-teams"></a><span data-ttu-id="0cbdf-103">Microsfot Teams で招待状に含まれている電話番号を設定する</span><span class="sxs-lookup"><span data-stu-id="0cbdf-103">Set the phone numbers included on invites in Microsoft Teams</span></span>

<span data-ttu-id="0cbdf-104">Microsoft 365 と Office 365 の電話会議を使用すると、組織内のユーザーは Microsoft Teams 会議を作成し、ユーザーが電話を使ってそれらの会議にダイヤルインできます。</span><span class="sxs-lookup"><span data-stu-id="0cbdf-104">Audio Conferencing in Microsoft 365 and Office 365 enables users in your organization to create Microsoft Teams meetings, and then allow users to dial in to those meetings using a phone.</span></span>
  
<span data-ttu-id="0cbdf-p101">会議ブリッジは、組織用のダイヤルイン電話番号のセットを提供します。これらの番号はすべて会議開催者が作成した会議に参加するために使用できますが、会議出席依頼にどの番号を含めるか選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="0cbdf-p101">A conferencing bridge gives you a set of dial-in phone numbers for your organization. All of them can be used to join the meetings that a meeting organizer has created, but you can select which ones will be included on their meeting invites.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0cbdf-107">会議主催者の会議出席依頼には、1 つの有料電話番号と 1 つの無料電話番号を含めることができますが、会議出席依頼の下部に、会議に参加するために使用できるダイヤルイン電話番号のすべての一覧を表示するリンクも記載されています。</span><span class="sxs-lookup"><span data-stu-id="0cbdf-107">There can be a maximum of one toll and one toll-free phone number on the meeting invite for a meeting organizer, but there is also a link located at the bottom of each meeting invite that opens the full list of all dial-in phone numbers that can be used to join a meeting.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="initial-assignment-of-phone-numbers-that-are-included-in-the-meeting-invites-for-new-users"></a><span data-ttu-id="0cbdf-108">新しいユーザーの会議出席招待に含まれる電話番号の初期割り当て</span><span class="sxs-lookup"><span data-stu-id="0cbdf-108">Initial assignment of phone numbers that are included in the meeting invites for new users</span></span>

<span data-ttu-id="0cbdf-109">電話会議が有効になっているユーザーの会議出席招待に含まれる電話番号は、既定の会議の有料電話番号と既定の会議の無料電話番号ユーザーの設定によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="0cbdf-109">The phone numbers that get included in the meeting invites of users enabled for Audio Conferencing are defined by the default conferencing toll phone number and the default conferencing toll-free phone number user's settings.</span></span> <span data-ttu-id="0cbdf-110">各設定では、特定のユーザーの会議出席招待に含める有料電話番号と無料電話番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="0cbdf-110">Each setting specifies which toll and toll-free number will be included in the meeting invite of a given user.</span></span> <span data-ttu-id="0cbdf-111">上で説明したように、各会議出席招待には、1 つの有料電話番号、1 つのオプションの無料電話番号、および特定の会議に参加するために使用できるすべてのダイヤルイン電話番号の完全なリストを開くリンクが含まれている。</span><span class="sxs-lookup"><span data-stu-id="0cbdf-111">As noted above, each meeting invite contains one toll number, one optional toll-free number and a link that opens the full list of all dial-in phone numbers that can be used to join a given meeting.</span></span>

<span data-ttu-id="0cbdf-112">新しいユーザーの場合、既定の会議の有料電話番号は、ユーザーが電話会議サービスに対して有効になっているときに、ユーザーの Microsoft 365 管理センターで設定されている使用場所に基づいて割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="0cbdf-112">For a new user, the default conferencing toll numbers is assigned based on the Usage Location that is set in the Microsoft 365 administration center of the user when the user is enabled for the Audio Conferencing service.</span></span> <span data-ttu-id="0cbdf-113">会議ブリッジにユーザーの国と一致する有料電話番号がある場合、その番号はユーザーの既定の有料電話番号として自動的に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="0cbdf-113">If there is a toll number in the conference bridge that matches the country of the user, that number will be automatically assigned as the default toll number of the user.</span></span> <span data-ttu-id="0cbdf-114">番号が 1 つない場合は、会議ブリッジの既定の有料電話番号として定義されている番号が、ユーザーの既定の有料電話番号として割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="0cbdf-114">If there isn't one, the number that is defined as the default toll number of the conference bridge will be assigned as the default toll number of the user.</span></span>  

<span data-ttu-id="0cbdf-115">ユーザーが電話会議サービスに対して有効になると、テナント管理者がユーザーの既定の有料電話番号と無料電話番号をいつでも初期値から変更できます。</span><span class="sxs-lookup"><span data-stu-id="0cbdf-115">Once the user is enabled for the Audio Conferencing service, the default toll and toll-free phone numbers of the user can be changed by the tenant administrator from their initial values at any moment.</span></span>

## <a name="set-or-change-the-default-audio-conferencing-phone-number-for-a-meeting-organizer-or-user"></a><span data-ttu-id="0cbdf-116">会議の開催者またはユーザーの既定の電話会議電話番号を設定または変更する</span><span class="sxs-lookup"><span data-stu-id="0cbdf-116">Set or change the default audio conferencing phone number for a meeting organizer or user</span></span>

<span data-ttu-id="0cbdf-117">![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターを使用する**</span><span class="sxs-lookup"><span data-stu-id="0cbdf-117">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

<span data-ttu-id="0cbdf-118">これらの変更を行うには、Teams サービス管理者であることが必要です。</span><span class="sxs-lookup"><span data-stu-id="0cbdf-118">You must be a Teams service admin to make these changes.</span></span> <span data-ttu-id="0cbdf-119">「[Teams 管理者ロールを使用してチームを管理する](./using-admin-roles.md)」をご覧いただき、管理者ロールとアクセス許可を取得する方法について読んでください。</span><span class="sxs-lookup"><span data-stu-id="0cbdf-119">See [Use Teams administrator roles to manage Teams](./using-admin-roles.md) to read about getting admin roles and permissions.</span></span>

1. <span data-ttu-id="0cbdf-120">管理センターにMicrosoft Teamsします。</span><span class="sxs-lookup"><span data-stu-id="0cbdf-120">Log in to the Microsoft Teams admin center.</span></span>

2. <span data-ttu-id="0cbdf-121">左側のナビゲーションで、[ユーザー] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="0cbdf-121">In the left navigation, click **Users**.</span></span>

    ![管理センターでユーザーを選択Microsoft Teams表示する](media/Admin-users.png)

3. <span data-ttu-id="0cbdf-123">使用可能なユーザーの一覧からユーザー名をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0cbdf-123">Click the user name from the list of available users.</span></span>

4. <span data-ttu-id="0cbdf-124">[**電話会議**] の横の [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0cbdf-124">Next to **Audio Conferencing**, click **Edit**.</span></span>

    ![[電話会議] の横にある [編集] をクリックします。](media/teams-set-phone-numbers-on-invites-image3.png)

5. <span data-ttu-id="0cbdf-126">[有料 **電話番号] フィールドまたは** **[無料電話番号]** フィールドを使用して、ユーザーの番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="0cbdf-126">Use the **Toll number** or **Toll-free number** fields to enter the numbers for the user.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0cbdf-127">ユーザーの電話会議の設定を変更する場合は、定期的な会議とMicrosoft Teams会議を更新して出席者に送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0cbdf-127">When you change a user's audio conferencing settings, recurring and future Microsoft Teams meetings must be updated and sent to attendees.</span></span>

## <a name="want-to-use-windows-powershell"></a><span data-ttu-id="0cbdf-128">アプリケーションを使用Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0cbdf-128">Want to use Windows PowerShell</span></span>

<span data-ttu-id="0cbdf-129">Windows PowerShellは、ユーザーの管理と、ユーザーが許可または許可されていない操作についてすべて行います。</span><span class="sxs-lookup"><span data-stu-id="0cbdf-129">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="0cbdf-130">このWindows PowerShell、1 つの管理Microsoft 365または Office 365 を管理し、複数のタスクを実行する場合に毎日の作業を簡略化できます。</span><span class="sxs-lookup"><span data-stu-id="0cbdf-130">With Windows PowerShell, you can manage Microsoft 365 or Office 365 by using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="0cbdf-131">Windows PowerShell の使用を開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0cbdf-131">To get started with Windows PowerShell, see these topics:</span></span>

- [<span data-ttu-id="0cbdf-132">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="0cbdf-132">Why you need to use Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- <span data-ttu-id="0cbdf-133">[アプリを使用してMicrosoft 365またはOffice 365を管理Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="0cbdf-133">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>

<span data-ttu-id="0cbdf-134">Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](/powershell/module/teams/?view=teams-ps)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0cbdf-134">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="0cbdf-135">関連トピック</span><span class="sxs-lookup"><span data-stu-id="0cbdf-135">Related topics</span></span>

[<span data-ttu-id="0cbdf-136">電話会議を試用または購入するには、Microsoft 365またはOffice 365</span><span class="sxs-lookup"><span data-stu-id="0cbdf-136">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)

[<span data-ttu-id="0cbdf-137">電話会議ブリッジの電話番号を変更する</span><span class="sxs-lookup"><span data-stu-id="0cbdf-137">Change the phone numbers on your Audio Conferencing bridge</span></span>](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)