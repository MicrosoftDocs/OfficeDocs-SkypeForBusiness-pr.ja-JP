---
title: ビジネス オンラインの Skype のユーザーの会議 ID をリセットします。
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
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'ユーザーをリセットする手順の Skype での会議 ID のビジネス オンラインでは、会議の会議出席依頼の更新と移行ツールへのリンクを取得するかを説明します。 '
ms.openlocfilehash: d569dfb015db5cea79c57233ba455adfd90a3182
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23887547"
---
# <a name="reset-a-conference-id-for-a-user-in-skype-for-business-online"></a>ビジネス オンラインの Skype のユーザーの会議 ID をリセットします。

> [!NOTE]
> Microsoft Teams で会議 ID をリセットする方法の詳細については、「 [Microsoft Teams でユーザーの会議 ID をリセットする](/MicrosoftTeams/reset-a-conference-id-for-a-user-in-teams)」を参照してください。

動的な会議 ID は、発信者が会議にコールインするのに使用できるダイヤルイン番号と一緒に、会議出席依頼の下に含まれています。 ユーザーが電話番号をダイヤルするときに、発信者が会議に参加できるように、会議の自動応答は発信者にこの会議 ID の入力を求めます。
  
> [!NOTE]
> 会議プロバイダーが Microsoft の場合、ユーザーの会議 ID がデフォルトで「動的のみ」に設定されます。 残念ながら、Skype for Business 管理センターで会議 ID を変更できる機能、または Windows Powershell を使用して動的会議 ID を静的会議 ID に変更する機能は、現在サポートされていないため、ありません。 会議 ID は、電話会議が有効にされる Skype for Business ユーザーにのみ自動的に設定されます。 

## <a name="resetting-the-conference-id-for-a-user"></a>ユーザーの会議 ID をリセットします。
   
1. **ビジネス管理センターの Skype**では、[**電話会議**] をクリックします > **ユーザー**ユーザーを選択し、し、[操作] ウィンドウの [**会議 ID** ] の [**リセット**] をクリックします。
    
2. A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled. A conference ID will be automatically created and an email sent to the user with the new conference ID. 既定では、ユーザーに電子メールが送信されますが、これを無効にできます。
    
> [!NOTE]
> 会議 ID をリセットすると、新しい会議 ID を記載したメールがユーザーに送信されます。このメールはプライマリ メール アドレスに送信されます。ほとんどの場合は、Office 365 のメールボックスに送信されます。新しい会議 ID、既定のダイヤルイン電話番号、Skype for Business Meeting Update Tool を使って既存の会議を更新する方法がメールに記載されています。 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a>他に必要な情報はありますか?

- 操作ウィンドウでのユーザーの [**電子メール経由での会議の情報を送信**] をクリックして、会議 ID とダイヤルインの電話番号を含む電子メールでユーザーにすべての会議の情報を送信できます。 PIN は送信されません。
    
- 会議 ID が 7 桁の数字を含めるし、ビジネス管理センターまたは Windows PowerShell を使用して、Skype では、その長さを変更することはできません。
    
- 会議 ID をリセットすると、新しい会議 ID が [ **電話会議 ID**] に一覧表示されます。
    
- [**ユーザー** ] ページで、ユーザーを選択すると、**オーディオ会議**の下にある操作ウィンドウの下部にあるユーザーが電話会議の会議 ID を表示できます。
    
- You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. The users can use Skype for Business Meeting Migration Tool to update their existing meetings. ユーザーは、ビジネス会議ツールの Skype を使用して、既存の会議を更新します。 ダウンロード、インストール、および、Skype をビジネス会議の更新ツールを実行する方法を参照してください。
    
  - [Skype for Business Meeting Update Tool と Lync Meeting Update Tool](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)
    
  - [Skype for Business Online、会議移行ツール (64 ビット)](https://go.microsoft.com/fwlink/?LinkID=626047)
    
  - [Skype for Business Online、会議移行ツール (32 ビット)](https://www.microsoft.com/en-us/download/details.aspx?id=54079)
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell で管理する方法

- Windows PowerShell で行うのは、ユーザーを管理し、ユーザーに何を許可して何を禁止するかを管理することです。Windows PowerShell を利用すると、Office 365 と Skype for Business Online の管理を 1 か所で行うことができるので、複数のタスクを担当する管理者の日常業務を単純化できます。Windows PowerShell の使用を開始するには、次のトピックを参照してください。
    
  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell には、ただ Office 365 管理センターを使用するだけではなく、速度、単純さ、生産性において多くの利点があります。次のトピックでこれらの利点について説明します。
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [クイック リファレンス: Windows PowerShell を使用した一般的な Lync Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>See also

[オーディオ会議の暗証番号 (pin) をリセットします。](reset-the-audio-conferencing-pin.md)
