---
title: "参照してください、変更、およびユーザーに割り当てられている会議 ID をリセットします。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 77d36233-2aab-4802-ba9c-e9a8885ea643
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
description: "については、ビジネスの Skype のユーザーに会議 ID を割り当てる方法と、どのような会議 ID のパラメーターにする必要があります。 "
ms.openlocfilehash: 46edf684a835984524ce988da532b6b9a14931da
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/15/2017
---
# <a name="see-change-and-reset-a-conference-id-assigned-to-a-user"></a>参照してください、変更、およびユーザーに割り当てられている会議 ID をリセットします。

会議 ID が、Skype のビジネスまたはマイクロソフトのチームのユーザーに割り当てられたは、Office 365 での音声会議用に設定し、Microsoft を使用して、オーディオ会議プロバイダーとして自動的にします。 会議 ID が割り当てられている静的または動的のどちらかにすることができ、会議がスケジュールされているときに会議出席依頼の送信します。
  
静的の Id は、組織内のユーザーはランダムな番号を覚えておく必要があるときに使用します。特定の番号を選択したり、覚えやすいものを使用することができます。 動的会議 Id を使用する場合各会議ユーザのスケジュールは割り当てられます会議の一意の id。 場合に割り当てる静的な会議 Id を[ここ](using-audio-conferencing-dynamic-ids-in-your-organization.md)にではなく動的です。
  
静的な会議 ID が自動的に作成され、ユーザーに割り当てられているが場合がありますこの 1 つを使用するユーザーが望まないし、特定の数に設定するとき、またはユーザーが覚えられないか、会議 ID が失われている場合 **Skype**ビジネス管理センターは、Windows PowerShell を使用するには表示、変更、および、会議 ID をリセットするには
  
会議 ID と既定の電話会議の電話番号をユーザーに電子メールが送信される、または会議 ID がない、暗証番号 (pin) に含まれている会議 ID をリセットする場合、別の電子メールが送信されます。
  
## <a name="view-and-change-conference-ids"></a>表示し、会議 Id を変更します。

### <a name="to-view-the-conference-id"></a>会議 ID を表示するのには

会議 ID を表示し、ユーザーに送信することができます。
  
1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. **Office 365 管理センター**を参照して > **ビジネス用の Skype**です。
    
3. **ビジネス管理センターの Skype**の> **オーディオ会議** > **ユーザー**ユーザーが必要な会議の id を選択。
    
4. [アクション] ページで、[**会議 ID**] を確認します。
    
    > [!TIP]
    > [**ユーザー** ] ページで、ユーザーを選択した後に**電子メールを使用して会議情報を送信する**リンクをクリックして、会議 ID とオーディオの電話番号を含む電子メールでユーザーにすべての会議の情報を送信できます。
  
    ユーザーの会議 ID を表示するのには、Windows PowerShell を使用できます。 これを行うには、次のコマンドを実行します。
    
  ```
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"  
  ```

    コマンドレットの詳細については、 [Get CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 )を参照してください。
    
### <a name="to-assign-or-change-the-conference-id"></a>割り当て、または会議 ID を変更するには

ユーザーの会議 ID を変更する場合、たとえば、覚えやすいものである会議 ID を割り当てたりできます。

  > [!NOTE]
  > ビジネス管理センターの Skype は自動的に作成されている会議 ID を編集するのには使用できませんが、編集、または設定した会議 ID を変更する Windows PowerShell を使用することができます。 
     
編集またはユーザーの会議 ID を変更する、次のコマンドを実行します。
    
  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ConferenceId 8271964
  ```

  > [!TIP]
  > 会議 ID が 7 桁の数字を含める必要があり、ビジネス管理センターまたは Windows PowerShell を使用して、Skype で変更することはできません。 
  
### <a name="to-reset-the-conference-id"></a>会議 ID をリセットするのには

ユーザーの会議 ID をリセットすることができる場合、忘れた場合などです。
  
1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. **Office 365 管理センター**を参照して > **ビジネス用の Skype**です。
    
3. **ビジネス管理センターの Skype**の> **電話会議** > **ユーザー**、操作ウィンドウの [**会議 ID**に**リセット**] をクリックします。
    
4. **会議 ID をリセットしますか?** ] ウィンドウで、[**はい**] をクリックします。 会議 ID が自動的に作成し、新しい会議 ID を持つユーザーに送信する電子メール
    
    ユーザーの会議 ID をリセットするには、Windows PowerShell を使用します。 これを行うには、次のコマンドを実行します。
    
  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ResetLeaderPIN 8271964
  ```

## <a name="what-else-should-you-know"></a>その他の情報

   > [!IMPORTANT]
   >  新しい会議 ID が作成されるか、1 つは、リセット後、は、呼び出し元が古い会議 ID を使用できません。 ミーティングの招待新しい会議 ID が、招待状に追加されることを確認するのには、既存のスケジュールを変更するのにはユーザーに通知する必要があります。 ユーザーは、ビジネス会議の移行ツールの Skype を使用して、既存の会議を更新します。 ダウンロード、インストール、およびツールを実行する方法を参照してください:[ビジネスと Lync の Skype の会議の更新ツール](http://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)、 [Skype](http://go.microsoft.com/fwlink/?LinkID=626047)、および[Skype](https://www.microsoft.com/en-us/download/details.aspx?id=54079)です。
  
- コマンドレットの詳細については、[設定 CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 )を参照してください。
    
- 会議 ID は、オーディオ会議ブリッジを設定する桁の長さを満たす必要があります。 会議 Id のアルファベット順または特殊文字を使うことはできません。数値のみを使用できます。
    
- オーディオ会議のユーザーのすべての会議 ID が既定では、7 桁になるし、以下の桁数を変更することはできません。
    
- サード ・ パーティ製のオーディオ会議プロバイダーにオーディオ会議プロバイダーとして、ユーザーがマイクロソフトから移動したりされたり、オーディオ会議プロバイダーが**[なし]**に設定されて、会議 ID が動作しなくなります。 [オーディオ会議プロバイダーとしてサード パーティを割り当てる](assign-a-third-party-as-the-audio-conferencing-provider.md)か、[マイクロソフトのユーザーのオーディオ会議プロバイダーの移動](moving-a-user-s-audio-conferencing-provider-to-microsoft.md)を参照してください。
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell で管理する方法

- Windows PowerShell で行うのは、ユーザーを管理し、ユーザーに何を許可して何を禁止するかを管理することです。Windows PowerShell を利用すると、Office 365 と Skype for Business Online の管理を 1 か所で行うことができるので、複数のタスクを担当する管理者の日常業務を単純化できます。Windows PowerShell の使用を開始するには、次のトピックを参照してください。
    
  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Office 365 の PowerShell を使用する必要がある理由](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell には、ただ Office 365 管理センターを使用するだけではなく、速度、単純さ、生産性において多くの利点があります。次のトピックでこれらの利点について説明します。
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>関連トピック

[Skype for Business および Microsoft Teams の電話会議のセットアップ](set-up-audio-conferencing.md)
  

