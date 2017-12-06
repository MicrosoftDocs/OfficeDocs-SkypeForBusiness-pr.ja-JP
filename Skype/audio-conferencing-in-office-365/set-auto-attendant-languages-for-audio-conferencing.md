---
title: "電話会議の自動案内の言語を設定する"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/14/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- Strat_SB_PSTN
ms.assetid: 26d73dda-ab26-4af4-8aec-d17f3479ae50
description: "See how to select the auto-attendant lanugages for a dial-in conferencing number."
---

# 電話会議の自動案内の言語を設定する

> [!IMPORTANT]
> この記事は機械翻訳されています。機械翻訳についての「[免責事項](26d73dda-ab26-4af4-8aec-d17f3479ae50.md#MT_Footer)」をお読みください。この記事の英語版を参照するには、[ここ](https://support.office.com/en-us/article/26d73dda-ab26-4af4-8aec-d17f3479ae50)をクリックしてください。 
  
Skype for Business および Microsoft Teams 用の電話会議の自動案内は、ダイヤルインの通話者に対して、会議に参加するときに複数の言語で挨拶メッセージを出すことができます。
  
第 1 言語 1 つと、第 2 言語 4 つまで選びます。設定する第 1 言語が最初に使用され、第 2 言語は選択した順に自動応答で使用されます。
  
> [!NOTE]
> 言語は、国内のダイヤルイン アクセス電話番号に対してのみ設定できます。 
  
## 電話会議の自動応答の言語を設定する

この手順を実行するには、[Office 365 の管理者ロールについて](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)または[Office 365 の管理者ロールについて](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)としてログインしている必要があります。
  
1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. **Office 365 管理センター**、[ **Skype for Business**] の順に移動します。
    
3. **Skype for Business 管理センター**の左のナビゲーションで、[ **電話会議**] に移動し、[ **Microsoft ブリッジ**] をクリックします。
    
4. 操作ウィンドウで、リストから電話会議の電話番号を選び、[ **言語を設定**] をクリックします。
    
5. [ **言語を設定**] ページで、[ **第 1 言語**] の下のボックスの一覧をクリックして、利用可能な全言語のリストを表示します。必要に応じて [ **第 2 言語**] の各ボックスの一覧をクリックして第 2 言語を選びます。
    
    > [!NOTE]
    > サポートされる第 1 言語と第 2 言語が表示されます。発信者に対する言語の表示順は、ドロップダウンで言語を選んだ順序になります。 
  
6. [ **保存**] をクリックします。
    
## その他の情報

- 電話会議でサポートされる言語のリストを確認するには、「[音声会議でサポートされる言語](audio-conferencing-supported-languages.md)」をご覧ください。
    
- 専用電話番号には言語を設定できますが、共有電話番号には設定できません。
    
- Microsoft をプロバイダーとして使用する Office 365 での電話会議を利用できる国/地域のリストを確認するには、「[電話会議の電話番号](phone-numbers-for-audio-conferencing.md)」をご覧ください。
    
## Windows PowerShell を使用する場合

この手順を自動化するには、[Set-CsOnlineDialInConferencingServiceNumber ](https://go.microsoft.com/fwlink/?LinkId=617689) コマンドレットと[Get-CsOnlineDialInConferencingLanguagesSupported ](https://go.microsoft.com/fwlink/?LinkId=617684) コマンドレットを使用できます。
  
詳細については、「[Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)」をご覧ください。
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **機械翻訳についての免責事項**: この記事の翻訳はコンピューター システムによって行われており、人間の手は加えられていません。マイクロソフトでは、英語を話さないユーザーがマイクロソフトの製品、サービス、テクノロジに関するコンテンツを理解するのに役立てるため、こうした機械翻訳を提供しています。記事は機械翻訳されているため、用語、構文、文法などに誤りがある場合があります。 
  
## 関連項目
<a name="MT_Footer"> </a>

#### 

[Skype for Business および Microsoft Teams の電話会議のセットアップ](set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams.md)

