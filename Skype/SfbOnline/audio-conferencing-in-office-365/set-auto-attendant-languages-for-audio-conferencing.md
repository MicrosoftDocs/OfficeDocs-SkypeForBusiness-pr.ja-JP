---
title: "電話会議の自動応答の言語を設定します。"
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
description: "電話会議の番号に電話会議の自動応答の言語を選択する方法を参照してください。"
ms.openlocfilehash: 85dd6fb9328e3362d84315f7c8a7f3d7e8e2df86
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="set-auto-attendant-languages-for-audio-conferencing"></a>電話会議の自動応答の言語を設定します。

Skype for Business とチームの Microsoft の電話会議の自動応答できますして、電話の発信者に応答数を別の言語で会議に参加するとき。
  
1 つのプライマリ言語を選択し、4 つの第 2 言語をセットアップします。設定されている主言語が最初に使用して、第 2 言語が使用する自動応答を選択するようにします。 
  
> [!NOTE]
>  国内の音声アクセス番号のみで言語を設定できます。
  
## <a name="set-the-conferencing-auto-attendant-languages"></a>会議の自動応答の言語を設定します。

この手順を実行するのには、 [Office 365 グローバル管理者](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)または[Skype for Business の管理者](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)があります。
  
1. 職場または学校のアカウントで Office 365 にサインインします。
    
2. **Office 365 管理センター**に移動 > **Skype for Business**します。
    
3. **Skype for Business 管理センター**] で、左のナビゲーションでは、**音声会議**に移動し、[ **Microsoft bridge**] をクリックします。
    
4. 電話会議の電話番号を選択し、リストから、操作ウィンドウで、[**言語の設定**] をクリックします。 
    
5. [**言語の設定**] ページには、利用可能な言語の一覧を表示する**主言語**のリストをクリックします。必要がある場合は、第 2 言語を選択する**第 2 言語**リストの各をクリックします。
    
    > [!NOTE]
    > サポートされているプライマリおよびセカンダリ言語が表示されます。順序を選択することで、リストの発信者に応答する表示言語の順序となります。 
  
6. {[**保存**] をクリックします。}
    
## <a name="want-else-should-i-know"></a>しますそれ以外の場合はありますか。

- 電話会議のサポートされる言語の一覧を表示するには、[電話会議言語をサポートする](audio-conferencing-supported-languages.md)をご覧ください。
    
- 専用にし、共有の電話番号ではなく、言語を設定できます。
    
- プロバイダーとして Microsoft を使って Office 365 で音声会議で利用できる国/地域の一覧については、[電話会議の電話番号](phone-numbers-for-audio-conferencing.md)を参照してください。
    
## <a name="want-to-use-windows-powershell"></a>Windows PowerShell を使用するとしていますか。

この手順を自動化するには、 [Set-csonlinedialinconferencingservicenumber](https://go.microsoft.com/fwlink/?LinkId=617689)と[Get CsOnlineDialInConferencingLanguagesSupported](https://go.microsoft.com/fwlink/?LinkId=617684)のコマンドレットを使用することができます。
  
詳細については、[共通の Skype for Business Online の管理タスクを実行する Windows PowerShell を使用する](https://go.microsoft.com/fwlink/?LinkId=525038)を参照してください。
  
## <a name="related-topics"></a>関連トピック

[Skype for Business とチームの Microsoft の音声会議をセットアップする設定します。](set-up-audio-conferencing.md)

