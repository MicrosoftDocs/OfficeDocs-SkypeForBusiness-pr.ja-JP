---
title: 電話会議ブリッジの設定を変更する
ms.author: heidip
author: MicrosoftHeidi
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
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- ms.teamsadmincenter.audioconferencing.bridgesettings
- seo-marvel-mar2020
description: 電話会議ブリッジの設定を変更します。これには、入退室通知、再生名または電話番号、トーン、発信者に名前の記録を求めるメッセージが表示されます。
ms.openlocfilehash: d9853826d9a93c5794017185f561b9d6a6cd1ffb
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2022
ms.locfileid: "67641788"
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a>電話会議ブリッジの設定を変更する

Microsoft 365 またはOffice 365で電話会議を設定すると、電話会議ブリッジと呼ばれるものからユーザーの電話番号を受け取ります。 電話会議ブリッジには 1 つまたは複数の電話番号を含めることができます。 この電話番号は、発信者が会議にダイヤルインするときに使用されます。 電話番号は Teams 会議の招待の下部に含まれています。
  
電話会議ブリッジは着信に応答し、会議の自動応答を使用して音声案内で発信者を案内し、それから設定に応じて、通知メッセージを再生し、発信者に自分の名前を記録することと、PIN の設定を管理することを求めます。 PIN は、Microsoft Teams アプリを使用していないときに会議を開始できるように、会議の開催者に提供されます。

  > [!IMPORTANT]
  > PIN は、Teams アプリ ユーザーがまだ会議を開始していない場合にのみ、会議の開催者に必要です。 全員が会議にダイヤルインすると、会議の開催者が会議を開始するために PIN が必要になります。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

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
    詳細については、「 [Microsoft Teams で電話会議の設定が変更されたときにユーザーに自動的に送信される電子メール](emails-sent-to-users-when-their-settings-change-in-teams.md) 」を参照してください。

6. **[保存]** をクリックします。

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell での管理方法について

- 時間を節約したり、このプロセスを自動化したりするには、[Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingBridge) コマンドレットを使用できます。

- Windows PowerShell は、ユーザーと、ユーザーに許可されていることと許可されていないことを管理するためにあります。Windows PowerShell があれば、一元管理を使用して Microsoft 365 または Office 365 を管理し、複数のタスクを抱えているときに、日常の仕事を簡素化することができます。Windows PowerShell を開始するには、これらのトピックを参照してください。

  - [Office 365 PowerShell を使用する必要がある理由](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

  - [Windows PowerShell で Microsoft 365 または Office 365 を管理するための最善の方法](/previous-versions//dn568025(v=technet.10))

- Windows PowerShellには、多くのユーザーに対して一度に設定を変更する場合など、Microsoft 365 管理センターのみを使用するよりも、速度、シンプルさ、生産性に多くの利点があります。 次のトピックでこれらの利点について説明します。

  - [Microsoft Teams PowerShell の概要](teams-powershell-overview.md)

  - [Microsoft Teams PowerShell モジュールをインストールする](teams-powershell-install.md)
  
## <a name="related-topics"></a>関連項目

[Microsoft Teams の電話会議を設定する](set-up-audio-conferencing-in-teams.md)
