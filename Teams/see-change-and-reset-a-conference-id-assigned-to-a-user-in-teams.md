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
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Microsoft Teams でユーザーに会議 ID を割り当てる方法と、会議 ID のパラメーターを指定する方法について説明します。 '
ms.openlocfilehash: d134a3664a6cee588d08f3d1a33bc6018d97a1fa
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2019
ms.locfileid: "37571339"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-microsoft-teams"></a>Microsoft Teams でユーザーに割り当てられている会議 ID を表示およびリセットする

会議 ID は、Office 365 で電話会議用にセットアップされ、電話会議プロバイダーとして Microsoft を使用している場合に、Microsoft Teams ユーザーに自動的に割り当てられます。 会議がスケジュールされると、割り当てられた会議 ID が会議の出席依頼に送信されます。 ユーザーがスケジュール設定した各会議には、一意の会議通話 ID が割り当てられます。 
  
会議 ID は自動的に作成され、ユーザーに割り当てられますが、ユーザーがこの機能を使用したくない場合や、特定の番号に設定したい場合、またはユーザーが自分の会議 ID を忘れてしまったり、紛失したりする場合もあります。 Microsoft Teams 管理センターまたは Windows PowerShell を使用して、会議 ID を表示、変更、リセットすることができます。
  
ユーザーに会議 ID と既定の電話会議の電話番号が含む電子メールが送信されるか、または会議 ID をリセットすると、PINではない 会議 ID を含む別の電子メールが送信されます。 会議の開催者のPINをリセットするの詳細については、 [ここ](reset-a-conference-id-for-a-user-in-teams.md)をクリックします。 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="view-and-reset-conference-ids"></a>会議 Idの表示と リセット

### <a name="to-view-the-conference-id"></a>会議 ID を表示するには

![Microsoft teams](media/teams-logo-30x30.png) **管理センターを使用し**た microsoft teams ロゴを示すアイコン

1. 左側のナビゲーションで、[**ユーザー**] をクリックしてから、空いているユーザーのリストからユーザーを選択します。

2. ページの上部にある [**編集**] をクリックします。

3. [電話**会議**] の下の [**電話会議 ID**] を確認します。

    > [!TIP]
    > [メールの電話**会議情報を送信**] リンクをクリックすると、会議 ID と電話番号を含むメールのユーザーにすべての会議情報を送信できます。
  
**Windows PowerShell を使用する**

詳細については、[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)をご覧ください。
    
  
### <a name="to-reset-the-conference-id"></a>会議 ID をリセットするには

例えば忘れてしまったなどの場合のために、ユーザーの会議 ID をリセットできます。
  
![Microsoft teams](media/teams-logo-30x30.png) **管理センターを使用し**た microsoft teams ロゴを示すアイコン

1. 左側のナビゲーションで、[**ユーザー**] をクリックしてから、空いているユーザーのリストからユーザーを選択します。

2. ページの上部にある [**編集**] をクリックします。

3. [**電話会議**] で [**会議通話 ID のリセット**] をクリックします。

4. [**電話会議 ID のリセット**] ウィンドウで、[**リセット**] をクリックします。 A conference ID will be automatically created and an email sent to the user with the new conference ID.
  
**Windows PowerShell を使用する**

詳細については、[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)をご覧ください。


## <a name="what-else-should-you-know"></a>その他の情報

   > [!IMPORTANT]
   >  新しい会議 ID を作成するか、またはリセットした後は、古い会議 ID を発信者が使用することはできません。 既存の会議の出席依頼のスケジュールを変更して、新しい会議 ID を出席依頼に追加するように、ユーザーに通知してください。 
  
    
- 会議 ID は、オーディオ会議ブリッジに設定された桁の長さを満たす必要があります。 会議 Id には、アルファベットまたは特殊文字を使うことはできません。数値のみが使用できます。
   
    
## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell の詳細情報

Windows PowerShell で行うのは、ユーザーを管理し、ユーザーに何を許可して何を禁止するかを管理することです。Windows PowerShell を利用すると、Office 365 の管理を 1 か所で行うことができるので、複数のタスクを担当する管理者の日常業務を単純化できます。Windows PowerShell の使用を開始するには、次のトピックを参照してください。
    
  - [Office 365 PowerShell を使用する必要がある理由](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)」をご覧ください。
    
## <a name="related-topics"></a>関連項目

[Office 365 での電話会議を試用または購入する](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)

