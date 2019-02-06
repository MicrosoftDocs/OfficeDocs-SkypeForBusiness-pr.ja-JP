---
title: Microsoft Teams で電話会議の PIN をリセットする
mms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 67866a47-89c1-4593-8766-3a68777e2be6
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
description: 'PIN について知っておくべきことと、Microsoft Teams でそれらをリセットする方法について確認します。 '
ms.openlocfilehash: 44229d57a8f09b8b687f6fc0367686e81e898c5a
ms.sourcegitcommit: 31827526894ffb75d64fcb0a7c76ee874ad3c269
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2019
ms.locfileid: "29754114"
---
# <a name="reset-the-audio-conferencing-pin-in-microsoft-teams"></a>Microsoft Teams で電話会議の PIN をリセットする

PIN は数で構成されるコードで、電話会議の利用が有効になっている各 Microsoft Teams ユーザーに対して作成されます。 電話会議 PIN は会議の開催者によって、自分たちが会議の開催者であることを識別し、電話を経由して会議を開始することができるようにするために使用されます。 会議を開始するために Microsoft Teams アプリを使用する場合、PIN は必要ありません。 ユーザーが PIN を忘れてしまい、電話会議の利用が有効になったときに送られてきたメールから見つけることができない場合は、管理者がそれらのユーザーの PIN をリセットするか、ユーザー自身が自分の PIN をリセットすることができます。
  
会議を開始できるのは、認証済みユーザーが Microsoft Teams アプリを使用して参加する場合か、開催者が自分の PIN を使用して電話で参加する場合です。 会議の開始に PIN が必要な場合、電話で参加するユーザーはロビーで待機し、会議が開始するまで保留音を聞くことになります。 会議の開催者が、電話で会議を開始するための PIN を要求しない場合、発信者は会議に参加しようとするときに PIN の提示を求められません。

## <a name="reset-a-users-pin"></a>ユーザーの PIN をリセットする

![チーム ・ ロゴ ・ 30x30.png](media/teams-logo-30x30.png) **、マイクロソフトのチーム管理センターを使用して**

1. 左側のナビゲーションでは、**ユーザー**] をクリックしてで使用可能なユーザーの一覧からユーザーを選択します。

2. [**編集**] をクリックします。

3. **オーディオ会議**では、[ **PIN のリセット**] をクリックします。

4. [**リセット**] をクリックします。
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-his-or-her-own-pin"></a>ユーザーが自分の PIN のリセット

1. ユーザーには、 [https://admin0m.online.lync.com/lscp/usp/pstnconferencing](https://admin0m.online.lync.com/lscp/usp/pstnconferencing)。
2. **PIN のリセット**] をクリックします。 


## <a name="what-else-should-you-know-about-pins"></a>PIN について知っておくべきその他のこと

- セキュリティ保護のため、PIN のリセット時に PIN は 1 回だけ管理者に表示されます。 暗証番号 (pin) は、管理者がリセットされますが後の暗証番号 (pin) が表示されます。。
    
- デフォルトで有効化は自動的にユーザーに電子メールを送信して、ユーザー音声会議や、PIN をリセットする場合は有効にしている場合、PIN の電子メールが送信されます。 自動的に無効にした場合電子メールを送信するユーザーに PIN リセットの電子メールを送信しないユーザーに暗証番号 (pin) の情報を手動で送信する必要があります。
    
- 会議が始まると、ロビー内のすべてのユーザーは自動的にその会議に参加します。 たとえば、会議が始まる前に 2 人の参加者が会議に参加しようとすると、ロビーで待って保留音を聞くことになります。会議の開催者が自分の PIN を使用して電話で参加すると、会議が始まり、ロビーにいる参加者が会議に参加します。
    
- 既定の設定では、匿名の呼び出しを開始するための会議を許可しないようにします。
    
- オーディオ会議のユーザーを有効にすると、既定で送信される会議の情報と PIN を含む電子メール。 ユーザーは PIN をリセットすると、新しい暗証番号 (pin) はでは、プライマリ SMTP アドレス (エイリアス)、ユーザーに設定されている電子メールのユーザーに送信されますので、Office 365 のメールボックスに必要です。
    
- オーディオ会議を設定するときは、組織内のピンに必要な数字を設定します。 ピンは 12 桁、4 - デフォルトは 5 です。 暗証番号 (pin) の長さの設定を変更すると、設定は、新しく生成されたピンの位置にのみ適用し、オーディオ会議を有効になっている既存のユーザーの暗証番号 (pin) の設定に適用されていません。 [オーディオ会議の会議の暗証番号 (pin) の長さの設定](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md)を参照してください。
    
- 既定で電子メールは、ユーザーの Office 365 のプライマリ SMTP アドレスに設定されます。 Office 365 以外のアドレス、Hotmail または MSN の電子メール アドレスに電子メールを送信できます。 デフォルトの電子メール アドレスは、Windows PowerShell を使用してオーバーライドできます。 これは、ユーザーが Office 365 の Exchange メールボックスを持っていない場合に便利です。

    

## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell の詳細情報

Windows PowerShell は、ユーザーと、ユーザーに許可されていることと許可されていないことを管理するためにあるということです。Windows PowerShell があれば、一元管理を使用して Office 365 を管理し、複数のタスクを抱えているときに、日常の仕事を簡素化することができます。Windows PowerShell を開始するには、これらのトピックを参照してください。
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)」をご覧ください。
  
## <a name="related-topics"></a>関連トピック

[ユーザーの会議 ID をリセットする](reset-a-conference-id-for-a-user-in-teams.md)
