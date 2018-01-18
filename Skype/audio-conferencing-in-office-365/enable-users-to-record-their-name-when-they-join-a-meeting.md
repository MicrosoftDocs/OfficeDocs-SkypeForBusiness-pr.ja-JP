---
title: "会議に参加するときに自分の名前を記録するようにユーザーを有効にします。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 1d649328-ada7-422d-a074-d6da4da36970
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: "有効にするか、ユーザーが会議に参加するときの名前を記録できるかどうかを無効にする方法を学習します。 "
ms.openlocfilehash: f07bb24530e7b59ab6f54dfe2cd4eadf91def20c
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/15/2017
---
# <a name="enable-users-to-record-their-name-when-they-join-a-meeting"></a><span data-ttu-id="a806e-103">会議に参加するときに自分の名前を記録するようにユーザーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="a806e-103">Enable users to record their name when they join a meeting</span></span>

<span data-ttu-id="a806e-104">Office 365 に電話会議を設定する場合の電話番号と、オーディオ会議ブリッジと呼ばれるが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a806e-104">When you are setting up Audio Conferencing in Office 365, you will receive phone numbers and what is called an audio conferencing bridge.</span></span> <span data-ttu-id="a806e-105">会議用ブリッジは、専用または共有の電話番号は、1 つまたは複数の電話番号を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="a806e-105">A conferencing bridge can contain one or more phone numbers that can be a dedicated or shared phone number.</span></span>
  
<span data-ttu-id="a806e-106">会議用ブリッジの電話を使用して会議にダイヤルインするユーザーが呼び出しに応答します。</span><span class="sxs-lookup"><span data-stu-id="a806e-106">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="a806e-107">会議用ブリッジは、自動応答から音声メッセージを呼び出し元に回答し、それらの設定によって再生できる通知、呼び出し元が自分の名前を記録し、会議の開催者の暗証番号 (pin) のセキュリティを設定するに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="a806e-107">The conferencing bridge answers the caller with voice prompts from an auto attendant, and then, depending on their settings, can play notifications, ask callers to record their name, and set up the PIN security for meeting organizers.</span></span> <span data-ttu-id="a806e-108">ピンは、会議の開始を許可するように、ミーティングの開催者に与えられます。</span><span class="sxs-lookup"><span data-stu-id="a806e-108">PINs are given to meeting organizers to allow them to start a meeting.</span></span> <span data-ttu-id="a806e-109">ただし、ことができますを設定すると、暗証番号 (pin) が会議を開始する必要はありませんので。</span><span class="sxs-lookup"><span data-stu-id="a806e-109">However, you can set it up so a PIN isn't required to start a meeting.</span></span>
  
## <a name="set-whether-callers-should-record-their-name"></a><span data-ttu-id="a806e-110">呼び出し元が自分の名前を記録するかどうかを設定します。</span><span class="sxs-lookup"><span data-stu-id="a806e-110">Set whether callers should record their name</span></span>

1. <span data-ttu-id="a806e-111">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="a806e-111">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="a806e-112">**Office 365 管理センター**を参照して > **ビジネス用の Skype**です。</span><span class="sxs-lookup"><span data-stu-id="a806e-112">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="a806e-113">**電話会議**には、**ビジネス管理センターの Skype**、左側のナビゲーションでの > **Microsoft ブリッジ設定**します。</span><span class="sxs-lookup"><span data-stu-id="a806e-113">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="a806e-114">**会議参加の経験**をするには、[**ミーティングの入場を有効にして終了の通知をオンにする**というラベルの付いたチェック ボックスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a806e-114">Under **Meeting join experience**, see the check box labeled **Enable meeting entry and exit notifications to be turned on**.</span></span>
    
  - <span data-ttu-id="a806e-115">**選択**会議に入る前に自分の名前を記録するための呼び出し元が求められます。</span><span class="sxs-lookup"><span data-stu-id="a806e-115">**Selected** Callers will be asked to record their name before they enter the meeting.</span></span> <span data-ttu-id="a806e-116">これがデフォルトで選択されます。</span><span class="sxs-lookup"><span data-stu-id="a806e-116">This is selected by default.</span></span>
    
  - <span data-ttu-id="a806e-117">**クリア**呼び出し元はない会議に入る前に自分の名前を記録するよう求められます。</span><span class="sxs-lookup"><span data-stu-id="a806e-117">**Cleared** Callers won't be asked to record their name before they enter the meeting.</span></span>
    
5. <span data-ttu-id="a806e-118">変更を行ったら、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a806e-118">After you make your changes, click **Save**.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="a806e-119">Windows PowerShell で管理する方法</span><span class="sxs-lookup"><span data-stu-id="a806e-119">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="a806e-120">時間を短縮または、これを自動化するには、[セット CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757)コマンドレットを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="a806e-120">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingTenantSettings ](https://go.microsoft.com/fwlink/?LinkId=715757) cmdlet.</span></span>
    
-  <span data-ttu-id="a806e-121">Windows PowerShell は、ユーザーとは、ユーザーの許可を管理します。</span><span class="sxs-lookup"><span data-stu-id="a806e-121">Windows PowerShell is all about managing users and what users are allowed to do.</span></span> <span data-ttu-id="a806e-122">Windows PowerShell を実行する複数のタスクがある場合、日常的な作業を簡素化する管理の単一ポイントを使用して Office 365 を管理できます。</span><span class="sxs-lookup"><span data-stu-id="a806e-122">With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="a806e-123">Windows PowerShell を使い始めるには、以下のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a806e-123">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="a806e-124">Office 365 の PowerShell を使用する必要がある理由</span><span class="sxs-lookup"><span data-stu-id="a806e-124">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="a806e-125">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="a806e-125">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="a806e-126">Windows PowerShell には、実行しようとする設定の変更多くのユーザーを一度に 1 つなど、Office 365 管理センターを使用するだけでスピード、シンプルさと生産性に多くの利点があります。</span><span class="sxs-lookup"><span data-stu-id="a806e-126">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="a806e-127">次のトピックで、これらの利点について学習します。</span><span class="sxs-lookup"><span data-stu-id="a806e-127">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="a806e-128">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="a806e-128">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="a806e-129">Windows PowerShell による Skype for Business Online の管理</span><span class="sxs-lookup"><span data-stu-id="a806e-129">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="a806e-130">Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行</span><span class="sxs-lookup"><span data-stu-id="a806e-130">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="a806e-p106">Skype for Business Online 用 Windows PowerShell モジュールでは、リモート Windows PowerShell セッションを作成して Skype for Business Online に接続できます。このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「[Skype for Business Online 用 Windows PowerShell モジュール](https://go.microsoft.com/fwlink/?LinkId=294688)」からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="a806e-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="a806e-133">関連トピック</span><span class="sxs-lookup"><span data-stu-id="a806e-133">Related topics</span></span>

[<span data-ttu-id="a806e-134">Skype for Business および Microsoft Teams の電話会議のセットアップ</span><span class="sxs-lookup"><span data-stu-id="a806e-134">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](set-up-audio-conferencing.md)

