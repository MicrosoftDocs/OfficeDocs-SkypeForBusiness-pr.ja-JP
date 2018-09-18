---
title: Microsoft Teams でユーザーの会議 ID をリセットする
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
description: 'Microsoft Teams でユーザーの会議 ID をリセットする手順と、会議の更新および移行のツールへのリンクを取得する手順を説明します。 '
ms.openlocfilehash: 4e338e5ad00792a48e0a6c9e0791c0c5e4b759ac
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23887853"
---
# <a name="reset-a-conference-id-for-a-user-in-microsoft-teams"></a>Microsoft Teams でユーザーの会議 ID をリセットする

動的な会議 ID は、発信者が会議にコールインするのに使用できるダイヤルイン番号と一緒に、会議出席依頼の下に含まれています。 ユーザーが電話番号をダイヤルするときに、発信者が会議に参加できるように、会議の自動応答は発信者にこの会議 ID の入力を求めます。
  
> [!NOTE]
> お使いの電話会議プロバイダーが Microsoft の場合、ユーザーの会議 ID は既定で動的のみに設定されます。 これを変更して静的にすることは、現在サポート対象外のため、できません。 会議 ID は、電話会議で有効になっている Microsoft Teams ユーザーに対してのみ、自動的に設定されます。 


## <a name="resetting-the-conference-id-for-a-user"></a>ユーザーのために会議 ID をリセットする

1. 左側のナビゲーションで、[**ユーザー**] をクリックしてから、空いているユーザーのリストからユーザーを選択します。

2. ページの上部で、[**編集**] をクリックします。

3. [**電話会議**] の下で、[**会議 ID のリセット**] をクリックします。

2. [**会議 ID のリセット**] ウィンドウで、[**リセット**] をクリックします。 会議 ID は自動的に作成され、新しい会議 ID が記載されたメールがユーザーに送信されます。 既定では、メールはユーザーに送信されます。ただし、この動作はオフにすることができます。   

    
> [!NOTE]
> 会議 ID をリセットした後、新しい会議 ID が記載されたメールがユーザーに送信されます。 このメールはプライマリ メール アドレスに送信され、多くの場合は、Office 365 のメールボックスに送られます。 メールには、新しい会議 ID、既定のダイヤルイン電話番号、既存の会議を更新するための手順が含まれています。 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a>その他の情報

- [**電話会議**] セクションのユーザーについて [**電話会議情報をメールで送信**] をクリックすると、会議 ID とダイヤルイン電話番号を含んでいるメールで、会議に必要なすべての情報をユーザーに送信することができます。 このメールでは PIN は送信されません。
    
- 会議 ID は 7 桁の値です。この長さを変更することはできません。
    
- 会議 ID をリセットすると、新しい会議 ID が [**会議 ID**] に一覧表示されます。
    
- 新しい会議 ID が作成されると、発信者は以前の会議 ID を使用することができなくなります。 ユーザーに対して、新しい会議 ID が招待状に追加されるようにするために、既存の会議の招待をスケジュールし直すことを通知する必要があります。 

## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell の詳細情報

Windows PowerShell は、ユーザーと、ユーザーに許可されていることと許可されていないことを管理するためにあるということです。Windows PowerShell があれば、一元管理を使用して Office 365 を管理し、複数のタスクを抱えているときに、日常の仕事を簡素化することができます。Windows PowerShell を開始するには、これらのトピックを参照してください。
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)」をご覧ください。
    
## <a name="related-topics"></a>関連トピック

[電話会議の PIN をリセットする](reset-the-audio-conferencing-pin-in-teams.md)
