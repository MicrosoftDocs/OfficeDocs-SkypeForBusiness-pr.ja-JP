---
title: Microsoft Teams で PIN を使用せずに電話で電話会議を開始する
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d5b1f775-d7ed-4d30-853a-1d49f81e8fde
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
description: '匿名の発信者が Teams 管理センターから会議に参加することを有効または無効にする方法を説明します。 '
ms.openlocfilehash: 5f2dbd84b71058e75b710f37994e41c9adb488ef
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32227096"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-microsoft-teams"></a>Microsoft Teams で PIN を使用せずに電話で電話会議を開始する

ユーザーが会議にダイヤルインしたのに、Microsoft Teams 会議の開催者が会議を開始していないため、保留音の音楽を聞きながら会議のロビーで待たされると、不快な思いをしてしまう可能性があります。 
  
会議の開催者が会議にダイヤルインする場合、既定では、会議を開始するために PIN が必要です。 どのユーザーが会議にダイヤルインしても会議の開始で PIN を求められることがないように、会議を設定することができます。 管理センターを使用して、この設定を 1 人のユーザーに対して有効または無効にすることができます。
  
あるユーザーが Microsoft Teams アプリから会議を開始した場合、会議の開催者に PIN が要求されることはありません。 PIN が必要になるのは、会議の開催者が電話で自分の会議に参加する場合のみです。 ユーザーに**電話会議**ライセンスが割り当てられているか、ユーザーが電話会議会議で有効である場合、会議の PIN がその電話会議ユーザーに送信されます。 「[電話会議の情報が記載されたメールをユーザーに送信する](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)」および「[電話会議の設定が変更されたときにユーザーに自動的に送信されるメール](emails-sent-to-users-when-their-settings-change-in-teams.md)」をご覧ください。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a>匿名の発信者の会議への参加を有効または無効にする

![チーム ・ ロゴ ・ 30x30.png](media/teams-logo-30x30.png) **、マイクロソフトのチーム管理センターを使用して**

1. 左側のナビゲーションで [**ユーザー**] をクリックします。 

2. リスト内でユーザーを選択し、ページ上部にある [**編集**] をクリックします。 

3. [**電話会議**] の隣で、[**編集**] をクリックします。

4. [**電話会議**] ペインで、[**Unauthenticated callers can be the first person in a meeting (認証されてない発信者を会議の最初のユーザーにすることができる)**] を有効または無効にします。
    
4. [**保存**] をクリックします。 

**Windows PowerShell を使用する**
  
詳細については、[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)をご覧ください。

## <a name="what-else-should-you-know"></a>その他の情報

- PIN をリセットする必要がある場合は、「[電話会議の PIN をリセットする](reset-the-audio-conferencing-pin-in-teams.md)」をご覧ください。
    
- 匿名アクセスが有効、または会議の開始に PIN が必要でない設定になっている場合:
    
  - 会議がまだ開始していない場合 (会議にまだ誰もいない場合): 発信者には開催者であるかどうかを確認するメッセージが表示されます。発信者が「はい」と答えると、PIN の入力を求められます。PIN を入力した後、会議が始まり、そのユーザーが会議に参加します。
    
  - 会議が既に開始している場合 (会議に既に他のユーザーがいる場合): 発信者に開催者であるかどうかを確認するメッセージが表示されることはなく、PIN の入力も求められません。会議は既に始まっていて、発信者はその会議に参加します。
    
- 匿名アクセスが無効、または会議の開始に PIN が必要な設定になっている場合:
    
  - 会議がまだ開始していない場合 (会議にまだ誰もいない場合): 発信者に開催者であるかどうかを確認するメッセージが表示されることはなく、PIN の入力も求められません。 開催者の設定がオフになっているため、会議が始まり、匿名の発信者が会議に参加します。
    
  - 会議が既に開始している場合 (会議に既に他のユーザーがいる場合): 発信者に開催者であるかどうかを確認するメッセージが表示されることはなく、PIN の入力も求められません。会議は既に始まっていて、発信者はその会議に参加します。
    
## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell の詳細情報

Windows PowerShell は、ユーザーと、ユーザーに許可されていることと許可されていないことを管理するためにあるということです。Windows PowerShell があれば、一元管理を使用して Office 365 を管理し、複数のタスクを抱えているときに、日常の仕事を簡素化することができます。Windows PowerShell を開始するには、これらのトピックを参照してください。
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)」をご覧ください。
  
## <a name="related-topics"></a>関連トピック

[Office 365 での電話会議を使用または購入する](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
