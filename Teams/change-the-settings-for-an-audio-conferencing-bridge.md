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
description: 電話会議ブリッジの設定を変更します。これには、エントリの入力や終了の通知、名前または電話番号、トーンの再生、発信者に名前を記録するためのプロンプトも含まれます。
ms.openlocfilehash: aaff3518675e1db56340f9dc1568b994cf2ed6e6
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/03/2020
ms.locfileid: "43139086"
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a>電話会議ブリッジの設定を変更する

Office 365 で電話会議を設定している場合、電話会議ブリッジと呼ばれるものからユーザーの電話番号を受信します。 電話会議ブリッジには 1 つまたは複数の電話番号を含めることができます。 この電話番号は、発信者が会議にダイヤルインするときに使用されます。 電話番号は、Skype for Business または Microsoft Teams の会議出席依頼の下部にあります。
  
電話会議ブリッジは着信に応答し、会議の自動応答を使用して音声案内で発信者を案内し、それから設定に応じて、通知メッセージを再生し、発信者に自分の名前を記録することと、PIN の設定を管理することを求めます。 PIN は 会議の開催者に付与され、Skype for Business または Microsoft Teams のアプリを使用していないときに会議を開始できます。

  > [!IMPORTANT]
  > PIN が必要になるのは、Skype for Business または Microsoft Teams のアプリのユーザーがまだ会議を開始していないときの、会議の開催者のみです。 全員が会議にダイヤルインすると、会議の開催者が会議を開始するために PIN が必要になります。 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) Microsoft Teams 管理センターの使用

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


## <a name="an-icon-showing-the-skype-for-business-logo--using-the-skype-for-business-admin-center"></a>![Skype for Business ロゴを示すアイコン](media/sfb-logo-30x30.png)  Skype for Business 管理センターの使用

 **発信者が会議に参加するときの会議エクスペリエンスを設定する**
    
1. **Skype for Business 管理センター**の左側のナビゲーション ウィンドウで、[**電話会議**]  >  [**Microsoft ブリッジ設定**] の順に移動します。
    
2. [**Microsoft ブリッジ設定**] ページの [**会議に参加**] から次を選択します。
    
   - [**会議の開始と終了の通知を有効にする**] これは既定で選択されています。 このチェック ボックスの選択を外すと、誰かが入室したり退出したりしたときに、既に参加済みのユーザーは通知を受け取りません。
    
   - [**会議の開始と終了の通知を有効にする**] を選択すると、[**開始または終了のお知らせの種類**] リストから次のオプションを選択できます。
    
   - [**名前または電話番号**] ユーザーが会議にダイヤルインすると、ユーザーの参加時に参加者の電話番号が再生されます。
    
   - [**トーン**] ユーザーが会議にダイヤルインすると、ユーザーの参加時にオーディオ トーンが再生されます。
  
   - [**発信者に会議に参加する前に自分の名前を記録するように要求する**] これは既定で選択されています。 チェック ボックスから選択を外すと、発信者が会議に参加する前に自分の名前を記録するよう求められることはありません。
    
3. 変更を完了したら、[**保存**] をクリックします。
    
**会議の PIN の長さを設定する**
  
1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. **Microsoft 365 管理センター** > **Skype for Business** に移動します。
    
3. **Skype for Business 管理センター**の左側のナビゲーション ウィンドウで、[**電話会議**]  >  [**Microsoft ブリッジ設定**] の順に移動します。
    
4. [**Microsoft ブリッジの設定**] ウィンドウの [**セキュリティ**] で、[**PIN の長さ**] リストに PIN の桁数を入力し、[**保存**] をクリックします。
    
    > [!IMPORTANT]
    > PIN は 4 桁から 12 桁の間の値にする必要があります。 
  
**ユーザーにメールを送信するかどうかを選択する**
  
1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. **Microsoft 365 管理センター** > **Skype for Business** に移動します。
    
3. **Skype for Business 管理センター**の左側のナビゲーション ウィンドウで、[**電話会議**]  >  [**Microsoft ブリッジ設定**] の順に移動します。
    
4. [**Microsoft ブリッジ設定**] ページで [**ダイヤルイン情報を変更したらユーザーに自動的に電子メールを送信する**] を選択または選択解除して [**保存**] をクリックします。
    
    詳細については、「[Microsoft Teams で電話会議の設定を変更したときにユーザーに送信されるメール](emails-sent-to-users-when-their-settings-change-in-teams.md)」または「[Skype for Business Online で設定を変更したときにユーザーに送信されるメール](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change)」を参照してください。
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell での管理方法について

- 時間を節約したり、このプロセスを自動化したりするには、[Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617686) コマンドレットを使用できます。
    
- Windows PowerShell で行うのは、ユーザーを管理し、ユーザーに何を許可して何を禁止するかを管理することです。Windows PowerShell を利用すると、Office 365 の管理を 1 か所で行うことができるので、複数のタスクを担当する管理者の日常業務を単純化できます。Windows PowerShell の使用を開始するには、次のトピックを参照してください。
    
  - [Office 365 PowerShell を使用する必要がある理由](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell には、Microsoft 365 管理センターを使用する場合にのみ、速度、シンプルさ、生産性を向上させるための多くの利点があります。たとえば、複数のユーザーに対して同時に設定を変更する場合です。次のトピックで、これらの利点について説明します。 
    
  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Skype for Business Online 用の Windows PowerShell モジュールがあれば、Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成できます。このモジュールは、64 ビット版のコンピューターでのみサポートされており、「[Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688)」の Microsoft ダウンロード センターからダウンロードできます。
  
## <a name="related-topics"></a>関連トピック

[Microsoft Teams の電話会議を設定する](set-up-audio-conferencing-in-teams.md)

[Skype for Business Online 用電話会議を設定する](/skypeforbusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)
