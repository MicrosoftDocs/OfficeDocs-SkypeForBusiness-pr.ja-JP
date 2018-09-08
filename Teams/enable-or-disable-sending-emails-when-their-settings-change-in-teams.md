---
title: 有効にするか、マイクロソフトのチームでのオーディオ会議設定を変更すると、送信メールを無効にします。
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26ea19d3-e420-4fc1-baa3-2692d17e5e1d
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
description: '有効にするか、暗証番号 (pin) などの設定が変更されたときにユーザー、またはマイクロソフトのチームで既定の会議番号の変更に電子メールを送信することから Skype を無効にする方法を説明します。 '
ms.openlocfilehash: a59553f26ee39e042fa28d9e58e7f5ae2aae21be
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23892503"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-microsoft-teams"></a>有効にするか、マイクロソフトのチームでのオーディオ会議設定を変更すると、送信メールを無効にします。

ユーザーは、電話会議が有効になっているときに自動的に電子メールで通知されます。 場合があります、ただし、マイクロソフトのチームのユーザーに送信される電子メールの数を減らしたいとします。 このような場合は、電子メールの送信を無効にできます。
  
オーディオ会議の電子メールをユーザーが有効になっているか、オーディオ会議は、会議 ID と既定の会議の電話番号の変更と、PIN をリセットすると無効にすると、電子メールを含む、ユーザーに送信されません送信メールを無効にした場合.
  
電話会議が有効になっているときに、ユーザーに送信されるメールの例を以下に示します。
  
![オーディオ会議の電子メール](media/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a>メール ユーザーに送信するのでしょうか。

- 送信される、組織内のユーザーを有効にした後には、オーディオ会議のいくつかの電子メールがあります。
    
  - **電話会議** のライセンスがユーザーに割り当てられた場合。
    
  - リセットすると手動で電話会議のユーザーの暗証番号 (pin) です。
    
  - ユーザーの会議 ID を手動でリセットした場合。
    
  - **電話会議**のライセンスは、それらから削除されます。
    
  - オーディオ会議プロバイダーのユーザーの変更されたとき Microsoft から別のプロバイダーまたは **[なし]** にします。
    
  - マイクロソフトにユーザーの電話会議プロバイダーが変更されたとき。


## <a name="enable-or-disable-email-from-being-sent-to-users"></a>有効にするか、ユーザーに送信される電子メールを無効にします。

有効にするか、ユーザーに送信される電子メールを無効にするのには、マイクロソフトのチームまたは Windows PowerShell を使用できます。

![チーム ・ ロゴ ・ 30x30.png](media/teams-logo-30x30.png) **、マイクロソフトのチームとビジネス管理センターの Skype を使用します。**
1. 左側のナビゲーションでは、**会議**に移動 > **会議ブリッジ**です。 

2. **会議ブリッジ**のページの上部には、**ブリッジの設定**をクリックします。 

3. **ブリッジの設定**ウィンドウで、有効または、**ユーザーのダイヤルインの設定を変更する場合に e メールを自動的に送信**を無効にします。

4. [ **保存**] をクリックします。

  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

**The conference ID and default dial-in conferencing phone number is included on the meeting invite but not the PIN.**
  
詳細については[マイクロソフト チームの PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)を参照してください。

    
## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell の詳細情報

Windows PowerShell は、ユーザーと、ユーザーに許可されていることと許可されていないことを管理するためにあるということです。Windows PowerShell があれば、一元管理を使用して Office 365 を管理し、複数のタスクを抱えているときに、日常の仕事を簡素化することができます。Windows PowerShell を開始するには、これらのトピックを参照してください。
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Windows PowerShell の詳細については、[マイクロソフト チームの PowerShell の参照](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)の詳細についてを参照してください。
    
  
## <a name="related-topics"></a>関連トピック

[オーディオ会議設定を変更するときにユーザーに送信される電子メール](emails-sent-to-users-when-their-settings-change-in-teams.md)

[ユーザーに電話会議情報が含まれたメールを送信する](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)


