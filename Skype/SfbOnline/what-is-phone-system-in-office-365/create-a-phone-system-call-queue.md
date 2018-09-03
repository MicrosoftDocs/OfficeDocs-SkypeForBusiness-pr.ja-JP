---
title: 電話システムの通話キューを作成する
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: makolomi
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
localization_priority: Priority
f1keywords: None
ms.custom:
- Phone System
description: 'Office 365 (Cloud PBX) のシステムの通話キュー設定方法　組織のメッセージ、保留音、流通リスト内の企業及びセキュリティ　グループを呼び出すリダイレクト通話。通話キューの最大サイズ、タイムアウトそして通話処理オプションの設定も可能です。 '
ms.openlocfilehash: 5a3ace77542a86aea1dd77e1ddcf594f61abb738
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2018
ms.locfileid: "23780425"
---
# <a name="create-a-phone-system-call-queue"></a>電話システムの通話キューを作成する

電話システムの通話キューには、組織の電話番号に着信がある場合、自動的に保留にする機能と発信者が保留音を聞いている間に次に対応可能なコールエージェントを検索する機能が含まれています。　
  
電話システムの通話キューは次の機能を提供します:
  
- 組織の応答メッセージ。
    
- 通話の保留中に再生される保留音。
    
- 有効なメール配布リスト内のコールエージェントとセキュリティ グループへのリダイレクト通話。
    
- 通話キューの最大サイズ、タイムアウト、通話対応オプションの設定。
    
通話キューが設定されている電話番号に発信すると、最初に応答メッセージ (設定されている場合) が再生され、キューに置かれ、次に対応可能なコールエージェントを待機します。発信者は保留音を聞いている間、通話は *先入先出法*  (FIFO) でコール エージェントに送られます。
  
キューで待機しているすべての通話は、応答ルーティング モードまたはシリアル・ルーティングモードを使用して配信されます。
  
- 応答のルーティングでは、キュー内の最初の呼び出しがすべてのエージェントを同時に呼び出します。
    
- シリアル・ルーティングでは、キュー内の最初の呼び出しがすべてのコールエージェントを一件ずつ呼び出します。
    
    > [!NOTE]
    >  **オフライン**中のコールエージェントは、 **取り込み中** のプレゼンスを設定するか、通話キューからの呼び出しをオプトアウトしてください。
  
- 一度に 1 回のみの着信通知 (キューの最初にある通話) がコール エージェントに送信されます。
    
- コール エージェントが通話を受けると、キューにある次の着信がコール エージェントを呼び出します。
    
## <a name="step-1---getting-started"></a>ステップ 1 - はじめに

通話キューを使用する場合は、次の重要な点について留意してください。
  
- 組織は、（少なくとも）エンタープライズの E3 と **電話システム** のライセンスまたはエンタープライズ E5 のライセンスが必要です。 **電話システム**のユーザーライセンス番号は、通話キューに使用する利用可能なサービス番号に影響する番号に割り当てられています。 ユーザーが持てる通話キューの数は、組織に割り当てられている **電話システム** および **オーディオ会議** のライセンスの数に依存しています。 ライセンスに関する詳細については、 [こちらを](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md) ご覧下さい。

    
    > [!NOTE]
    > オンライン中の組織内のユーザーへリダイレクトするには、エンタープライズ ボイス**電話システム**のライセンスを取得して有効にするか、Office 365通話プランが必要です。 「[Skype for Business と Microsoft Teams のライセンスを割り当てる](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)」をご覧ください。 エンタープライズ VoIP を有効にするには、Windows PowerShell を使用できます。 たとえば、以下を実行します。  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- Office 365通話プランの詳細については、「[Office 365 通話プランと何ですか？](/microsoftteams/what-are-calling-plans-in-office-365)」及び「[Office 365の通話プラン](/microsoftteams/calling-plans-for-office-365)」をご覧下さい。
    
    > [!NOTE]
    > Lync Server 2010 を使用している内部設置型のホストユーザーは、通話キューエージェントとしてサポートされていません。 
  
- **Skype for Business 管理センター**で取得または 別のサービスプロバイダーから電話システム通話キューへ移行した、有料またはフリーダイヤルの番号のみを割り当てることができます。 フリー ダイヤル番号の取得および使用は、コミュニケーションク レジットを設定する必要があります。
    
    > [!NOTE]
    > ユーザー (購読者) の電話番号を通話キューに割り当てることはできません。サービスの有料電話番号または無料電話番号のみを使用できます。 
  
- 電話システム通話キューからの着信呼び出しを配布するときは、コール エージェントの以下のクライアントがサポートされます:
    
  - Skype for Business デスクトップ クライアント 2016 (32 および 64 ビット バージョン)
    
  - Lync デスクトップ クライアント 2013 (32 および 64 ビット バージョン)
    
  -  IP 電話のすべてのモデルは Skype for Business Onlineにサポートされています。[Skype for Business Onlineで使用する電話を入手する](getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online.md)を参照してください。
    
  - Mac版  Skype for Business クライアント (バージョン 16.8.196 以降) 
    
  - Aandroid Skype for Business クライアント (バージョン 6.16.0.9 以降)
    
  - iPhone Skype for Business Client クライアント(バージョン 6.16.0 以降)
    
  - Mac版  Skype for Business クライアント (バージョン 6.16.0 以降)

  - Microsoft Teams Windows クライアント (バージョン 32 および 64 ビット)

  - Microsoft Teams Mac クライアント

  - Microsoft Teams iPhone用 アプリ

  - Microsoft Teams Android用 アプリ
    
## <a name="step-2---getting-or-transferring-toll-or-toll-free-service-phone-numbers"></a>ステップ 2 - 有料またはフリーダイヤルサービスの電話番号の取得または移行

通話キューを作成し設定する前に、既存の有料または無料のサービス番号を取得もしくは転送する必要があります。 有料または無料のサービスの電話番号を取得した後、  **Skype for Business 管理センター** > **音声** > **電話番号** に番号が表示され、  **番号の種類** のリストには、 **サービスー無料** として一覧表示されます。 サービス番号を取得するには、  [Skype for Business と Microsoft Teams 用のサービス電話番号の取得](getting-service-phone-numbers.md) を参照するか、既存のサービス番号を転送する場合は、  [Office 365 に電話番号を転送する](/microsoftteams/transfer-phone-numbers-to-office-365) を参照してください。
  
> [!NOTE]
> 米国以外の国では、Skype for Business 管理センターを使用してサービス番号を取得することはできません。 米国以外の国でのサービス番号を取得する方法ではなく、 [組織の電話番号を管理する](/microsoftteams/manage-phone-numbers-for-your-organization) をご覧ください。
  
## <a name="step-3---create-a-new-call-queue"></a>ステップ 3 - 新しい通話キューの作成

![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Skype for Business の管理センターを使用する**

**Skype for Business 管理センター**で、 **Call routing** > **Call queues**をクリックし、次に **新しく追加する**をクリックする:
  
### <a name="set-the-call-queue-display-name-phone-number-and-domain-if-any"></a>通話キューの表示名、電話番号、ドメイン (存在する場合) を設定します。

![通話キューの設定](../images/37ecc300-a108-4294-8463-fce570dfce72.png)
***
![1](../images/sfbcallout1.png)<br/>
**名前** 通話キュー表示名を入力します。これは必須項目で、空白を含む最大 64 文字を含めることができます。 <br/> この名前は着信の通知に表示されます。
***
![2](../images/sfbcallout2.png)<br/>**電話番号** 通話キューの有料サービスまたはフリーダイヤルサービスの電話番号を選択します。 これはオプションです。 <br/> 一覧表示されない場合は、この通話キューを作成する前にサービス番号を取得する必要があります。 サービス番号を取得するには、 [ Skype for Business and Microsoft Teamsの電話番号サービスの取得](getting-service-phone-numbers.md) を参照してください。
***
![3](../images/sfbcallout3.png)<br/>**ドメイン** 利用可能な場合は、使用する Office 365 ドメインを選択します。この項目は、Office 365 で使用しているドメインが 1 つ以上存在する場合にのみ利用できます。1 つ以上存在する場合は、リストからドメイン名を選択します。 <br/> たとえば、次のようなドメインが存在します。 _contoso.com or redmond.contoso.com_
   
### <a name="set-the-greeting-and-music-played-while-on-hold"></a>応答メッセージおよび保留中の保留音を設定する

![通話キューの設定](../images/1d395a93-7cab-4178-9295-12d5379e20de.png)
  
***
![1](../images/sfbcallout1.png)<br/>**応答メッセージ**はオプションです。 これは、発信者が通話キュー番号を使用中に再生される応答メッセージです。 <br/> オーディオファイル (.wav, .mp3 または .wma 形式) をアップロードできます。
***
![2](../images/sfbcallout2.png)<br/>**保留音** 通話キューに提供されている既定の保留音を使用するか、カスタムの保留音として使用する音声ファイルを .wav、mp3 または .wma 形式でアップロードすることができます。 
   

### <a name="select-the-call-distribution-method"></a>着信分配メソッドを選択する

![着信分配メソッドのオプションを表示する](../images/5d249515-d532-4af2-90da-011404028b89.png)
  
***
![1](../images/sfbcallout1.png)<br/>**着信分配メソッド** 通話キュー分配メソッドでは、 **[Attendant]** または **[Serial]** のいずれかを選択することができます。 新規および既存のすべての通話キューは、応答のルーティングが既定値で選択されます。 シリアル ルーティングを使用するには、UI およびコマンドレットの **シリアル** のルーティング オプションを明示的に選択する必要があります。 <br/><br/> シリアルのルーティングを選択して通話キューを保存すると、通話キューからの発信は、エージェントリストの先頭から1つずつ行われます。 エージェントが退出中、または応答しない場合、リスト上の次のエージェントを呼び出し、キューで待機中の発信が応答するかタイムアウトになるまで、すべてのエージェントの呼び出しを 1 件ずつ試みます。   

> [!NOTE]
>  **オフライン**中、**取り込み中**表示、またはこのキューからの着信を **オプトアウト** したエージェントは、シリアルルーティングからスキップされます。 
   
### <a name="select-an-agent-opt-out-option"></a>エージェントのオプトアウトのオプションを選択する

![オプトアウトするエージェントのチェック ボックスの表示](../images/99279eff-db61-4acf-9b62-64be84b6414b.png)
  
***
![1](../images/sfbcallout1.png)<br/>**エージェント オプトアウト オプション** **エージェントのオプトアウト オプション**選択して特定のキューからの着信をオプトアウトすることができます。  <br/> このオプションを有効にすると、このキュー内のすべてのエージェントはこの通話からの着信を自由に開始または停止することができます。 チェックボックスの削除することによっていつでもオプトアウトの取消しが可能で、オプトアウトされたエージェントはこの通話キューへ自動的にもう一度オプトインされます。 (すべてのエージェントの初期設定)  <br/><br/> エージェントは次の操作を行うと、オプトアウトのオプションにアクセスできます:
 1. Skype for Business クライアントデスクトップで、 **オプション** を開きます。 
 2.  **[通話転送]** タブで、 **[オンライン編集の設定]** リンクをクリックします。
 3. ユーザー設定ページで、 **通話キュー**をクリックし、次にオプトアウトしたいキューのチェック ボックスを削除します。
 
    > [!NOTE] 
    > Mac、モバイル、または Lync 2013 クライアントを使用しているエージェント、または Skype for Business 2015 サーバーを使用しているオンプレミスでホストされている Hybrid Voice ユーザーは、 [https://aka.ms/cqsettings](https://aka.ms/cqsettings) で、オプトアウトのオプションにアクセスすることができます。
   
### <a name="add-call-agents-to-a-call-queue"></a>コール エージェントを通話キューに追加する

![通話キューの設定](../images/skype-for-business-add-agents-to-call-queue.png)
  
***
![1](../images/sfbcallout1.png)<br/><br/>コール エージェント (最大数 50 件) は以下のことができます：
*     **電話システム** のライセンスを持つオンラインのユーザーとして、エンタープライズ ボイスまたは 通話の計画を有効にします。 <br/><br/> **注:** オンライン中である組織内のユーザーへリダイレクトするには、 **電話システム** のライセンスを取得し、エンタープライズ ボイスを有効にするか、通話プランを取得することが必要です。 「 [Skype for Business と Microsoft Teams のライセンスを割り当てる](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) 」をご覧ください。 エンタープライズ VoIP を有効にするには、Windows PowerShell を使用できます。 たとえば、以下を実行します。  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true` <br/><br/>
*    **電話システム** ライセンスおよび通話プランを取得しているオンラインユーザーは、計画を呼び出すと、Office 365 グループ、有効なメールの分配リスト、またはセキュリティ グループに追加されます。 分配リストまたはセキュリティグループに追加された新しいエージェントは、通話キューからの受信を開始するのには最大 30 分かかる場合があります。 新しく作成した分配リストまたはセキュリティ グループでは、通話キューで使用可能になるまで最大で48時間を要する場合があります。 新しく作成された Office 365 グループは、ほぼ瞬時にご利用可能です。 <br/> 

    > [!NOTE] 
    > Lync Server 2010を使用中のオンプレミスでホストされているユーザーはサポートされていません。           
   
### <a name="set-the-maximum-queue-size-and-maximum-wait-time"></a>最大キュー サイズと最大待機時間を設定する

![通話キューの設定](../images/3f018734-16fe-458b-827d-71fc25155cde.png)
  
***
![1](../images/sfbcallout1.png)<br/><br/>**キュー内の最大通話数** この項目を使用して、同時に通話がキュー内で待機できる最大通話数を設定します。 既定値は 50 ですが、0 から 200 に変動することができます。最大通話数に達した場合、 **で設定した方法で通話に対応します。最大通話数が以下の** 設定に達した場合:
***
![2](../images/sfbcallout2.png)<br/><br/>**最大通話数に達した場合** 通話キューが最大サイズに達した場合 ([ **キュー内の最大通話数** ] 設定を使用して設定) 、新しい着信の処理を選択できます。
*    **ビジー信号で切断します** 通話は切断されます。
*    **転送先** この項目を選択する場合は、次のオプションがあります。
     *    **社内のユーザー** **電話システム** のライセンスを持つオンラインのユーザーそしてエンタープライズ ボイス を有効にするか通話プランを取得する必要があります。 発信中のユーザーがボイスメールに転送されるように設定できます。 この設定を行うには、**[社内のユーザー] **を選択して、そのユーザーの通話が直接ボイスメールに転送されるように設定します。 <br/> <br/>ボイスメールに必要なライセンスについては、 [電話システムのボイス メールの設定](/microsoftteams/set-up-phone-system-voicemail)を参照してください。 
     
        > [!Note]
        > Lync Server 2010を使用中のオンプレミスでホストされているユーザーはサポートされていません。<br/>
     
     *    **通話キュー** 別の通話キューを選択するには、まずその通話キューを作成する必要があります。
     *    **自動応答** 自動応答を選択するには、まずその自動応答を作成する必要があります。  [「電話システムの自動応答を設定する」](set-up-a-phone-system-auto-attendant.md) を参照してください。
***
![3](../images/sfbcallout3.png)<br/><br/>**通話のキュー内での待機時間** タイムアウトが発生し、通話のリダイレクトまたは切断が必要となるまでに、通話をキュー内で保留できる時間を決定することもできます。リダイレクト先は [ **通話がタイムアウトした場合**] 設定に基づきます。0 から 45 分に設定できます。 <br/><br/> タイムアウト値は秒単位で、 15 秒間隔で設定することができます。 これにより、通話フローを細かく操作することができます。 たとえば、エージェントが 30 秒以内に応答しなかった場合、ディレクトリ検索の自動応答に転送するように指定することができます。 

***
![4](../images/sfbcallout4.png)<br/><br/>**通話がタイムアウトした場合** [ **通話のキュー内での待機時間**] 設定で指定した制限に達した通話に対する処理方法を選択できます。
*    **切断** 通話は切断されます。
*    **転送先** この項目を選択する場合は、次のオプションがあります。
     *     **社内のユーザー** **電話システム** のライセンスを持つオンラインユーザーで、エンタープライズ ボイス が有効化されているまたは、通話プランを取得済みである必要があります。 発信中のユーザーがボイスメールに転送されるように設定することができます。 この設定を行うには、**[社内のユーザー]** を選択して、そのユーザーの通話が直接ボイスメールに転送されるように設定します。 </br><br/>  ボイスメールに必要なライセンスについては、 [「電話システムのボイスメールの設定」](/microsoftteams/set-up-phone-system-voicemail) を参照してください。 

        > [!Note]
        > Lync Server 2010 を使用中のオンプレミスでホストされているユーザーはサポートされていません。<br/>

     *    **通話キュー** 別の通話キューを選択するには、まずその通話キューを作成する必要があります。
     *    **自動応答** 自動応答を選択するには、まずその自動応答を作成する必要があります。  [「電話システムの自動応答を設定する」](set-up-a-phone-system-auto-attendant.md) を参照してください。
   
## <a name="changing-the-users-caller-id-to-be-a-call-queues-phone-number"></a>ユーザーの発信者番号通知を通話キューの電話番号に変更する

**New-CallingLineIdentity** コマンドレットを使用してポリシーを作成する代わりに、アウトバウンドコールの発信者番号通知を通話キューに変更することでユーザーIDを保護します。
  
これを行う場合は、次を実行します。
  
```
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

 **Grant-CallingLineIdentity** コマンドレットを使用してユーザーのポリシーを適用します。 これを行う場合は、次を実行します。
  
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

- Windows PowerShell は、ユーザーと、ユーザーが実行できる作業範囲を管理します。 Windows PowerShell を利用すると、Office 365 と Skype for Business Online の管理を 1 か所で行うことができるので、複数のタスクを担当する管理者の日常業務を単純化できます。 Windows PowerShell の使用を開始するには、次のトピックを参照してください。
    
  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Office 365 のWindows PowerShell を使用する理由](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell には、ただ Office 365 管理センターを使用するだけではなく、速度、単純さ、生産性において多くの利点があります。次のトピックでこれらの利点について説明します。
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [クイック リファレンス: Windows PowerShell を使用した一般的な Lync Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>関連トピック
[Office 365 の電話システムで利用できる機能](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[Skype for Business および Microsoft Teams のサービス電話番号の取得](getting-service-phone-numbers.md)

[国および地域ごとの電話会議および通話プランの利用可能性](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

  
 
