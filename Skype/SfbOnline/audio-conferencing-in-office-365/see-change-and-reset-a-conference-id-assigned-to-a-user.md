---
title: Skype for Business Online でユーザーに割り当てられている会議 ID を表示、変更、リセットする
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
ms.openlocfilehash: f12982298903485d93582fae3a4f39aaed49170c
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237053"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-skype-for-business-online"></a>Skype of businessオンラインのユーザーに割り当てられている会議 ID を表示させリセットしてください。

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> Microsoft Teams でのユーザー会議 ID の詳細については、「Microsoft Teams でユーザーに割り当てられている会議 ID を表示およびリセットする」[を参照してください](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams)。

Microsoft 365 または Office 365 で電話会議用に設定され、Microsoft を電話会議プロバイダーとして使用すると、Skype for Business ユーザーに会議 ID が自動的に割り当てられます。 割り当てられた会議 ID は、会議がスケジュールされているときに会議出席招待で送信されます。 ユーザーがスケジュール設定した各会議には、一意の会議通話 ID が割り当てられます。

会議 ID は自動的に作成され、ユーザーに割り当てられますが、ユーザーはこの ID を使用したくない場合や、特定の数に設定したり、ユーザーが会議 ID を記憶したり失われたりする場合があります。 管理者センターと Skype for Business **を** 使用してWindows PowerShell ID の表示、変更、リセットを行えます。

ユーザーに会議 ID と既定の電話会議の電話番号が含む電子メールが送信されるか、または会議 ID をリセットすると、PINではない 会議 ID を含む別の電子メールが送信されます。 会議の開催者のPINをリセットするの詳細については、 [ここ](reset-a-conference-id-for-a-user.md)をクリックします。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="view-and-reset-conference-ids"></a>会議 Idの表示と リセット

### <a name="to-view-the-conference-id"></a>会議 ID を表示するには

![Skype for Business のロゴを表示したアイコン](../images/sfb-logo-30x30.png) **Skype for Business 管理センターの使用**

会議 ID を表示し、ユーザーに送信することができます。

1. 仕事用または学校用のアカウントでサインインします。

2. [管理センター] に移動 **> Skype for Business。**

3. **Skype of business管理センター** の> **オーディオ会議** > **ユーザー** で会議IDを必要とするユーザー を選択します。

4. アクション ページで、**会議 ID** を確認します。

    > [!TIP]
    > [ユーザー] ページでユーザーを選択した後、[会議情報を電子メールで送信する] リンクをクリックすると、会議ID と音声電話番号を含むメールですべての会議情報をユーザーに **送信** できます。

**Windows PowerShell を使用する**

ユーザーの会議 ID を表示するのにWindows PowerShell を使用できます。 これを行うには、次のコマンドを実行します。

  ```powershell
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"
  ```

コマンドレット [の詳細については、「Get-CsOnlineDialInConferencingUser」](/powershell/module/skype/Get-CsOnlineDialInConferencingUser) を参照してください。


### <a name="to-reset-the-conference-id"></a>会議 ID をリセットするには

例えば忘れてしまったなどの場合のために、ユーザーの会議 ID をリセットできます。

![Skype for Business のロゴを表示したアイコン](../images/sfb-logo-30x30.png) **Skype for Business 管理センターの使用**

1. 仕事用または学校用のアカウントでサインインします。

2. [管理センター] に移動 **> Skype for Business。**

3. 管理センター **Skype for Business 電話** 会議ユーザー ] の [会議 ID] の [アクション] ウィンドウで、[リセット] >    >  を **クリックします**。 

4. [会議 **ID のリセット] ウィンドウで、[** はい] を **クリックします**。 A conference ID will be automatically created and an email sent to the user with the new conference ID.

**Windows PowerShell を使用する**

ユーザーの会議 ID をリセットするには、Windows PowerShell を使用します。 これを行う場合は、次を実行します。

  ```PowerShell
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble" -ResetConferenceID
  ```

## <a name="what-else-should-you-know"></a>その他の情報

   > [!IMPORTANT]
   >  新しい会議 ID が作成された後、または 1 つがリセットされた後、古い会議 ID を呼び出し元が使用することはできません。 既存の会議の出席依頼のスケジュールを変更して、新しい会議 ID を出席依頼に追加するように、ユーザーに通知してください。 ユーザーは、新しい会議Skype for Businessを使用して、既存の会議を更新できます。 ツールをダウンロード、インストール、実行する方法については[、「Skype for Business](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)および Lync の会議更新ツール」、Skype for Business Online、会議移行ツール[(64 ビット)、](https://go.microsoft.com/fwlink/?LinkID=626047)および Skype for Business Online、会議移行ツール[(32](https://www.microsoft.com/download/details.aspx?id=54079)ビット) を参照してください。

- コマンドレット [の詳細については、「Set-CsOnlineDialInConferencingUser」](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) を参照してください。

- 会議 ID は、オーディオ会議ブリッジに設定された桁の長さを満たす必要があります。 会議 Id には、アルファベットまたは特殊文字を使うことはできません。数値のみが使用できます。

- すべての電話会議ユーザーの電話会議 ID は既定で 9 桁の数字で、数字の数は変更できません。


## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell での管理方法について

- Windows PowerShell で行うのは、ユーザーを管理し、ユーザーに何を許可して何を禁止するかを管理することです。 Windows PowerShellでは、1 つの管理ポイントを使用して Microsoft 365 または Office 365 と Skype for Business Online を管理できます。複数のタスクを実行する場合は、毎日の作業を簡略化できます。 Windows PowerShell の使用を開始するには、次のトピックを参照してください。

  - [Windows PowerShell と Skype for Business Online の概要](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [PowerShell で使用する必要があるMicrosoft 365またはOffice 365理由](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- Windows PowerShell多くのユーザーに対して一度に設定を変更する場合など、Microsoft 365 管理センターを使用する場合に限って、速度、シンプルさ、生産性に多くの利点があります。 次のトピックでこれらの利点について説明します。

  - [アプリを使用してMicrosoft 365またはOffice 365を管理Windows PowerShell](/previous-versions//dn568025(v=technet.10))

  - [Windows PowerShell による Skype for Business Online の管理](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

## <a name="related-topics"></a>関連項目

[電話会議を試用または購入するには、Microsoft 365またはOffice 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
