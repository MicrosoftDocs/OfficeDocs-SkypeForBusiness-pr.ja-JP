---
title: マイクロソフトのチームでの携帯電話への招待に含まれている番号の設定します。
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 32954439-d365-4125-872f-b37466ecb035
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'マイクロソフトのチーム ミーティングに参加するのには呼び出し元の既定の電話番号を作成する手順を取得します。 '
ms.openlocfilehash: f62a6e63181c474d19f403d6c81f858177bd8cd0
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2018
ms.locfileid: "25016198"
---
# <a name="set-the-phone-numbers-included-on-invites-in-microsoft-teams"></a>Microsfot Teams で招待状に含まれている電話番号を設定する

マイクロソフト チームの会議を作成して、電話を使用してその会議にダイヤルインするユーザーを許可し、組織内のユーザーを Office 365 での音声会議に使用できます。 、Office 365 では、マイクロソフトのオーディオ会議ブリッジまたは、承認済みの音声会議プロバイダー (ACP) によってホストされているサード ・ パーティ製のオーディオ会議ブリッジを使用するオプションがあります。
  
会議ブリッジは、組織用のダイヤルイン電話番号のセットを提供します。これらの番号はすべて会議開催者が作成した会議に参加するために使用できますが、会議出席依頼にどの番号を含めるか選ぶことができます。
  
> [!NOTE]
> 会議主催者の会議出席依頼には、1 つの有料電話番号と 1 つの無料電話番号を含めることができますが、会議出席依頼の下部に、会議に参加するために使用できるダイヤルイン電話番号のすべての一覧を表示するリンクも記載されています。 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="set-or-change-the-default-audio-conferencing-phone-number-for-a-meeting-organizer-or-user"></a>会議の開催者またはユーザーのために、既定の電話会議の電話番号を設定または変更する

1. 左側のナビゲーションで、[**ユーザー**] をクリックしてから、空いているユーザーのリストからユーザーを選択します。

    ![Microsoft Teams と Skype for Business の管理センターでのユーザーの選択を示す](media/teamsselectusers.png)

2. ページの上部で、[**編集**] をクリックします。

    ![Microsoft Teams と Skype for Business の管理センターで [編集] をクリックする](media/teamsedituser.png)

3. [**電話会議**] の隣で、[**編集**] をクリックします。 
    
    ![電話会議の隣の [編集] をクリックする](media/teamseditaudioconf.png)

4. [**有料電話番号**] または [**無料電話番号**] フィールドを使用してユーザーの電話番号を入力します。


> [!IMPORTANT]
> ユーザーの電話会議設定を変更するときは、繰り返し発生する今後の Microsoft Teams 会議が更新されて、出席者に送信されるようにする必要があります。 

## <a name="want-to-use-windows-powershell"></a>Windows PowerShell を使用する場合

Windows PowerShell は、ユーザーと、ユーザーに許可されていることと許可されていないことを管理するためにあるということです。Windows PowerShell があれば、一元管理を使用して Office 365 を管理し、複数のタスクを抱えているときに、日常の仕事を簡素化することができます。Windows PowerShell を開始するには、これらのトピックを参照してください。
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)」をご覧ください。 
  
    
## <a name="related-topics"></a>関連トピック

[Office 365 での電話会議を使用または購入する](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
