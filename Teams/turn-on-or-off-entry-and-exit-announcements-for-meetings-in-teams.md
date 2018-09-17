---
title: Microsoft Teams で会議の入退室通知をオンまたはオフにする
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: f2c7b5ea-07b6-4b77-8023-bec9596fcc32
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
description: 'Microsoft Teams の会議の入退室通知をオンまたはオフにする方法について説明します。 '
ms.openlocfilehash: 94a091590ff00d2c78278e8ad559b61b1e732130
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23884630"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-microsoft-teams"></a><span data-ttu-id="d6c9f-103">Microsoft Teams で会議の入退室通知をオンまたはオフにする</span><span class="sxs-lookup"><span data-stu-id="d6c9f-103">For information about entry and exit announcements in Microsoft Teams, see Turn on or off entry and exit announcements for meetings in Microsoft Teams.</span></span>

<span data-ttu-id="d6c9f-104">Office 365 の電話会議をセットアップしている場合、電話会議ブリッジを取得します。</span><span class="sxs-lookup"><span data-stu-id="d6c9f-104">When you are setting up Audio Conferencing in Office 365, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="d6c9f-105">電話会議ブリッジには、ユーザーが Microsoft Teams の会議にダイヤルインするために使用する 1 つまたは複数の電話番号を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="d6c9f-105">A conferencing bridge can contain one or more phone numbers that people will use to call in to a Skype for Business meeting.</span></span> 
  
<span data-ttu-id="d6c9f-106">電話会議ブリッジは、電話機を使用して会議にダイヤルインしているユーザーの通話に応答します。</span><span class="sxs-lookup"><span data-stu-id="d6c9f-106">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="d6c9f-107">会議ブリッジは、まず会議の自動応答の音声プロンプトで呼び出し元に応答します。設定によっては、次に通知を再生、呼び出し元に名前を記録するよう依頼し、PIN セキュリティをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="d6c9f-107">The conferencing bridge answers the caller with voice prompts from a conferencing auto attendant, and then, depending on your settings, can play notifications, ask callers to record their name, and set up the PIN security.</span></span> <span data-ttu-id="d6c9f-108">PIN は Microsoft Teams の会議の開催者に付与され、Microsoft Teams アプリを使用して会議を開始することができない場合に、PIN で会議を開始することができます。</span><span class="sxs-lookup"><span data-stu-id="d6c9f-108">A PIN is given to a Skype for Business meeting organizer, and it allows them to start a meeting if they can't start the meeting using the Skype for Business app.</span></span> <span data-ttu-id="d6c9f-109">ただし、会議を開始するのに PIN を必要としないように設定することができます。</span><span class="sxs-lookup"><span data-stu-id="d6c9f-109">You can, however, set it so that a PIN isn't required to start a meeting.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a><span data-ttu-id="d6c9f-110">会議参加のオプションを設定する</span><span class="sxs-lookup"><span data-stu-id="d6c9f-110">Setting meeting join options</span></span>

1. <span data-ttu-id="d6c9f-111">左側のナビゲーションで、[**会議**]  >  [**会議ブリッジ**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="d6c9f-111">In the left navigation, go to **Audio conferencing** > **Users**.</span></span> 

2. <span data-ttu-id="d6c9f-112">[**会議ブリッジ**] ページの最上部で、[**ブリッジの設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d6c9f-112">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span> 

3. <span data-ttu-id="d6c9f-113">[**ブリッジ設定**] ウィンドウで、[**会議の開始と終了の通知**] を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="d6c9f-113">In the **Bridge settings** pane, enable or disable **Meeting entry and exit notifications**.</span></span> <span data-ttu-id="d6c9f-114">これは既定では選択されています。</span><span class="sxs-lookup"><span data-stu-id="d6c9f-114">This is selected by default.</span></span> <span data-ttu-id="d6c9f-115">この選択をクリアすると、既に参加済みのユーザーは、誰かが入ってきたり退出したりしたときに通知を受け取りません。</span><span class="sxs-lookup"><span data-stu-id="d6c9f-115">If you clear this check box, users who have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span></span>
    
4. <span data-ttu-id="d6c9f-116">[**開始/終了のお知らせの種類**] で、[**名前または電話番号**] または [**トーン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d6c9f-116">Under **Entry/exit announcement type**, select **Names or phone numbers** or **Tones**.</span></span>
    
5. <span data-ttu-id="d6c9f-117">[**名前または電話番号**] を選ぶ場合は、[**発信者に、会議に参加する前に自分の名前を記録するように要求します**] を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="d6c9f-117">If you chose **Names or phone numbers**, enable or disable **Ask callers to record their name before joining the meeting**.</span></span>
    
6. <span data-ttu-id="d6c9f-118">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d6c9f-118">Click **Save**.</span></span>

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="d6c9f-119">Windows PowerShell の詳細情報</span><span class="sxs-lookup"><span data-stu-id="d6c9f-119">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="d6c9f-p104">Windows PowerShell は、ユーザーと、ユーザーに許可されていることと許可されていないことを管理するためにあるということです。Windows PowerShell があれば、一元管理を使用して Office 365 を管理し、複数のタスクを抱えているときに、日常の仕事を簡素化することができます。Windows PowerShell を開始するには、これらのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d6c9f-p104">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="d6c9f-123">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="d6c9f-123">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="d6c9f-124">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="d6c9f-124">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="d6c9f-125">Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d6c9f-125">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="d6c9f-126">関連トピック</span><span class="sxs-lookup"><span data-stu-id="d6c9f-126">Related topics</span></span>

[<span data-ttu-id="d6c9f-127">電話会議に関するよくある質問</span><span class="sxs-lookup"><span data-stu-id="d6c9f-127">Audio Conferencing common questions</span></span>](audio-conferencing-common-questions.md)
