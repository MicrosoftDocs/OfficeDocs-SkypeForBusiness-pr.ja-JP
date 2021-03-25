---
title: Skype for Business Online でユーザーに割り当てられた会議 ID を表示、変更、リセットする
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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Skype of business オンライン のユーザーに会議 ID を割り当てる方法と、会議ID パラメーターのあるべき姿について学びます。 '
ms.openlocfilehash: 79c83999fdf9a9736dfe1ee425337edf938d3375
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51110013"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-skype-for-business-online"></a>Skype of businessオンラインのユーザーに割り当てられている会議 ID を表示させリセットしてください。

> [!Note]
> Microsoft Teams でのユーザー会議 ID の詳細については [、「Microsoft Teams](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams)でユーザーに割り当てられた会議 ID を表示およびリセットする」を参照してください。

会議 ID は、Microsoft 365 または Office 365 で電話会議用にセットアップされ、Microsoft を電話会議プロバイダーとして使用すると、自動的に Skype for Business ユーザーに割り当てられます。 割り当てられた会議 ID は、会議のスケジュール時に会議出席招待で送信されます。 ユーザーがスケジュール設定した各会議には、一意の会議通話 ID が割り当てられます。

会議 ID は自動的に作成され、ユーザーに割り当てられますが、ユーザーがこれを使いたくないときに特定の番号に設定したい場合や、ユーザーが会議 ID を思い出したり紛失したりできない場合があります。 Skype for **Business** 管理センターを使用して、Windows PowerShell ID の表示、変更、リセットを行えます。

ユーザーに会議 ID と既定の電話会議の電話番号が含む電子メールが送信されるか、または会議 ID をリセットすると、PINではない 会議 ID を含む別の電子メールが送信されます。 会議の開催者のPINをリセットするの詳細については、 [ここ](reset-a-conference-id-for-a-user.md)をクリックします。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="view-and-reset-conference-ids"></a>会議 Idの表示と リセット

### <a name="to-view-the-conference-id"></a>会議 ID を表示するには

![Skype for Business のロゴを表示したアイコン](../images/sfb-logo-30x30.png) **Skype for Business 管理センターの使用**

会議 ID を表示し、ユーザーに送信することができます。

1. 仕事用または学校用のアカウントでサインインします。

2. Skype for Business の管理> **に移動します**。

3. **Skype of business管理センター** の> **オーディオ会議** > **ユーザー** で会議IDを必要とするユーザー を選択します。

4. アクション ページで、**会議 ID** を確認します。

    > [!TIP]
    > [ユーザー] ページでユーザーを選択した後、[電話会議情報をメールで送信] リンクをクリックすると、会議ID と音声電話番号を含むメールで、すべての会議情報をユーザーに送信できます。

**Windows PowerShell を使用する**

ユーザーの会議 ID を表示するのにWindows PowerShell を使用できます。 これを行うには、次を実行します。

  ```powershell
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"
  ```

コマンドレット [の詳細については、Get-CsOnlineDialInConferencingUser](/powershell/module/skype/Get-CsOnlineDialInConferencingUser) を参照してください。


### <a name="to-reset-the-conference-id"></a>会議 ID をリセットするには

例えば忘れてしまったなどの場合のために、ユーザーの会議 ID をリセットできます。

![Skype for Business のロゴを表示したアイコン](../images/sfb-logo-30x30.png) **Skype for Business 管理センターの使用**

1. 仕事用または学校用のアカウントでサインインします。

2. Skype for Business の管理センター> **に移動します**。

3. Skype **for Business 管理センター** の電話会議ユーザーの [電話会議 ID] の [操作] ウィンドウで、[リセット] >    >  をクリック **します**。 

4. [会議 **ID のリセット] ウィンドウで、[** はい] を **クリックします**。 A conference ID will be automatically created and an email sent to the user with the new conference ID.

**Windows PowerShell を使用する**

ユーザーの会議 ID をリセットするには、Windows PowerShell を使用します。 これを行う場合は、次を実行します。

  ```PowerShell
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble" -ResetConferenceID
  ```

## <a name="what-else-should-you-know"></a>その他の情報

   > [!IMPORTANT]
   >  新しい会議 ID が作成またはリセットされると、古い会議 ID を発信者が使用することはできません。 既存の会議の出席依頼のスケジュールを変更して、新しい会議 ID を出席依頼に追加するように、ユーザーに通知してください。 ユーザーは Skype for Business 会議移行ツールを使用して、既存の会議を更新できます。 このツールをダウンロード、インストール、実行する方法については [、「Skype for Business](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)および Lync の会議更新ツール、Skype for Business Online、会議移行ツール [(64](https://go.microsoft.com/fwlink/?LinkID=626047)ビット)、Skype for Business Online、会議移行ツール  [(32 ビット)」](https://www.microsoft.com/download/details.aspx?id=54079)を参照してください。

- コマンドレット [の詳細については、「Set-CsOnlineDialInConferencingUser」](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) を参照してください。

- 会議 ID は、オーディオ会議ブリッジに設定された桁の長さを満たす必要があります。 会議 Id には、アルファベットまたは特殊文字を使うことはできません。数値のみが使用できます。

- すべての電話会議ユーザーの会議 ID は既定で 9 桁の数字で、数字の数は変更できません。


## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell での管理方法について

- Windows PowerShell で行うのは、ユーザーを管理し、ユーザーに何を許可して何を禁止するかを管理することです。 Windows PowerShell を使用すると、単一の管理ポイントを使用して Microsoft 365 または Office 365 と Skype for Business Online を管理できます。複数のタスクを実行する必要がある場合に毎日の作業を簡略化できます。 Windows PowerShell の使用を開始するには、次のトピックを参照してください。

  - [Windows PowerShell と Skype for Business Online の概要](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [Microsoft 365 または Office 365 PowerShell を使用する必要がある理由](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- Windows PowerShellは、多くのユーザーに対して同時に設定変更を行う場合など、Microsoft 365 管理センターを使用する場合に限って、速度、シンプルさ、生産性の点で多くの利点があります。 次のトピックでこれらの利点について説明します。

  - [Microsoft 365 または Office 365 を管理するための最適Windows PowerShell](/previous-versions//dn568025(v=technet.10))

  - [Windows PowerShell による Skype for Business Online の管理](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

## <a name="related-topics"></a>関連項目

[Microsoft 365 または Office 365 で電話会議を試用または購入する](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)