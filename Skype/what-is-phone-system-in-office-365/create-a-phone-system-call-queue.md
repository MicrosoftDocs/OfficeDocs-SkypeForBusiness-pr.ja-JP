---
title: "電話システムで通話キューを作成します。"
ms.author: tonysmit
author: tonysmit
ms.date: 11/15/2017
ms.audience: ITPro
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.custom: Strat_SB_PSTN
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061

description: "Learn how to set up phone system for Office 365 (Cloud PBX) call queues to give you an organizational greeting, music on hold, and redirecting calls to call agents in distribution lists and security groups. You can also set the maximum queue size, time out, and call handling options. "
---

# 電話システムで通話キューを作成します。

> [!IMPORTANT]
> この記事は機械翻訳されています。機械翻訳についての「[免責事項](67ccda94-1210-43fb-a25b-7b9785f8a061.md#MT_Footer)」をお読みください。この記事の英語版を参照するには、[ここ](https://support.office.com/en-us/article/67ccda94-1210-43fb-a25b-7b9785f8a061)をクリックしてください。 
  
Skype for Business Online クラウド PBX の通話キューには、他のユーザーからの自分の組織の電話番号への通話に対する応答メッセージ、自動的に通話を保留する機能、および通話の発信者が保留メロディを聴いている間に通話を処理するために次に利用できるコール エージェントの検索が含まれます。組織では単一または複数の通話キューを作成できます。
  
クラウド PBX の通話キューでは次の項目を提供できます。
  
- 組織の応答メッセージ。
    
- 通話の保留中に再生される保留音。
    
- メール対応配布リストとセキュリティ グループを使用した、コール エージェントへの通話のリダイレクト。
    
- 通話キューの最大サイズ、タイムアウト、通話処理オプションの設定。
    
通話キューが設定されている電話番号に通話すると、最初に応答メッセージ (設定されている場合) が再生され、キューに置かれます。次のコール エージェントが利用可能になるまで待機します。保留中で待機しているときには、保留音が再生されます。通話は *先入先出法*  (FIFO) でコール エージェントに送られます。
  
キューで待機しているすべての通話は、応答ルーティング モードを使用して配布されます。
  
- キューにある最初の通話はすべてのコール エージェントを同時に呼び出します。
    
    > [!NOTE]
    > **オフライン**のコール エージェントまたは状況を **応答不可**に設定しているコール エージェントは呼び出されません。 
  
- 一度に 1 回のみの着信通知 (キューの最初にある通話) がコール エージェントに送信されます。
    
- コール エージェントが通話を受けると、キューにある次の着信がコール エージェントを呼び出します。
    
## ステップ 1 - はじめに

通話キューを使用する場合は、次の重要な点について留意してください。
  
- 組織には、(最低でも) Enterprise E3 および Skype for Business クラウド PBX ライセンスまたは Enterprise E5 ライセンスが必要です。割り当てる Skype for Business クラウド PBX ユーザー ライセンスの数量は、通話キューで使用できるサービス電話番号の数量に影響します。利用可能な通話キューの数量は、組織に割り当てられている Skype for Business クラウド PBX と PSTN 会議のライセンス数によって異なります。ライセンスの詳細については、[Skype for Business と Microsoft Teams のアドオン ライセンス](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)をご覧ください。
    
    > [!NOTE]
    > オンラインにある、組織内のユーザーに通話をリダイレクトするには、エンタープライズ ボイスを有効にするや、PSTN 通話プランがある、クラウド PBX ライセンスが必要があります。[Skype for Business と Microsoft Teams のライセンスを割り当てる](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)を参照してください。エンタープライズ ボイスを有効に Windows PowerShell を使用することができます。実行例:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- PSTN 通話の詳細については、「[Office 365 の通話プランについて](../what-are-calling-plans-in-office-365/what-are-calling-plans-in-office-365.md)」および「[Office 365 向けの通話プラン](../skype-for-business-and-microsoft-teams-add-on-licensing/calling-plans-for-office-365.md)」をご覧ください
    
    > [!NOTE]
    > Skype for Business Server 2015 または Lync Server 2013/2010 を使用するオンプレミスでホストされるユーザーは通話キュー エージェントとしてサポートされません。 
  
- 割り当てることができる電話番号は Skype for Business 管理センターで取得した有料および無料のサービス電話番号、または別のサービス プロバイダーからクラウド PBX 通話キューに移行した有料および無料のサービス電話番号のみです。無料のサービス電話番号を取得して使用するには、PSTN 従量課金プランを設定する必要があります。この設定を行うには、「[通信クレジットについて](../skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits.md)」および「[組織のために通信クレジットをセットアップする](../skype-for-business-and-microsoft-teams-add-on-licensing/set-up-communications-credits-for-your-organization.md)」をご覧ください。
    
    > [!NOTE]
    > ユーザー (購読者) の電話番号を通話キューに割り当てることはできません。サービスの有料電話番号または無料電話番号のみを使用できます。 
  
- クラウド PBX 通話キューからの着信通話を配布している場合、これらのクライアントは通話エージェントでサポートされます。
    
  - Skype for Business デスクトップ クライアント 2016 (32 および 64 ビット バージョン)
    
  - Lync デスクトップ クライアント 2013 (32 および 64 ビット バージョン)
    
  - Skype for Business Online でサポートされるすべての IP 電話機モデル。「[Skype for Business Online で使う電話を入手する](getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online.md)」をご覧ください。
    
  - Mac の Skype for Business クライアント (バージョン 16.8.196 以降)
    
  - Android の Skype for Business クライアント (バージョン 6.16.0.9 以降)
    
  - iPhone の Skype for Business クライアント (バージョン 6.16.0 以降)
    
  - iPad Skype for Business クライアント (バージョン 6.16.0 以降)
    
## ステップ 2 - 有料またはフリーダイヤルのサービス電話番号の取得または移行

通話キューを作成し、設定する前に、有料またはフリーダイヤルのサービス番号を取得するか、既存の番号を移行する必要があります。有料またはフリーダイヤルのサービス番号を取得すると、[ **Skype for Business 管理センター**] > [ **音声**] > [ **電話番号**] タブに表示され、[ **番号の種類**] が [ **サービス - フリーダイヤル**] として一覧表示されます。サービス番号を取得するには、「[Skype for Business サービスの電話番号を取得する](getting-service-phone-numbers-for-skype-for-business-and-microsoft-teams.md)」をご覧ください。既存のサービス番号を移行する場合は、「[Office 365 への電話番号に転送します。](../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md)」をご覧ください。
  
> [!NOTE]
> 米国以外の国では、Skype for Business 管理センターを使用してサービス番号を取得することはできません。米国以外の国でのサービス番号を取得する方法については、[組織の電話番号を管理する](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)をご覧ください。 
  
## ステップ 3 - 新しい通話キューの作成

 **Skype for Business 管理センター**で、[ **通話ルーティング**] > [ **通話キュー**] の順にクリックしてから、[ **新規追加**] をクリックします。
  
### 通話キューの表示名、電話番号、ドメイン (存在する場合) を設定します。

![Setting up a call queue.](../images/37ecc300-a108-4294-8463-fce570dfce72.png)
  
|||
|:-----|:-----|
|**1** <br/> |**名前** 通話キューの分かりやすい名前を入力します。この項目は必須で、空白を含む最大 64 文字を含めることができます。 <br/> この名前は着信の通知に表示されます。  <br/> |
|**2** <br/> |**電話番号** 通話キューのサービスの有料電話番号または無料電話番号を選択します。この項目は必須です。 <br/> 一覧表示されない場合は、この通話キューを作成する前にサービス番号を取得する必要があります。サービス番号を取得するには、「[Skype for Business サービスの電話番号を取得する](getting-service-phone-numbers-for-skype-for-business-and-microsoft-teams.md)」をご覧ください。  <br/> |
|**3** <br/> |**ドメイン** 利用可能な場合は、使用する Office 365 ドメインを選択します。この項目は、Office 365 で使用しているドメインが 1 つ以上存在する場合にのみ利用できます。1 つ以上存在する場合は、リストからドメイン名を選択します。 <br/> たとえば、次のようなドメインが存在します。 _contoso.com or redmond.contoso.com_ <br/> |
   
### 応答メッセージおよび保留中の保留音を設定する

![Setting up a call queue.](../images/1d395a93-7cab-4178-9295-12d5379e20de.png)
  
|||
|:-----|:-----|
|**1** <br/> |**応答メッセージ**は省略可能です。これは、発信者が通話キュー番号に入っているときに再生される応答メッセージです。  <br/> 音声ファイル (.wav, .mp3 または .wma 形式) をアップロードできます。  <br/> |
|**2** <br/> |**保留音**。通話キューに提供されている既定の保留音を使用するか、カスタムの保留音として使用する音声ファイルを .wav、mp3 または .wma 形式でアップロードできます。  <br/> |
   
### コール エージェントを通話キューに追加する

![Set up call queues.](../images/9c0c551b-218b-4268-9b73-c85000c99296.png)
  
|||
|:-----|:-----|
|**1**| コール エージェント (最大 50) は次に設定できます。 Skype for Business クラウド PBX ライセンスを持ち、エンタープライズ VoIP を有効にしているか PSTN 通話プランを使用している Online ユーザー。> [!NOTE]>  オンラインにある、組織内のユーザーに通話をリダイレクトするには、エンタープライズ ボイスを有効にするや、PSTN 通話プランがある、クラウド PBX ライセンスが必要があります。[Skype for Business と Microsoft Teams のライセンスを割り当てる](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)を参照してください。エンタープライズ ボイスを有効に Windows PowerShell を使用することができます。実行例:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`           メール対応の配布リストまたはセキュリティ グループに追加された Skype for Business クラウド PBX ライセンスまたは PSTN 通話プランを持つ Online ユーザー。配布リストまたはセキュリティ グループに追加された新しいエージェントが通話キューから通話を受信し始めるまでに最長で 30 分かかる場合があります。新規に作成された配布リストまたはセキュリティ グループが通話キューで使用できるようになるまでに最長で 48 時間かかる場合があります。> [!NOTE]>  Office 365 グループ (最新) は、通話キューでは使用できません。          > [!NOTE]>  Skype for Business Server 2015 または Lync Server 2013/2010 を使用するオンプレミスでホストされるユーザーはサポートされません。          |
   
### 最大キュー サイズと最大待機時間を設定する

![Set up a call queue.](../images/3f018734-16fe-458b-827d-71fc25155cde.png)
  
|||
|:-----|:-----|
|**1** <br/> |**キュー内の最大通話数** この項目を使用して、同時に通話がキュー内で待機できる最大通話数を設定します。既定は 50 ですが、0 から 200 の範囲で設定できます。 <br/> この制限に達すると、通話は次の [ **呼び出しの最大数に達した場合**] 設定で指定した方法で処理されます。  <br/> |
|**2** <br/> |**呼び出しの最大数に達した場合** 通話キューがその最大サイズ ([ **キュー内の最大通話数**] 設定で指定) に達したときの着信の処理を選択できます。  <br/> **ビジー信号を切断します** 通話は切断されます。 <br/> **転送先** この項目を選択する場合は、次のオプションがあります。 <br/> **あなたの会社の人** Skype for Business クラウド PBX ライセンスを持ち、エンタープライズ VoIP を有効にしているか PSTN 通話プランを使用している Online ユーザー。発信者をボイスメールに移動するように設定できます。この設定を行うには、[ **あなたの会社の人**] を選択します。この人への通話は直接ボイスメールに転送されます。  <br/> > [!NOTE]>  Skype for Business Server 2015 および Lync Server 2013/2010 を使用するオンプレミスでホストされるユーザーはサポートされません。          **通話キュー** 別の通話キューを既に作成している必要があります。作成している場合は、その通話キューを選択できます。 <br/> **自動応答** 別の自動応答を既に作成している必要があります。作成している場合は、その自動応答を選択できます。「[電話システムでの自動応答を設定します。](set-up-a-phone-system-auto-attendant.md)」をご覧ください。  <br/> |
|**3** <br/> |**通話のキュー内での待機時間** タイムアウトが発生し、通話のリダイレクトまたは切断が必要となるまでに、通話をキュー内で保留できる時間を決定することもできます。リダイレクト先は [ **通話がタイムアウトした場合**] 設定に基づきます。0 から 45 分に設定できます。  <br/> |
|**4** <br/> | <br/> **通話がタイムアウトした場合** [ **通話のキュー内での待機時間**] 設定で指定した制限に達した通話に対する処理方法を選択できます。  <br/> **切断** 通話は切断されます。 <br/> **転送先** この項目を選択する場合は、次のオプションがあります。 <br/> **あなたの会社の人** Skype for Business クラウド PBX ライセンスを持ち、エンタープライズ VoIP を有効にしているか PSTN 通話プランを使用している Online ユーザー。発信者をボイスメールに移動するように設定できます。この設定を行うには、[ **あなたの会社の人**] を選択します。この人への通話は直接ボイスメールに転送されます。  <br/> > [!NOTE]>  Skype for Business Server 2015 および Lync Server 2013/2010 を使用するオンプレミスでホストされるユーザーはサポートされません。          **通話キュー** 別の通話キューを既に作成している必要があります。作成している場合は、その通話キューを選択できます。 <br/> **自動応答** 別の自動応答を既に作成している必要があります。作成している場合は、その自動応答を選択できます。「[電話システムでの自動応答を設定します。](set-up-a-phone-system-auto-attendant.md)」をご覧ください。  <br/> |
   
## 通話キューにユーザーの発信者番号を変更します。

ユーザーの id を保護するには、 **New-CallingLineIdentity** コマンドレットを使用してポリシーを作成して、代わりに発信通話キューに、発信者を変更します。
  
この実行を実行します。
  
```
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

 **Grant-CallingLineIdentity** コマンドレットを使用してユーザーにポリシーを適用します。この実行を実行します。
  
```
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

組織内の発信者 ID の設定を変更する方法の詳細についてご[組織内での発信者番号の使用方法](../what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization.md)です。
  
## 詳細情報

Windows PowerShell を使用して通話キューを作成し、設定することもできます。
  
### 通話キューのコマンドレット

通話キューの管理で必要なコマンドレットを以下に示します。
  
- [New-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796459.aspx)
    
- [Set-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796457.aspx)
    
- [Get-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796458.aspx)
    
- [Remove-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796456.aspx)
    
### Windows PowerShell の詳細について

- Windows PowerShell で行うのは、ユーザーを管理し、ユーザーに何を許可して何を禁止するかを管理することです。Windows PowerShell を利用すると、Office 365 と Skype for Business Online の管理を 1 か所で行うことができるので、複数のタスクを担当する管理者の日常業務を単純化できます。Windows PowerShell の使用を開始するには、次のトピックを参照してください。
    
  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Office 365 PowerShell を使用する必要がある理由](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell には、ただ Office 365 管理センターを使用するだけではなく、速度、単純さ、生産性において多くの利点があります。次のトピックでこれらの利点について説明します。
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **機械翻訳についての免責事項**: この記事の翻訳はコンピューター システムによって行われており、人間の手は加えられていません。マイクロソフトでは、英語を話さないユーザーがマイクロソフトの製品、サービス、テクノロジに関するコンテンツを理解するのに役立てるため、こうした機械翻訳を提供しています。記事は機械翻訳されているため、用語、構文、文法などに誤りがある場合があります。 
  

