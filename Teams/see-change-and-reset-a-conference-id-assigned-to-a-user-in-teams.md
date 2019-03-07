---
title: Microsoft Teams でユーザーに割り当てられている会議 ID を表示、変更、リセットする
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
- Teams_ITAdmin_Help
- M365-collaboration
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: '会議 ID を Microsoft Teams のユーザーに割り当てる方法と、会議 ID のパラメーターの値がどうなるかについて説明します。 '
ms.openlocfilehash: 6d1db1836ef5681416907936a7fab8db0d5ffb7a
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/07/2019
ms.locfileid: "30460461"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-microsoft-teams"></a>Microsoft Teams でユーザーに割り当てられた会議 ID を表示、リセットする

Microsoft Teams ユーザーが Office 365 での電話会議を利用できるようにセットアップされ、Microsoft を電話会議プロバイダーとして使用する場合に、会議 ID が自動的にユーザーに割り当てられます。 割り当てられた会議 ID は静的または動的で、会議がスケジュールされると会議の招待状で送信されます。 ユーザーがスケジュール設定した各会議には、一意の会議 ID が割り当てられます。 
  
会議 ID は自動的に作成されユーザーに割り当てられますが、ユーザーがそれを使いたくないため特定の番号に設定しようと考える場合や、ユーザーが会議 ID を覚えられない、または紛失してしまう場合があります。 Microsoft Teams の管理センターまたは Windows PowerShell を使用して、会議 ID を表示、変更、およびリセットすることができます。
  
ユーザーに会議 ID と既定の電話会議の電話番号が含む電子メールが送信されるか、または会議 ID をリセットすると、PINではない 会議 ID を含む別の電子メールが送信されます。 会議の開催者のPINをリセットするの詳細については、 [ここ](reset-a-conference-id-for-a-user-in-teams.md)をクリックします。 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="view-and-reset-conference-ids"></a>会議 Idの表示と リセット

### <a name="to-view-the-conference-id"></a>会議 ID を表示するには

![チーム ・ ロゴ ・ 30x30.png](media/teams-logo-30x30.png) **、マイクロソフトのチーム管理センターを使用して**

1. 左側のナビゲーションで、[**ユーザー**] をクリックしてから、空いているユーザーのリストからユーザーを選択します。

2. ページの上部で、[**編集**] をクリックします。

3. [**電話会議**] の下で、[**会議 ID **] を確認します。

    > [!TIP]
    > [**電話会議情報をメールで送信**] リンクをクリックすると、会議 ID や電話会議の電話番号を含んでいるメールで、会議に必要なすべての情報をユーザーに送信することができます。
  
**Windows PowerShell を使用する**

詳細については、[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)をご覧ください。
    
  
### <a name="to-reset-the-conference-id"></a>会議 ID をリセットするには

ユーザーの会議 ID を、ユーザーが忘れてしまった場合などに、リセットすることができます。
  
![チーム ・ ロゴ ・ 30x30.png](media/teams-logo-30x30.png) **、マイクロソフトのチーム管理センターを使用して**

1. 左側のナビゲーションで、[**ユーザー**] をクリックしてから、空いているユーザーのリストからユーザーを選択します。

2. ページの上部で、[**編集**] をクリックします。

3. [**電話会議**] の下で、[**会議 ID のリセット**] をクリックします。

4. [**会議 ID のリセット**] ウィンドウで、[**リセット**] をクリックします。 会議 ID は自動的に作成され、新しい会議 ID が記載されたメールがユーザーに送信されます。
  
**Windows PowerShell を使用する**

詳細については、[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)をご覧ください。


## <a name="what-else-should-you-know"></a>その他の情報

   > [!IMPORTANT]
   >  新しい会議 ID が作成されるか、会議 ID がリセットされると、発信者は以前の会議 ID を使用することができなくなります。 ユーザーに対して、新しい会議 ID が招待状に追加されるようにするために、既存の会議の招待をスケジュールし直すことを通知する必要があります。 
  
    
- 会議 ID は、電話会議ブリッジで設定された桁数での長さを満たしている必要があります。 会議 Id には、アルファベットまたは特殊文字を使うことはできません。数値のみが使用できます。
    
- オーディオ会議のすべてのユーザーの会議 ID は、既定では、7 桁になります。桁数を変更することはできません。
    
    
## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell の詳細情報

Windows PowerShell は、ユーザーと、ユーザーに許可されていることと許可されていないことを管理するためにあるということです。Windows PowerShell があれば、一元管理を使用して Office 365 を管理し、複数のタスクを抱えているときに、日常の仕事を簡素化することができます。Windows PowerShell を開始するには、これらのトピックを参照してください。
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)」をご覧ください。
    
## <a name="related-topics"></a>関連トピック

[Office 365 での電話会議を使用または購入する](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)

