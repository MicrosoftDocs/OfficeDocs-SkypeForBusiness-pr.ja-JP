---
title: Microsoft Teams で PIN を使用せずに電話で電話会議を開始する
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d5b1f775-d7ed-4d30-853a-1d49f81e8fde
ms.tgt.pltfrm: cloud
ms.service:
- -msteams
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
description: '匿名の発信者が Teams 管理センターから会議に参加することを有効または無効にする方法を説明します。 '
ms.openlocfilehash: 4aec566b165385a111162641f233cd1b1e3027f4
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2018
ms.locfileid: "25014108"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-microsoft-teams"></a>Microsoft Teams で PIN を使用せずに電話で電話会議を開始する

ユーザーが会議にダイヤルインしたのに、Microsoft Teams 会議の開催者が会議を開始していないため、保留音の音楽を聞きながら会議のロビーで待たされると、不快な思いをしてしまう可能性があります。 
  
会議の開催者を呼び出す場合、会議出席依頼には、既定では、会議を開始するのには、暗証番号 (pin) が必要です。 できますを設定することをだれでも会議にダイヤルイン会議を開始するのには暗証番号 (pin) には求められません。 有効にするか、1 人のユーザーに対してこの設定を無効にするのには、管理センターを使用できます。
  
誰かマイクロソフトのチームのアプリケーションから会議が開始された場合、暗証番号 (pin) は会議の開催者のために必要はありません。 PIN が必要であるのは、会議の開催者が電話で自分の会議に参加する場合のみです。 会議の暗証番号 (pin) は、**オーディオ会議**のライセンスが割り当てられている音声会議が有効になっていると、オーディオのユーザーに送信されます。 [オーディオ会議の情報を持つユーザーに電子メールを送信](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)し、[ユーザーが電話会議の設定を変更するときに自動的に送信される電子メール](emails-sent-to-users-when-their-settings-change-in-teams.md)を参照してください。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a>匿名の発信者の会議への参加を有効または無効にする

![teams-logo-30x30.png](media/teams-logo-30x30.png) **Microsoft Teams と Skype for Business 管理センターを使用する: **

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
    
  - 会議が開始されていない場合 (は誰もまだ会議で): 開催者は、彼女と彼女がするメッセージは表示されません、暗証番号 (pin) の場合、呼び出し元は要求されません。 開催者の設定がオフになっているため、会議が始まり、匿名の発信者が会議に参加します。
    
  - 会議が既に開始している場合 (会議に既に他のユーザーがいる場合): 発信者に開催者であるかどうかを確認するメッセージが表示されることはなく、PIN の入力も求められません。会議は既に始まっていて、発信者はその会議に参加します。
    
## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell の詳細情報

Windows PowerShell は、ユーザーと、ユーザーに許可されていることと許可されていないことを管理するためにあるということです。Windows PowerShell があれば、一元管理を使用して Office 365 を管理し、複数のタスクを抱えているときに、日常の仕事を簡素化することができます。Windows PowerShell を開始するには、これらのトピックを参照してください。
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)」をご覧ください。
  
## <a name="related-topics"></a>関連トピック

[Office 365 での電話会議を使用または購入する](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
