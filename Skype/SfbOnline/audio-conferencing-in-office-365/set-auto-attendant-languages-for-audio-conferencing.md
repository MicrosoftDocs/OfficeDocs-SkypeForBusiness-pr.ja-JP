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
description: Skype for Business Online で電話会議の自動応答言語を電話会議の電話番号として選択する方法をSkype for Businessしてください。
ms.openlocfilehash: 714312989bc3898fea2ed0d335fed8f5f2eebbb3
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237023"
---
# <a name="set-auto-attendant-languages-for-audio-conferencing-in-skype-for-business-online"></a>Skype for Business Online で電話会議の自動案内の言語を設定する

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> Microsoft Teams での自動案内言語設定に関する詳細については、[Microsoft Teams で電話会議の自動案内の言語を設定する](/MicrosoftTeams/set-auto-attendant-languages-for-audio-conferencing-in-teams)を参照してください。

会議の電話会議の自動応答Skype for Business会議に参加するときに、さまざまな言語で音声発信者にあいさつすることができます。
  
第 1 言語 1 つと、第 2 言語 4 つまで選びます。設定する第 1 言語が最初に使用され、第 2 言語は選択した順に自動応答で使用されます。 
  
> [!NOTE]
>  [専用] カテゴリの電話会議番号の言語のみを変更できます。 共有電話会議番号の言語は変更できません。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-conferencing-auto-attendant-languages"></a>電話会議の自動応答の言語を設定する

この手順を実行するには[、グローバル](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)[管理者Skype for Business管理者](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)である必要があります。
    
1. [Skype for Business **管理センター] の左側** のナビゲーションで、[レガシ ポータル]**に移動します**。 レガシ ポータルで、[電話会議] **を選択し**、[Microsoft Bridge] **をクリックします**。
    
2. 操作ウィンドウで、リストから電話会議の電話番号を選び、[ **言語を設定**] をクリックします。 専用電話会議番号の言語を変更できるのは、その言語のみです。  
    
3. [ **言語を設定**] ページで、[ **第 1 言語**] の下のボックスの一覧をクリックして、利用可能な全言語のリストを表示します。必要に応じて [ **第 2 言語**] の各ボックスの一覧をクリックして第 2 言語を選びます。
    
    > [!NOTE]
    > サポートされる第 1 言語と第 2 言語が表示されます。発信者に対する言語の表示順は、ドロップダウンで言語を選んだ順序になります。 
  
4. [ **保存**] をクリックします。
    
## <a name="want-else-should-i-know"></a>その他の情報

- 電話会議でサポートされる言語のリストを確認するには、「[ダイヤルイン会議でサポートされる言語](/MicrosoftTeams/audio-conferencing-supported-languages)」をご覧ください。
    
- 専用電話番号には言語を設定できますが、共有電話番号には設定できません。
    
- プロバイダーとして Microsoft を使用して Microsoft 365 または Office 365 の電話会議を利用できる国/地域の一覧については、「電話会議の 電話 番号」[を参照してください](phone-numbers-for-audio-conferencing.md)。
    
## <a name="want-to-use-windows-powershell"></a>Windows PowerShell を使用する場合

この手順を自動化するには [、Set-CsOnlineDialInConferencingServiceNumber](/powershell/module/skype/Set-CsOnlineDialInConferencingServiceNumber) コマンドレットと [Get-CsOnlineDialInConferencingLanguagesSupported](/powershell/module/skype/Get-CsOnlineDialInConferencingLanguagesSupported) コマンドレットを使用できます。
  
詳細については、「[Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)」をご覧ください。
  
## <a name="related-topics"></a>関連トピック

[電話会議を試用または購入するには、Microsoft 365またはOffice 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
