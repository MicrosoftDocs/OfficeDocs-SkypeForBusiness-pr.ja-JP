---
title: 参照してください、変更、およびオンライン ビジネスの Skype のユーザーに割り当てられている会議 ID をリセットします。
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
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Skype of business オンライン のユーザーに会議 ID を割り当てる方法と、会議ID パラメーターのあるべき姿について学びます。 '
ms.openlocfilehash: 7996cc91bd9461f733f82da3eb01eeac7109604a
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23883417"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-skype-for-business-online"></a>Skype of businessオンラインのユーザーに割り当てられている会議 ID を表示させリセットしてください。

> [!Note]
> マイクロソフト チーム内でのユーザー会議 Id の詳細については、 [マイクロソフト チーム 内のユーザーに割り当てられている会議 IDの表示とリセット](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams)を参照してください。

会議 ID は、Office 365 での音声会議用に設定し、Microsoft をオーディオ会議プロバイダーとしてを使用する場合に、Skype of business の ユーザーに自動的に割り当てられます。 会議 ID が割り当てられているは、会議がスケジュールされているとき、会議出席依頼で送信されます。 ユーザーをスケジュールする会議ごとに固有の会議 ID が割り当てられますを取得

会議 ID が自動的に作成され、ユーザーに割り当てられているが場合がありますこの 1 つを使用するユーザーが望まないし、特定の数に設定するとき、またはユーザーが覚えられないか、会議 ID が失われている場合 **Skype**ビジネス管理センターは、Windows PowerShell を使用するには表示、変更、および、会議 ID をリセットするには

ユーザーに会議 ID と既定の電話会議の電話番号が含む電子メールが送信されるか、または会議 ID をリセットすると、PINではない 会議 ID を含む別の電子メールが送信されます。 会議の開催者のPINをリセットするの詳細については、 [ここ](reset-a-conference-id-for-a-user.md)をクリックします。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="view-and-reset-conference-ids"></a>会議 Idの表示と リセット

### <a name="to-view-the-conference-id"></a>会議 ID を表示するのには

![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Skype for Business の管理センターを使用する**

会議 ID を表示し、ユーザーに送信することができます。

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。

2. ** [Office 365 管理センター] ** > ** [Skype for Business]** に移動します。

3. **Skype of business管理センター**の> **オーディオ会議** > **ユーザー**で会議IDを必要とするユーザー を選択します。

4. アクション ページで、**会議 ID** を確認します。

    > [!TIP]
    > [**ユーザー** ] ページで、ユーザーを選択した後に**電子メールを使用して会議情報を送信する**リンクをクリックして、会議 ID とオーディオの電話番号を含む電子メールでユーザーにすべての会議の情報を送信できます。

**The conference ID and default dial-in conferencing phone number is included on the meeting invite but not the PIN.**

ユーザーの会議 ID を表示するのにWindows PowerShell を使用できます。 これを行うには、次のコマンドを実行します。

  ```
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"
  ```

    See [Get-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 ) to learn more about the cmdlet.


### <a name="to-reset-the-conference-id"></a>会議 ID をリセットするのには

例えば忘れてしまったなどの場合のために、ユーザーの会議 ID をリセットできます。

![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Skype for Business の管理センターを使用する**

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。

2. ** [Office 365 管理センター] ** > ** [Skype for Business]** に移動します。

3. **ビジネス管理センターの Skype**の> **電話会議** > **ユーザー**、操作ウィンドウの [**会議 ID**に**リセット**] をクリックします。

4. A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled. A conference ID will be automatically created and an email sent to the user with the new conference ID.

**The conference ID and default dial-in conferencing phone number is included on the meeting invite but not the PIN.**

ユーザーの会議 ID をリセットするには、Windows PowerShell を使用します。 これを行う場合は、次を実行します。

  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ResetConferenceID 8271964
  ```

## <a name="what-else-should-you-know"></a>その他の情報

   > [!IMPORTANT]
   >  新しい会議 ID が作成されるか、1 つは、リセット後、は、呼び出し元が古い会議 ID を使用できません。 The users can use Skype for Business Meeting Migration Tool to update their existing meetings. To see how to download, install and run the Lync Meeting Update Tool, see:> Meeting Update Tool for Skype for Business and LyncSkype for Business Online, Meeting Migration Tool (64-bit)Skype for Business Online, Meeting Migration Tool (32-bit) ダウンロード、インストール、およびツールを実行する方法を参照してください:[ビジネスと Lync の Skype の会議の更新ツール](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)、 [Skype](https://go.microsoft.com/fwlink/?LinkID=626047)、および[Skype](https://www.microsoft.com/en-us/download/details.aspx?id=54079)です。

- After a new conference ID is created, the old conference ID can't be used by callers. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. The users can use Skype for Business Meeting Migration Tool to update their existing meetings. To see how to download, install and run the Lync Meeting Update Tool, see:> Meeting Update Tool for Skype for Business and LyncSkype for Business Online, Meeting Migration Tool (64-bit)Skype for Business Online, Meeting Migration Tool (32-bit)

- 会議 ID は、オーディオ会議ブリッジに設定された桁の長さを満たす必要があります。 会議 Id には、アルファベットまたは特殊文字を使うことはできません。数値のみが使用できます。

- オーディオ会議のすべてのユーザーの会議 ID は、既定では、7 桁になります。桁数を変更することはできません。


## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Go to the Office 365 admin centerSkype for Business.

- Windows PowerShell で行うのは、ユーザーを管理し、ユーザーに何を許可して何を禁止するかを管理することです。Windows PowerShell を利用すると、Office 365 と Skype for Business Online の管理を 1 か所で行うことができるので、複数のタスクを担当する管理者の日常業務を単純化できます。Windows PowerShell の使用を開始するには、次のトピックを参照してください。

  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525041)

- Windows PowerShell には、ただ Office 365 管理センターを使用するだけではなく、速度、単純さ、生産性において多くの利点があります。次のトピックでこれらの利点について説明します。

  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [クイック リファレンス: Windows PowerShell を使用した一般的な Lync Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>See also

[Office 365 での電話会議を使用または購入する](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

