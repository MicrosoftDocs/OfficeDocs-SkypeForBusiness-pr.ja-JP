---
title: Microsfot Teams で招待状に含まれている電話番号を設定する
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 32954439-d365-4125-872f-b37466ecb035
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: '発信者が Microsfot Teams 会議に参加するための既定の電話番号を作成する手順を説明します。 '
ms.openlocfilehash: eddab0762b679dba08dd9981d6ae61a1403ebf47
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23882961"
---
# <a name="set-the-phone-numbers-included-on-invites-in-microsoft-teams"></a>Microsfot Teams で招待状に含まれている電話番号を設定する

Office 365 の電話会議では、組織内のユーザーが Microsoft Teams 会議を作成することができます。ユーザーは電話を使用して作成した会議にダイヤルインすることができます。 Office 365 では、Microsoft を電話会議ブリッジとして使うか、承認済みの電話会議プロバイダー (ACP) によってホストされているサードパーティ ダイヤルイン会議ブリッジを使うオプションを選ぶことができます。
  
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
