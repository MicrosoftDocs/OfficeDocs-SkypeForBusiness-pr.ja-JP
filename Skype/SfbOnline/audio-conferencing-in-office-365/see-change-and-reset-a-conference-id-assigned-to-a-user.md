---
title: "表示、変更、およびユーザーに割り当てられている電話会議 ID をリセットします。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 77d36233-2aab-4802-ba9c-e9a8885ea643
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
description: "Skype for Business のユーザーに会議 ID を割り当てる方法と、どのような会議 ID パラメーターをする必要があります。 "
ms.openlocfilehash: f98257892c219e2777c52aefb3b2fd89bfb53710
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="see-change-and-reset-a-conference-id-assigned-to-a-user"></a>表示、変更、およびユーザーに割り当てられている電話会議 ID をリセットします。

Skype for Business または Microsoft チームのユーザーには、会議 ID が、Office 365 での電話会議用に設定し、電話会議プロバイダーとして Microsoft を使用して自動的に割り当てられています。割り当てられている電話会議 ID 静的または動的でき、会議がスケジュールされている場合は、会議の出席依頼の送信します。
  
静的な Id は、組織内のユーザーをランダムな番号を保存したくない場合に使用します。特定の番号を選択したり、覚えやすいものを使用することができます。動的会議 Id を使用する場合各会議ユーザーのスケジュールが取得割り当て会議の一意の id。場合は、割り当てる静的会議 Id、[ここ](using-audio-conferencing-dynamic-ids-in-your-organization.md)ではなく動的します。
  
静的会議 ID が自動的に作成され、ユーザーに割り当てられているがありますか、ユーザーが使用するし、特定の数を設定するユーザーに、会議 ID が喪失したか、思い出せない場合**Skype for Business 管理センター**と Windows PowerShell を使用するには、表示、変更、および、会議 ID をリセットするには
  
メール、会議 ID と既定電話会議の電話番号、ユーザーに送信されます。 または場合、会議 ID をリセットする別のメールが送信されますが、会議 ID、PIN いないに含まれています。
  
## <a name="view-and-change-conference-ids"></a>表示して、会議 Id を変更します。

### <a name="to-view-the-conference-id"></a>電話会議 ID を表示するには

自分の会議 ID を表示し、ユーザーに送信できます。
  
1. 職場または学校のアカウントで Office 365 にサインインします。
    
2. **Office 365 管理センター**に移動 > **Skype for Business**します。
    
3. **Skype for Business 管理センター**で> **電話会議** > **ユーザー**会議の id 必要なユーザーを選択。
    
4. [アクション] ページで、[**電話会議 ID**を確認します。
    
    > [!TIP]
    > すべての会議情報を**ユーザー** ] ページでユーザーを選択した後に**会議情報を電子メールで送信する**リンクをクリックして、会議 ID とオーディオの電話番号を含むメール内のユーザーに送信できます。
  
    ユーザーの会議 ID を表示するのには、Windows PowerShell を使うことができます。これを行うには、次のコマンドを実行します。
    
  ```
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"  
  ```

    [Get-csonlinedialinconferencinguser](https://go.microsoft.com/fwlink/?LinkId=617693 )コマンドレットの詳細を参照してください。
    
### <a name="to-assign-or-change-the-conference-id"></a>割り当てるか、会議 ID を変更するには

割り当てる場合、たとえば、覚えやすい会議 ID を特定のユーザーの会議 ID を変更したりできます。

  > [!NOTE]
  > Skype for Business 管理センターを使用すると、自動的に作成されている会議 ID を編集することはできませんが、編集または変更する設定した会議 ID に Windows PowerShell を使用することができます。 
     
編集または変更するユーザーの会議 ID を実行します。
    
  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ConferenceId 8271964
  ```

  > [!TIP]
  > 会議 ID が 7 つの数字を含める必要があり、Skype for Business 管理センター、または Windows PowerShell を使用してで変更することはできません。 
  
### <a name="to-reset-the-conference-id"></a>電話会議 ID をリセットするには

ユーザーの会議 ID をリセットする場合は、たとえば、忘れた場合。
  
1. 職場または学校のアカウントで Office 365 にサインインします。
    
2. **Office 365 管理センター**に移動 > **Skype for Business**します。
    
3. **Skype for Business 管理センター**で> **電話会議** > **ユーザー**の場合は、操作ウィンドウの [**電話会議 ID**を**リセット**] をクリックします。
    
4. **会議 ID をリセットですか?**ウィンドウで、[**はい**] をクリックします。会議 ID が自動的に作成し、新しい会議 ID を持つユーザーに送信されたメール
    
    Windows PowerShell を使用して、ユーザーの会議 ID をリセットできます。これを行うには、次のコマンドを実行します。
    
  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ResetLeaderPIN 8271964
  ```

## <a name="what-else-should-you-know"></a>他かする必要がありますか。

   > [!IMPORTANT]
   >  新しい会議 ID を作成または再設定する 1 つは、古い会議 ID 発信者では使用できません。既存ように招待状に ID が追加された新しい会議出席依頼を会議のスケジュールを変更するユーザーに通知する必要があります。ユーザーは、Skype for Business 会議の移行ツールを使用して、既存の会議を更新することができます。ダウンロード、インストール、およびツールを実行する方法を参照してください: [skype for Business と Lync Meeting Update Tool](http://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)、 [Skype for Business Online、会議の移行ツール (64 ビット)](http://go.microsoft.com/fwlink/?LinkID=626047)、および[Skype for Business Online、会議の移行ツール (32 ビット)](https://www.microsoft.com/en-us/download/details.aspx?id=54079)。
  
- コマンドレットの詳細については、[セット CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 )を参照してください。
    
- 電話会議 ID には、電話会議ブリッジの設定の桁の長さを満たす必要があります。会議 Id にアルファベット順または特殊文字を使うことはできません。数値のみを使用できます。
    
- すべての電話会議ユーザーの会議 ID 既定では、7 桁し、以下の桁数を変更することはできません。
    
- サードパーティ電話会議プロバイダーに電話会議プロバイダーとしてユーザーを Microsoft から移動、または電話会議プロバイダーは、 **[なし]**に設定されて、会議 ID は機能しなくなります。[電話会議プロバイダーとしてサードパーティ](assign-a-third-party-as-the-audio-conferencing-provider.md)を割り当てたり、[移動するのには、Microsoft のユーザーの電話会議プロバイダー](moving-a-user-s-audio-conferencing-provider-to-microsoft.md)を参照してください。
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell で管理する方法を知りたいとしていますか。

- Windows powershell となるはすべてを管理するユーザーとユーザーの許可または使用できません。Windows PowerShell で Office 365 と Skype for Business Online の複数のタスクを実行するがある場合、日常業務を簡素化する管理の 1 つのポイントを使用して管理できます。Windows PowerShell で開始するには、次のトピックを参照してください。
    
  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Office 365 PowerShell を使用する必要がある理由](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell では多くの利点速度、わかりやすいように、および生産性でのみ実行しようとする設定の変更、多くのユーザーに一度になどの Office 365 管理センターを使用します。次のトピックでこれらの利点について学習します。
    
  - [Windows PowerShell で Office 365 を管理する最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Windows PowerShell を使用して、Skype for Business Online の管理するには](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell を使用して、共通の Skype for Business Online の管理タスクを実行するには](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>関連トピック

[Skype for Business とチームの Microsoft の音声会議をセットアップする設定します。](set-up-audio-conferencing.md)
  

