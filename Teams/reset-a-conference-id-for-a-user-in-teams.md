---
title: Microsoft Teams でユーザーの会議 ID をリセットする
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6e12242c-55f7-4bf4-90d7-0f36c0326b8e
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
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
description: Microsoft Teams でユーザーの会議 ID をリセットし、会議の更新と移行ツールへのリンクを取得する手順について説明します。
ms.openlocfilehash: 008a479677723dedbfe1923f57358808b16fd9ec
ms.sourcegitcommit: 09ff11f8e4f6a93cedc34a5d732a133163df79a0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "44042454"
---
# <a name="reset-a-conference-id-for-a-user-in-microsoft-teams"></a><span data-ttu-id="63b59-103">Microsoft Teams でユーザーの会議 ID をリセットする</span><span class="sxs-lookup"><span data-stu-id="63b59-103">Reset a conference ID for a user in Microsoft Teams</span></span>

<span data-ttu-id="63b59-104">動的な会議 ID は、発信者が会議にコールインするのに使用できるダイヤルイン番号と一緒に、会議出席依頼の下に含まれています。</span><span class="sxs-lookup"><span data-stu-id="63b59-104">A dynamic conference ID is included at the bottom of meeting invitations along with the dial-in phone numbers that can be used by callers to call in to a meeting.</span></span> <span data-ttu-id="63b59-105">ユーザーが電話番号をダイヤルするときに、発信者が会議に参加できるように、会議の自動応答は発信者にこの会議 ID の入力を求めます。</span><span class="sxs-lookup"><span data-stu-id="63b59-105">When the user dials the phone number, the auto attendant for the meeting will ask the caller to enter this conference ID so they can attend the meeting.</span></span>
  
> [!NOTE]
> <span data-ttu-id="63b59-106">会議プロバイダーが Microsoft の場合、ユーザーの会議 ID がデフォルトで「動的のみ」に設定されます。</span><span class="sxs-lookup"><span data-stu-id="63b59-106">If your conferencing provider is Microsoft, your users' conference IDs are set to Dynamic Only by default.</span></span> <span data-ttu-id="63b59-107">残念ながら、これはサポートされていないため、静的になるように変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="63b59-107">Unfortunately, there's no ability to change it to become static, as this is now unsupported.</span></span> <span data-ttu-id="63b59-108">電話会議 Id は、電話会議用に有効になっている Microsoft Teams ユーザーに対してのみ自動的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="63b59-108">Conference IDs are only automatically set for Microsoft Teams users enabled for Audio Conferencing.</span></span> 


## <a name="resetting-the-conference-id-for-a-user"></a><span data-ttu-id="63b59-109">ユーザーの会議 ID をリセットする</span><span class="sxs-lookup"><span data-stu-id="63b59-109">Resetting the conference ID for a user</span></span>

<span data-ttu-id="63b59-110">![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターの使用**</span><span class="sxs-lookup"><span data-stu-id="63b59-110">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="63b59-111">左側のナビゲーションで、[**ユーザー**] をクリックしてから、空いているユーザーのリストからユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="63b59-111">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="63b59-112">[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63b59-112">Click **Edit**.</span></span>

3. <span data-ttu-id="63b59-113">[電話**会議**] の [**会議 ID のリセット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63b59-113">Under **Audio Conferencing** click **Reset conference ID**.</span></span>

2. <span data-ttu-id="63b59-114">[**電話会議 ID のリセット**] ウィンドウで、[**リセット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63b59-114">In the **Reset conference ID** window, click **Reset**.</span></span> <span data-ttu-id="63b59-115">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="63b59-115">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span> <span data-ttu-id="63b59-116">既定では、メールはユーザーに送信されますが、無効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="63b59-116">By default, emails are sent to users, but this can be turned off.</span></span>   

    
> [!NOTE]
> <span data-ttu-id="63b59-117">会議 ID をリセットすると、新しい会議 ID を含むメールがユーザーに送信されます。</span><span class="sxs-lookup"><span data-stu-id="63b59-117">After you reset the conference ID, an email with the new conference ID will be sent to the user.</span></span> <span data-ttu-id="63b59-118">このメールは、プライマリメールアドレス (多くの場合、Office 365 メールボックス) に送信されます。</span><span class="sxs-lookup"><span data-stu-id="63b59-118">This email will be sent to the primary email address, in many cases, their Office 365 mailbox.</span></span> <span data-ttu-id="63b59-119">このメールには、新しい会議 ID、既定のダイヤルイン電話番号、および既存の会議を更新するための手順が含まれています。</span><span class="sxs-lookup"><span data-stu-id="63b59-119">The email contains the new conference ID, default dial-in phone number(s) and instructions for updating existing meetings.</span></span> 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a><span data-ttu-id="63b59-120">他に必要な情報はありますか?</span><span class="sxs-lookup"><span data-stu-id="63b59-120">What else should I know?</span></span>

- <span data-ttu-id="63b59-121">電話会議**のセクションで**、[電話会議情報を**メールで送信**する] をクリックすると、会議 ID、ダイヤルイン電話番号など、会議のすべての情報をメールでユーザーに送信できます。</span><span class="sxs-lookup"><span data-stu-id="63b59-121">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking **Send conference info in email** for the user in the **Audio Conferencing** section.</span></span> <span data-ttu-id="63b59-122">PIN は送信されません。</span><span class="sxs-lookup"><span data-stu-id="63b59-122">It doesn't send the PIN.</span></span>
    
- <span data-ttu-id="63b59-123">会議 ID には8桁の数字が含まれており、その長さを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="63b59-123">A conference ID will contain 8 digits, and you can't change its length.</span></span>
    
- <span data-ttu-id="63b59-124">会議 ID をリセットすると、新しい会議 ID が [ **電話会議 ID**] に一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="63b59-124">After it has been reset, you can see the new conference ID listed under **Conference ID**.</span></span>
    
- <span data-ttu-id="63b59-125">新しい会議 ID が作成されると、古い会議 ID を使用してダイヤルインすることはできなくなります。</span><span class="sxs-lookup"><span data-stu-id="63b59-125">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="63b59-126">既存の会議の出席依頼のスケジュールを変更して、新しい会議 ID を出席依頼に追加するように、ユーザーに通知してください。</span><span class="sxs-lookup"><span data-stu-id="63b59-126">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> 

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="63b59-127">Windows PowerShell の詳細情報</span><span class="sxs-lookup"><span data-stu-id="63b59-127">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="63b59-p107">Windows PowerShell で行うのは、ユーザーを管理し、ユーザーに何を許可して何を禁止するかを管理することです。Windows PowerShell を利用すると、Office 365 の管理を 1 か所で行うことができるので、複数のタスクを担当する管理者の日常業務を単純化できます。Windows PowerShell の使用を開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="63b59-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="63b59-131">Office 365 PowerShell を使用する必要がある理由</span><span class="sxs-lookup"><span data-stu-id="63b59-131">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="63b59-132">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="63b59-132">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="63b59-133">Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="63b59-133">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="63b59-134">関連トピック</span><span class="sxs-lookup"><span data-stu-id="63b59-134">Related topics</span></span>

[<span data-ttu-id="63b59-135">電話会議の PIN をリセットする</span><span class="sxs-lookup"><span data-stu-id="63b59-135">Reset the Audio Conferencing PIN</span></span>](reset-the-audio-conferencing-pin-in-teams.md)
