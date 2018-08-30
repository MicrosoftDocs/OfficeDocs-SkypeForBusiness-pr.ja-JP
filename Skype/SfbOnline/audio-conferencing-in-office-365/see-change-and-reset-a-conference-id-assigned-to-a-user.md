---
title: Skype of businessオンラインのユーザーに割り当てられている会議 ID を参照、変更、リセットして下さい。
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 77d36233-2aab-4802-ba9c-e9a8885ea643
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
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
description: 'Skype of business オンライン のユーザーに会議 ID を割り当てる方法と、会議ID パラメーターのあるべき姿について学びます。 '
ms.openlocfilehash: 472f3b007a584979e029aade593c7b6c93ea1565
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/28/2018
ms.locfileid: "23252310"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-skype-for-business-online"></a>Skype of businessオンラインのユーザーに割り当てられている会議 ID を表示させリセットしてください。

> [!Note]
> マイクロソフト チーム内でのユーザー会議 Id の詳細については、 [マイクロソフト チーム 内のユーザーに割り当てられている会議 IDの表示とリセット](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams)を参照してください。

会議 ID は、Office 365 での音声会議用に設定し、Microsoft をオーディオ会議プロバイダーとしてを使用する場合に、Skype of business の ユーザーに自動的に割り当てられます。 割り当てられた会議 IDは、会議がスケジュールされている場合、会議出席依頼で送信されます。 ユーザーが計画する会議ごとに、固有の会議 ID が割り当てられます。

会議 ID は自動的に作成されてユーザーに割り当てられますが、ユーザーがこの ID を使用したくない場合や、特定の番号に設定したい場合、またはユーザーが会議 ID を覚えていなかったり、失くしてしまう場合もあります。 ** Skype of business 管理センター ** と Windows PowerShell を使用して、ユーザーの会議 ID を閲覧、変更、リセットすることができます。

ユーザーに会議 ID と既定の電話会議の電話番号が含む電子メールが送信されるか、または会議 ID をリセットすると、PINではない 会議 ID を含む別の電子メールが送信されます。 会議の開催者のPINをリセットするの詳細については、 [ここ](reset-a-conference-id-for-a-user.md)をクリックします。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="view-and-reset-conference-ids"></a>会議 Idの表示と リセット

### <a name="to-view-the-conference-id"></a>会議 ID を表示するには

![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Skype of business管理センターの使用**

会議 ID を表示し、ユーザーに送信することができます。

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。

2. **Office 365 管理センター** > **Skype of business**に移動します。

3.  **Skype of business管理センター**の> **オーディオ会議** > **ユーザー**で会議IDを必要とするユーザー を選択します。

4. アクション ページで、**会議 ID** を確認します。

    > [!TIP]
    > **ユーザー** ページで、ユーザーを選択した後に **電子メールを使用して会議情報を送信する** をクリックして、会議 ID とオーディオの電話番号を含む電子メールでユーザーにすべての会議の情報を送信できます。

**Windows PowerShellの使用**

ユーザーの会議 ID を表示するのにWindows PowerShell を使用できます。 これを行うには、次を実行します。

  ```
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"
  ```

    See [Get-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 ) to learn more about the cmdlet.


### <a name="to-reset-the-conference-id"></a>会議 ID をリセットするには

例えば忘れてしまったなどの場合のために、ユーザーの会議 ID をリセットできます。

![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Skype of business管理センターの使用**

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。

2. **Office 365 管理センター** > **Skype of business**に移動します。

3.  **Skype of business管理センター**の> **電話会議** > **ユーザー**、操作ウィンドウの 下の **会議 ID**で **リセット**をクリックします。

4. **会議IDをリセットしますか?** ウインドウで、 **はい** をクリックします。 会議 ID が自動的に生成されて、ユーザーに新しい会議 ID を含む電子メールが送信されます。

**Windows PowerShellの使用**

ユーザーの会議 ID をリセットするには、Windows PowerShell を使用します。 これを行う場合は、次を実行します。

  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ResetConferenceID 8271964
  ```

## <a name="what-else-should-you-know"></a>その他の情報は必要ですか？

   > [!IMPORTANT]
   >  新しい会議 ID が作成された後、あるいはリセット後は、呼び出し元は古い会議 ID を使用できません。 新しい会議 ID が招待状に追加されたことを確認するには、既存の会議招待を再スケジュールするのにユーザーに通知する必要があります。 ユーザーは、Skype of business会議移行ツールを使用して、既存の会議を更新します。 ツールをどのようにダウンロードし、インストールして実行するかについては、[Skype of businessおよびLync用会議移行ツール](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4),、[Skype of business オンライン、会議移行ツール(64-ビット)](https://go.microsoft.com/fwlink/?LinkID=626047)および [Skype of business オンライン、会議移行ツール(32-ビット)](https://www.microsoft.com/en-us/download/details.aspx?id=54079)を参照してください。

- cmdletの詳細については[Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) を参照してください。

- 会議 ID は、オーディオ会議ブリッジに設定された桁の長さを満たす必要があります。 会議 Id には、アルファベットまたは特殊文字を使うことはできません。数値のみが使用できます。

- オーディオ会議のすべてのユーザーの会議 ID は、既定では、7 桁になります。桁数を変更することはできません。


## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell を管理する方法を知る必要がありますか？

- Windows PowerShell で行うのは、ユーザーを管理し、ユーザーに何を許可して何を禁止するかを管理することです。Windows PowerShell を利用すると、Office 365 と Skype for Business Online の管理を 1 か所で行うことができるので、複数のタスクを担当する管理者の日常業務を単純化できます。Windows PowerShell の使用を開始するには、次のトピックを参照してください。

  - [Windows PowerShell と Skype of businessオンライン の紹介](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [Office 365 PowerShell を使用しなければならない理由](https://go.microsoft.com/fwlink/?LinkId=525041)

- Windows PowerShell には、ただ Office 365 管理センターを使用するだけではなく、速度、単純さ、生産性において多くの利点があります。次のトピックでこれらの利点について説明します。

  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [クイック リファレンス: Windows PowerShell を使用した一般的な Lync Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>関連トピック

[Office 365 での電話会議を使用または購入する](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

