---
title: "電話システムで通話キューを作成します。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: makolomi
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
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
- Phone System
- Strat_SB_PSTN
description: "電話システムで Office 365 (クラウド PBX) 通話キューを提供する組織あいさつ文]、[保留中の音楽配布リストとセキュリティ グループのエージェントの電話の通話をリダイレクトを設定する方法について説明します。キューの最大サイズ、タイムアウト、および通話処理オプションを設定することもできます。 "
ms.openlocfilehash: 363c6d7eefd63d1f89eb5d1420e516894d432b6b
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="create-a-phone-system-call-queue"></a>電話システムで通話キューを作成します。

電話システム キューには、組織、機能を自動的に、通話を保留する、および他のユーザーの中に通話の処理は、次の使用可能な通話エージェントの検索機能の電話番号着信あるときに使用されるあいさつ文が含まれています。通話は、[保留中に音楽を待機しています。組織の 1 つまたは複数の通話キューを作成できます。
  
電話システム通話キューを提供できます。
  
- 組織のあいさつ文の場合。
    
- ユーザーが待機しているときに音楽を保持します。
    
- メールが有効な配布リストとセキュリティ グループの担当者に着信のリダイレクトします。
    
- 通話キューの最大サイズ、タイムアウト、および通話処理オプションの設定を行っています。
    
他のユーザーを呼び出すと設定されている電話番号を通話キュー、それらが聞くあいさつ文を (いずれかを設定している) 場合は、最初にし、キューを保存して、次の使用可能な通話エージェントを待ちます。呼び出し先の人が呼び出し*最初に、最初に*(FIFO) のように通話エージェントに提供するは待機している場合、保留中に音楽を聞きます。
  
キュー内で待機しているすべての通話は応答ルーティング モードまたはシリアル ルーティング モードを使用して配布します。
  
- 応答ルーティングでは、キュー内の最初の呼び出しは、同時にすべてのエージェントを呼び出しします。
    
- シリアル ルーティングでは、キュー内の最初の呼び出しは 1 つずつのすべての通話エージェントをリングします。
    
    > [!NOTE]
    > **オフライン**では、**応答不可]**に自分のプレゼンスを設定してあるまたは通話キューから選んだ通話担当者と呼ばれるされません。
  
- 1 つだけ着信通知 (キューの先頭にある電話) への同時呼び出しエージェントに送信されます。
    
- 通話のエージェントでは、通話を承諾、着信通話エージェント キュー内の次の着信通話が開始されます。
    
## <a name="step-1---getting-started"></a>手順 1 - 作業の開始

通話キューの使用を開始するには、点に注意する必要は。
  
- 組織は、Enterprise E3 および**電話システム**のライセンスまたは Enterprise E5 ライセンス (最低) が必要です。割り当てられている**電話システムで**ユーザーのライセンスの数では、通話キューのために利用できるサービス番号の数に反映されます。ことが通話キューの数は、組織内で割り当てられている**電話システム**と**電話会議**のライセンスの数とは異なります。詳細については、ライセンス、[[次のとおり](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)です。
    
    > [!NOTE]
    > オンラインである、組織内のユーザーに通話をリダイレクトするには、エンタープライズ ボイスを有効にするや、Office 365 のプランを呼び出すことがある、**電話システムで**のライセンスが必要があります。[ビジネスや Microsoft チームのライセンスを割り当てる Skype](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)を参照してください。エンタープライズ ボイスを有効に Windows PowerShell を使用することができます。例を実行します。`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- Office 365 のプランを呼び出すの詳細については、次を参照してください。[とは、Office 365 のプランの呼び出しですか?](../what-are-calling-plans-in-office-365/what-are-calling-plans-in-office-365.md) [for Office 365 プランの呼び出し](../skype-for-business-and-microsoft-teams-add-on-licensing/calling-plans-for-office-365.md)とします。
    
    > [!NOTE]
    > ユーザーが内部設置型にホストされている Lync Server 2010 を使用して通話のキュー エージェントとしてはサポートされません。 
  
- のみ、有料電話番号と**Skype for Business 管理センター**で使用しているか、別のサービス プロバイダーから電話システムで通話キューに転送するサービスのフリー ダイヤル電話番号を割り当てることができます。サービスのフリー ダイヤル番号を使用して、アクセスするには、クレジットの通信を設定する必要があります。
    
    > [!NOTE]
    > キューの通話のみ有料サービスを提供するユーザー (サブスクライバー) の電話番号を割り当てることができませんまたはフリー ダイヤル電話番号を使用することができます。 
  
- 電話システムで通話キューから着信を配布する場合は、これらのクライアントが通話エージェントでサポートされます。
    
  - Skype for Business デスクトップ クライアント 2016 (32 と 64 ビット バージョン)
    
  - Lync デスクトップ クライアント 2013 (32 と 64 ビット バージョン)
    
  - すべての IP 電話モデルが Skype for Business Online に対応します。[Skype for Business Online の取得電話](getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online.md)を参照してください。
    
  - Mac の Skype for Business クライアント (バージョン 16.8.196 以降) 
    
  - Android の Skype for Business クライアント (バージョン 6.16.0.9 以降)
    
  - iPhone の Skype for Business クライアント (バージョン 6.16.0 以降)
    
  - iPad Skype for Business クライアント (バージョン 6.16.0 以降)
    
## <a name="step-2---getting-or-transferring-toll-or-toll-free-service-phone-numbers"></a>手順 2 - 取得または有料またはフリー ダイヤルのサービスの電話番号に転送します。

作成して、通話キューを設定する、前にしたり、既存の有料またはフリー ダイヤルのサービスに転送する必要があります。 数値。**Skype for Business 管理センター**で表示されますが、有料またはフリー ダイヤルのサービスの電話番号が表示されたら後、 > **音声** > **電話番号**、およびとして登録されている**サービス - 無料**数値型**の一覧に表示されます。**.サービス番号を移動するには、 [Skype for Business とチームの Microsoft の取得サービスの電話番号](getting-service-phone-numbers.md)が表示されるまたは転送を既存のサービス番号の場合は、 [Office 365 への電話番号に転送](../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md)を参照してください。
  
> [!NOTE]
> 米国外の場合は、Skype for Business 管理センターを使ってサービス番号を取得することはできません。米国の外部から行う方法を表示する代わりに[、組織の管理の電話番号](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)を移動します。
  
## <a name="step-3---create-a-new-call-queue"></a>手順 3 - 新しい通話キューを作成します。

**Skype for Business 管理センター**で、[**着信のルーティング**] をクリックします > **キューの通話**をには、[**新規追加**] をクリックします。
  
### <a name="set-the-call-queue-display-name-phone-number-and-domain-if-any"></a>通話キューの表示名、電話番号 (ある場合)、ドメインを設定します。

![通話キューを設定します。](../images/37ecc300-a108-4294-8463-fce570dfce72.png)
***
![数値 1](../images/sfbcallout1.png)<br/>
**名**通話キューのわかりやすい表示名を入力します。これは必須であり、スペースも含めて、最大 64 文字を含めることができます。<br/> 着信通話の通知には、この名前が表示されます。
***
![数値 2](../images/sfbcallout2.png)<br/>**電話番号**サービスの有料通話キューのフリー ダイヤル電話番号を選択します。これはオプションです。<br/> いずれかを使用する必要がある場合にこの通話キューを作成する前に、サービスの番号を取得する必要がありますが表示されます。サービス番号を移動するには、 [Skype for Business とチームの Microsoft の取得サービスの電話番号](getting-service-phone-numbers.md)を参照してください。
***
![数値 3](../images/sfbcallout3.png)<br/>**ドメイン**これを利用できる場合は、使用する Office 365 ドメインを選びます。これは、Office 365 で使用されている 1 つ以上のドメインがある場合にのみ。場合は、1 つ以上ある場合は、一覧からドメイン名を選択する必要があります。<br/> たとえばなどのドメインがある可能性があります: _contoso.com または redmond.contoso.com_
   
### <a name="set-the-greeting-and-music-played-while-on-hold"></a>あいさつ文と再生保留中に音楽を設定します。

![通話キューを設定します。](../images/1d395a93-7cab-4178-9295-12d5379e20de.png)
  
***
![数値 1](../images/sfbcallout1.png)<br/>**[あいさつ文**は省略可能です。これは、通話キュー番号に電話の発信元のユーザーに再生されるあいさつ文です。<br/> オーディオ ファイル (.wav、.mp3、または .wma 形式) をアップロードすることができます。
***
![数値 2](../images/sfbcallout2.png)<br/>**上の音楽を保持**通話キューで提供されている保留中で、既定の音楽を使用することができますか、または保留中のユーザー設定の音楽として使用する .wav、mp3、または .wma 形式でのオーディオ ファイルをアップロードすることができます。 
   

### <a name="select-the-call-distribution-method"></a>通話の配布方法を選択します。

![配布方法のオプションを表示するには、通話](../images/5d249515-d532-4af2-90da-011404028b89.png)
  
***
![数値 1](../images/sfbcallout1.png)<br/>**着信の配布方法****応答**または**シリアル**通話キュー配布方法を選択できます。すべての新規または既存の通話キュー アテンダント ルーティングが既定で選択されている必要があります。シリアルをルーティングする機能を使用するのには、明示的に UI とコマンドレットの**シリアル**ルーティング オプションを選択する必要があります。<br/><br/> シリアル ルーティングを選択すると、通話キューが保存されている、キューからの通話はエージェントのリストの先頭から 1 つずつエージェントをリングします。エージェント閉じ、通話は選択されない場合、通話はリストには、次のエージェントを呼び出し、エージェントの 1 つずつまで選択してまたはキュー待機して時刻をすべてしようとします。<br/><br/>  **メモ:**シリアル ルーティングが**オフライン****応答不可**] に自分のプレゼンスを設定している、またはのこのキューから通話を開始して**使用を停止した**担当者をスキップします。  
   
### <a name="select-an-agent-opt-out-option"></a>オプション脱退、エージェントの選択

![表示する、エージェントの利用を停止] チェック ボックス](../images/99279eff-db61-4acf-9b62-64be84b6414b.png)
  
***
![数値 1](../images/sfbcallout1.png)<br/>**エージェントが脱退オプション**通話キュー エージェント**エージェントが脱退] オプション**を選択して、特定のキューからの通話の応答を停止するには、次のように許可することができます。  <br/> このオプションを有効にするには、このキュー内のすべてのエージェント開始または停止するのには、この通話キューから電話を受けるにはことができます。ことで取り消せますエージェント オプトアウト特権いつでも、チェック ボックスをオフにしてエージェントになる自動的に加入してでこのキューでもう一度 (すべてのエージェントの既定の設定) する原因になっています。<br/><br/> 脱退オプションを使用するには、エージェントは、次の操作を行うことができます。
 1. デスクトップ、Skype for Business クライアントでは、**オプション**を開きます。 
 2. [**着信の転送**] タブの**オンライン設定の編集**] をクリックします。
 3. [ユーザー設定] ページは、**通話キュー**をクリックし、利用を停止する、キューのチェック ボックスをオフにし、します。
   
### <a name="add-call-agents-to-a-call-queue"></a>通話キューに通話エージェントを追加します。

![通話キューを設定します。](../images/skype-for-business-add-agents-to-call-queue.png)
  
***
![数値 1](../images/sfbcallout1.png)<br/><br/>通話エージェント (最大 50) があります。
*    **電話システムで**ライセンスを使って、オンラインのユーザーと、エンタープライズ ボイスや通話プランを有効にします。 <br/><br/> **メモ:** オンラインである、組織内のユーザーに通話をリダイレクトするには、エンタープライズ ボイスを有効にするや、通話プランを使って、**電話システムで**のライセンスが必要があります。[ビジネスや Microsoft チームのライセンスを割り当てる Skype](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)を参照してください。エンタープライズ ボイスを有効に Windows PowerShell を使用することができます。例を実行します。`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true` <br/><br/>
*    オンラインのユーザーに、**電話システムで**ライセンスされた通話プランは Office 365 グループをメールが有効な配布リスト、またはセキュリティ グループに追加するとします。配布リストまたは通話キューからの通話の受信を開始するセキュリティ グループに追加された新しいエージェントの 30 分ほどかかる場合があります。新しく作成された配布リストまたはセキュリティ グループは、通話キューで使用する使用可能になるまで 48 時間以内にかかる場合があります。新しく作成された Office 365 グループを利用すぐできます。<br/> 

    > [!NOTE] 
    > ユーザーが内部設置型にホストされている Lync Server 2010 の使用はサポートされません。           
   
### <a name="set-the-maximum-queue-size-and-maximum-wait-time"></a>キューの最大サイズと最大待機時間を設定します。

![通話キューを設定します。](../images/3f018734-16fe-458b-827d-71fc25155cde.png)
  
***
![数値 1](../images/sfbcallout1.png)<br/><br/>**最大通話キュー**同時にキュー内の待機できる、呼び出しの最大数を設定するのには、これを使用します。既定では、50 が範囲は 0 を取り出します。 この制限に達したときに、通話は、下の [**通話の最大数に達した場合**設定で設定した方法で処理されます。
***
![数値 2](../images/sfbcallout2.png)<br/><br/>**通話の最大数に達した場合**通話キューには、(**最大通話キュー**設定を使用する設定) の最大サイズになると、新しい着信通話はどうなりますかを選択できます。
*    **通話を切断**通話は切断されます。
*    **この通話を転送します。**この場合は、これらのオプション必要があります。
     *    **社内のユーザー****電話システムで**ライセンスを使って、オンラインのユーザーとのエンタープライズ ボイスを有効にする、または通話プランを使っています。相手呼び出しをボイス メールを送信できないようにする設定ことができます。これを行うには、**社内のユーザー**を選択し、着信が直接ボイス メールに転送するのには、この人を設定します。<br/>
     
        > [!Note]
        > ユーザーが内部設置型にホストされている Lync Server 2010 の使用はサポートされません。<br/>
     
     *    **キューを呼び出す**必要があります既に作成している別の通話キューが、その通話キューを選択できます。
     *    **自動応答**必要がありますが既に作成して、自動応答は、後は、その自動応答を選択することができます。[電話システムでの自動応答を設定する](set-up-a-phone-system-auto-attendant.md)を参照してください。
***
![数値 3](../images/sfbcallout3.png)<br/><br/>**通話を開始できるキューで待機する時間を確認します。**キュー内の保留中の通話時間ができることもできます前に、タイムアウトが発生して、リダイレクト、または接続が切断する必要があります。リダイレクト先は、**電話をかけるタイムアウトが発生する場合**の設定を設定する方法に基づいています。45 分を 0 から時刻を設定できます。<br/><br/> 15 秒間隔で秒単位でタイムアウト値を設定できます。これにより、細かくと通話の流れを操作することができます。たとえば、30 秒以内にエージェントが応答しないすべての呼び出しをディレクトリの検索の自動応答に移動することを指定した可能性があります。 

***
![番号 4](../images/sfbcallout4.png)<br/><br/>**電話をかけるタイムアウトが発生する場合**通話には、**電話をかけることができますキューで待機する時間**の設定で設定した制限に達すると、この呼び出しの動作を選択します。
*    **切断**通話は切断されます。
*    **この通話を転送します。**この場合は、これらのオプション必要があります。
     *    **社内のユーザー****電話システムで**ライセンスを使って、オンラインのユーザーのエンタープライズ ボイスを有効にするし、プランの呼び出しがあります。相手呼び出しをボイス メールを送信できないようにする設定ことができます。これを行うには、**社内のユーザー**を選択し、着信が直接ボイス メールに転送するのには、この人を設定します。 

        > [!Note]
        > ユーザーが内部設置型にホストされている Lync Server 2010 の使用はサポートされません。<br/>

     *    **キューを呼び出す**必要があります既に作成している別の通話キューが、その通話キューを選択できます。
     *    **自動応答**必要がありますが既に作成して、自動応答は、後は、その自動応答を選択することができます。[電話システムでの自動応答を設定する](set-up-a-phone-system-auto-attendant.md)を参照してください。
   
## <a name="changing-the-users-caller-id-to-be-a-call-queues-phone-number"></a>ユーザーの発信者番号に通話キューの電話番号を変更します。

ユーザーの代わりに**新しい CallingLineIdentity**コマンドレットを使用してポリシーを作成して、発信者番号の呼び出しキューに発信を変更することによって保護できます。
  
これを行うには、次のコマンドを実行します。
  
```
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

**許可を付与する CallingLineIdentity**コマンドレットを使用してユーザーにポリシーを適用します。これを行うには、次のコマンドを実行します。
  
```
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

組織内の発信者 ID の設定を変更する方法の詳細についてご[次のとおり](../what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization.md)です。
  
## <a name="want-to-know-more"></a>詳細を知りたいですか。

Windows PowerShell を使ってを作成し、通話キューを設定することもできます。
  
### <a name="call-queue-cmdlets"></a>通話キュー コマンドレット

通話キューを管理する必要があるコマンドレットを紹介します。
  
- [新しい-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796459.aspx)
    
- [設定 CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796457.aspx)
    
- [Get CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796458.aspx)
    
- [削除 CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796456.aspx)
    
### <a name="more-about-windows-powershell"></a>Windows PowerShell の詳細

- Windows powershell となるはすべてを管理するユーザーとユーザーの許可または使用できません。Windows PowerShell で Office 365 と Skype for Business Online の複数のタスクを実行するがある場合、日常業務を簡素化する管理の 1 つのポイントを使用して管理できます。Windows PowerShell で開始するには、次のトピックを参照してください。
    
  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Office 365 PowerShell を使用する必要がある理由](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell では多くの利点速度、わかりやすいように、および生産性でのみ実行しようとする設定の変更、多くのユーザーに一度になどの Office 365 管理センターを使用します。次のトピックでこれらの利点について学習します。
    
  - [Windows PowerShell で Office 365 を管理する最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Windows PowerShell を使用して、Skype for Business Online の管理するには](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell を使用して、共通の Skype for Business Online の管理タスクを実行するには](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>関連トピック
[ここではされた電話システムで Office 365 での表示](here-s-what-you-get-with-phone-system.md)

[Skype for Business とチームの Microsoft サービスの電話番号を取得します。](getting-service-phone-numbers.md)

[電話会議とプランの呼び出しの国と地域の空き時間情報](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
