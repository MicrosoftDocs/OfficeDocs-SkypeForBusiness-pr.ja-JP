---
title: "電話会議の自動案内の言語を設定する"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 26d73dda-ab26-4af4-8aec-d17f3479ae50
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: See how to select the auto-attendant lanugages for a dial-in conferencing number.
ms.openlocfilehash: 85dd6fb9328e3362d84315f7c8a7f3d7e8e2df86
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2018
---
# <a name="set-auto-attendant-languages-for-audio-conferencing"></a>電話会議の自動案内の言語を設定する

[] Skype for Business および Microsoft Teams 用の電話会議の自動案内は、ダイヤルインの通話者に対して、会議に参加するときに複数の言語で挨拶メッセージを出すことができます。
  
第 1 言語 1 つと、第 2 言語 4 つまで選びます。設定する第 1 言語が最初に使用され、第 2 言語は選択した順に自動応答で使用されます。 
  
> [!NOTE]
>  言語は、国内のダイヤルイン アクセス電話番号に対してのみ設定できます。
  
## <a name="set-the-conferencing-auto-attendant-languages"></a>電話会議の自動応答の言語を設定する

この手順を実行するには、[Office 365 の管理者ロールについて](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)または[Office 365 の管理者ロールについて](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)としてログインしている必要があります。
  
1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. Sign in to Office 365 with your work or school account.
    
3. **Skype for Business 管理センター**の左のナビゲーションで、[ **電話会議**] に移動し、[ **Microsoft ブリッジ**] をクリックします。
    
4. 操作ウィンドウで、リストから電話会議の電話番号を選び、[ **言語を設定**] をクリックします。 
    
5. [ **言語を設定**] ページで、[ **第 1 言語**] の下のボックスの一覧をクリックして、利用可能な全言語のリストを表示します。必要に応じて [ **第 2 言語**] の各ボックスの一覧をクリックして第 2 言語を選びます。
    
    > [!NOTE]
    > サポートされる第 1 言語と第 2 言語が表示されます。発信者に対する言語の表示順は、ドロップダウンで言語を選んだ順序になります。 
  
6. [ **保存**] をクリックします。
    
## <a name="want-else-should-i-know"></a>その他の情報

- 電話会議でサポートされる言語のリストを確認するには、「[ダイヤルイン会議でサポートされる言語](audio-conferencing-supported-languages.md)」をご覧ください。
    
- 専用電話番号には言語を設定できますが、共有電話番号には設定できません。
    
- Microsoft をプロバイダーとして使用する Office 365 での電話会議を利用できる国/地域のリストを確認するには、「[電話会議の電話番号](phone-numbers-for-audio-conferencing.md)」をご覧ください。
    
## <a name="want-to-use-windows-powershell"></a>Windows PowerShell を使用する場合

この手順を自動化するには、[Set-CsOnlineDialInConferencingServiceNumber ](https://go.microsoft.com/fwlink/?LinkId=617689) コマンドレットと[Get-CsOnlineDialInConferencingLanguagesSupported ](https://go.microsoft.com/fwlink/?LinkId=617684) コマンドレットを使用できます。
  
詳細については、「[Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)」をご覧ください。
  
## <a name="related-topics"></a>See also

[Skype for Business および Microsoft Teams の電話会議のセットアップ](set-up-audio-conferencing.md)

