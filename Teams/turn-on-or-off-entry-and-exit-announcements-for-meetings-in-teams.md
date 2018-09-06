---
title: エントリ無効を切り替えるし、マイクロソフトのチームでの会議のお知らせを終了します。
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: f2c7b5ea-07b6-4b77-8023-bec9596fcc32
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'エントリをオンにし、マイクロソフトのチーム会議で発表をオンまたはオフを終了する方法について説明します。 '
ms.openlocfilehash: b1409c34adce4bdb32013c184e273072858d3322
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2018
ms.locfileid: "23781176"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-microsoft-teams"></a><span data-ttu-id="0a76f-103">エントリ無効を切り替えるし、マイクロソフトのチームでの会議のお知らせを終了します。</span><span class="sxs-lookup"><span data-stu-id="0a76f-103">Turn on or off entry and exit announcements for meetings in Microsoft Teams</span></span>

<span data-ttu-id="0a76f-104">Office 365 で電話会議を設定する場合、電話会議ブリッジが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0a76f-104">When you are setting up Audio Conferencing in Office 365, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="0a76f-105">会議用ブリッジは、マイクロソフトのチーム会議へのコールを使用する 1 つまたは複数の電話番号を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="0a76f-105">A conferencing bridge can contain one or more phone numbers that people will use to call in to a Microsoft Teams meeting.</span></span> 
  
<span data-ttu-id="0a76f-106">会議ブリッジは、電話機を使用して会議にダイヤルインしようとしているユーザーの呼び出しに答えます。</span><span class="sxs-lookup"><span data-stu-id="0a76f-106">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="0a76f-107">会議ブリッジは、まず会議の自動応答の音声プロンプトで呼び出し元に応答します。設定によっては、次に通知を再生、呼び出し元に名前を記録するよう依頼し、PIN セキュリティをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="0a76f-107">The conferencing bridge answers the caller with voice prompts from a conferencing auto attendant, and then, depending on your settings, can play notifications, ask callers to record their name, and set up the PIN security.</span></span> <span data-ttu-id="0a76f-108">マイクロソフトのチーム会議の開催者に、暗証番号 (pin) が与えられるし、マイクロソフトのチームのアプリケーションを使用してミーティングを開始することはできない場合は、会議を開始することができます。</span><span class="sxs-lookup"><span data-stu-id="0a76f-108">A PIN is given to a Microsoft Teams meeting organizer, and it allows them to start a meeting if they can't start the meeting using the Microsoft Teams app.</span></span> <span data-ttu-id="0a76f-109">ただし、会議を開始するのに PIN が必要ないように設定をすることもできます。</span><span class="sxs-lookup"><span data-stu-id="0a76f-109">You can, however, set it so that a PIN isn't required to start a meeting.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a><span data-ttu-id="0a76f-110">会議の参加オプションの設定</span><span class="sxs-lookup"><span data-stu-id="0a76f-110">Setting meeting join options</span></span>

1. <span data-ttu-id="0a76f-111">左側のナビゲーションでは、**会議**に移動 > **会議ブリッジ**です。</span><span class="sxs-lookup"><span data-stu-id="0a76f-111">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="0a76f-112">**会議ブリッジ**のページの上部には、**ブリッジの設定**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0a76f-112">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span> 

3. <span data-ttu-id="0a76f-113">**ブリッジの設定**ウィンドウを有効にするまたは**ミーティングのエントリと終了の通知**を無効にします。</span><span class="sxs-lookup"><span data-stu-id="0a76f-113">In the **Bridge settings** pane, enable or disable **Meeting entry and exit notifications**.</span></span> <span data-ttu-id="0a76f-114">既定ではこれはすでに選択されています。</span><span class="sxs-lookup"><span data-stu-id="0a76f-114">This is selected by default.</span></span> <span data-ttu-id="0a76f-115">場合はこのオプションをオフにすると、データを入力したり、会議を離れると、会議に参加しているユーザーが通知されません。</span><span class="sxs-lookup"><span data-stu-id="0a76f-115">If you clear it, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
4. <span data-ttu-id="0a76f-116">[**エントリ/退出のお知らせの種類**] の下にある [**名前または電話番号**] または [**トーン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0a76f-116">Under **Entry/exit announcement type**, select **Names or phone numbers** or **Tones**.</span></span>
    
5. <span data-ttu-id="0a76f-117">**名前や電話番号**を選択した場合は、有効または、**ミーティングに参加する前に自分の名前を記録するための呼び出し元の確認**を無効にします。</span><span class="sxs-lookup"><span data-stu-id="0a76f-117">If you chose **Names or phone numbers**, enable or disable **Ask callers to record their name before joining the meeting**.</span></span>
    
6. <span data-ttu-id="0a76f-118">[ **保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0a76f-118">Click **Save**.</span></span>

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="0a76f-119">Windows PowerShell の詳細情報</span><span class="sxs-lookup"><span data-stu-id="0a76f-119">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="0a76f-p104">Windows PowerShell は、ユーザーと、ユーザーに許可されていることと許可されていないことを管理するためにあるということです。Windows PowerShell があれば、一元管理を使用して Office 365 を管理し、複数のタスクを抱えているときに、日常の仕事を簡素化することができます。Windows PowerShell を開始するには、これらのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0a76f-p104">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="0a76f-123">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="0a76f-123">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="0a76f-124">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="0a76f-124">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="0a76f-125">Windows PowerShell の詳細については、[マイクロソフト チームの PowerShell の参照](https://docs.microsoft.com/en-us/powershell/module/teams/?view=teams-ps)の詳細についてを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0a76f-125">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/en-us/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="0a76f-126">このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「Skype for Business Online 用 Windows PowerShell モジュール」からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="0a76f-126">Related topics</span></span>

[<span data-ttu-id="0a76f-127">電話会議に関するよくある質問</span><span class="sxs-lookup"><span data-stu-id="0a76f-127">Audio Conferencing common questions</span></span>](audio-conferencing-common-questions.md)
