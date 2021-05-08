---
title: ユーザーの会議 ID を表示、変更、リセットする
ms.author: tonysmit
author: tonysmit
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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-apr2020
description: 会議 ID をユーザーに割り当てる方法とMicrosoft Teams ID パラメーターの設定方法について説明します。
ms.openlocfilehash: b57a419266ceca09a73fc4bf75bb12153e41ea91
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117210"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-microsoft-teams"></a>グループ内のユーザーに割り当てられている会議 ID を表示およびリセットMicrosoft Teams

Microsoft 365 または Office 365 で電話会議用に設定され、Microsoft を電話会議プロバイダーとして使用すると、Microsoft Teams ユーザーに会議 ID が自動的に割り当てられます。 割り当てられた会議 ID は、会議がスケジュールされているときに会議出席招待で送信されます。 ユーザーがスケジュール設定した各会議には、一意の会議通話 ID が割り当てられます。 
  
会議 ID は自動的に作成され、ユーザーに割り当てられますが、ユーザーはこの ID を使用したくない場合や、特定の数に設定したり、ユーザーが会議 ID を記憶したり失われたりする場合があります。 管理センターまたはMicrosoft Teamsを使用してWindows PowerShellの会議 ID を表示、変更、リセットできます。
  
ユーザーに会議 ID と既定の電話会議の電話番号が含む電子メールが送信されるか、または会議 ID をリセットすると、PINではない 会議 ID を含む別の電子メールが送信されます。 会議[開催者の PIN をリセットする](reset-a-conference-id-for-a-user-in-teams.md)方法の詳細については、「Microsoft Teams でユーザーの会議 ID をリセットする」を参照してください。 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="view-and-reset-conference-ids"></a>会議 Idの表示と リセット

### <a name="to-view-the-conference-id"></a>会議 ID を表示するには

![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターを使用する**

1. 左側のナビゲーションで、[**ユーザー**] をクリックしてから、空いているユーザーのリストからユーザーを選択します。

2. ページの上部にある [編集] を **クリックします**。

3. [ **電話会議] で、[** 会議 ID] **を確認します**。

    > [!TIP]
    > [電子メールで会議情報を送信する] リンクをクリックすると、会議 ID と音声電話番号を含むすべての会議情報をメールでユーザー **に送信** できます。
  
**Windows PowerShell を使用する**

詳細については、[Microsoft Teams PowerShell のリファレンス](/powershell/module/teams/?view=teams-ps)をご覧ください。
    
  
### <a name="to-reset-the-conference-id"></a>会議 ID をリセットするには

例えば忘れてしまったなどの場合のために、ユーザーの会議 ID をリセットできます。
  
![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターを使用する**

1. 左側のナビゲーションで、[**ユーザー**] をクリックしてから、空いているユーザーのリストからユーザーを選択します。

2. ページの上部にある [編集] を **クリックします**。

3. [**電話会議**] で [**会議通話 ID のリセット**] をクリックします。

4. [会議 **ID のリセット] ウィンドウで** 、[リセット] を **クリックします**。 A conference ID will be automatically created and an email sent to the user with the new conference ID.
  
**Windows PowerShell を使用する**

詳細については、[Microsoft Teams PowerShell のリファレンス](/powershell/module/teams/?view=teams-ps)をご覧ください。


## <a name="what-else-should-you-know"></a>その他の情報

   > [!IMPORTANT]
   >  新しい会議 ID が作成された後、または 1 つがリセットされた後、古い会議 ID を呼び出し元が使用することはできません。 既存の会議の出席依頼のスケジュールを変更して、新しい会議 ID を出席依頼に追加するように、ユーザーに通知してください。 
  
    
- 会議 ID は、オーディオ会議ブリッジに設定された桁の長さを満たす必要があります。 会議 Id には、アルファベットまたは特殊文字を使うことはできません。数値のみが使用できます。
   
    
## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell の詳細情報

Windows PowerShellは、ユーザーの管理と、ユーザーが許可または許可されていない操作についてすべて行います。 このWindows PowerShell、1 つの管理Microsoft 365または Office 365 を管理し、複数のタスクを実行する場合に毎日の作業を簡略化できます。 Windows PowerShell の使用を開始するには、次のトピックを参照してください。
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [アプリを使用してMicrosoft 365またはOffice 365を管理Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](/powershell/module/teams/?view=teams-ps)」をご覧ください。
    
## <a name="related-topics"></a>関連トピック

[電話会議を試用または購入するには、Microsoft 365またはOffice 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)