---
title: "ユーザーの会議 ID をリセットする"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 6e12242c-55f7-4bf4-90d7-0f36c0326b8e
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'Learn the steps to reset a user''s meeting conference ID, and get links to meeting update and migration tools. '
ms.openlocfilehash: ba76f3afb5d92dadc66d09e07aa16d3589f57e4d
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2018
---
# <a name="reset-a-conference-id-for-a-user"></a>ユーザーの会議 ID をリセットする

組織は、会議 Id を動的に有効になっていない、静的な会議 ID はプロバイダーと Microsoft を使用してオーディオ会議のため、Skype のビジネスまたはマイクロソフトのチームのユーザーが有効になっているときに自動的に作成します。 この会議 ID では、会議出席依頼と会議へのコールを呼び出し元で使用できるダイヤルインの電話番号の下に含まれています。 ユーザーは、電話番号をダイヤルするとき、会議のための自動応答は、会議に出席することができますので、この会議 ID を入力するのには呼び出し元を求められます。
  
> [!NOTE]
> 会議プロバイダーがマイクロソフトの場合は、ユーザーの会議 Id が既定で動的なだけに設定されます。 残念ながら、ビジネス管理センターまたは Windows Powershell を使用して Skype でそれを変更することはできません。 マイクロソフト サポートに連絡する必要があります。 
  
Skype for Business 管理センターおよび Windows PowerShell を使用すると、ユーザーの会議 ID を表示、変更、リセットすることができます。 職場または学校のアカウントを使用して、Office 365 にサインインします。 場合に割り当てる静的な会議 Id を[ここ](using-audio-conferencing-dynamic-ids-in-your-organization.md)にではなく動的です。
  
会議 Id はのみ自動的に設定だけ Skype 音声会議を有効にするビジネスおよびマイクロソフトのチームのユーザーの Microsoft を使用して、オーディオ会議プロバイダーとしてです。 サード ・ パーティ製の音声会議プロバイダー (ACP) を使用してユーザーのための会議 ID をリセットする場合は、[プロパティ] ページで、ユーザーの会議 ID を手動で入力する必要があります。
  
## <a name="resetting-the-conference-id-for-a-user"></a>ユーザーの会議 ID をリセットします。

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. Go to the **Office 365 admin center** > **Skype for Business**.
    
3. **ビジネス管理センターの Skype**では、[**電話会議**] をクリックします > **ユーザー**ユーザーを選択し、し、[操作] ウィンドウの [**会議 ID** ] の [**リセット**] をクリックします。
    
4. A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled. A conference ID will be automatically created and an email sent to the user with the new conference ID. 既定では、ユーザーに電子メールが送信されますが、これを無効にできます。
    
    > [!NOTE]
    > 会議 ID をリセットすると、新しい会議 ID を記載したメールがユーザーに送信されます。このメールはプライマリ メール アドレスに送信されます。ほとんどの場合は、Office 365 のメールボックスに送信されます。新しい会議 ID、既定のダイヤルイン電話番号、Skype for Business Meeting Update Tool を使って既存の会議を更新する方法がメールに記載されています。 
  
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

[ユーザーの電話会議の PIN をリセットする](reset-the-audio-conferencing-pin-for-a-user.md)
