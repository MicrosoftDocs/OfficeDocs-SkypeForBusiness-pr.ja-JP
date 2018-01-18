---
title: "オーディオ会議のための自動応答の言語を設定します。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 26d73dda-ab26-4af4-8aec-d17f3479ae50
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: "オーディオ会議自動アテンダントの言語のオーディオ会議の番号を選択する方法を参照してください。"
ms.openlocfilehash: 1c6b5acda947b97d7bbfbd5888159b48bf5e95aa
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/15/2017
---
# <a name="set-auto-attendant-languages-for-audio-conferencing"></a>オーディオ会議のための自動応答の言語を設定します。

ビジネスおよびマイクロソフトのチームの Skype のオーディオ会議自動アテンダントを呼びかけますオーディオ呼び出し元のさまざまな言語で会議に参加するとき。
  
1 つのプライマリ言語を選択し、最大 4 つのセカンダリ言語です。 主言語を設定することが最初に使用してセカンダリの言語が使用する自動応答を選択するようにします。 
  
> [!NOTE]
>  国内のオーディオのアクセスの電話番号だけでは、言語を構成できます。
  
## <a name="set-the-conferencing-auto-attendant-languages"></a>会議自動アテンダントの言語を設定します。

この手順を実行するには、 [Office 365 のグローバル管理者](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)または[ビジネス管理者の Skype](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)をする必要があります。
  
1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. **Office 365 管理センター**を参照して > **ビジネス用の Skype**です。
    
3. **Skype**ビジネス管理センターは、左側のナビゲーションでは、では、**オーディオ会議**に移動し、 **Microsoft ブリッジ**] をクリックします。
    
4. 電話会議の電話番号を選択します] ボックスの一覧から、操作ウィンドウで、**言語の設定**] をクリックします。 
    
5. [**言語の設定**] ページで利用可能な言語の完全な一覧を表示するのには、**主言語**] ボックスの一覧をクリックします。 必要がある場合、各セカンダリ言語を選択するのには**第 2 言語**のリストをクリックします。
    
    > [!NOTE]
    > サポートされているプライマリとセカンダリの言語が一覧表示されます。 選択するために、リスト内の順序は、呼び出し元に表示される言語の順序になります。 
  
6. [ **保存**] をクリックします。
    
## <a name="want-else-should-i-know"></a>かどうかも確認する必要があります。

- オーディオ会議については、サポートされている言語の一覧を参照してください、[電話会議がサポートされている言語](audio-conferencing-supported-languages.md)を参照してください。
    
- 専用が、共有の電話番号ではなく、言語を設定できます。
    
- プロバイダーと Microsoft を使用して Office 365 のオーディオ会議で使用可能な国/地域の一覧については、[電話会議の電話番号](phone-numbers-for-audio-conferencing.md)を参照してください。
    
## <a name="want-to-use-windows-powershell"></a>Windows PowerShell を使用します。

この手順を自動化するには、[セット CsOnlineDialInConferencingServiceNumber](https://go.microsoft.com/fwlink/?LinkId=617689)と[Get CsOnlineDialInConferencingLanguagesSupported](https://go.microsoft.com/fwlink/?LinkId=617684)コマンドレットを使用できます。
  
詳細については、[共通の Skype のオンライン ビジネスの管理タスクを実行する Windows PowerShell を使用する](https://go.microsoft.com/fwlink/?LinkId=525038)を参照してください。
  
## <a name="related-topics"></a>関連トピック

[Skype for Business および Microsoft Teams の電話会議のセットアップ](set-up-audio-conferencing.md)

