---
title: Skype for Business Online で電話会議の自動案内の言語を設定する
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26d73dda-ab26-4af4-8aec-d17f3479ae50
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: Skype for Business Online で電話会議番号の電話会議自動応答言語を選択する方法について説明します。
ms.openlocfilehash: d2b4c0d9be666a6ee7de9c2bd36b8dd06cccdf32
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51110003"
---
# <a name="set-auto-attendant-languages-for-audio-conferencing-in-skype-for-business-online"></a><span data-ttu-id="a1cbd-103">Skype for Business Online で電話会議の自動案内の言語を設定する</span><span class="sxs-lookup"><span data-stu-id="a1cbd-103">Set auto attendant languages for Audio Conferencing in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="a1cbd-104">Microsoft Teams での自動案内言語設定に関する詳細については、[Microsoft Teams で電話会議の自動案内の言語を設定する](/MicrosoftTeams/set-auto-attendant-languages-for-audio-conferencing-in-teams)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a1cbd-104">For information about setting the auto attendant language in Microsoft Teams, see [Set auto attendant languages for Audio Conferencing in Microsoft Teams](/MicrosoftTeams/set-auto-attendant-languages-for-audio-conferencing-in-teams).</span></span>

<span data-ttu-id="a1cbd-105">Skype for Business の電話会議の自動応答では、会議に参加するときに、さまざまな言語で音声の発信者に挨拶を行います。</span><span class="sxs-lookup"><span data-stu-id="a1cbd-105">The Audio Conferencing auto attendant for Skype for Business can greet audio callers in a number of different languages when they join a meeting.</span></span>
  
<span data-ttu-id="a1cbd-p101">第 1 言語 1 つと、第 2 言語 4 つまで選びます。設定する第 1 言語が最初に使用され、第 2 言語は選択した順に自動応答で使用されます。</span><span class="sxs-lookup"><span data-stu-id="a1cbd-p101">Choose one primary language and up to four secondary languages. The primary language that you set will be used first and the secondary languages will be used by the auto-attendant in order that you select.</span></span> 
  
> [!NOTE]
>  <span data-ttu-id="a1cbd-108">変更できるのは、専用カテゴリの電話会議番号の言語のみです。</span><span class="sxs-lookup"><span data-stu-id="a1cbd-108">You can only change the languages of audio conferencing numbers that are of the Dedicated category.</span></span> <span data-ttu-id="a1cbd-109">共有電話会議番号の言語は変更できません。</span><span class="sxs-lookup"><span data-stu-id="a1cbd-109">The languages of Shared audio conferencing number can't be changed.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-conferencing-auto-attendant-languages"></a><span data-ttu-id="a1cbd-110">電話会議の自動応答の言語を設定する</span><span class="sxs-lookup"><span data-stu-id="a1cbd-110">Set the conferencing auto attendant languages</span></span>

<span data-ttu-id="a1cbd-111">この手順を実行 [するには、グローバル管理者](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) または [Skype for Business](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) 管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="a1cbd-111">You must be a [global admin](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) or [Skype for Business admin](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) to perform this step.</span></span>
    
1. <span data-ttu-id="a1cbd-112">Skype **for Business 管理センターの** 左側のナビゲーションで、従来のポータルに **移動します**。</span><span class="sxs-lookup"><span data-stu-id="a1cbd-112">In the **Skype for Business admin center**, in the left navigation, go to **Legacy portal**.</span></span> <span data-ttu-id="a1cbd-113">従来のポータルに入り、[ **電話会議]** を選び **、[Microsoft Bridge] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="a1cbd-113">Once in the legacy portal, select **Audio conferencing**, and then click **Microsoft bridge**.</span></span>
    
2. <span data-ttu-id="a1cbd-114">操作ウィンドウで、リストから電話会議の電話番号を選び、[ **言語を設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a1cbd-114">Select the audio conferencing phone number from the list, and in the Action pane, click **Set languages**.</span></span> <span data-ttu-id="a1cbd-115">専用の電話会議番号の言語のみを変更できます。</span><span class="sxs-lookup"><span data-stu-id="a1cbd-115">It is only possible to change the languages of Dedicated audio conferencing numbers.</span></span>  
    
3. <span data-ttu-id="a1cbd-p105">[ **言語を設定**] ページで、[ **第 1 言語**] の下のボックスの一覧をクリックして、利用可能な全言語のリストを表示します。必要に応じて [ **第 2 言語**] の各ボックスの一覧をクリックして第 2 言語を選びます。</span><span class="sxs-lookup"><span data-stu-id="a1cbd-p105">On the **Set languages** page, click the **Primary language** list to view the complete list of available languages. If you need to, click each of the **Secondary languages** lists to select secondary language.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a1cbd-p106">サポートされる第 1 言語と第 2 言語が表示されます。発信者に対する言語の表示順は、ドロップダウンで言語を選んだ順序になります。</span><span class="sxs-lookup"><span data-stu-id="a1cbd-p106">The primary and secondary languages that are supported are listed. The order in which you select them in the lists will be the order of the languages presented to callers.</span></span> 
  
4. <span data-ttu-id="a1cbd-120">[ **保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a1cbd-120">Click **Save**.</span></span>
    
## <a name="want-else-should-i-know"></a><span data-ttu-id="a1cbd-121">その他の情報</span><span class="sxs-lookup"><span data-stu-id="a1cbd-121">Want else should I know?</span></span>

- <span data-ttu-id="a1cbd-122">電話会議でサポートされる言語のリストを確認するには、「[ダイヤルイン会議でサポートされる言語](/MicrosoftTeams/audio-conferencing-supported-languages)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a1cbd-122">To see the list of supported languages for Audio Conferencing, see [Audio Conferencing supported languages](/MicrosoftTeams/audio-conferencing-supported-languages).</span></span>
    
- <span data-ttu-id="a1cbd-123">専用電話番号には言語を設定できますが、共有電話番号には設定できません。</span><span class="sxs-lookup"><span data-stu-id="a1cbd-123">Languages can be set for dedicated but not for shared phone numbers.</span></span>
    
- <span data-ttu-id="a1cbd-124">Microsoft をプロバイダーとして使用して Microsoft 365 または Office 365 の電話会議を利用できる国/地域の一覧については[](phone-numbers-for-audio-conferencing.md)、「電話会議の電話番号」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a1cbd-124">To see a list of countries/regions in which Audio Conferencing in Microsoft 365 or Office 365 using Microsoft as the provider is available, see [Phone numbers for Audio Conferencing](phone-numbers-for-audio-conferencing.md).</span></span>
    
## <a name="want-to-use-windows-powershell"></a><span data-ttu-id="a1cbd-125">Windows PowerShell を使用する場合</span><span class="sxs-lookup"><span data-stu-id="a1cbd-125">Want to use Windows PowerShell?</span></span>

<span data-ttu-id="a1cbd-126">この手順を自動化するには [、Set-CsOnlineDialInConferencingServiceNumber](/powershell/module/skype/Set-CsOnlineDialInConferencingServiceNumber) コマンドレットと [Get-CsOnlineDialInConferencingLanguagesSupported](/powershell/module/skype/Get-CsOnlineDialInConferencingLanguagesSupported) コマンドレットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="a1cbd-126">To automate this step, you can use the [Set-CsOnlineDialInConferencingServiceNumber](/powershell/module/skype/Set-CsOnlineDialInConferencingServiceNumber) and [Get-CsOnlineDialInConferencingLanguagesSupported](/powershell/module/skype/Get-CsOnlineDialInConferencingLanguagesSupported) cmdlets.</span></span>
  
<span data-ttu-id="a1cbd-127">詳細については、「[Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a1cbd-127">To learn more, see [Using Windows PowerShell to do common Skype for Business Online management tasks](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="a1cbd-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="a1cbd-128">Related topics</span></span>

[<span data-ttu-id="a1cbd-129">Microsoft 365 または Office 365 で電話会議を試用または購入する</span><span class="sxs-lookup"><span data-stu-id="a1cbd-129">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)