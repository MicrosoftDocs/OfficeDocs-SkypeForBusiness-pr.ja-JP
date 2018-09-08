---
title: 参照してください、変更、およびマイクロソフトのチーム内のユーザーに割り当てられている会議 ID をリセットします。
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 77d36233-2aab-4802-ba9c-e9a8885ea643
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'についてはマイクロソフトのチーム内のユーザーに会議 ID を割り当てる方法と、どのような会議 ID のパラメーターにする必要があります。 '
ms.openlocfilehash: d0ee177fbbe286cc68c45e1c41f391b52c44291e
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/08/2018
ms.locfileid: "23892034"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-microsoft-teams"></a>表示し、マイクロソフトのチーム内のユーザーに割り当てられている会議 ID をリセットします。

会議 ID が自動的に割り当てられているマイクロソフトのチームのユーザーに Office 365 での音声会議用に設定し、Microsoft を使用して、オーディオ会議プロバイダーとして。 会議 ID が割り当てられているは、会議がスケジュールされているとき、会議出席依頼で送信されます。 ユーザーをスケジュールする会議ごとに固有の会議 ID が割り当てられますを取得 
  
会議 ID が自動的に作成され、ユーザーに割り当てられているが場合がありますこの 1 つを使用するユーザーが望まないし、特定の数に設定するとき、またはユーザーが覚えられないか、会議 ID が失われている場合 マイクロソフトのチーム管理センターまたは Windows PowerShell を使用するには表示、変更、および、会議 ID をリセットするには
  
ユーザーに会議 ID と既定の電話会議の電話番号が含む電子メールが送信されるか、または会議 ID をリセットすると、PINではない 会議 ID を含む別の電子メールが送信されます。 会議の開催者のPINをリセットするの詳細については、 [ここ](reset-a-conference-id-for-a-user-in-teams.md)をクリックします。 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="view-and-reset-conference-ids"></a>会議 Idの表示と リセット

### <a name="to-view-the-conference-id"></a>会議 ID を表示するのには

![チーム ・ ロゴ ・ 30x30.png](media/teams-logo-30x30.png) **、マイクロソフトのチームとビジネス管理センターの Skype を使用します。**

1. 左側のナビゲーションでは、**ユーザー**] をクリックしてで使用可能なユーザーの一覧からユーザーを選択します。

2. ページの上部で、[**編集**] をクリックします。

3. [**オーディオ会議**、**会議 ID**の下を確認します。

    > [!TIP]
    > **電子メールで会議の情報を送信する**リンクをクリックして、会議 ID とオーディオの電話番号を含む電子メールでユーザーにすべての会議の情報を送信できます。
  
**The conference ID and default dial-in conferencing phone number is included on the meeting invite but not the PIN.**

詳細については[マイクロソフト チームの PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)を参照してください。
    
  
### <a name="to-reset-the-conference-id"></a>会議 ID をリセットするのには

例えば忘れてしまったなどの場合のために、ユーザーの会議 ID をリセットできます。
  
![チーム ・ ロゴ ・ 30x30.png](media/teams-logo-30x30.png) **、マイクロソフトのチームとビジネス管理センターの Skype を使用します。**

1. 左側のナビゲーションでは、**ユーザー**] をクリックしてで使用可能なユーザーの一覧からユーザーを選択します。

2. ページの上部で、[**編集**] をクリックします。

3. [**オーディオ会議**、**会議 ID のリセット**をクリックします。

4. **会議 ID のリセット**] ウィンドウで、[**リセット**] をクリックします。 A conference ID will be automatically created and an email sent to the user with the new conference ID.
  
**The conference ID and default dial-in conferencing phone number is included on the meeting invite but not the PIN.**

詳細については[マイクロソフト チームの PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)を参照してください。


## <a name="what-else-should-you-know"></a>その他の情報

   > [!IMPORTANT]
   >  新しい会議 ID が作成されるか、1 つは、リセット後、は、呼び出し元が古い会議 ID を使用できません。 The users can use Skype for Business Meeting Migration Tool to update their existing meetings. 
  
    
- 会議 ID は、オーディオ会議ブリッジに設定された桁の長さを満たす必要があります。 会議 Id には、アルファベットまたは特殊文字を使うことはできません。数値のみが使用できます。
    
- オーディオ会議のすべてのユーザーの会議 ID は、既定では、7 桁になります。桁数を変更することはできません。
    
    
## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell の詳細情報

Windows PowerShell は、ユーザーと、ユーザーに許可されていることと許可されていないことを管理するためにあるということです。Windows PowerShell があれば、一元管理を使用して Office 365 を管理し、複数のタスクを抱えているときに、日常の仕事を簡素化することができます。Windows PowerShell を開始するには、これらのトピックを参照してください。
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Windows PowerShell の詳細については、[マイクロソフト チームの PowerShell の参照](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)の詳細についてを参照してください。
    
## <a name="related-topics"></a>関連トピック

[Office 365 での電話会議を使用または購入する](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)

