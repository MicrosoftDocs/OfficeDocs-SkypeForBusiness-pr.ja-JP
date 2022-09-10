---
title: ユーザーの会議 ID を表示、変更、リセットする
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 77d36233-2aab-4802-ba9c-e9a8885ea643
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-apr2020
description: Microsoft Teams のユーザーに会議 ID を割り当てる方法と、会議 ID パラメーターを指定する必要がある方法について説明します。
ms.openlocfilehash: 9ff068a8485f77531ba034ebeaab3e27e1ed42ef
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2022
ms.locfileid: "67642118"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-microsoft-teams"></a>Microsoft Teams のユーザーに割り当てられている会議 ID を表示してリセットする

電話会議 ID は、Microsoft 365 で電話会議用に設定されている場合、またはOffice 365、Microsoft を電話会議プロバイダーとして使用するときに、Microsoft Teams ユーザーに自動的に割り当てられます。 割り当てられた会議 ID は、会議がスケジュールされたときに会議の招待に送信されます。 ユーザーがスケジュール設定した各会議には、一意の会議通話 ID が割り当てられます。
  
会議 ID は自動的に作成され、ユーザーに割り当てられますが、ユーザーがこの会議 ID を使用したくない場合や、特定の番号に設定したい場合や、ユーザーが会議 ID を記憶できない、または紛失した場合があります。 Microsoft Teams 管理センターまたはWindows PowerShellを使用して、会議 ID を表示、変更、リセットできます。
  
ユーザーに会議 ID と既定の電話会議の電話番号が含む電子メールが送信されるか、または会議 ID をリセットすると、PINではない 会議 ID を含む別の電子メールが送信されます。 会議開催者の PIN をリセットする方法の詳細については、「 [Microsoft Teams のユーザー](reset-a-conference-id-for-a-user-in-teams.md) の会議 ID をリセットする」を参照してください。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="view-and-reset-conference-ids"></a>会議 Idの表示と リセット

### <a name="to-view-the-conference-id"></a>会議 ID を表示するには

#### <a name="view-the-conference-id-using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターを使用して会議 ID を表示する

1. 左側のナビゲーションで、[**ユーザー**] をクリックしてから、空いているユーザーのリストからユーザーを選択します。

2. ページの上部にある [編集] をクリック **します**。

3. [ **電話会議**] で、[ **会議 ID**] の下を確認します。

    > [!TIP]
    > [電子メールで会議情報を送信する] リンクをクリックすると、会議 ID と音声電話番号を含むすべての **会議情報を電子メールでユーザーに送信** できます。
  
#### <a name="view-the-conference-id-using-windows-powershell"></a>Windows PowerShellを使用して会議 ID を表示する

詳細については、[Microsoft Teams PowerShell のリファレンス](/powershell/module/teams/?view=teams-ps)をご覧ください。

### <a name="to-reset-the-conference-id"></a>会議 ID をリセットするには

例えば忘れてしまったなどの場合のために、ユーザーの会議 ID をリセットできます。
  
#### <a name="reset-the-conference-id-using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターを使用して会議 ID をリセットする

1. 左側のナビゲーションで、[**ユーザー**] をクリックしてから、空いているユーザーのリストからユーザーを選択します。

2. ページの上部にある [編集] をクリック **します**。

3. [**電話会議**] で [**会議通話 ID のリセット**] をクリックします。

4. [ **会議 ID のリセット** ] ウィンドウで、[ **リセット**] をクリックします。 A conference ID will be automatically created and an email sent to the user with the new conference ID.
  
#### <a name="reset-the-conference-id-using-windows-powershell"></a>Windows PowerShellを使用して会議 ID をリセットする

詳細については、[Microsoft Teams PowerShell のリファレンス](/powershell/module/teams/?view=teams-ps)をご覧ください。

## <a name="what-else-should-you-know"></a>その他の情報

> [!IMPORTANT]
> 新しい会議 ID が作成された後、またはリセットされた後は、以前の会議 ID を呼び出し元が使用することはできません。 既存の会議の出席依頼のスケジュールを変更して、新しい会議 ID を出席依頼に追加するように、ユーザーに通知してください。

- 会議 ID は、オーディオ会議ブリッジに設定された桁の長さを満たす必要があります。 会議 Id には、アルファベットまたは特殊文字を使うことはできません。数値のみが使用できます。

## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell の詳細情報

Windows PowerShellはすべて、ユーザーの管理と、ユーザーの許可または許可されていない操作です。 Windows PowerShellを使用すると、1 つの管理ポイントを使用して Microsoft 365 またはOffice 365を管理できます。複数のタスクがある場合に毎日の作業を簡略化できます。 Windows PowerShell の使用を開始するには、次のトピックを参照してください。

- [Windows PowerShell で Office 365 を管理するための最善の方法](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [Windows PowerShell で Microsoft 365 または Office 365 を管理するための最善の方法](/previous-versions//dn568025(v=technet.10))

Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](/powershell/module/teams/?view=teams-ps)」をご覧ください。

## <a name="related-topics"></a>関連トピック

[Microsoft Teams 用の Microsoft 365 で電話会議を試用または購入する](try-or-purchase-audio-conferencing-in-office-365-for-teams.md)
