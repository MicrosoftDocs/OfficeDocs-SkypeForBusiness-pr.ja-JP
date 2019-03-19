---
title: 電話システムの呼び出しキューを作成する
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: phans, wasseemh
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: ms.teamsadmincenter.callqueues.overview
ms.custom:
- Phone System
description: 'Office 365 (Cloud PBX) のシステムの通話キュー設定方法　組織のメッセージ、保留音、流通リスト内の企業及びセキュリティ　グループを呼び出すリダイレクト通話。通話キューの最大サイズ、タイムアウトそして通話処理オプションの設定も可能です。 '
ms.openlocfilehash: 204959e68fa398300352e477fc7e78ea870aa359
ms.sourcegitcommit: 8e62025d630c511ffb0361b9643d46c762188102
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "30664632"
---
# <a name="create-a-phone-system-call-queue"></a>電話システムの呼び出しキューを作成する

Phone System call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold. You can create single or multiple call queues for your organization.
  
電話システムの通話キューは次の機能を提供します:
  
- 組織の応答メッセージ。
- 通話の保留中に再生される保留音。
- メールが有効な配布リストおよびセキュリティ グループ内のエージェントを呼び出しへの呼び出しをリダイレクトします。
- 呼び出しキューの最大サイズ、タイムアウト、および呼び出しの処理オプションの設定を行っています。

呼び出しキューに設定されている電話番号へ呼び出し、それら、あいさつのメッセージが聞こえます (いずれかの設定されている) 場合、その後に、キューを保存して、次の呼び出しを使用可能なエージェントを待機します。 待機中、保留中であるし、呼び出し*最初に、先入れ先出し*(FIFO) の方法で呼び出しエージェントに提供するときに、相手呼び出しは音楽を聞きます。
  
キューで待機しているすべての呼び出しは、アテンダントのルーティング モードまたはシリアル ルーティング モードを使用して配布されます。
  
- 応答のルーティングでは、キュー内の最初の呼び出しを同時にすべてのエージェントが呼び出されます。
- シリアル・ルーティングでは、キュー内の最初の呼び出しがすべてのコールエージェントを一件ずつ呼び出します。

    > [!NOTE]
    > **オフライン**中のコールエージェントは、 **取り込み中** のプレゼンスを設定するか、通話キューからの呼び出しをオプトアウトしてください。
  
- 一度に 1 回のみの着信通知 (キューの最初にある通話) がコール エージェントに送信されます。
- コール エージェントが通話を受けると、キューにある次の着信がコール エージェントを呼び出します。

## <a name="step-1---getting-started"></a>ステップ 1 - はじめに

通話キューを使用する場合は、次の重要な点について留意してください。
  
- Your organization must have (at a minimum) an Enterprise E3 plus **Phone System** license or an Enterprise E5 license. The number of **Phone System** user licenses that are assigned affects the number of service numbers that are available to be used for call queues. The number of call queues you can have is dependent on the number of **Phone System** and **Audio Conferencing** licenses that are assigned in your organization. To learn more about licensing, go [here](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).

    > [!NOTE]
    > To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans. See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). To enable them for Enterprise Voice, you can use Windows PowerShell. For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- Office 365 のプランを呼び出す方法の詳細については、[電話システムを呼び出すことを計画](/microsoftteams/calling-plan-landing-page)し、 [Office 365 のプランを呼び出す](/microsoftteams/calling-plans-for-office-365)を参照してください。

    > [!NOTE]
    > ユーザーには、設置がホストされているキューを呼び出すエージェントとしては、Lync Server 2010 を使用してがサポートされていません。 
  
- You can only assign toll and toll-free service phone numbers that you got in the **Skype for Business admin center** or transferred from another service provider to Phone System call queues. To get and use toll-free service numbers, you need to set up Communications Credits.

    > [!NOTE]
    > ユーザー (購読者) の電話番号を通話キューに割り当てることはできません。サービスの有料電話番号または無料電話番号のみを使用できます。 
  
- 電話システム呼び出しキューからの着信呼び出しを配布するときは、コール エージェントのこれらのクライアントがサポートされます。

  - Skype for Business デスクトップ クライアント 2016 (32 および 64 ビット バージョン)

  - Lync デスクトップ クライアント 2013 (32 および 64 ビット バージョン)

  - All IP phone models supported for Skype for Business Online. See [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online.md).

  - Mac版  Skype for Business クライアント (バージョン 16.8.196 以降) 

  - Aandroid Skype for Business クライアント (バージョン 6.16.0.9 以降)

  - iPhone Skype for Business Client クライアント(バージョン 6.16.0 以降)

  - Mac版  Skype for Business クライアント (バージョン 6.16.0 以降)

  - Microsoft Teams Windows クライアント (バージョン 32 および 64 ビット)

  - Microsoft Teams Mac クライアント

  - マイクロソフト チームの iPhone アプリ

  - マイクロソフト チーム Android アプリ

## <a name="step-2---getting-or-transferring-toll-or-toll-free-service-phone-numbers"></a>ステップ 2 - 有料またはフリーダイヤルのサービス電話番号の取得または移行

Before you can create and set up your call queues, you will need to get or transfer your existing toll or toll-free service numbers. After you get the toll or toll-free service phone numbers, they will show up in **Skype for Business admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**. To get your service numbers, see [Getting service phone numbers for Skype for Business and Microsoft Teams](getting-service-phone-numbers.md) or if you want to transfer and existing service number, see [Transfer phone numbers to Office 365](/microsoftteams/transfer-phone-numbers-to-office-365).
  
> [!NOTE]
> If you are outside the United States, you can't use the Skype for Business admin center to get service numbers. Go to [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) instead to see how to do it from the outside of the United States.
  
## <a name="step-3---create-a-new-call-queue"></a>ステップ 3 - 新しい通話キューの作成

 **マイクロソフトのチーム管理センターを使用してください。**

**マイクロソフトのチーム管理センター**でをクリックして![デバイスのロゴ-30x30.png](../images/sfb-logo-30x30.png) **レガシー ポータル** >  **呼のルーティング** > **キューを呼び出す**には、 **+ 新規追加**] をクリックします。
  
### <a name="set-the-call-queue-display-name-phone-number-and-domain-if-any"></a>通話キューの表示名、電話番号、ドメイン (存在する場合) を設定します。

![Setting up a call queue.](../images/37ecc300-a108-4294-8463-fce570dfce72.png)
***
![1](../images/sfbcallout1.png)<br/>
**名前** 通話キューの分かりやすい名前を入力します。この項目は必須で、空白を含む最大 64 文字を含めることができます。<br/> この名前は着信の通知に表示されます。
***
![2](../images/sfbcallout2.png)<br/>**Phone number** Select a service toll or toll-free phone number for the call queue. This is optional. <br/> If there aren't any listed, you need to get service numbers before you can create this call queue. To get your service numbers, see [Getting service phone numbers for Skype for Business and Microsoft Teams](getting-service-phone-numbers.md)
***
![3](../images/sfbcallout3.png)<br/>**ドメイン** 利用可能な場合は、使用する Office 365 ドメインを選択します。この項目は、Office 365 で使用しているドメインが 1 つ以上存在する場合にのみ利用できます。1 つ以上存在する場合は、リストからドメイン名を選択します。 <br/> たとえば、次のようなドメインが存在します。 _contoso.com or redmond.contoso.com_

### <a name="set-the-greeting-and-music-played-while-on-hold"></a>応答メッセージおよび保留中の保留音を設定する

![Setting up a call queue.](../images/1d395a93-7cab-4178-9295-12d5379e20de.png)
  
***
![1](../images/sfbcallout1.png)<br/>**Greeting** is optional. This is the greeting that is played for people who call in to the call queue number. <br/> オーディオ ファイル (.wav、.mp3、.wma 形式) をアップロードすることができます。
***
![2](../images/sfbcallout2.png)<br/>**上の音楽を保持**呼び出しキューで提供されている保留中のデフォルトの音楽を使用するか、または保留中のカスタムの音楽として使用する .wav、mp3、または .wma ファイルの形式でのオーディオ ファイルをアップロードすることができます。

### <a name="select-the-call-distribution-method"></a>着信分配メソッドを選択する

![着信分配メソッドのオプションを表示する](../images/5d249515-d532-4af2-90da-011404028b89.png)
  
***
![1](../images/sfbcallout1.png)<br/>**Call distribution method** You can choose either **Attendant** or **Serial** for your call queue distribution method. All new and existing call queues will have attendant routing selected by default. To use serial routing, you must explicitly choose the **Serial** routing option in UI and cmdlets. <br/><br/> When serial routing is chosen and the call queue is saved, the calls from the queue will ring your agents one by one, starting from the beginning of the agent list. If an agent dismisses or does not pick up a call, the call will ring the next agent on the list and will try all agents one by one until it is picked up or times out waiting in the queue.   

> [!NOTE]
> **オフライン**中、**取り込み中**表示、またはこのキューからの着信を **オプトアウト** したエージェントは、シリアルルーティングからスキップされます。 

### <a name="select-an-agent-opt-out-option"></a>エージェントのオプトアウトのオプションを選択する

![オプトアウトするエージェントのチェック ボックスの表示](../images/99279eff-db61-4acf-9b62-64be84b6414b.png)
  
***
![1](../images/sfbcallout1.png)<br/>**エージェント オプトアウト オプション** **エージェントのオプトアウト オプション**選択して特定のキューからの着信をオプトアウトすることができます。  <br/> Enabling this option allows all agents in this queue to start or stop receiving call from this call queue at will. You can revoke the agent opt-out privilege at any time by clearing the check box, causing agents to become automatically opted in for this queue again (the default setting for all agents).  <br/><br/> エージェントは次の操作を行うと、オプトアウトのオプションにアクセスできます:
 1. Skype for Business クライアントデスクトップで、 **オプション** を開きます。 
 2. **[通話転送]** タブで、 **[オンライン編集の設定]** リンクをクリックします。
 3. ユーザー設定ページで、 **通話キュー**をクリックし、次にオプトアウトしたいキューのチェック ボックスを削除します。

    > [!NOTE] 
    > Mac、モバイル、または Lync 2013 クライアントを使用しているエージェント、または Skype for Business 2015 サーバーを使用しているオンプレミスでホストされている Hybrid Voice ユーザーは、 [https://aka.ms/cqsettings](https://aka.ms/cqsettings) で、オプトアウトのオプションにアクセスすることができます。

### <a name="add-call-agents-to-a-call-queue"></a>コール エージェントを通話キューに追加する

![Set up call queues.](../images/skype-for-business-add-agents-to-call-queue.png)
  
***
![1](../images/sfbcallout1.png)<br/><br/>コール エージェント (最大で 200) を指定できます。
* **電話システム** のライセンスを持つオンラインのユーザーとして、エンタープライズ ボイスまたは 通話の計画を有効にします。 <br/><br/> **Note:**  To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have a Calling Plan. See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). To enable them for Enterprise Voice, you can use Windows PowerShell. For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true` <br/><br/>
* Online users with a **Phone System** license and a Calling Plan that are added to an Office 365 Group, a mail-enabled Distribution List, or a Security Group. It might take up to 30 minutes for a new agent added for a distribution list or a security group to start receiving calls from a call queue. A newly created distribution list or security group might take up to 48 hours to become available to be used with call queues. Newly created Office 365 Groups are available almost immediately. <br/> 

  > [!NOTE] 
  > ユーザーには、設置がホストされている Lync Server 2010 の使用はサポートされていません。

### <a name="set-the-maximum-queue-size-and-maximum-wait-time"></a>最大キュー サイズと最大待機時間を設定する

![Set up a call queue.](../images/3f018734-16fe-458b-827d-71fc25155cde.png)
  
***
![1](../images/sfbcallout1.png)<br/><br/>**Maximum calls in the queue** Use this to set the maximum calls that can wait in the queue at the same time. The default is 50, but it can range from 0 to 200.When this limit is reached, the call will be handled in way you have set on the **When the maximum number of calls is reached** setting below.
***
![2](../images/sfbcallout2.png)<br/><br/>**呼び出しの最大数に達したとき**呼び出しキューでは、(**キューの最大数を呼び出す**設定を使用して設定) の最大のサイズに達すると、新しくかかってきた呼び出しの動作を選択します。
* **ビジー信号を切断します** 通話は切断されます。
* **呼び出しを転送します。** これを選択するとこれらのオプションが用意されます。
  * **Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have a Calling Plan. You can set it up so the person calling in can be sent to voicemail. To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail. <br/> <br/>ボイスメールに必要なライセンスについては、 [電話システムのボイス メールの設定](/microsoftteams/set-up-phone-system-voicemail)を参照してください。 

    > [!Note]
    > ユーザーには、設置がホストされている Lync Server 2010 の使用はサポートされていません。<br/>

  * **キューを呼び出す**作成する必要が既に別の呼び出しは、キューが、その呼び出しキューを選択するには後、。
  * **Auto Attendant** You must have already created an auto attendant, but after you do, you can select that auto attendant. See [Set up a Phone System auto attendant](set-up-a-phone-system-auto-attendant.md).
***
![3](../images/sfbcallout3.png)<br/><br/>**通話のキュー内での待機時間** タイムアウトが発生し、通話のリダイレクトまたは切断が必要となるまでに、通話をキュー内で保留できる時間を決定することもできます。リダイレクト先は [ **通話がタイムアウトした場合**] 設定に基づきます。0 から 45 分に設定できます。 <br/><br/> The timeout value can be set in seconds, at 15-second intervals. This allows you to manipulate the call flow with finer granularity. For example, you could specify that any calls that are not answered by an agent within 30 seconds go to a Directory Search Auto Attendant. 

***
![4](../images/sfbcallout4.png)<br/><br/>**通話がタイムアウトした場合** [ **通話のキュー内での待機時間**] 設定で指定した制限に達した通話に対する処理方法を選択できます。
* **切断** 通話は切断されます。
* **呼び出しを転送します。** これを選択するとこれらのオプションが用意されます。
  * **Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have Calling Plans. You can set it up so the person calling in can be sent to voicemail. To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail. </br><br/>  ボイスメールに必要なライセンスについては、 [「電話システムのボイスメールの設定」](/microsoftteams/set-up-phone-system-voicemail) を参照してください。 

    > [!Note]
    > ユーザーには、設置がホストされている Lync Server 2010 の使用はサポートされていません。<br/>

  * **キューを呼び出す**作成する必要が既に別の呼び出しは、キューが、その呼び出しキューを選択するには後、。
  * **Auto Attendant** You must have already created an auto attendant, but after you do, you can select that auto attendant. See [Set up a Phone System auto attendant](set-up-a-phone-system-auto-attendant.md).
   
## <a name="changing-the-users-caller-id-to-be-a-call-queues-phone-number"></a>ユーザーの発信者番号通知を通話キューの電話番号に変更する

**New-CallingLineIdentity** コマンドレットを使用してポリシーを作成する代わりに、アウトバウンドコールの発信者番号通知を通話キューに変更することでユーザーIDを保護します。
  
これを行う場合は、次を実行します。
  
```
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

Then apply the policy to the user using the **Grant-CallingLineIdentity** cmdlet. To do this, run:
  
```
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

組織内の発信者番号通知の変更方法の詳細については、 [こちら](../what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization.md)です。
  
## <a name="want-to-know-more"></a>詳細情報

Windows PowerShell を使用して通話キューを作成し、設定することもできます。
  
### <a name="call-queue-cmdlets"></a>通話キューのコマンドレット

通話キューの管理で必要なコマンドレットを以下に示します。
  
- [New--CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796459.aspx)

- [Set-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796457.aspx)

- [Get-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796458.aspx)

- [Remove-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796456.aspx)

### <a name="more-about-windows-powershell"></a>Windows PowerShell の詳細について

- Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:

  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525041)

- Windows PowerShell には、ただ Office 365 管理センターを使用するだけではなく、速度、単純さ、生産性において多くの利点があります。次のトピックでこれらの利点について説明します。

  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [クイック リファレンス: Windows PowerShell を使用した一般的な Lync Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>関連項目
[Office 365 での電話システムで利用できる機能](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[Skype for Business および Microsoft Teams のサービス電話番号の取得](getting-service-phone-numbers.md)

[国および地域ごとの電話会議および通話プランの利用可能性](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)
