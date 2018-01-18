---
title: "ユーザーの会議 ID をリセットする"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 6e12242c-55f7-4bf4-90d7-0f36c0326b8e
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'Learn the steps to reset a user''s meeting conference ID, and get links to meeting update and migration tools. '
ms.openlocfilehash: 2f2cbd6efa61e05defb17ef05f86fd9a228987ac
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/15/2017
---
# <a name="reset-a-conference-id-for-a-user"></a>ユーザーの会議 ID をリセットする

組織は、会議 Id を動的に有効になっていない、静的な会議 ID はプロバイダーと Microsoft を使用してオーディオ会議のため、Skype のビジネスまたはマイクロソフトのチームのユーザーが有効になっているときに自動的に作成します。 この会議 ID では、会議出席依頼と会議へのコールを呼び出し元で使用できるダイヤルインの電話番号の下に含まれています。 ユーザーは、電話番号をダイヤルするとき、会議のための自動応答は、会議に出席することができますので、この会議 ID を入力するのには呼び出し元を求められます。
  
> [!NOTE]
> 会議プロバイダーがマイクロソフトの場合は、ユーザーの会議 Id が既定で動的なだけに設定されます。 残念ながら、ビジネス管理センターまたは Windows Powershell を使用して Skype でそれを変更することはできません。 マイクロソフト サポートに連絡する必要があります。 
  
静的の Id は、組織内のユーザーはランダムな番号を覚えておく必要があるときに使用します。特定の番号を選択したり、覚えやすいものを使用することができます。 動的会議 Id を使用する場合各会議ユーザのスケジュールは割り当てられます会議の一意の id。 場合に割り当てる静的な会議 Id を[ここ](using-audio-conferencing-dynamic-ids-in-your-organization.md)にではなく動的です。
  
会議 Id はのみ自動的に設定だけ Skype 音声会議を有効にするビジネスおよびマイクロソフトのチームのユーザーの Microsoft を使用して、オーディオ会議プロバイダーとしてです。 サード ・ パーティ製の音声会議プロバイダー (ACP) を使用してユーザーのための会議 ID をリセットする場合は、[プロパティ] ページで、ユーザーの会議 ID を手動で入力する必要があります。
  
## <a name="resetting-the-conference-id-for-a-user"></a>ユーザーの会議 ID をリセットします。

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. **Office 365 管理センター**を参照して > **ビジネス用の Skype**です。
    
3. **ビジネス管理センターの Skype**では、[**電話会議**] をクリックします > **ユーザー**ユーザーを選択し、し、[操作] ウィンドウの [**会議 ID** ] の [**リセット**] をクリックします。
    
4. **会議 ID をリセットしますか?** ] ウィンドウで、[**はい**] をクリックします。 会議 ID が自動的に作成し、新しい会議 ID を持つユーザーに送信する電子メール 既定では、ユーザーに電子メールが送信されますが、これを無効にできます。
    
    > [!NOTE]
    > 会議 ID をリセットすると、新しい会議 ID を記載したメールがユーザーに送信されます。このメールはプライマリ メール アドレスに送信されます。ほとんどの場合は、Office 365 のメールボックスに送信されます。新しい会議 ID、既定のダイヤルイン電話番号、Skype for Business Meeting Update Tool を使って既存の会議を更新する方法がメールに記載されています。 
  
## <a name="what-else-should-i-know"></a>他に必要な情報はありますか?

- 操作ウィンドウでのユーザーの [**電子メール経由での会議の情報を送信**] をクリックして、会議 ID とダイヤルインの電話番号を含む電子メールでユーザーにすべての会議の情報を送信できます。 暗証番号 (pin) を送信しないことです。
    
- 会議 ID が 7 桁の数字を含めるし、ビジネス管理センターまたは Windows PowerShell を使用して、Skype では、その長さを変更することはできません。
    
- 会議 ID をリセットすると、新しい会議 ID が [ **電話会議 ID**] に一覧表示されます。
    
- [**ユーザー** ] ページで、ユーザーを選択すると、**オーディオ会議**の下にある操作ウィンドウの下部にあるユーザーが電話会議の会議 ID を表示できます。
    
- 新しい会議 ID が作成されると、呼び出し元が古い会議 ID を使用できません。 ミーティングの招待新しい会議 ID が、招待状に追加されることを確認するのには、既存のスケジュールを変更するのにはユーザーに通知する必要があります。 ユーザーは、ビジネス会議ツールの Skype を使用して、既存の会議を更新します。 ダウンロード、インストール、および、Skype をビジネス会議の更新ツールを実行する方法を参照してください。
    
  - [Skype for Business Meeting Update Tool と Lync Meeting Update Tool](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)
    
  - [Skype for Business Online、会議移行ツール (64 ビット)](https://go.microsoft.com/fwlink/?LinkID=626047)
    
  - [Skype for Business Online、会議移行ツール (32 ビット)](https://www.microsoft.com/en-us/download/details.aspx?id=54079)
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell で管理する方法

- Windows PowerShell で行うのは、ユーザーを管理し、ユーザーに何を許可して何を禁止するかを管理することです。Windows PowerShell を利用すると、Office 365 と Skype for Business Online の管理を 1 か所で行うことができるので、複数のタスクを担当する管理者の日常業務を単純化できます。Windows PowerShell の使用を開始するには、次のトピックを参照してください。
    
  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Office 365 の PowerShell を使用する必要がある理由](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell には、ただ Office 365 管理センターを使用するだけではなく、速度、単純さ、生産性において多くの利点があります。次のトピックでこれらの利点について説明します。
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>関連トピック

[ユーザーのオーディオ会議の PIN をリセットします。](reset-the-audio-conferencing-pin-for-a-user.md)
