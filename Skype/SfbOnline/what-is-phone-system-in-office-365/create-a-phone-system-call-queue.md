---
title: 電話システム呼び出しキューを作成します。
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: makolomi
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
- Strat_SB_PSTN
description: 'Learn how to set up phone system for Office 365 (Cloud PBX) call queues to give you an organizational greeting, music on hold, and redirecting calls to call agents in distribution lists and security groups. You can also set the maximum queue size, time out, and call handling options. '
ms.openlocfilehash: a6eac4b7fec191d9e897f41e3c32b270ab21abcf
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/03/2018
---
# <a name="create-a-phone-system-call-queue"></a>電話システム呼び出しキューを作成します。

電話システム キューには、保留中の呼び出しを自動的に配置する機能などを検索する人の中に呼び出しを処理するために次の呼び出しを使用可能なエージェントの機能の電話番号への呼び出し際に使用するあいさつ文が含まれています。呼び出しが保留中の音楽をリッスンしています。 組織の 1 つまたは複数の呼び出しキューを作成します。
  
電話システム コールのキューを提供します。
  
- 組織の応答メッセージ。
    
- 通話の保留中に再生される保留音。
    
- メールが有効な配布リストおよびセキュリティ グループ内のエージェントを呼び出しへの呼び出しをリダイレクトします。
    
- 呼び出しキューの最大サイズ、タイムアウト、および呼び出しの処理オプションの設定を行っています。
    
誰かを呼び出すと設定されている電話番号を呼び出しキューでは、それらが聞こえますあいさつ文 (いずれかの設定されている) 場合、その後に、キューを保存して、次の呼び出しを使用可能なエージェントを待機します。 待機中、保留中であるし、呼び出し*最初に、先入れ先出し*(FIFO) の方法で呼び出しエージェントに提供するときに、相手呼び出しは音楽を聞きます。
  
キューで待機しているすべての呼び出しは、アテンダントのルーティング モードまたはシリアル ルーティング モードを使用して配布されます。
  
- 応答のルーティングでは、キュー内の最初の呼び出しを同時にすべてのエージェントが呼び出されます。
    
- シリアルのルーティングでは、キュー内の最初の呼び出しの呼び出しのすべてのエージェントで 1 つが呼び出されます。
    
    > [!NOTE]
    > **オフライン**不可**、**自分の存在を設定して、呼び出しキューを選択して、エージェントを呼び出しハンドラーは呼び出されません。
  
- 一度に 1 回のみの着信通知 (キューの最初にある通話) がコール エージェントに送信されます。
    
- コール エージェントが通話を受けると、キューにある次の着信がコール エージェントを呼び出します。
    
## <a name="step-1---getting-started"></a>ステップ 1 - はじめに

通話キューを使用する場合は、次の重要な点について留意してください。
  
- 組織は、エンタープライズの E3 と**電話システム**のライセンスまたはエンタープライズ E5 のライセンス (最低) が必要です。 キューの呼び出しに使用する利用可能なサービス番号の番号を割り当てられている**電話システム**のユーザー ライセンスの数に影響します。 呼び出しキューを持つことができます数は、組織に割り当てられている**電話システム**および**オーディオ会議**のライセンスの数に依存しています。 、ライセンスに関する詳細については、移動[は、ここ](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)です。
    
    > [!NOTE]
    > オンラインにいる人が、組織内への呼び出しをリダイレクトするには、エンタープライズ VoIP を有効にするし、Office 365 のプランを呼び出すことがある、**電話システム**のライセンスが必要です。 「[Skype for Business と Microsoft Teams のライセンスを割り当てる](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)」をご覧ください。 エンタープライズ VoIP を有効にするには、Windows PowerShell を使用できます。 例を実行します。`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- Office 365 のプランを呼び出す方法の詳細についてを参照してください[Office 365 のプランを呼び出すことは何ですか?](../what-are-calling-plans-in-office-365/what-are-calling-plans-in-office-365.md) [Office 365 のプランを呼び出す](../skype-for-business-and-microsoft-teams-add-on-licensing/calling-plans-for-office-365.md)とします。
    
    > [!NOTE]
    > ユーザーには、設置がホストされているキューを呼び出すエージェントとしては、Lync Server 2010 を使用してがサポートされていません。 
  
- 有料電話番号と**Skype**でまたは別のサービス プロバイダーからの呼び出しの電話システムのキューに転送する電話番号をフリー ダイヤル サービスをのみ割り当てることができます。 取得し、サービスのフリー ダイヤル番号を使用して、通信のクレジットを設定する必要があります。
    
    > [!NOTE]
    > ユーザー (購読者) の電話番号を通話キューに割り当てることはできません。サービスの有料電話番号または無料電話番号のみを使用できます。 
  
- 電話システム呼び出しキューからの着信呼び出しを配布するときは、コール エージェントのこれらのクライアントがサポートされます。
    
  - Skype for Business デスクトップ クライアント 2016 (32 および 64 ビット バージョン)
    
  - Lync デスクトップ クライアント 2013 (32 および 64 ビット バージョン)
    
  - すべての IP 電話の機種が、Skype for Business Online でサポートされます。 [ビジネス オンラインの Skype の電話を取得](getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online.md)を参照してください。
    
  - ビジネス クライアントの Mac Skype (バージョン 16.8.196 以降) 
    
  - ビジネス クライアント用の android の Skype (バージョン 6.16.0.9 以降)
    
  - iPhone ビジネス クライアント用の Skype (バージョン 6.16.0 以降)
    
  - iPad ビジネス クライアント用の Skype (バージョン 6.16.0 以降)
    
## <a name="step-2---getting-or-transferring-toll-or-toll-free-service-phone-numbers"></a>ステップ 2 - 有料またはフリーダイヤルのサービス電話番号の取得または移行

Before you can create and set up your call queues, you will need to get or transfer your existing toll or toll-free service numbers. 有料または無料のサービスの電話番号を取得した後が表示されます**ビジネス管理センターの Skype** > **音声** > **電話番号**と**番号の種類**の一覧には、無料**サービスとして一覧表示されます**. サービス番号を取得するには、 [Skype のビジネスおよびマイクロソフトのチームの取得サービスの電話番号](getting-service-phone-numbers.md)を参照するか、転送し、既存のサービス番号にする場合は、 [Office 365 に電話番号を転送する](../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md)を参照してください。
  
> [!NOTE]
> 米国以外のユーザーは、サービス番号を取得するビジネス管理センターの Skype を使うことはできません。 [組織の電話番号を管理](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)する代わりに、米国の外側から行う方法を参照してください。
  
## <a name="step-3---create-a-new-call-queue"></a>ステップ 3 - 新しい通話キューの作成

In the **Skype for Business admin center**, click **Call routing** > **Call queues**, then click **Add new**:
  
### <a name="set-the-call-queue-display-name-phone-number-and-domain-if-any"></a>通話キューの表示名、電話番号、ドメイン (存在する場合) を設定します。

![Setting up a call queue.](../images/37ecc300-a108-4294-8463-fce570dfce72.png)
***
![番号 1](../images/sfbcallout1.png)<br/>
**名前** 通話キューの分かりやすい名前を入力します。この項目は必須で、空白を含む最大 64 文字を含めることができます。<br/> この名前は着信の通知に表示されます。
***
![番号 2](../images/sfbcallout2.png)<br/>**電話番号** 通話キューのサービスの有料電話番号または無料電話番号を選択します。 これは省略可能です。 <br/> 一覧表示されない場合は、この通話キューを作成する前にサービス番号を取得する必要があります。 サービス番号を取得するには、 [Skype のビジネスおよびマイクロソフトのチームの取得サービスの電話番号](getting-service-phone-numbers.md)を参照してください。
***
![番号 3](../images/sfbcallout3.png)<br/>**ドメイン** 利用可能な場合は、使用する Office 365 ドメインを選択します。この項目は、Office 365 で使用しているドメインが 1 つ以上存在する場合にのみ利用できます。1 つ以上存在する場合は、リストからドメイン名を選択します。<br/> たとえば、次のようなドメインが存在します。 _contoso.com or redmond.contoso.com_
   
### <a name="set-the-greeting-and-music-played-while-on-hold"></a>応答メッセージおよび保留中の保留音を設定する

![Setting up a call queue.](../images/1d395a93-7cab-4178-9295-12d5379e20de.png)
  
***
![番号 1](../images/sfbcallout1.png)<br/>**応答メッセージ**は省略可能です。 これは、応答メッセージが、キューの番号に電話通話する相手を再生します。 <br/> オーディオ ファイル (.wav、.mp3、.wma 形式) をアップロードすることができます。
***
![番号 2](../images/sfbcallout2.png)<br/>**上の音楽を保持**呼び出しキューで提供されている保留中のデフォルトの音楽を使用するか、または保留中のカスタムの音楽として使用する .wav、mp3、または .wma ファイルの形式でのオーディオ ファイルをアップロードすることができます。 
   

### <a name="select-the-call-distribution-method"></a>呼び出しの配布方法を選択します。

![呼び出しの配布方法のオプションを示しています](../images/5d249515-d532-4af2-90da-011404028b89.png)
  
***
![番号 1](../images/sfbcallout1.png)<br/>**配布メソッドを呼び出す**呼び出しキューの配布方法の**アテンダント**または**シリアル**のいずれかを選択できます。 新規および既存の呼び出しのすべてのキューは、応答のルーティングが既定で選択されているがあります。 シリアルのルーティングを使用するには、UI およびコマンドレットの**シリアル**のルーティング オプションを明示的に選択する必要があります。 <br/><br/> シリアルのルーティングを選択すると、呼び出しキューを保存する、キューからの呼び出しは、[エージェント] ボックスの一覧の先頭から開始、エージェント、1 つずつをリングします。 エージェントを閉じる、または呼び出しを受けない呼び出しがリストには、次のエージェントが呼び出され、すべてのエージェントによって 1 つ選択して、または、キューで待機していた時間を試みます。  <br/><br/>  **注:**シリアルのルーティングと、**オフライン**は、自分の存在を**不可**に設定している、または**削除**このキューからの呼び出しを取得するユーザー エージェントはスキップされます。  
   
### <a name="select-an-agent-opt-out-option"></a>エージェントの選択] のオプションが脱退します。

![エージェントの選択を表示する] チェック ボックス](../images/99279eff-db61-4acf-9b62-64be84b6414b.png)
  
***
![番号 1](../images/sfbcallout1.png)<br/>**エージェントは、オプションを選択****エージェントの選択] オプションを**選択すると、特定のキューからの呼び出しを実行することを辞退するキュー エージェントの呼び出しを許可することができます。  <br/> このオプションを有効にすると、このキュー内のすべてのエージェントを開始または停止するのには、この呼び出しキューからの呼び出しを受信するには使用できます。 ことができます権限を取り消す、エージェント脱退はいつでも、チェック ボックスをオフにしてに自動的に有効になってこのキューに対して再度 (すべてのエージェントの既定の設定) するようにエージェントを引き起こしています。  <br/><br/> 脱退オプションにアクセスするにエージェントは次の操作を行うことができます。
 1. ビジネス クライアント用のデスクトップ、Skype では、**オプション**を開きます。 
 2. **呼び出しの転送**] タブでは、**オンラインの設定を編集**] リンクをクリックします。
 3. [ユーザー設定] ページで、**キューの呼び出し**、] をクリックし、脱退する任意のキューのチェック ボックスをオフにし、します。
 
    > [!NOTE] 
    > Mac を使用してエージェントでは、モバイル、または Lync 2013 クライアント、またはハイブリッド音声ユーザーにホストの設置型ビジネス 2015年サーバーでは、Skype を使用することができますには、 [https://aka.ms/cqsettings](https://aka.ms/cqsettings) 、opt out オプションにアクセスします。
   
### <a name="add-call-agents-to-a-call-queue"></a>コール エージェントを通話キューに追加する

![Set up call queues.](../images/skype-for-business-add-agents-to-call-queue.png)
  
***
![番号 1](../images/sfbcallout1.png)<br/><br/>コール エージェント (最大 50) を指定できます。
*    **電話システム**のライセンスを持つオンラインのユーザー、またはエンタープライズ VoIP の計画を呼び出すことを有効にします。 <br/><br/> **注:** オンラインにいる人が、組織内への呼び出しをリダイレクトするのには、**電話システム**のライセンスが必要しエンタープライズ VoIP を有効にすることも計画を呼び出します。 「[Skype for Business と Microsoft Teams のライセンスを割り当てる](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)」をご覧ください。 エンタープライズ VoIP を有効にするには、Windows PowerShell を使用できます。 例を実行します。`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true` <br/><br/>
*    オンラインのユーザーに、**電話システム**のライセンスを呼び出す計画、Office 365 のグループ、メールが有効な配布リスト、またはセキュリティ グループに追加されるとします。 配布リストまたは通話キューからの呼び出しの受信を開始するのにはセキュリティ グループに追加された新しいエージェントの最大 30 分間がかかる場合があります。 新しく作成した配布リストまたはセキュリティ グループでは、呼び出しキューで使用できるようになるには最大で 48 時間をかかる場合があります。 新しく作成された Office 365 グループは、利用可能なほぼ瞬時に。 <br/> 

    > [!NOTE] 
    > ユーザーには、設置がホストされている Lync Server 2010 の使用はサポートされていません。           
   
### <a name="set-the-maximum-queue-size-and-maximum-wait-time"></a>最大キュー サイズと最大待機時間を設定する

![Set up a call queue.](../images/3f018734-16fe-458b-827d-71fc25155cde.png)
  
***
![番号 1](../images/sfbcallout1.png)<br/><br/>**キュー内の最大通話数** この項目を使用して、同時に通話がキュー内で待機できる最大通話数を設定します。 既定値 50 が、その範囲は 0 から 200. この制限に達すると、呼び出しは、**呼び出しの最大数に達すると**下の設定で設定した方法で処理します。
***
![番号 2](../images/sfbcallout2.png)<br/><br/>**呼び出しの最大数に達したとき**呼び出しキューでは、(**キューの最大数を呼び出す**設定を使用して設定) の最大のサイズに達すると、新しくかかってきた呼び出しの動作を選択します。
*    **ビジー信号を切断します** 通話は切断されます。
*    **呼び出しを転送します。**これを選択するとこれらのオプションが用意されます。
     *    **あなたの会社の人****電話システム**のライセンスを持つオンラインのユーザーとエンタープライズ VoIP を有効にすることも計画を呼び出します。 発信中のユーザーがボイスメールに送信されるように設定できます。 これを行うは、 **、会社の担当者**を選択し、通話をボイスメールに直接転送されるには、このユーザーを設定します。 <br/> <br/>ボイスメールに必要なライセンスについては、[電話システムのボイス メールの設定](../what-is-phone-system-in-office-365/phone-system-voicemail/set-up-phone-system-voicemail.md)を参照してください。 
     
        > [!Note]
        > ユーザーには、設置がホストされている Lync Server 2010 の使用はサポートされていません。<br/>
     
     *    **キューを呼び出す**作成する必要が既に別の呼び出しは、キューが、その呼び出しキューを選択するには後、。
     *    **自動応答**必要があります作成済みの自動応答が行うと、その自動アテンダントを選択できます。 [電話システムの自動応答の設定](set-up-a-phone-system-auto-attendant.md)を参照してください。
***
![番号 3](../images/sfbcallout3.png)<br/><br/>**通話のキュー内での待機時間** タイムアウトが発生し、通話のリダイレクトまたは切断が必要となるまでに、通話をキュー内で保留できる時間を決定することもできます。リダイレクト先は [ **通話がタイムアウトした場合**] 設定に基づきます。0 から 45 分に設定できます。<br/><br/> 15 秒間隔で、秒単位でタイムアウト値を設定できます。 これにより、細かい粒度での呼び出しの流れを操作することができます。 たとえば、ディレクトリ検索の自動応答を 30 秒以内に、エージェントが応答しないすべての呼び出しを移動することを指定できます。 

***
![番号 4](../images/sfbcallout4.png)<br/><br/>**通話がタイムアウトした場合** [ **通話のキュー内での待機時間**] 設定で指定した制限に達した通話に対する処理方法を選択できます。
*    **切断** 通話は切断されます。
*    **呼び出しを転送します。**これを選択するとこれらのオプションが用意されます。
     *    **あなたの会社の人****電話システム**のライセンスを持つオンラインのユーザーのエンタープライズ VoIP を有効にするか、計画を呼び出すことがあるとします。 発信中のユーザーがボイスメールに送信されるように設定できます。 これを行うは、 **、会社の担当者**を選択し、通話をボイスメールに直接転送されるには、このユーザーを設定します。 </br><br/>  ボイスメールに必要なライセンスについては、[電話システムのボイス メールの設定](../what-is-phone-system-in-office-365/phone-system-voicemail/set-up-phone-system-voicemail.md)を参照してください。 

        > [!Note]
        > ユーザーには、設置がホストされている Lync Server 2010 の使用はサポートされていません。<br/>

     *    **キューを呼び出す**作成する必要が既に別の呼び出しは、キューが、その呼び出しキューを選択するには後、。
     *    **自動応答**必要があります作成済みの自動応答が行うと、その自動アテンダントを選択できます。 [電話システムの自動応答の設定](set-up-a-phone-system-auto-attendant.md)を参照してください。
   
## <a name="changing-the-users-caller-id-to-be-a-call-queues-phone-number"></a>呼び出しキューの電話番号を使用するユーザーの呼び出し元の ID を変更します。

**新規 CallingLineIdentity**コマンドレットを使用してポリシーを作成して代わりに呼び出しキューに発信呼び出しの発信者番号通知を変更することによって、ユーザーの id を保護できます。
  
これを行う場合は、次を実行します。
  
```
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

**許可 CallingLineIdentity**コマンドレットを使用してユーザーにポリシーを適用します。 これを行う場合は、次を実行します。
  
```
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

すれば、組織内の呼び出し元 ID の設定を変更する方法の詳細について[は、ここ](../what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization.md)です。
  
## <a name="want-to-know-more"></a>詳細情報

Windows PowerShell を使用して通話キューを作成し、設定することもできます。
  
### <a name="call-queue-cmdlets"></a>通話キューのコマンドレット

通話キューの管理で必要なコマンドレットを以下に示します。
  
- [新しい-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796459.aspx)
    
- [セット CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796457.aspx)
    
- [Get CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796458.aspx)
    
- [削除 CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796456.aspx)
    
### <a name="more-about-windows-powershell"></a>Windows PowerShell の詳細について

- Windows PowerShell で行うのは、ユーザーを管理し、ユーザーに何を許可して何を禁止するかを管理することです。Windows PowerShell を利用すると、Office 365 と Skype for Business Online の管理を 1 か所で行うことができるので、複数のタスクを担当する管理者の日常業務を単純化できます。Windows PowerShell の使用を開始するには、次のトピックを参照してください。
    
  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell には、ただ Office 365 管理センターを使用するだけではなく、速度、単純さ、生産性において多くの利点があります。次のトピックでこれらの利点について説明します。
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [クイック リファレンス: Windows PowerShell を使用した一般的な Lync Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>See also
[Office 365 での電話システムで利用できる機能](here-s-what-you-get-with-phone-system.md)

[Skype for Business および Microsoft Teams のサービス電話番号の取得](getting-service-phone-numbers.md)

[国および地域ごとの電話会議および通話プランの利用可能性](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

  
 