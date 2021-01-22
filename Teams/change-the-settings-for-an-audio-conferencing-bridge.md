---
title: 電話会議ブリッジの設定を変更する
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 783fad3f-b77c-422b-b91f-7c8b0af324fb
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- ms.teamsadmincenter.audioconferencing.bridgesettings
- seo-marvel-mar2020
description: 入退出通知、名前または電話番号の再生、トーン、発信者に名前の録音を促すメッセージなど、電話会議ブリッジの設定を変更します。
ms.openlocfilehash: 9694ac0cddecc5b00c0df133c5c494e4b5bc0d17
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918709"
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a>電話会議ブリッジの設定を変更する

Microsoft 365 または Office 365 で電話会議をセットアップすると、電話会議ブリッジと呼ばれるものからユーザーの電話番号を受け取ります。 電話会議ブリッジには 1 つまたは複数の電話番号を含めることができます。 この電話番号は、発信者が会議にダイヤルインするときに使用されます。 電話番号は、Skype for Business または Microsoft Teams の会議出席依頼の下部にあります。
  
電話会議ブリッジは着信に応答し、会議の自動応答を使用して音声案内で発信者を案内し、それから設定に応じて、通知メッセージを再生し、発信者に自分の名前を記録することと、PIN の設定を管理することを求めます。 PIN は 会議の開催者に付与され、Skype for Business または Microsoft Teams のアプリを使用していないときに会議を開始できます。

  > [!IMPORTANT]
  > PIN が必要になるのは、Skype for Business または Microsoft Teams のアプリのユーザーがまだ会議を開始していないときの、会議の開催者のみです。 全員が会議にダイヤルインすると、会議の開催者が会議を開始するために PIN が必要になります。 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![Microsoft Teams のロゴが表示されたアイコン](media/teams-logo-30x30.png) Microsoft Teams 管理センターの使用

1. 左側のナビゲーションで、[**会議**]  >  [**会議ブリッジ**] に移動します。 

2. [**会議ブリッジ**] ページの最上部で、[**ブリッジの設定**] をクリックします。 

3. [**ブリッジ設定**] ウィンドウで、 
   - [**会議の開始と終了の通知**] を選択します。この選択を外すと、既に参加済みのユーザーは、誰かが入ってきたり退出したりしたときに通知を受け取りません。
    
     [**会議の開始と終了通知**] を有効にすると、以下のオプションを選択できます。
    
   - [**名前または電話番号**] ユーザーが会議にダイヤルインすると、ユーザーの参加時に参加者の電話番号が再生されます。
    
   - [**トーン**] ユーザーが会議にダイヤルインすると、ユーザーの参加時にオーディオ トーンが再生されます。
      
   - [**発信者に会議に参加する前に自分の名前を記録するように要求する**] これをオフにすると、発信者は会議に参加する前に名前を録音するように求められません。

4. 電話会議の PIN の長さを設定するには、[**PIN の長さ**] リストの PIN に希望の桁数を選択します。

5. ユーザーに電子メールを送信するかどうか指定するには、[**電話会議設定を変更した場合ユーザーに自動的に電子メールを送信する**] を有効または無効にします。
    詳細については、「[Microsoft Teams で電話会議の設定を変更したときにユーザーに送信されるメール](emails-sent-to-users-when-their-settings-change-in-teams.md)」または「[Skype for Business Online で設定を変更したときにユーザーに送信されるメール](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change)」を参照してください。
 
6. [**保存**] をクリックします。 

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell での管理方法について

- 時間を節約したり、このプロセスを自動化したりするには、[Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617686) コマンドレットを使用できます。
    
- Windows PowerShellは、ユーザーの管理と、ユーザーに許可する操作と許可しない操作の管理に使います。 Windows PowerShell では、単一の管理ポイントを使用して Microsoft 365 または Office 365 を管理できます。複数のタスクを実行する必要がある場合に毎日の作業を簡略化できます。 Windows PowerShell の使用を開始するには、次のトピックを参照してください。
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Microsoft 365 または Office 365 を他のユーザーとWindows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShellは、多くのユーザーに対して一度に設定変更を行う場合など、Microsoft 365 管理センターのみを使用する場合と同様に、速度、シンプルさ、生産性に多くの利点があります。 次のトピックで、これらの利点を説明します。 
    
  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Skype for Business Online 用の Windows PowerShell モジュールがあれば、Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成できます。このモジュールは、64 ビット版のコンピューターでのみサポートされており、「[Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688)」の Microsoft ダウンロード センターからダウンロードできます。
  
## <a name="related-topics"></a>関連トピック

[Microsoft Teams の電話会議を設定する](set-up-audio-conferencing-in-teams.md)

[Skype for Business Online 用電話会議を設定する](/skypeforbusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)
