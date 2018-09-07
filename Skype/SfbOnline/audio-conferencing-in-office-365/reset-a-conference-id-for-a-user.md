---
title: Skype for Business Online でユーザーの会議 ID をリセットする
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6e12242c-55f7-4bf4-90d7-0f36c0326b8e
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Skype for Business Online でユーザーの会議 ID をリセットする手順を学び、会議を更新するためのリンクと移行ツールへのリンクを取得します。 '
ms.openlocfilehash: 34e165d92f4dc63eea8fc31c05612b6e20b64025
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23850063"
---
# <a name="reset-a-conference-id-for-a-user-in-skype-for-business-online"></a>Skype for Business Online でユーザーの会議 ID をリセットする

> [!NOTE]
> Microsoft Teams で会議 ID をリセットする方法の詳細については、「 [Microsoft Teams でユーザーの会議 ID をリセットする](/MicrosoftTeams/reset-a-conference-id-for-a-user-in-teams)」を参照してください。

動的な会議 ID は、発信者が会議にコールインするのに使用できるダイヤルイン番号と一緒に、会議出席依頼の下に含まれています。 ユーザーが電話番号をダイヤルするときに、発信者が会議に参加できるように、会議の自動応答は発信者にこの会議 ID の入力を求めます。
  
> [!NOTE]
> 会議プロバイダーが Microsoft の場合、ユーザーの会議 ID がデフォルトで「動的のみ」に設定されます。 残念ながら、Skype for Business 管理センターで会議 ID を変更できる機能、または Windows Powershell を使用して動的会議 ID を静的会議 ID に変更する機能は、現在サポートされていないため、ありません。 会議 ID は、電話会議が有効にされる Skype for Business ユーザーにのみ自動的に設定されます。 

## <a name="resetting-the-conference-id-for-a-user"></a>ユーザーの会議 ID をリセットする
   
1. **Skype for Business 管理センター**で、**[電話会議]** > **[ユーザー]** をクリックして、[操作] ウィンドウの下の**会議 ID** で **[リセット]** をクリックします。
    
2. [**会議 ID をリセットしますか?**] ウインドウで、 **[はい]** をクリックします。 会議 ID が自動的に生成されて、ユーザーに新しい会議 ID を含む電子メールが送信されます。 デフォルトで、電子メールがユーザーに送信されますが、この設定をオフにすることができます。
    
> [!NOTE]
> 会議 ID をリセットすると、新しい会議 ID を記載したメールがユーザーに送信されます。このメールはプライマリ メール アドレスに送信されます。ほとんどの場合は、Office 365 のメールボックスに送信されます。新しい会議 ID、既定のダイヤルイン電話番号、Skype for Business Meeting Update Tool を使って既存の会議を更新する方法がメールに記載されています。 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a>他に必要な情報はありますか?

- [操作] ウィンドウでユーザーのために [**電話会議情報をメールで送信**] をクリックすると、会議 ID とダイヤルイン電話番号など、会議に必要なすべての情報をメールに記載して、ユーザーに送信することができます。 PIN は送信されません。
    
- 会議 ID には 7 桁の情報が含まれます。Skype for Business 管理センターで、または Windows PowerShell を使用して、この長さを変更することはできません。
    
- 会議 ID をリセットすると、新しい会議 ID が [ **電話会議 ID**] に一覧表示されます。
    
- ユーザーが電話会議に使用する会議 ID は、[ **ユーザー**] ページでユーザーを選ぶと、[ **電話会議**] の [操作] ウィンドウの下に表示されます。
    
- 新しい会議 ID が作成された後、呼び出し元は古い会議 ID を使用できません。 新しい会議 ID が招待状に追加されたことを確認するには、既存の会議招待を再スケジュールするのにユーザーに通知する必要があります。 ユーザーは Skype for Business Meeting Tool を使って、既存の会議を更新できます。 Skype for Business Meeting Update Tool をダウンロード、インストール、実行する方法については、以下を参照してください。
    
  - [Skype for Business Meeting Update Tool と Lync Meeting Update Tool](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)
    
  - [Skype for Business Online、会議移行ツール (64 ビット)](https://go.microsoft.com/fwlink/?LinkID=626047)
    
  - [Skype for Business Online、会議移行ツール (32 ビット)](https://www.microsoft.com/en-us/download/details.aspx?id=54079)
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell を管理する方法を知る必要がありますか？

- Windows PowerShell で行うのは、ユーザーを管理し、ユーザーに何を許可して何を禁止するかを管理することです。Windows PowerShell を利用すると、Office 365 と Skype for Business Online の管理を 1 か所で行うことができるので、複数のタスクを担当する管理者の日常業務を単純化できます。Windows PowerShell の使用を開始するには、次のトピックを参照してください。
    
  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell には、ただ Office 365 管理センターを使用するだけではなく、速度、単純さ、生産性において多くの利点があります。次のトピックでこれらの利点について説明します。
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [クイック リファレンス: Windows PowerShell を使用した一般的な Lync Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>関連トピック

[電話会議の暗証番号 (PIN) をリセットする](reset-the-audio-conferencing-pin.md)
