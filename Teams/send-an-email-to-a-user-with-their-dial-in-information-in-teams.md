---
title: Microsoft Teams で電話会議の情報が記載されたメールをユーザーに送信する
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 7440d3e2-1b49-4258-bd2c-79e9072f8c8d
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1keywords: None
ms.custom:
- Audio Conferencing
description: Microsoft Teams で電話会議の情報が記載されたメールをユーザーに送信します。
ms.openlocfilehash: 9ebd650e487b4ef3108d50ecce31eea0a936b176
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2018
ms.locfileid: "25012322"
---
# <a name="send-an-email-to-a-user-with-their-audio-conferencing-information-in-microsoft-teams"></a>Microsoft Teams で電話会議の情報が記載されたメールをユーザーに送信する

マイクロソフトのチームのユーザーの電話会議の情報を送信する必要があります。 [ユーザーのプロパティ] で**電子メールを使用して会議情報を送信**をクリックしてこれを行うことができます。 この電子メールを送信するとき、すべてが含まれますのオーディオ会議の情報を含みます。
  
- ユーザー用の会議の電話番号またはダイヤルイン電話番号。
    
- ユーザーの会議 ID。
    
   
ユーザーに送信されるメールの例を次に示します。
  
![ダイヤルイン会議のメール](media/audio-conferencing-info.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>電話会議の情報が記載されたメールをユーザーに送信する

1. 左側のナビゲーションで、[**ユーザー**] をクリックしてから、空いているユーザーのリストからユーザーを選択します。

2. ページの上部で、[**編集**] をクリックします。

3. [**電話会議**] の下で、[**電話会議情報をメールで送信**] をクリックします。


## <a name="what-else-should-you-know-about-this-email"></a>このメールについて知っておくべきその他のこと

- 組織内のユーザーが電話会議で有効になった後に、それらのユーザーに送信されるメールは複数あります。
    
  - **電話会議** のライセンスがユーザーに割り当てられた場合。
    
  - ユーザーの電話会議の PIN を手動でリセットした場合。
    
  - ユーザーの会議 ID を手動でリセットした場合。
    
  - **電話会議** のライセンスがユーザーから削除された場合。
    
  - ユーザーの電話会議プロバイダーが Microsoft から別のプロバイダー、または [**なし**] に変更された場合。
    
  - ユーザーの電話会議プロバイダーが Microsoft に変更された場合。
    
- 既定では、電子メールの送信者が、Office 365 からなりますが、電子メール アドレスを変更し、Windows PowerShell を使用して名前を表示できます。 詳細については[マイクロソフト チームの PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)を参照してください。
  
## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell の詳細情報

Windows PowerShell は、ユーザーと、ユーザーに許可されていることと許可されていないことを管理するためにあるということです。Windows PowerShell があれば、一元管理を使用して Office 365 を管理し、複数のタスクを抱えているときに、日常の仕事を簡素化することができます。Windows PowerShell を開始するには、これらのトピックを参照してください。
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)」をご覧ください。
    
  
## <a name="related-topics"></a>関連トピック

[Office 365 での電話会議を使用または購入する](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
