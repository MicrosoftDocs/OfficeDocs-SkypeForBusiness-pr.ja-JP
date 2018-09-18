---
title: Microsfot Teams で招待状に含まれている電話番号を設定する
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 32954439-d365-4125-872f-b37466ecb035
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: '発信者が Microsfot Teams 会議に参加するための既定の電話番号を作成する手順を説明します。 '
ms.openlocfilehash: eddab0762b679dba08dd9981d6ae61a1403ebf47
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23882961"
---
# <a name="set-the-phone-numbers-included-on-invites-in-microsoft-teams"></a><span data-ttu-id="8aaf0-103">Microsfot Teams で招待状に含まれている電話番号を設定する</span><span class="sxs-lookup"><span data-stu-id="8aaf0-103">For information about meeting invite phone numbers in Microsoft Teams, see Set the phone numbers included on invites in Microsoft Teams.</span></span>

<span data-ttu-id="8aaf0-104">Office 365 の電話会議では、組織内のユーザーが Microsoft Teams 会議を作成することができます。ユーザーは電話を使用して作成した会議にダイヤルインすることができます。</span><span class="sxs-lookup"><span data-stu-id="8aaf0-104">Audio Conferencing in Office 365 enables users in your organization to create Skype for Business meetings, and then allow users to dial in to those meetings using a phone.</span></span> <span data-ttu-id="8aaf0-105">Office 365 では、Microsoft を電話会議ブリッジとして使うか、承認済みの電話会議プロバイダー (ACP) によってホストされているサードパーティ ダイヤルイン会議ブリッジを使うオプションを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="8aaf0-105">Audio Conferencing in Office 365 enables users in your organization to create a Skype for Business and Microsoft Teams meetings and then allow users to dial in to it using a phone. In Office 365, you have the option of using a Microsoft audio conferencing bridge or to use a third-party audio conferencing bridge that is hosted by an approved audio conferencing provider (ACP).</span></span>
  
<span data-ttu-id="8aaf0-p102">会議ブリッジは、組織用のダイヤルイン電話番号のセットを提供します。これらの番号はすべて会議開催者が作成した会議に参加するために使用できますが、会議出席依頼にどの番号を含めるか選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="8aaf0-p102">A conferencing bridge gives you a set of dial-in phone numbers for your organization. All of them can be used to join the meetings that a meeting organizer has created, but you can select which ones will be included on their meeting invites.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8aaf0-108">会議主催者の会議出席依頼には、1 つの有料電話番号と 1 つの無料電話番号を含めることができますが、会議出席依頼の下部に、会議に参加するために使用できるダイヤルイン電話番号のすべての一覧を表示するリンクも記載されています。</span><span class="sxs-lookup"><span data-stu-id="8aaf0-108">There can be a maximum of one toll and one toll-free phone number on the meeting invite for a meeting organizer, but there is also a link located at the bottom of each meeting invite that opens the full list of all dial-in phone numbers that can be used to join a meeting.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="set-or-change-the-default-audio-conferencing-phone-number-for-a-meeting-organizer-or-user"></a><span data-ttu-id="8aaf0-109">会議の開催者またはユーザーのために、既定の電話会議の電話番号を設定または変更する</span><span class="sxs-lookup"><span data-stu-id="8aaf0-109">Set or change the default audio conferencing phone number for a meeting organizer or user</span></span>

1. <span data-ttu-id="8aaf0-110">左側のナビゲーションで、[**ユーザー**] をクリックしてから、空いているユーザーのリストからユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="8aaf0-110">In the left navigation of the **Office 365 admin center, go to UsersActive users**, and then select the user or users from the list of available users.</span></span>

    ![Microsoft Teams と Skype for Business の管理センターでのユーザーの選択を示す](media/teamsselectusers.png)

2. <span data-ttu-id="8aaf0-112">ページの上部で、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8aaf0-112">At the top of the Conference Bridges page, click Bridge Settings.</span></span>

    ![Microsoft Teams と Skype for Business の管理センターで [編集] をクリックする](media/teamsedituser.png)

3. <span data-ttu-id="8aaf0-114">[**電話会議**] の隣で、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8aaf0-114">Next to **Audio Conferencing**, click **Edit**.</span></span> 
    
    ![電話会議の隣の [編集] をクリックする](media/teamseditaudioconf.png)

4. <span data-ttu-id="8aaf0-116">[**有料電話番号**] または [**無料電話番号**] フィールドを使用してユーザーの電話番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="8aaf0-116">A third-party is the provider: use the **Toll number** and **Toll-free number** fields to enter the numbers for the user.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="8aaf0-117">ユーザーの電話会議設定を変更するときは、繰り返し発生する今後の Microsoft Teams 会議が更新されて、出席者に送信されるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8aaf0-117">When you change a user's audio conferencing settings, recurring and future Skype for Business and Microsoft Teams meetings must be updated and sent to attendees.</span></span> 

## <a name="want-to-use-windows-powershell"></a><span data-ttu-id="8aaf0-118">Windows PowerShell を使用する場合</span><span class="sxs-lookup"><span data-stu-id="8aaf0-118">Want to use Windows PowerShell?</span></span>

<span data-ttu-id="8aaf0-p103">Windows PowerShell は、ユーザーと、ユーザーに許可されていることと許可されていないことを管理するためにあるということです。Windows PowerShell があれば、一元管理を使用して Office 365 を管理し、複数のタスクを抱えているときに、日常の仕事を簡素化することができます。Windows PowerShell を開始するには、これらのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8aaf0-p103">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="8aaf0-122">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="8aaf0-122">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="8aaf0-123">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="8aaf0-123">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="8aaf0-124">Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8aaf0-124">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span> 
  
    
## <a name="related-topics"></a><span data-ttu-id="8aaf0-125">関連トピック</span><span class="sxs-lookup"><span data-stu-id="8aaf0-125">Related topics</span></span>

[<span data-ttu-id="8aaf0-126">Office 365 での電話会議を使用または購入する</span><span class="sxs-lookup"><span data-stu-id="8aaf0-126">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
