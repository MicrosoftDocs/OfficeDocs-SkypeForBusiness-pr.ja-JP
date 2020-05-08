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
description: Skype for Business Online で電話会議番号の電話会議の自動応答の言語を選ぶ方法について説明します。
ms.openlocfilehash: 93b6ea917c7f79747273366893efc47a22b89bb2
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2020
ms.locfileid: "44163907"
---
# <a name="set-auto-attendant-languages-for-audio-conferencing-in-skype-for-business-online"></a>Skype for Business Online で電話会議の自動案内の言語を設定する

> [!Note]
> Microsoft Teams での自動案内言語設定に関する詳細については、[Microsoft Teams で電話会議の自動案内の言語を設定する](/MicrosoftTeams/set-auto-attendant-languages-for-audio-conferencing-in-teams)を参照してください。

Skype for Business の電話会議の自動応答では、電話会議に参加するときに、さまざまな言語で音声の発信者を挨拶メッセージことができます。
  
第 1 言語 1 つと、第 2 言語 4 つまで選びます。設定する第 1 言語が最初に使用され、第 2 言語は選択した順に自動応答で使用されます。 
  
> [!NOTE]
>  専用カテゴリの電話会議番号の言語のみを変更できます。 共有電話会議番号の言語を変更することはできません。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-conferencing-auto-attendant-languages"></a>電話会議の自動応答の言語を設定する

この手順を実行するには、[グローバル管理](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)者または[Skype for business の管理者](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)である必要があります。
    
1. **Skype For business 管理センター**の左側のナビゲーションで、[**従来のポータル**] に移動します。 従来のポータルで、[**電話会議**] を選び、[ **Microsoft bridge**] をクリックします。
    
2. 操作ウィンドウで、リストから電話会議の電話番号を選び、[ **言語を設定**] をクリックします。 専用の電話会議番号の言語を変更することはできません。  
    
3. [ **言語を設定**] ページで、[ **第 1 言語**] の下のボックスの一覧をクリックして、利用可能な全言語のリストを表示します。必要に応じて [ **第 2 言語**] の各ボックスの一覧をクリックして第 2 言語を選びます。
    
    > [!NOTE]
    > サポートされる第 1 言語と第 2 言語が表示されます。発信者に対する言語の表示順は、ドロップダウンで言語を選んだ順序になります。 
  
4. [ **保存**] をクリックします。
    
## <a name="want-else-should-i-know"></a>その他の情報

- 電話会議でサポートされる言語のリストを確認するには、「[ダイヤルイン会議でサポートされる言語](/MicrosoftTeams/audio-conferencing-supported-languages)」をご覧ください。
    
- 専用電話番号には言語を設定できますが、共有電話番号には設定できません。
    
- Microsoft 365 または Office 365 の電話会議が、プロバイダーとして Microsoft を使用している場合は、「[電話会議の電話番号](phone-numbers-for-audio-conferencing.md)」を参照してください。
    
## <a name="want-to-use-windows-powershell"></a>Windows PowerShell を使用する場合

この手順を自動化するには、 [set-csonlinedialinconferencingservicenumber](https://go.microsoft.com/fwlink/?LinkId=617689)と[get-csonlinedialinconferencinglanguagessupported](https://go.microsoft.com/fwlink/?LinkId=617684)コマンドレットを使用します。
  
詳細については、「[Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)」をご覧ください。
  
## <a name="related-topics"></a>関連項目

[Microsoft 365 または Office 365 で電話会議を試用または購入する](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
