---
title: Skype for Business Online でユーザーの会議 ID をリセットする
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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Skype for Business Online でユーザーの会議 ID をリセットし、会議の更新および移行ツールへのリンクを取得する手順について説明します。 '
ms.openlocfilehash: 24037de3849ae54920777636e7eb745671ae2f57
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237773"
---
# <a name="reset-a-conference-id-for-a-user-in-skype-for-business-online"></a>Skype for Business Online でユーザーの会議 ID をリセットする

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!NOTE]
> Microsoft Teams で会議 ID をリセットする方法の詳細については、「 [Microsoft Teams でユーザーの会議 ID をリセットする](/MicrosoftTeams/reset-a-conference-id-for-a-user-in-teams)」を参照してください。

動的な会議 ID は、発信者が会議にコールインするのに使用できるダイヤルイン番号と一緒に、会議出席依頼の下に含まれています。 ユーザーが電話番号をダイヤルするときに、発信者が会議に参加できるように、会議の自動応答は発信者にこの会議 ID の入力を求めます。
  
> [!NOTE]
> 会議プロバイダーが Microsoft の場合、ユーザーの会議 ID は [動的のみ] に設定されます。 これは変更できません。 会議 ID は、電話会議が有効にされる Skype for Business ユーザーにのみ自動的に設定されます。 

## <a name="resetting-the-conference-id-for-a-user"></a>ユーザーの会議 ID のリセット
   
1. [Skype for Business **センターで、[電話** 会議ユーザー]をクリックし、ユーザーを選択し、[操作] ウィンドウの [会議 ID] で [リセット]  >  を **クリックします**。 
    
2. [会議 **ID のリセット] ウィンドウで、[** はい] を **クリックします**。 A conference ID will be automatically created and an email sent to the user with the new conference ID. 既定では、メールはユーザーに送信されますが、オフにできます。
    
> [!NOTE]
> 会議 ID をリセットすると、新しい会議 ID を含むメールがユーザーに送信されます。 このメールは、プライマリ メール アドレス (多くの場合、ユーザーのメール アドレスまたはMicrosoft 365送信Office 365されます。 電子メールには、新しい会議 ID、既定のダイヤルイン電話番号、Skype for Business 会議更新ツールを使用して既存の会議を更新する手順が含まれている。 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a>他に必要な情報はありますか?

- [操作] ウィンドウでユーザーの [電子メールで会議情報を送信する] をクリックすると、会議 ID とダイヤルイン電話番号を含むメールですべての会議情報をユーザーに送信できます。 PIN は送信されません。
    
- 会議 ID には 7 桁の数字が含まれるので、Skype for Business 管理センターまたは会議の長さを変更Windows PowerShell。
    
- 会議 ID をリセットすると、新しい会議 ID が [ **電話会議 ID**] に一覧表示されます。
    
- 電話会議のユーザーの会議 ID は、[ユーザー] ページでユーザーを選択すると、[電話会議] の [操作] ウィンドウの下部に **表示** されます。
    
- 新しい会議 ID が作成されると、古い会議 ID を使用してダイヤルインすることはできなくなります。 既存の会議の出席依頼のスケジュールを変更して、新しい会議 ID を出席依頼に追加するように、ユーザーに通知してください。 ユーザーは、会議ツールSkype for Business既存の会議を更新できます。 会議更新ツールをダウンロード、インストール、実行する方法については、Skype for Businessを参照してください。
    
  - [Skype for Business Meeting Update Tool と Lync Meeting Update Tool](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)
    
  - [Skype for Business Online、会議移行ツール (64 ビット)](https://go.microsoft.com/fwlink/?LinkID=626047)
    
  - [Skype for Business Online、会議移行ツール (32 ビット)](https://www.microsoft.com/download/details.aspx?id=54079)
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell での管理方法について

- Windows PowerShell で行うのは、ユーザーを管理し、ユーザーに何を許可して何を禁止するかを管理することです。 Windows PowerShellでは、1 つの管理ポイントを使用して Microsoft 365 または Office 365 と Skype for Business Online を管理できます。複数のタスクを実行する場合は、毎日の作業を簡略化できます。 Windows PowerShell の使用を開始するには、次のトピックを参照してください。
    
  - [Windows PowerShell と Skype for Business Online の概要](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [PowerShell で使用する必要があるMicrosoft 365またはOffice 365理由](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
 
- Windows PowerShell多くのユーザーに対して一度に設定を変更する場合など、Microsoft 365 管理センターを使用する場合に限って、速度、シンプルさ、生産性に多くの利点があります。 次のトピックでこれらの利点について説明します。
    
  - [アプリを使用してMicrosoft 365またはOffice 365を管理Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
  - [Windows PowerShell による Skype for Business Online の管理](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a>関連項目

[電話会議の PIN をリセットする](reset-the-audio-conferencing-pin.md)
