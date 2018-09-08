---
title: マイクロソフトのチーム内のユーザーの会議 ID をリセットします。
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6e12242c-55f7-4bf4-90d7-0f36c0326b8e
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
description: 'ユーザーをリセットする手順は、マイクロソフト チームの会議 ID を会議の会議出席依頼の更新と移行ツールへのリンクを取得するかを説明します。 '
ms.openlocfilehash: 4e338e5ad00792a48e0a6c9e0791c0c5e4b759ac
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23887853"
---
# <a name="reset-a-conference-id-for-a-user-in-microsoft-teams"></a>マイクロソフトのチーム内のユーザーの会議 ID をリセットします。

動的な会議 ID は、発信者が会議にコールインするのに使用できるダイヤルイン番号と一緒に、会議出席依頼の下に含まれています。 ユーザーが電話番号をダイヤルするときに、発信者が会議に参加できるように、会議の自動応答は発信者にこの会議 ID の入力を求めます。
  
> [!NOTE]
> 会議プロバイダーが Microsoft の場合、ユーザーの会議 ID がデフォルトで「動的のみ」に設定されます。 残念ながら、これは、静的になるように変更することはありませんサポートされていません。 会議 Id は、マイクロソフトのチームのユーザーが電話会議を有効になっているだけ自動的に設定されています。 


## <a name="resetting-the-conference-id-for-a-user"></a>ユーザーの会議 ID をリセットします。

1. 左側のナビゲーションでは、**ユーザー**] をクリックしてで使用可能なユーザーの一覧からユーザーを選択します。

2. ページの上部で、[**編集**] をクリックします。

3. **オーディオ会議**の下には、**会議 ID のリセット**をクリックします。

2. **会議 ID のリセット**] ウィンドウで、[**リセット**] をクリックします。 A conference ID will be automatically created and an email sent to the user with the new conference ID. 既定では、ユーザーに電子メールが送信されますが、これを無効にできます。   

    
> [!NOTE]
> 会議 ID をリセットした後は、新しい会議 ID を持つ電子メールをユーザーに送信されます。 この送信されます、プライマリ電子メール アドレスに、多くの場合、Office 365 メールボックスです。 電子メールには、新しい会議 ID、既定のダイヤルに電話番号と既存のミーティングを更新するための手順が含まれています。 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a>他に必要な情報はありますか?

- **オーディオ会議**セクション内のユーザーの [**電子メールで会議の情報を送信**] をクリックして、会議 ID とダイヤルインの電話番号を含む電子メールでユーザーにすべての会議の情報を送信できます。 PIN は送信されません。
    
- 会議 ID が 7 桁の数字を含めるし、その長さを変更することはできません。
    
- 会議 ID をリセットすると、新しい会議 ID が [ **電話会議 ID**] に一覧表示されます。
    
- You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. The users can use Skype for Business Meeting Migration Tool to update their existing meetings. 

## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell の詳細情報

Windows PowerShell は、ユーザーと、ユーザーに許可されていることと許可されていないことを管理するためにあるということです。Windows PowerShell があれば、一元管理を使用して Office 365 を管理し、複数のタスクを抱えているときに、日常の仕事を簡素化することができます。Windows PowerShell を開始するには、これらのトピックを参照してください。
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Windows PowerShell の詳細については、[マイクロソフト チームの PowerShell の参照](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)の詳細についてを参照してください。
    
## <a name="related-topics"></a>関連トピック

[オーディオ会議の暗証番号 (pin) をリセットします。](reset-the-audio-conferencing-pin-in-teams.md)
