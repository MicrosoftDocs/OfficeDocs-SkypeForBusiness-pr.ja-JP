---
title: Microsoft Teams で会議の入退室通知をオンまたはオフにする
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: f2c7b5ea-07b6-4b77-8023-bec9596fcc32
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Microsoft Teams の会議の入退室通知をオンまたはオフにする方法について説明します。 '
ms.openlocfilehash: d7e900a86a8292c56e9ce0d941506b8a894c8141
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32228476"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-microsoft-teams"></a><span data-ttu-id="88dfd-103">Microsoft Teams で会議の入退室通知をオンまたはオフにする</span><span class="sxs-lookup"><span data-stu-id="88dfd-103">Turn on or off entry and exit announcements for meetings in Microsoft Teams</span></span>

<span data-ttu-id="88dfd-104">Office 365 の電話会議をセットアップしている場合、電話会議ブリッジを取得します。</span><span class="sxs-lookup"><span data-stu-id="88dfd-104">When you are setting up Audio Conferencing in Office 365, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="88dfd-105">電話会議ブリッジには、ユーザーが Microsoft Teams の会議にダイヤルインするために使用する 1 つまたは複数の電話番号を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="88dfd-105">A conferencing bridge can contain one or more phone numbers that people will use to call in to a Microsoft Teams meeting.</span></span> 
  
<span data-ttu-id="88dfd-106">電話会議ブリッジは、電話機を使用して会議にダイヤルインしているユーザーの通話に応答します。</span><span class="sxs-lookup"><span data-stu-id="88dfd-106">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="88dfd-107">会議ブリッジは、まず会議の自動応答の音声プロンプトで呼び出し元に応答します。設定によっては、次に通知を再生、呼び出し元に名前を記録するよう依頼し、PIN セキュリティをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="88dfd-107">The conferencing bridge answers the caller with voice prompts from a conferencing auto attendant, and then, depending on your settings, can play notifications, ask callers to record their name, and set up the PIN security.</span></span> <span data-ttu-id="88dfd-108">PIN は Microsoft Teams の会議の開催者に付与され、Microsoft Teams アプリを使用して会議を開始することができない場合に、PIN で会議を開始することができます。</span><span class="sxs-lookup"><span data-stu-id="88dfd-108">A PIN is given to a Microsoft Teams meeting organizer, and it allows them to start a meeting if they can't start the meeting using the Microsoft Teams app.</span></span> <span data-ttu-id="88dfd-109">ただし、会議を開始するのに PIN を必要としないように設定することができます。</span><span class="sxs-lookup"><span data-stu-id="88dfd-109">You can, however, set it so that a PIN isn't required to start a meeting.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a><span data-ttu-id="88dfd-110">会議参加のオプションを設定する</span><span class="sxs-lookup"><span data-stu-id="88dfd-110">Setting meeting join options</span></span>

<span data-ttu-id="88dfd-111">![チーム ・ ロゴ ・ 30x30.png](media/teams-logo-30x30.png) **、マイクロソフトのチーム管理センターを使用して**</span><span class="sxs-lookup"><span data-stu-id="88dfd-111">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="88dfd-112">左側のナビゲーションで、[**会議**]  >  [**会議ブリッジ**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="88dfd-112">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="88dfd-113">[**会議ブリッジ**] ページの最上部で、[**ブリッジの設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="88dfd-113">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span> 

3. <span data-ttu-id="88dfd-114">[**ブリッジ設定**] ウィンドウで、[**会議の開始と終了の通知**] を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="88dfd-114">In the **Bridge settings** pane, enable or disable **Meeting entry and exit notifications**.</span></span> <span data-ttu-id="88dfd-115">これは既定では選択されています。</span><span class="sxs-lookup"><span data-stu-id="88dfd-115">This is selected by default.</span></span> <span data-ttu-id="88dfd-116">この選択をクリアすると、既に参加済みのユーザーは、誰かが入ってきたり退出したりしたときに通知を受け取りません。</span><span class="sxs-lookup"><span data-stu-id="88dfd-116">If you clear it, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
4. <span data-ttu-id="88dfd-117">[**開始/終了のお知らせの種類**] で、[**名前または電話番号**] または [**トーン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="88dfd-117">Under **Entry/exit announcement type**, select **Names or phone numbers** or **Tones**.</span></span>
    
5. <span data-ttu-id="88dfd-118">[**名前または電話番号**] を選ぶ場合は、[**発信者に、会議に参加する前に自分の名前を記録するように要求します**] を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="88dfd-118">If you chose **Names or phone numbers**, enable or disable **Ask callers to record their name before joining the meeting**.</span></span>
    
6. <span data-ttu-id="88dfd-119">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="88dfd-119">Click **Save**.</span></span>

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="88dfd-120">Windows PowerShell の詳細情報</span><span class="sxs-lookup"><span data-stu-id="88dfd-120">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="88dfd-p104">Windows PowerShell は、ユーザーと、ユーザーに許可されていることと許可されていないことを管理するためにあるということです。Windows PowerShell があれば、一元管理を使用して Office 365 を管理し、複数のタスクを抱えているときに、日常の仕事を簡素化することができます。Windows PowerShell を開始するには、これらのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="88dfd-p104">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="88dfd-124">Office 365 PowerShell を使用する必要がある理由</span><span class="sxs-lookup"><span data-stu-id="88dfd-124">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="88dfd-125">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="88dfd-125">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="88dfd-126">Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="88dfd-126">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="88dfd-127">関連トピック</span><span class="sxs-lookup"><span data-stu-id="88dfd-127">Related topics</span></span>

[<span data-ttu-id="88dfd-128">電話会議に関するよくある質問</span><span class="sxs-lookup"><span data-stu-id="88dfd-128">Audio Conferencing common questions</span></span>](audio-conferencing-common-questions.md)
