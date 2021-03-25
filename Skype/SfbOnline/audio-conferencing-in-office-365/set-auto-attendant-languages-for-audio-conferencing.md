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
# <a name="set-auto-attendant-languages-for-audio-conferencing-in-skype-for-business-online"></a>Skype for Business Online で電話会議の自動案内の言語を設定する

> [!Note]
> Microsoft Teams での自動案内言語設定に関する詳細については、[Microsoft Teams で電話会議の自動案内の言語を設定する](/MicrosoftTeams/set-auto-attendant-languages-for-audio-conferencing-in-teams)を参照してください。

Skype for Business の電話会議の自動応答では、会議に参加するときに、さまざまな言語で音声の発信者に挨拶を行います。
  
第 1 言語 1 つと、第 2 言語 4 つまで選びます。設定する第 1 言語が最初に使用され、第 2 言語は選択した順に自動応答で使用されます。 
  
> [!NOTE]
>  変更できるのは、専用カテゴリの電話会議番号の言語のみです。 共有電話会議番号の言語は変更できません。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-conferencing-auto-attendant-languages"></a>電話会議の自動応答の言語を設定する

この手順を実行 [するには、グローバル管理者](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) または [Skype for Business](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) 管理者である必要があります。
    
1. Skype **for Business 管理センターの** 左側のナビゲーションで、従来のポータルに **移動します**。 従来のポータルに入り、[ **電話会議]** を選び **、[Microsoft Bridge] をクリックします**。
    
2. 操作ウィンドウで、リストから電話会議の電話番号を選び、[ **言語を設定**] をクリックします。 専用の電話会議番号の言語のみを変更できます。  
    
3. [ **言語を設定**] ページで、[ **第 1 言語**] の下のボックスの一覧をクリックして、利用可能な全言語のリストを表示します。必要に応じて [ **第 2 言語**] の各ボックスの一覧をクリックして第 2 言語を選びます。
    
    > [!NOTE]
    > サポートされる第 1 言語と第 2 言語が表示されます。発信者に対する言語の表示順は、ドロップダウンで言語を選んだ順序になります。 
  
4. [ **保存**] をクリックします。
    
## <a name="want-else-should-i-know"></a>その他の情報

- 電話会議でサポートされる言語のリストを確認するには、「[ダイヤルイン会議でサポートされる言語](/MicrosoftTeams/audio-conferencing-supported-languages)」をご覧ください。
    
- 専用電話番号には言語を設定できますが、共有電話番号には設定できません。
    
- Microsoft をプロバイダーとして使用して Microsoft 365 または Office 365 の電話会議を利用できる国/地域の一覧については[](phone-numbers-for-audio-conferencing.md)、「電話会議の電話番号」を参照してください。
    
## <a name="want-to-use-windows-powershell"></a>Windows PowerShell を使用する場合

この手順を自動化するには [、Set-CsOnlineDialInConferencingServiceNumber](/powershell/module/skype/Set-CsOnlineDialInConferencingServiceNumber) コマンドレットと [Get-CsOnlineDialInConferencingLanguagesSupported](/powershell/module/skype/Get-CsOnlineDialInConferencingLanguagesSupported) コマンドレットを使用できます。
  
詳細については、「[Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)」をご覧ください。
  
## <a name="related-topics"></a>関連項目

[Microsoft 365 または Office 365 で電話会議を試用または購入する](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)