---
title: Microsoft Teams で電話会議の自動案内の言語を設定する
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26d73dda-ab26-4af4-8aec-d17f3479ae50
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
description: Microsoft Teams での電話会議番号に対応する電話会議の自動案内の言語を選択する方法を確認します。
ms.openlocfilehash: b9613b5e64bad0428975a6acd3b11db16a42c680
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2018
ms.locfileid: "25017954"
---
# <a name="set-auto-attendant-languages-for-audio-conferencing-in-microsoft-teams"></a><span data-ttu-id="350c2-103">Microsoft Teams で電話会議の自動案内の言語を設定する</span><span class="sxs-lookup"><span data-stu-id="350c2-103">Set auto attendant languages for Audio Conferencing in Microsoft Teams</span></span>

<span data-ttu-id="350c2-104">Microsoft Teams での電話会議の自動案内は、発信者に向けて、会議に参加するときに複数の言語で挨拶メッセージを出すことができます。</span><span class="sxs-lookup"><span data-stu-id="350c2-104">The Audio Conferencing auto attendant for Microsoft Teams can greet audio callers in a number of different languages when they join a meeting.</span></span>
  
<span data-ttu-id="350c2-p101">第 1 言語 1 つと、第 2 言語 4 つまで選びます。設定する第 1 言語が最初に使用され、第 2 言語は選択した順に自動応答で使用されます。</span><span class="sxs-lookup"><span data-stu-id="350c2-p101">Choose one primary language and up to four secondary languages. The primary language that you set will be used first and the secondary languages will be used by the auto-attendant in order that you select.</span></span> 
  
> [!NOTE]
>  <span data-ttu-id="350c2-107">言語は、国内のダイヤルイン アクセス電話番号に対してのみ設定できます。</span><span class="sxs-lookup"><span data-stu-id="350c2-107">You can configure the languages on domestic audio access phone numbers only.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="set-the-conferencing-auto-attendant-languages"></a><span data-ttu-id="350c2-108">電話会議の自動案内の言語を設定する</span><span class="sxs-lookup"><span data-stu-id="350c2-108">Set the conferencing auto attendant languages</span></span>

1. <span data-ttu-id="350c2-109">左側のナビゲーションで、[**会議**]  >  [**会議ブリッジ**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="350c2-109">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span>

2. <span data-ttu-id="350c2-110">電話会議の電話番号をリストから選択して、ページの最上部で、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="350c2-110">Select the audio conferencing phone number from the list, and at the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="350c2-111">右側のペインで、希望する既定の言語と、任意の代替言語を選びます。</span><span class="sxs-lookup"><span data-stu-id="350c2-111">In the pane on the right, choose the default language you want and any alternate languages.</span></span> 
 
    > [!NOTE]
    > <span data-ttu-id="350c2-112">デフォルトおよびサポートされている別の言語が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="350c2-112">The default and alternate languages that are supported are listed.</span></span> <span data-ttu-id="350c2-113">選択するために、リスト内の順序は、呼び出し元に表示される言語の順序になります。</span><span class="sxs-lookup"><span data-stu-id="350c2-113">The order in which you select them in the lists will be the order of the languages presented to callers.</span></span> 

4. <span data-ttu-id="350c2-114">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="350c2-114">Click **Save**.</span></span>

    
## <a name="want-else-should-i-know"></a><span data-ttu-id="350c2-115">その他の情報</span><span class="sxs-lookup"><span data-stu-id="350c2-115">Want else should I know?</span></span>

- <span data-ttu-id="350c2-116">電話会議でサポートされる言語のリストを確認するには、「[ダイヤルイン会議でサポートされる言語](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/audio-conferencing-supported-languages)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="350c2-116">To see the list of supported languages for Audio Conferencing, see [Audio Conferencing supported languages](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/audio-conferencing-supported-languages).</span></span>
    
- <span data-ttu-id="350c2-117">専用電話番号には言語を設定できますが、共有電話番号には設定できません。</span><span class="sxs-lookup"><span data-stu-id="350c2-117">Languages can be set for dedicated but not for shared phone numbers.</span></span>
    
- <span data-ttu-id="350c2-118">Microsoft をプロバイダーとして使用する Office 365 での電話会議を利用できる国/地域のリストを確認するには、「[電話会議の電話番号](phone-numbers-for-audio-conferencing-in-teams.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="350c2-118">To see a list of countries/regions in which Audio Conferencing in Office 365 using Microsoft as the provider is available, see [Phone numbers for Audio Conferencing](phone-numbers-for-audio-conferencing-in-teams.md).</span></span>
    
## <a name="want-to-use-windows-powershell"></a><span data-ttu-id="350c2-119">Windows PowerShell を使用する場合</span><span class="sxs-lookup"><span data-stu-id="350c2-119">Want to use Windows PowerShell?</span></span>

<span data-ttu-id="350c2-120">詳細については、[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="350c2-120">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="350c2-121">関連トピック</span><span class="sxs-lookup"><span data-stu-id="350c2-121">Related topics</span></span>

[<span data-ttu-id="350c2-122">Office 365 での電話会議を使用または購入する</span><span class="sxs-lookup"><span data-stu-id="350c2-122">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)

