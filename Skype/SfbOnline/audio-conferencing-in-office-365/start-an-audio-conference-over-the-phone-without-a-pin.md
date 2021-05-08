---
title: Skype for Business Online で PIN を使用せずに電話で電話会議を開始する
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d5b1f775-d7ed-4d30-853a-1d49f81e8fde
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: '匿名の発信者による Skype for Business 管理センターからの会議への参加や PowerShell スクリプトの使用を有効または無効にする方法を説明します。 '
ms.openlocfilehash: 655f61c449554a9044095a5b8ef8bd8ef2940bc4
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237593"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-skype-for-business-online"></a>Skype for Business Online で PIN を使用せずに電話で電話会議を開始する

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> Microsoft Teams で PIN を使用せずに電話会議を開始する場合の詳細については、「[Microsoft Teams で PIN を使用せずに 電話で電話会議を開始する](/MicrosoftTeams/start-an-audio-conference-over-the-phone-without-a-pin-in-teams)」をご覧ください。

Skype for Business 会議の開催者が会議を開始しないので、会議にダイヤルインするユーザーが音楽を聴いて会議のロビーで開催されるのは、不満な場合があります。 
  
会議の開催者が会議にコールインする場合、既定では、会議を開始するために PIN が必要です。 誰でも会議にダイヤルインし、PIN で会議を開始するように求めららなく設定できます。 Skype for Business 管理センターを使用すると、この設定を 1 人のユーザーに対して有効または無効にすることができます。
  
他のユーザーが自分のアプリから会議を開始した場合、会議の開催者に PIN はSkype for Businessはありません。 PIN が必要であるのは、会議の開催者が電話で自分の会議に参加する場合のみです。 会議の PIN は、電話会議ライセンスが割り当て済みで電話会議が有効になると、音声ユーザーに送信されます。 「 [電話会議の設定が変](send-an-email-to-a-user-with-their-dial-in-information.md) わると自動的にユーザーに送信される電話会議情報とメールをユーザーに送信する [」を参照してください](emails-sent-to-users-when-their-settings-change.md)。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a>匿名の発信者の会議への参加を有効または無効にする
    
1. 管理センター **Skype for Business左側** のナビゲーションで、[電話会議ユーザー]**に移動**  >  **します**。 
    
2. 一覧でユーザーを選択し、[操作] ウィンドウで [編集] を **クリックします**。 
    
3. ユーザーのプロパティ ページの [会議オプション] で、[認証されていない発信者を会議の最初のユーザーに許可する] をオンまたは **オフにします。ない場合は、認証されたユーザーが に参加するまでロビーで待機します**。
    
4. **[保存]** をクリックします。 


    
 **PowerShell Windows使用する**
  
- 次のコマンドを実行します。 
    
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true | $false
  ```

## <a name="what-else-should-you-know"></a>その他の情報

- PIN をリセットする場合は、「電話会議 PIN をリセット [する」を参照してください](reset-the-audio-conferencing-pin.md)。
    
- 匿名アクセス (会議を開始するために PIN を必要としない) が無効になっている場合:
    
  - 会議が開始されていない場合 (会議にまだ誰もいない場合): 開催者の場合、発信者にメッセージが表示されます。「はい」と言った場合は、PIN の入力を求めるメッセージが表示され、PIN を入力すると、会議が開始され、ユーザーが会議に参加します。
    
  - 会議が既に開始されている場合 (他のユーザーが既に会議に参加している場合): 発信者に開催者の場合はメッセージが表示されません。PIN の入力を求めるメッセージは表示されません。会議が既に開始され、呼び出し元が会議に参加します。
    
- 匿名アクセス (会議を開始するために PIN を必要としない) が有効になっている場合:
    
  - 会議が開始されていない場合 (まだ会議に誰もいない場合): 発信者に開催者の場合はメッセージが表示されません。PIN の入力を求めるメッセージは表示されません。 開催者の設定がオフになっているため、会議が始まり、匿名の発信者が会議に参加します。
    
  - 会議が既に開始されている場合 (他のユーザーが既に会議に参加している場合):発信者に開催者の場合はメッセージが表示されません。PIN の入力を求めるメッセージは表示されません。会議は既に開始され、発信者はその会議に参加します。
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell での管理方法について

- 時間を節約したり、複数のユーザーに対してこの動作を自動化したりするには、[Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) コマンドレットを使用できます。
    
- Windows PowerShell の場合、Skype for Business Online はユーザーの管理と、ユーザーが許可されている操作や許可されていない操作の管理に使います。 このWindows PowerShell、1 つの管理Microsoft 365またはOffice 365を管理し、複数のタスクを実行する場合に毎日の作業を簡略化できます。 Windows PowerShell の使用を開始するには、次のトピックを参照してください。
    
  - [PowerShell で使用する必要があるMicrosoft 365またはOffice 365理由](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [アプリを使用してMicrosoft 365またはOffice 365を管理Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- 多くのユーザーの設定を同時に変更するときなどは、Microsoft 365 管理センターのみを使用するよりも、Windows PowerShell を使用した方が、速度、わかりやすさ、生産性の点で多くのメリットがあります。次のトピックで、これらの利点を説明します。 
    
  - [Windows PowerShell と Skype for Business Online の概要](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    [Windows PowerShell による Skype for Business Online の管理](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > Skype for Business Online 用の Windows PowerShell モジュールがあれば、Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成できます。このモジュールは、64 ビット版のコンピューターでのみサポートされており、「[Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688)」の Microsoft ダウンロード センターからダウンロードできます。
  
## <a name="related-topics"></a>関連トピック

[電話会議を試用または購入するには、Microsoft 365またはOffice 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
