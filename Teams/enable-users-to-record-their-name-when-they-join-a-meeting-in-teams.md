---
title: Microsoft Teams でユーザーが会議に参加したときに自分の名前を記録できるようにする
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1d649328-ada7-422d-a074-d6da4da36970
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
description: Microsoft Teams でユーザーが会議に参加したときに自分の名前を記録できるようにするかどうかの設定方法について説明します。
ms.openlocfilehash: 36e55b4cbffe4f1f57771578104f426f705a5ecd
ms.sourcegitcommit: 31827526894ffb75d64fcb0a7c76ee874ad3c269
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2019
ms.locfileid: "29754244"
---
# <a name="enable-users-to-record-their-name-when-they-join-a-meeting-in-microsoft-teams"></a><span data-ttu-id="99ad6-103">Microsoft Teams でユーザーが会議に参加したときに自分の名前を記録できるようにする</span><span class="sxs-lookup"><span data-stu-id="99ad6-103">Enable users to record their name when they join a meeting in Microsoft Teams</span></span>

<span data-ttu-id="99ad6-p101">[] Skype for Business Online でダイヤルイン会議をセットアップしているときには、電話番号とダイヤルインまたは電話会議ブリッジと呼ばれるものを受け取ります。会議ブリッジには、1 つ以上の電話番号 (専用または共有の電話番号の場合もある) が含まれることがあります。</span><span class="sxs-lookup"><span data-stu-id="99ad6-p101">When you are setting up Audio Conferencing in Office 365, you will receive phone numbers and what is called an audio conferencing bridge. A conferencing bridge can contain one or more phone numbers that can be a dedicated or shared phone number.</span></span>
  
<span data-ttu-id="99ad6-p102">ユーザーが電話を使って会議にダイヤルインすると、その通話は会議ブリッジによって応答されます。会議ブリッジでは、自動応答の音声プロンプトで発信者に応答してから、設定に応じて、お知らせを再生したり、発信者に名前を記録するように依頼したり、会議開催者の PIN セキュリティをセットアップしたりします。PIN が会議開催者に与えられて、開催者は会議を開始できるようになります。ただし、PIN がなくても会議を開始できるように設定できます。</span><span class="sxs-lookup"><span data-stu-id="99ad6-p102">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone. The conferencing bridge answers the caller with voice prompts from an auto attendant, and then, depending on their settings, can play notifications, ask callers to record their name, and set up the PIN security for meeting organizers. PINs are given to meeting organizers to allow them to start a meeting. However, you can set it up so a PIN isn't required to start a meeting.</span></span>

  
## <a name="set-whether-callers-should-record-their-name"></a><span data-ttu-id="99ad6-110">発信者が名前を記録すべきかどうかを設定する</span><span class="sxs-lookup"><span data-stu-id="99ad6-110">Set whether callers should record their name</span></span>

<span data-ttu-id="99ad6-111">![チーム ・ ロゴ ・ 30x30.png](media/teams-logo-30x30.png) **、マイクロソフトのチーム管理センターを使用して**</span><span class="sxs-lookup"><span data-stu-id="99ad6-111">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="99ad6-112">左側のナビゲーションで、[**会議**]  >  [**会議ブリッジ**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="99ad6-112">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="99ad6-113">**会議ブリッジ**のページの上部には、**ブリッジの設定**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="99ad6-113">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="99ad6-114">有効にするか、**ミーティングのエントリと終了の通知**を無効にします。</span><span class="sxs-lookup"><span data-stu-id="99ad6-114">Enable or disable **Meeting entry and exit notifications**.</span></span>

4. <span data-ttu-id="99ad6-115">通知を有効にする場合**の名前や電話番号\*\*\*\*の開始/終了のお知らせの種類**] を選択しを有効にし、 **、会議に参加する前に自分の名前を記録するための呼び出し元に問い合わせてください**。</span><span class="sxs-lookup"><span data-stu-id="99ad6-115">If enabling notifications, choose **Names or phone numbers** under **Entry/exit announcement type**, and then turn on **Ask callers to record their name before joining a meeting.**</span></span>

6. <span data-ttu-id="99ad6-116">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="99ad6-116">Click **Save**.</span></span>
    
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="99ad6-117">Windows PowerShell の詳細情報</span><span class="sxs-lookup"><span data-stu-id="99ad6-117">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="99ad6-p103">Windows PowerShell は、ユーザーと、ユーザーに許可されていることと許可されていないことを管理するためにあるということです。Windows PowerShell があれば、一元管理を使用して Office 365 を管理し、複数のタスクを抱えているときに、日常の仕事を簡素化することができます。Windows PowerShell を開始するには、これらのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="99ad6-p103">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="99ad6-121">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="99ad6-121">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="99ad6-122">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="99ad6-122">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="99ad6-123">Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="99ad6-123">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="99ad6-124">関連トピック</span><span class="sxs-lookup"><span data-stu-id="99ad6-124">Related topics</span></span>

[<span data-ttu-id="99ad6-125">Office 365 での電話会議を使用または購入する</span><span class="sxs-lookup"><span data-stu-id="99ad6-125">Try or purchase Audio Conferencing in Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
