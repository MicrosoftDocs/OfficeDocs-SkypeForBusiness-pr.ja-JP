---
title: Microsoft Teams で電話会議の PIN をリセットする
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 67866a47-89c1-4593-8766-3a68777e2be6
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Pin について知っておくべきことと、Microsoft Teams で Pin をリセットする方法について説明します。 '
ms.openlocfilehash: 6d0d986789fb987494ded16bb8d6f6d7c3bf58a4
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "41693832"
---
# <a name="reset-the-audio-conferencing-pin-in-microsoft-teams"></a>Microsoft Teams で電話会議の PIN をリセットする

PIN は、電話会議が有効になっている Microsoft Teams ユーザーごとに作成された番号から構成されるコードです。 電話会議の Pin は、会議の開催者が会議の開催者であり、電話で会議を開始できることを示すために使用されます。 Microsoft Teams アプリを使って会議を開始する場合、PIN は必要ありません。 ユーザーが PIN を忘れた場合、電話会議用に有効にしたときに送信されたメールでその PIN が見つからない場合は、管理者が自分の pin をリセットするか、自分の pin をリセットすることができます。
  
会議を開始できるのは、認証されたユーザーが Microsoft Teams アプリを使って参加した場合、または開催者が電話で自分の PIN を使用して参加した場合です。 会議の開始に PIN が必要な場合、電話で参加するユーザーはロビーで待機し、会議が開始するまで保留音を聞くことになります。 会議の開催者が、電話で会議を開始するための PIN を要求しない場合、発信者は会議に参加しようとするときに PIN の提示を求められません。

## <a name="reset-a-users-pin"></a>ユーザーの PIN をリセットする

![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターの使用**

1. 左側のナビゲーションで、[**ユーザー**] をクリックしてから、空いているユーザーのリストからユーザーを選択します。

2. [**編集**] をクリックします。

3. [**電話会議**] の [ **PIN のリセット**] をクリックします。

4. [**リセット**] をクリックします。
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-his-or-her-own-pin"></a>ユーザーが自分の PIN をリセットする

1. ユーザーにアクセス権を[https://admin0m.online.lync.com/lscp/usp/pstnconferencing](https://admin0m.online.lync.com/lscp/usp/pstnconferencing)付与します。
2. [ **PIN のリセット**] をクリックします。 


## <a name="what-else-should-you-know-about-pins"></a>PIN について知っておくべきその他のこと

- セキュリティ保護のため、PIN のリセット時に PIN は 1 回だけ管理者に表示されます。 PIN が管理者によってリセットされると、PIN が "* * * * *" と表示されます。
    
- ユーザーにメールを自動的に送信する機能は既定で有効になっています。電話会議が有効になっているか、PIN がリセットされると、ユーザーは PIN を含むメールを受信します。 ただし、メールの自動送信を無効にした場合、PIN のリセットメールはユーザーに送信されず、ユーザーに PIN 情報を手動で送信する必要があります。
    
- 会議が始まると、ロビー内のすべてのユーザーは自動的にその会議に参加します。 たとえば、会議が始まる前に 2 人の参加者が会議に参加しようとすると、ロビーで待って保留音を聞くことになります。会議の開催者が自分の PIN を使用して電話で参加すると、会議が始まり、ロビーにいる参加者が会議に参加します。
    
- 既定の設定では、匿名の発信者が会議を開始することは許可されていません。
    
- 電話会議のユーザーを有効にすると、既定では、会議の情報とその PIN を含むメールが送信されます。 PIN がリセットされると、ユーザーに対して設定されているプライマリ SMTP アドレス (エイリアス) 宛てに、ユーザーに Office 365 メールボックスがある必要があります。
    
- 電話会議をセットアップするときには、組織内の Pin に必要な数字を設定します。 Pin は 4 ~ 12 桁にすることができます。既定値は5です。 PIN の長さの設定を変更した場合、設定は新しく生成された Pin にのみ適用され、電話会議用に有効になっている既存のユーザーの PIN の設定には適用されません。 「[電話会議の PIN の長さを設定](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md)する」を参照してください。
    
- 既定では、メールはユーザーの Office 365 プライマリ SMTP アドレスに設定されます。 Hotmail または MSN のメールアドレスなど、Office 以外の365のアドレスにメールを送信することができます。 Windows PowerShell を使用して、既定のメールアドレスを上書きできます。 これは、ユーザーが Office 365 の Exchange メールボックスを持っていない場合に便利です。

    

## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell の詳細情報

Windows PowerShell で行うのは、ユーザーを管理し、ユーザーに何を許可して何を禁止するかを管理することです。Windows PowerShell を利用すると、Office 365 の管理を 1 か所で行うことができるので、複数のタスクを担当する管理者の日常業務を単純化できます。Windows PowerShell の使用を開始するには、次のトピックを参照してください。
    
  - [Office 365 PowerShell を使用する必要がある理由](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)」をご覧ください。
  
## <a name="related-topics"></a>関連トピック

[ユーザーの会議 ID をリセットする](reset-a-conference-id-for-a-user-in-teams.md)
