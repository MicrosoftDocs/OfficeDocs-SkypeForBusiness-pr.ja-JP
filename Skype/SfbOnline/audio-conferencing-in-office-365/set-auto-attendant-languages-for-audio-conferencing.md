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
ms.openlocfilehash: 393ba3433ba7241ca5c992114de02191b7fb1044
ms.sourcegitcommit: 0458232441d3aed8dd578f41a13078aa379c9b00
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/10/2019
ms.locfileid: "27788987"
---
# <a name="set-auto-attendant-languages-for-audio-conferencing-in-skype-for-business-online"></a>Skype for Business Online で電話会議の自動案内の言語を設定する

> [!Note]
> Microsoft Teams での自動案内言語設定に関する詳細については、[Microsoft Teams で電話会議の自動案内の言語を設定する](/MicrosoftTeams/set-auto-attendant-languages-for-audio-conferencing-in-teams)を参照してください。

ビジネス用の Skype のオーディオ会議自動アテンダントを呼びかけますオーディオ呼び出し元のさまざまな言語で会議に参加するとき。
  
第 1 言語 1 つと、第 2 言語 4 つまで選びます。設定する第 1 言語が最初に使用され、第 2 言語は選択した順に自動応答で使用されます。 
  
> [!NOTE]
>  のみ、専用のカテゴリは、オーディオ会議の番号の言語を変更できます。 オーディオ会議の番号を共有の言語を変更できません。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-conferencing-auto-attendant-languages"></a>電話会議の自動応答の言語を設定する

この手順を実行するには、[Office 365 の管理者ロールについて](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)または[Office 365 の管理者ロールについて](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)としてログインしている必要があります。
    
1. **Skype**ビジネス管理センターの左のナビゲーションでは、**従来のポータル**に移動します。 1 回従来のポータルでは、**オーディオ会議**、し**Microsoft ブリッジ**] をクリックします。
    
2. 操作ウィンドウで、リストから電話会議の電話番号を選び、[ **言語を設定**] をクリックします。 専用の電話会議の番号の言語を変更することはのみです。  
    
3. [ **言語を設定**] ページで、[ **第 1 言語**] の下のボックスの一覧をクリックして、利用可能な全言語のリストを表示します。必要に応じて [ **第 2 言語**] の各ボックスの一覧をクリックして第 2 言語を選びます。
    
    > [!NOTE]
    > サポートされる第 1 言語と第 2 言語が表示されます。発信者に対する言語の表示順は、ドロップダウンで言語を選んだ順序になります。 
  
4. [ **保存**] をクリックします。
    
## <a name="want-else-should-i-know"></a>その他の情報

- 電話会議でサポートされる言語のリストを確認するには、「[ダイヤルイン会議でサポートされる言語](/MicrosoftTeams/audio-conferencing-supported-languages)」をご覧ください。
    
- 専用電話番号には言語を設定できますが、共有電話番号には設定できません。
    
- Microsoft をプロバイダーとして使用する Office 365 での電話会議を利用できる国/地域のリストを確認するには、「[電話会議の電話番号](phone-numbers-for-audio-conferencing.md)」をご覧ください。
    
## <a name="want-to-use-windows-powershell"></a>Windows PowerShell を使用する場合

この手順を自動化するには、[Set-CsOnlineDialInConferencingServiceNumber ](https://go.microsoft.com/fwlink/?LinkId=617689) コマンドレットと[Get-CsOnlineDialInConferencingLanguagesSupported ](https://go.microsoft.com/fwlink/?LinkId=617684) コマンドレットを使用できます。
  
詳細については、「[Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)」をご覧ください。
  
## <a name="related-topics"></a>See also

[Office 365 での電話会議を使用または購入する](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
