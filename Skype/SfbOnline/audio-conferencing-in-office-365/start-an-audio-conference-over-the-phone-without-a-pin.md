---
title: Skype for Business Online で PIN を使用せずに電話で電話会議を開始する
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d5b1f775-d7ed-4d30-853a-1d49f81e8fde
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
f1keywords: None
ms.custom:
- Audio Conferencing
description: '匿名の発信者による Skype for Business 管理センターからの会議への参加や PowerShell スクリプトの使用を有効または無効にする方法を説明します。 '
ms.openlocfilehash: af62ed29ed2bbe835ab811651152b231a85caaf8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34302772"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-skype-for-business-online"></a>Skype for Business Online で PIN を使用せずに電話で電話会議を開始する

> [!Note]
> Microsoft Teams で PIN を使用せずに電話会議を開始する場合の詳細については、「[Microsoft Teams で PIN を使用せずに 電話で電話会議を開始する](/MicrosoftTeams/start-an-audio-conference-over-the-phone-without-a-pin-in-teams)」をご覧ください。

会議にダイヤルインしても、Skype for Business 会議の開催者が会議を開始していないために、音楽を聞く会議のロビーで保留になっているユーザーにとっては不快な場合があります。 
  
会議の開催者が会議にコールインする場合、既定では、会議を開始するために PIN が必要になります。 すべてのユーザーが会議にダイヤルインできるように設定することができます。また、会議を開始するために PIN の入力を求められることはありません。 Skype for Business 管理センターを使用すると、この設定を 1 人のユーザーに対して有効または無効にすることができます。
  
他のユーザーが Skype for Business アプリから会議を開始した場合、会議の開催者に PIN は必要ありません。 PIN が必要であるのは、会議の開催者が電話で自分の会議に参加する場合のみです。 会議の PIN は、電話**会議**ライセンスが割り当てられており、電話会議用に有効になっている場合に、音声ユーザーに送信されます。 「電話会議の[設定が変更されたときにユーザーに自動的に送信される](emails-sent-to-users-when-their-settings-change.md)[電話会議情報とメールをユーザーに送信](send-an-email-to-a-user-with-their-dial-in-information.md)する」を参照してください。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a>匿名の発信者の会議への参加を有効または無効にする
    
1. **Skype for business 管理センター**の左側のナビゲーションで、[**電話会議** > **ユーザー**] に移動します。 
    
2. リストでユーザーを選び、操作ウィンドウで [**編集**] をクリックします。 
    
3. ユーザーのプロパティページの [**会議オプション**] で、[**認証されていない発信者が会議の最初のユーザーになることを許可する] をオンまたはオフにします。満たされていない場合は、認証されたユーザーが参加するまでロビーで待機**します。
    
4. [**保存**] をクリックします。 


    
 **Windows Powershell を使用する**
  
- 次のコマンドを実行します。 
    
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true | $false
  ```

## <a name="what-else-should-you-know"></a>その他の情報

- PIN をリセットする場合は、「[電話会議の pin をリセット](reset-the-audio-conferencing-pin.md)する」を参照してください。
    
- 匿名アクセスが許可されている場合、または会議の開始に PIN が必要ではない場合は、次の操作を行います。
    
  - 会議が開始されていない (会議にまだ参加していない) 場合: 発信者が開催者であるかどうかを確認するメッセージが表示されます。「はい」というメッセージが表示されると、PIN の入力が求められます。 PIN を入力すると、会議が開始され、ユーザーが会議に参加します。
    
  - 会議が既に始まっている場合 (他のユーザーが既に会議に参加している場合): 発信者は開催者であるかどうかを確認するメッセージは表示されず、PIN の入力を求められることはありません。会議が既に始まっていて、発信者が会議に参加します。
    
- 匿名アクセスが許可されている場合、または会議の開始に PIN が必要な場合は無効になります。
    
  - 会議が開始されていない (会議にまだ参加していない) 場合: 発信者が開催者であるかどうかを確認するメッセージは表示されません。 PIN の入力を求められることはありません。 開催者の設定がオフになっているため、会議が始まり、匿名の発信者が会議に参加します。
    
  - 会議が既に開始されている場合 (他のユーザーが既に会議に参加している場合): 発信者であるかどうかを確認するメッセージは表示されません。会議は既に始まっていて、発信者はその会議に参加します。
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell での管理方法について

- 時間を節約したり、複数のユーザーに対してこの動作を自動化したりするには、[Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) コマンドレットを使用できます。
    
- Windows PowerShell の場合、Skype for Business Online はユーザーの管理と、ユーザーが許可されている操作や許可されていない操作の管理に使います。Windows PowerShell により、単一の管理ポイントを使って Office 365 を管理でき、複数の作業を実行する必要があるときに日常業務を合理化できます。Windows PowerShell を使い始めるには、次のトピックを参照してください。
    
  - [Office 365 PowerShell を使用する必要がある理由](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- 多くのユーザーの設定を同時に変更するときなどは、Office 365 管理センターのみを使用するよりも、Windows PowerShell の方に、速度、わかりやすさ、生産性の点で多くのメリットがあります。 
    
  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Skype for Business Online 用の Windows PowerShell モジュールがあれば、Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成できます。このモジュールは、64 ビット版のコンピューターでのみサポートされており、「[Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688)」の Microsoft ダウンロード センターからダウンロードできます。
  
## <a name="related-topics"></a>関連項目

[Office 365 での電話会議を試用または購入する](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
