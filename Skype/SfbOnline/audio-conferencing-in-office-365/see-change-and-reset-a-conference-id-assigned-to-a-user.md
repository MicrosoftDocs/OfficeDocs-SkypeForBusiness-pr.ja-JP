---
title: Skype for Business Online のユーザーに割り当てられている会議 ID を表示、変更、リセットする
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
ms.openlocfilehash: a8f0e64ef30e1e503a1e3b78c9823f5d115df837
ms.sourcegitcommit: b72bf3827e7145b9b6a95c84e88a7879c6e8c337
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/12/2020
ms.locfileid: "46643607"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-skype-for-business-online"></a>Skype of businessオンラインのユーザーに割り当てられている会議 ID を表示させリセットしてください。

> [!Note]
> Microsoft Teams のユーザー会議 id の詳細については、「 [Microsoft teams でユーザーに割り当てられている会議 ID を表示およびリセット](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams)する」を参照してください。

会議 ID は、Microsoft 365 または Office 365 で電話会議用にセットアップされ、電話会議プロバイダーとして Microsoft を使用している場合に、Skype for Business ユーザーに自動的に割り当てられます。 会議がスケジュールされると、割り当てられた会議 ID が会議の出席依頼に送信されます。 ユーザーがスケジュール設定した各会議には、一意の会議通話 ID が割り当てられます。

会議 ID は自動的に作成され、ユーザーに割り当てられますが、ユーザーがこの機能を使用したくない場合や、特定の番号に設定したい場合、またはユーザーが自分の会議 ID を忘れてしまったり、紛失したりする場合もあります。 **Skype For business 管理センター**と Windows PowerShell を使用して、会議 ID を表示、変更、リセットすることができます。

ユーザーに会議 ID と既定の電話会議の電話番号が含む電子メールが送信されるか、または会議 ID をリセットすると、PINではない 会議 ID を含む別の電子メールが送信されます。 会議の開催者のPINをリセットするの詳細については、 [ここ](reset-a-conference-id-for-a-user.md)をクリックします。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="view-and-reset-conference-ids"></a>会議 Idの表示と リセット

### <a name="to-view-the-conference-id"></a>会議 ID を表示するには

![Skype for Business のロゴを表示したアイコン](../images/sfb-logo-30x30.png) **Skype for Business 管理センターの使用**

会議 ID を表示し、ユーザーに送信することができます。

1. 職場または学校のアカウントを使用してサインインします。

2. **Skype For business**> 管理センターに移動します。

3. **Skype of business管理センター**の> **オーディオ会議** > **ユーザー**で会議IDを必要とするユーザー を選択します。

4. アクション ページで、**会議 ID** を確認します。

    > [!TIP]
    > [**ユーザー** ] ページでユーザーを選択した後、[電話会議**情報をメールで送信**] リンクをクリックすると、会議 ID と電話番号を含むメールのユーザーにすべての会議情報を送信できます。

**Windows PowerShell を使用する**

ユーザーの会議 ID を表示するのにWindows PowerShell を使用できます。 そのためには、次を実行します。

  ```powershell
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"
  ```

コマンドレットの詳細については、 [get-csonlinedialinconferencinguser](https://go.microsoft.com/fwlink/?LinkId=617693 )を参照してください。


### <a name="to-reset-the-conference-id"></a>会議 ID をリセットするには

例えば忘れてしまったなどの場合のために、ユーザーの会議 ID をリセットできます。

![Skype for Business のロゴを表示したアイコン](../images/sfb-logo-30x30.png) **Skype for Business 管理センターの使用**

1. 職場または学校のアカウントを使用してサインインします。

2. **Skype For business**> 管理センターに移動します。

3. **Skype for business 管理センター**の >  **電話会議**  >  **ユーザー**で、操作ウィンドウの [**会議 ID**] で [**リセット**] をクリックします。

4. [**会議 ID をリセットしますか?** ] ウィンドウで、[**はい**] をクリックします。 A conference ID will be automatically created and an email sent to the user with the new conference ID.

**Windows PowerShell を使用する**

ユーザーの会議 ID をリセットするには、Windows PowerShell を使用します。 これを行う場合は、次を実行します。

  ```PowerShell
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble" -ResetConferenceID
  ```

## <a name="what-else-should-you-know"></a>その他の情報

   > [!IMPORTANT]
   >  新しい会議 ID を作成するか、またはリセットした後は、古い会議 ID を発信者が使用することはできません。 既存の会議の出席依頼のスケジュールを変更して、新しい会議 ID を出席依頼に追加するように、ユーザーに通知してください。 ユーザーは Skype for Business 会議移行ツールを使用して、既存の会議を更新することができます。 このツールのダウンロード、インストール、実行の方法については、「 [skype For business および Lync の会議更新ツール](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)」、「 [Skype for Business Online、会議移行ツール (64 ビット)](https://go.microsoft.com/fwlink/?LinkID=626047)」、「 [Skype For Business online、会議移行ツール (32 ビット)](https://www.microsoft.com/download/details.aspx?id=54079)」を参照してください。

- コマンドレットの詳細については、「 [Set-get-csonlinedialinconferencinguser](https://go.microsoft.com/fwlink/?LinkId=617688 ) 」を参照してください。

- 会議 ID は、オーディオ会議ブリッジに設定された桁の長さを満たす必要があります。 会議 Id には、アルファベットまたは特殊文字を使うことはできません。数値のみが使用できます。

- 電話会議のすべてのユーザーの会議 ID は、既定で9桁の数字になり、数字の数を変更することはできません。


## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell での管理方法について

- Windows PowerShell で行うのは、ユーザーを管理し、ユーザーに何を許可して何を禁止するかを管理することです。 Windows PowerShell を使用すると、複数のタスクがある場合に、1つの管理ポイントを使用して、Microsoft 365 または Office 365 と Skype for Business Online を管理することができます。 Windows PowerShell の使用を開始するには、次のトピックを参照してください。

  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [Microsoft 365 または Office 365 PowerShell を使用する必要がある理由](https://go.microsoft.com/fwlink/?LinkId=525041)

- Windows PowerShell には、多くのユーザーについて同時に設定を変更する場合など、Microsoft 365 管理センターを使用する場合にのみ、速度、シンプルさ、生産性を高めることができます。 次のトピックでこれらの利点について説明します。

  - [Windows PowerShell を使用して Microsoft 365 または Office 365 を管理するのに最適な方法](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>関連項目

[Microsoft 365 または Office 365 で電話会議を試用または購入する](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

