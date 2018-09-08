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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: ビジネス オンラインの Skype での音声会議自動アテンダントの言語のオーディオ会議の番号を選択する方法を参照してください。
ms.openlocfilehash: f7b7357d38941ba8d7e1f586f32daa8e02b29012
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23882211"
---
# <a name="set-auto-attendant-languages-for-audio-conferencing-in-skype-for-business-online"></a><span data-ttu-id="563cd-103">Skype for Business Online で電話会議の自動案内の言語を設定する</span><span class="sxs-lookup"><span data-stu-id="563cd-103">Set auto attendant languages for Audio Conferencing in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="563cd-104">Microsoft Teams での自動案内言語設定に関する詳細については、[Microsoft Teams で電話会議の自動案内の言語を設定する](/MicrosoftTeams/set-auto-attendant-languages-for-audio-conferencing-in-teams)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="563cd-104">For information about setting the auto attendant language in Microsoft Teams, see [Set auto attendant languages for Audio Conferencing in Microsoft Teams](/MicrosoftTeams/set-auto-attendant-languages-for-audio-conferencing-in-teams).</span></span>

<span data-ttu-id="563cd-105">ビジネス用の Skype のオーディオ会議自動アテンダントを呼びかけますオーディオ呼び出し元のさまざまな言語で会議に参加するとき。</span><span class="sxs-lookup"><span data-stu-id="563cd-105">The Audio Conferencing auto attendant for Skype for Business can greet audio callers in a number of different languages when they join a meeting.</span></span>
  
<span data-ttu-id="563cd-p101">第 1 言語 1 つと、第 2 言語 4 つまで選びます。設定する第 1 言語が最初に使用され、第 2 言語は選択した順に自動応答で使用されます。</span><span class="sxs-lookup"><span data-stu-id="563cd-p101">Choose one primary language and up to four secondary languages. The primary language that you set will be used first and the secondary languages will be used by the auto-attendant in order that you select.</span></span> 
  
> [!NOTE]
>  <span data-ttu-id="563cd-108">言語は、国内のダイヤルイン アクセス電話番号に対してのみ設定できます。</span><span class="sxs-lookup"><span data-stu-id="563cd-108">You can configure the languages on domestic audio access phone numbers only.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-conferencing-auto-attendant-languages"></a><span data-ttu-id="563cd-109">電話会議の自動応答の言語を設定する</span><span class="sxs-lookup"><span data-stu-id="563cd-109">Set the conferencing auto attendant languages</span></span>

<span data-ttu-id="563cd-110">この手順を実行するには、[Office 365 の管理者ロールについて](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)または[Office 365 の管理者ロールについて](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)としてログインしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="563cd-110">You must be an [Office 365 global admin](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) or [Skype for Business admin](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) to perform this step.</span></span>
    
1. <span data-ttu-id="563cd-111">**Skype for Business 管理センター**の左のナビゲーションで、[ **電話会議**] に移動し、[ **Microsoft ブリッジ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="563cd-111">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and then click **Microsoft bridge**.</span></span>
    
2. <span data-ttu-id="563cd-112">操作ウィンドウで、リストから電話会議の電話番号を選び、[ **言語を設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="563cd-112">Select the audio conferencing phone number from the list, and in the Action pane, click **Set languages**.</span></span> 
    
3. <span data-ttu-id="563cd-p102">[ **言語を設定**] ページで、[ **第 1 言語**] の下のボックスの一覧をクリックして、利用可能な全言語のリストを表示します。必要に応じて [ **第 2 言語**] の各ボックスの一覧をクリックして第 2 言語を選びます。</span><span class="sxs-lookup"><span data-stu-id="563cd-p102">On the **Set languages** page, click the **Primary language** list to view the complete list of available languages. If you need to, click each of the **Secondary languages** lists to select secondary language.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="563cd-p103">サポートされる第 1 言語と第 2 言語が表示されます。発信者に対する言語の表示順は、ドロップダウンで言語を選んだ順序になります。</span><span class="sxs-lookup"><span data-stu-id="563cd-p103">The primary and secondary languages that are supported are listed. The order in which you select them in the lists will be the order of the languages presented to callers.</span></span> 
  
4. <span data-ttu-id="563cd-117">[ **保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="563cd-117">Click **Save**.</span></span>
    
## <a name="want-else-should-i-know"></a><span data-ttu-id="563cd-118">その他の情報</span><span class="sxs-lookup"><span data-stu-id="563cd-118">Want else should I know?</span></span>

- <span data-ttu-id="563cd-119">電話会議でサポートされる言語のリストを確認するには、「[ダイヤルイン会議でサポートされる言語](/MicrosoftTeams/audio-conferencing-supported-languages)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="563cd-119">To see the list of supported languages for Audio Conferencing, see [Audio Conferencing supported languages](/MicrosoftTeams/audio-conferencing-supported-languages).</span></span>
    
- <span data-ttu-id="563cd-120">専用電話番号には言語を設定できますが、共有電話番号には設定できません。</span><span class="sxs-lookup"><span data-stu-id="563cd-120">Languages can be set for dedicated but not for shared phone numbers.</span></span>
    
- <span data-ttu-id="563cd-121">Microsoft をプロバイダーとして使用する Office 365 での電話会議を利用できる国/地域のリストを確認するには、「[電話会議の電話番号](phone-numbers-for-audio-conferencing.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="563cd-121">To see a list of countries/regions in which Audio Conferencing in Office 365 using Microsoft as the provider is available, see [Phone numbers for Audio Conferencing](phone-numbers-for-audio-conferencing.md).</span></span>
    
## <a name="want-to-use-windows-powershell"></a><span data-ttu-id="563cd-122">Windows PowerShell を使用する場合</span><span class="sxs-lookup"><span data-stu-id="563cd-122">Want to use Windows PowerShell?</span></span>

<span data-ttu-id="563cd-123">この手順を自動化するには、[Set-CsOnlineDialInConferencingServiceNumber ](https://go.microsoft.com/fwlink/?LinkId=617689) コマンドレットと[Get-CsOnlineDialInConferencingLanguagesSupported ](https://go.microsoft.com/fwlink/?LinkId=617684) コマンドレットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="563cd-123">To automate this step, you can use the [Set-CsOnlineDialInConferencingServiceNumber ](https://go.microsoft.com/fwlink/?LinkId=617689) and [Get-CsOnlineDialInConferencingLanguagesSupported ](https://go.microsoft.com/fwlink/?LinkId=617684) cmdlets.</span></span>
  
<span data-ttu-id="563cd-124">詳細については、「[Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="563cd-124">To learn more, see [Using Windows PowerShell to do common Skype for Business Online management tasks](https://go.microsoft.com/fwlink/?LinkId=525038)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="563cd-125">See also</span><span class="sxs-lookup"><span data-stu-id="563cd-125">Related topics</span></span>

[<span data-ttu-id="563cd-126">Office 365 での電話会議を使用または購入する</span><span class="sxs-lookup"><span data-stu-id="563cd-126">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
