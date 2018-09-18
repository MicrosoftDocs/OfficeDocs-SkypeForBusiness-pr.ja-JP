---
title: Microsoft Teams で電話会議の PIN をリセットする
mms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 67866a47-89c1-4593-8766-3a68777e2be6
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
description: 'PIN について知っておくべきことと、Microsoft Teams でそれらをリセットする方法について確認します。 '
ms.openlocfilehash: 9c63df504150dce7ba1d46329fc86a27c75ced8d
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/08/2018
ms.locfileid: "23892955"
---
# <a name="reset-the-audio-conferencing-pin-in-microsoft-teams"></a>Microsoft Teams で電話会議の PIN をリセットする

PIN は数で構成されるコードで、電話会議の利用が有効になっている各 Microsoft Teams ユーザーに対して作成されます。 電話会議 PIN は会議の開催者によって、自分たちが会議の開催者であることを識別し、電話を経由して会議を開始することができるようにするために使用されます。 会議を開始するために Microsoft Teams アプリを使用する場合、PIN は必要ありません。 ユーザーが PIN を忘れてしまい、電話会議の利用が有効になったときに送られてきたメールから見つけることができない場合は、管理者がそれらのユーザーの PIN をリセットするか、ユーザー自身が自分の PIN をリセットすることができます。
  
会議を開始できるのは、認証済みユーザーが Microsoft Teams アプリを使用して参加する場合か、開催者が自分の PIN を使用して電話で参加する場合です。 会議の開始に PIN が必要な場合、電話で参加するユーザーはロビーで待機し、会議が開始するまで保留音を聞くことになります。 会議の開催者が、電話で会議を開始するための PIN を要求しない場合、発信者は会議に参加しようとするときに PIN の提示を求められません。

## <a name="reset-a-users-pin"></a>ユーザーの PIN をリセットする

1. 左側のナビゲーションで、[**ユーザー**] をクリックしてから、空いているユーザーのリストからユーザーを選択します。

2. ページの上部で、[**編集**] をクリックします。

3. [**電話会議**] の下で、[**PIN のリセット**] をクリックします。
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-his-or-her-own-pin"></a>ユーザーに自分の PIN をリセットさせる

1. ユーザーに [https://admin0m.online.lync.com/lscp/usp/pstnconferencing](https://admin0m.online.lync.com/lscp/usp/pstnconferencing) に移動してもらいます。
2. [**PIN のリセット**] をクリックします。 


## <a name="what-else-should-you-know-about-pins"></a>PIN について知っておくべきその他のこと

- セキュリティ保護のため、PIN のリセット時に PIN は管理者に 1 回だけ表示されます。 PIN は管理者によってリセットされた後、*********** とリストに表示されます。
    
- ユーザーへのメールの自動送信は既定で有効です。ユーザーが電話会議で有効になるか、PIN がリセットされると、ユーザーは自分の PIN が記載されたメールを受信します。 ただし、メールの自動送信を無効にしても、ユーザーには PIN リセットのメールは送信されず、そのユーザーには手動で PIN 情報を送信する必要があります。
    
- 会議が始まると、ロビー内のすべてのユーザーは自動的にその会議に参加します。 たとえば、会議が始まる前に 2 人の参加者が会議に参加しようとすると、ロビーで待って保留音を聞くことになります。会議の開催者が自分の PIN を使用して電話で参加すると、会議が始まり、ロビーにいる参加者が会議に参加します。
    
- 既定の設定では、匿名の発信者が会議を開始することはできません。
    
- 電話会議でユーザーを有効にすると、既定でユーザーに電話会議の情報と PIN が記載されたメールが送信されます。 ユーザーは Office 365 メールボックスを持っている必要があります。PIN がリセットされると、ユーザーに設定されているプライマリ SMTP アドレス (エイリアス) へのメールで、新しい PIN がユーザーに送信されるためです。
    
- 電話会議をセットアップすると、所属する組織の PIN で必要な桁数を設定することになります。 PIN は 4 桁から 12 桁の間にすることができます。既定では 5 桁です。 PIN の長さの設定を変更すると、その設定は新たに生成された PIN のみに適用され、電話会議で有効になっている既存のユーザーの PIN 設定には適用されません。 「[Set the length of the PIN for Audio Conferencing meetings (電話会議の PIN の長さを設定する)](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md)」をご覧ください。
    
- 既定では、メールはユーザーの Office 365 プライマリ SMTP アドレスに送信されるように設定されています。 Hotmail や MSN のメール アドレスなどの Office 365 以外のアドレスにメールを送信することもできます。 Windows PowerShell を使用して、既定のメール アドレスを上書きすることができます。 これは、ユーザーが Office 365 の Exchange メールボックスを持っていない場合に便利です。

    

## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell の詳細情報

Windows PowerShell は、ユーザーと、ユーザーに許可されていることと許可されていないことを管理するためにあるということです。Windows PowerShell があれば、一元管理を使用して Office 365 を管理し、複数のタスクを抱えているときに、日常の仕事を簡素化することができます。Windows PowerShell を開始するには、これらのトピックを参照してください。
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)」をご覧ください。
  
## <a name="related-topics"></a>関連トピック

[ユーザーのために会議 ID をリセットする](reset-a-conference-id-for-a-user-in-teams.md)
