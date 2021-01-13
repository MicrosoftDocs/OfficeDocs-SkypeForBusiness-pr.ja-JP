---
title: Skype for Business Server Exchange Serverユニファイド メッセージングの構成
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/11/2019
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1be9c4f4-fd8e-4d64-9798-f8737b12e2ab
description: '概要: Skype for Business Server Exchange Serverユニファイド メッセージングを構成します。'
ms.openlocfilehash: 68cf4a11deccac9ad71bdb6216c4126362787498
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834037"
---
# <a name="configure-exchange-server-unified-messaging-for-skype-for-business-server-voice-mail"></a>Skype for Business Server Exchange Serverユニファイド メッセージングの構成
 
**概要:** Skype for Business Server Exchange Serverユニファイド メッセージングを構成します。
  
Skype for Business Server では、ボイスメール メッセージを Exchange Server 2016 または Exchange Server 2013 に保存できます。これらのボイスメール メッセージは、ユーザーの受信トレイに電子メール メッセージとして表示されます。 

> [!NOTE]
> Exchange 2019 では、以前に知られている Exchange ユニファイド メッセージングは使用できなくなりましたが、引き続き電話システムを使用してボイスメール メッセージを録音し、その録音をユーザーの Exchange メールボックスに残しておく必要があります。 詳細 [については、「クラウド ボイスメール サービスを計画](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) する」を参照してください。
  
Skype for Business Server と Exchange Server 2016 または Exchange Server 2013 の間でサーバー間認証を既に構成している場合は、ユニファイド メッセージングをセットアップする準備が整っています。 これを行うには、最初に新しいユニファイド メッセージング ダイヤル プランを作成し、そのダイヤル プランに割り当Exchange Server。 たとえば、次の 2 つのコマンド (Exchange 管理シェル 内から実行) は、Exchange の新しい 3 桁のダイヤル プランを構成します。
  
```powershell
New-UMDialPlan -Name "RedmondDialPlan" -VoIPSecurity "Secured" -NumberOfDigitsInExtension 3 -URIType "SipName" -CountryOrRegionCode 1
Set-UMDialPlan "RedmondDialPlan" -ConfiguredInCountryOrRegionGroups "Anywhere,*,*,*" -AllowedInCountryOrRegionGroups "Anywhere"
```

例の最初のコマンドで、VoIPSecurity パラメーターとパラメーター値 "Secured" は、信号チャネルがトランスポート層セキュリティ (TLS) を使用して暗号化されたかどうかを示します。 URIType "SipName" は、SIP プロトコルを使用してメッセージが送受信されることを指定し、CountryOrRegionCode の 1 は、ダイヤル プランが US に適用されることを指定します。
  
2 番目のコマンドで、ConfiguredInCountryOrRegionGroups パラメーターに渡されるパラメーター値は、このダイヤル プランで使用できる国内のグループを指定します。 パラメーター値 "Anywhere, \* \* , , " \* は、以下を設定します。
  
- グループ名 ("Anywhere")
    
- AllowedNumberString ( \* , a wildcard character indicating that any number string is allowed)
    
- DialNumberString ( \* , a wildcard character indicating that any dialed number is allowed number is allowed)
    
- TextComment ( \* , a wildcard character indicating that any text command is allowed)
    
> [!NOTE]
> 新しいダイヤル プランを作成すると、既定のメールボックス ポリシーも作成されます。 
  
新しいダイヤル プランを作成して構成した後、新しいダイヤル プランをユニファイド メッセージング サーバーに追加し、そのサーバーのスタートアップ モードを変更する必要があります。特に、スタートアップ モードを "デュアル" に設定する必要があります。 これらの両方のタスクは、Exchange 管理シェル 内から実行できます。
  
```powershell
Set-UmService -Identity "atl-exchangeum-001.litwareinc.com" -DialPlans "RedmondDialPlan" -UMStartupMode "Dual"
```

ユニファイド メッセージング サーバーを構成した後、次に Enable-ExchangeCertificate コマンドレットを実行して、Exchange 証明書がユニファイド メッセージング サービスに適用されていることを確認する必要があります。
  
```powershell
Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "EA5A332496CC05DA69B75B66111C0F78A110D22d" -Services "SMTP","IIS","UM"
```

証明書の割り当てが適切に行われた後、ユニファイド メッセージング サーバー上の MsExchangeUM サービスを停止し、再起動する必要があります。このサービスは、スタートアップ モードを変更した場合はいつでも、停止して再起動する必要があります。
  
ユニファイド メッセージング サーバーの構成が終了すると、UM Call Router を構成できます。
  
```powershell
Set-UMCallRouterSettings -Server "atl-exchange-001.litwareinc.com" -UMStartupMode "Dual" -DialPlans "RedmondDialPlan" 
Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "45BAA32496CC891169B75B9811320F78A1075DDA" -Services "IIS","UMCallRouter"
```

スタートアップ モードが変更されているため、UM Call Router をホストしているコンピューター上で MsExchangeUMCR サービスを停止および再起動する必要があります。
  
ユニファイド メッセージングのセットアップを完了するには、UM メールボックス ポリシーを作成し、そのポリシーを使用して、ユーザーに対してユニファイド メッセージングを有効にする必要があります。次のようなコマンドを使用して、メールボックス ポリシーを作成できます。
  
```powershell
New-UMMailboxPolicy -Name "RedmondMailboxPolicy" -AllowedInCountryOrRegionGroups "Anywhere"
```

また、次のようなコマンドを使用して、ユーザーに対してユニファイド メッセージングを有効にできます。
  
```powershell
Enable-UMMailbox -Extensions 100 -SIPResourceIdentifier "kenmyer@litwareinc.com" -Identity "litwareinc\kenmyer" -UMMailboxPolicy "RedmondMailboxPolicy"
```

上のコマンドで、Extensions パラメーターはユーザーの内線番号を表します。この例の場合、ユーザーの内線番号は 100 です。
  
メールボックスを有効にすると、ユーザー kenmyer@litwareinc.com は Exchange ユニファイド メッセージングを使用できるようになります。 Skype for Business Server 管理シェル内から [Test-CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/test-csexumconnectivity?view=skype-ps) コマンドレットを実行すると、ユーザーが Exchange UM に接続できると確認できます。
  
```powershell
$credential = Get-Credential "litwareinc\kenmyer"
Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential
```

ユニファイド メッセージングが有効化されている 2 番目のユーザーがいる場合は、[Test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/test-csexumvoicemail?view=skype-ps) コマンドレットを使用して、この 2 番目のユーザーが最初のユーザーにボイスメール メッセージを残すことができるかを確認できます。
  
```powershell
$credential = Get-Credential "litwareinc\pilar"
Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential
```



## <a name="configuring-unified-messaging-on-microsoft-exchange-server"></a>Microsoft Exchange Server でのユニファイド メッセージングのMicrosoft Exchange Server 
> [!IMPORTANT]
> Exchange ユニファイド メッセージング (UM) を使用して エンタープライズ VoIP ユーザーに通話応答、Outlook Voice Access、または自動応答サービスを提供する場合は [、「Plan for Exchange Unified Messaging integration in Skype for Business」](../../plan-your-deployment/integrate-with-exchange/unified-messaging.md)を参照し、このセクションの手順に従います。 

Exchange ユニファイド メッセージング (UM) を構成してメールボックスとエンタープライズ VoIPするには、次のタスクを実行する必要があります。

- Exchange ユニファイド メッセージング (UM) サービスを実行しているサーバーで証明書を構成する
  > [!NOTE]
  > すべてのクライアント アクセス サーバーとメールボックス サーバーをすべての UM SIP URI ダイヤル プランに追加します。 設定されていない場合、発信通話ルーティングは期待通り動作しません。 
- 必要に応じて、1 つ以上の UM SIP URI ダイヤル プランとサブスクライバー アクセス電話番号を作成し、対応する L ダイヤル プランを作成します。

- 次のexchucutil.ps1スクリプトを使用します。
    - UM IP ゲートウェイを作成します。
    - UM ハント グループを作成します。
    - UM Active Directory ドメイン サービス オブジェクトを読み取るアクセス許可を Skype for Business Server に付与します。
- UM 自動応答オブジェクトを作成します。
- サブスクライバー アクセス オブジェクトを作成します。
- 各ユーザーの SIP URI を作成し、ユーザーを UM SIP URI ダイヤル プランに関連付けします。

### <a name="requirements-and-recommendations"></a>要件と推奨事項

開始する前に、このセクションのドキュメントでは、Exchange の役割であるクライアント アクセスとメールボックスが展開されている必要があります。 このMicrosoft Exchange Server Exchange UM は、これらのサーバー上でサービスとして実行されます。

以下の点にも注意してください。
- Exchange UM が複数のフォレストにインストールされている場合は、各 UM Exchange Serverの統合手順を実行する必要があります。 さらに、Skype for Business Server が展開されているフォレストを信頼するように各 UM フォレストを構成し、Skype for Business Server が展開されているフォレストを各 UM フォレストを信頼するように構成する必要があります。
- 統合手順は、ユニファイド メッセージング サービスが実行されているExchange Serverの役割と、Skype for Business Server を実行しているサーバーの両方で実行されます。 Lync Server 2013 Exchange Serverを実行する前に、ユニファイド メッセージング統合の手順を実行する必要があります。
  > [!NOTE]
  > どのサーバーと管理者の役割で実行される統合手順を確認するには、オンプレミスのユニファイド メッセージングと Skype for Business を統合するための展開プロセスの概要を  [参照してください](../../plan-your-deployment/integrate-with-exchange/deployment-overview.md)。 

Exchange UM を実行する各サーバーで次のツールを使用できる必要があります。
- Exchange 管理シェル
- exchucutil.ps1 スクリプト。このスクリプトは以下のタスクを実行します。
    - 各 Skype for Business Server の UM IP ゲートウェイを作成します。
    - 各ゲートウェイのハント グループを作成します。 各ハント グループのパイロット識別子は、ゲートウェイに関連付けられているフロントエンド プールまたは Standard Edition サーバーによって使用される UM SIP URI ダイヤル プランを指定します。
    - Skype for Business Server に、Active Directory ドメイン サービスの Exchange UM オブジェクトを読み取るアクセス許可を付与します。



### <a name="configure-unified-messaging-on-microsoft-exchange-with-exchucutilps1"></a>ユニファイド メッセージングを使用して Microsoft Exchange でユニファイド メッセージングをExchUCUtil.ps1 

Microsoft Skype for Business Server を Exchange ユニファイド メッセージング (UM) と統合する場合は、シェルで ExchUcUtil.ps1 スクリプトを実行する必要があります。 ExchUcUtil.ps1 スクリプトは次の処理を行います。

- Skype for Business Server プールごとに UM IP ゲートウェイを作成します。

> [!IMPORTANT]
> ExchUcUtil.ps1 スクリプトは、1 つまたは複数の UM IP ゲートウェイを作成します。 スクリプトで作成した 1 つのゲートウェイを除き、すべての UM IP ゲートウェイでの発信呼び出しを無効にする必要があります。 これにはスクリプトを実行する前に作成した UM IP ゲートウェイでの発信呼び出しを無効にすることが含まれます。 

- UM IP ゲートウェイごとに UM ハント グループを作成します。 各ハント グループのパイロット識別子は、UM IP ゲートウェイに関連付けられている Skype for Business Server フロント エンド プールまたは Standard Edition サーバーによって使用される UM SIP URI ダイヤル プランを指定します。
- UM ダイヤル プラン、自動応答、UM IP ゲートウェイ、UM ハント グループなどの Active Directory UM コンテナー オブジェクトを読み取るアクセス許可を Skype for Business Server に付与します。
  > [!IMPORTANT]
  > 各 UM フォレストは、Skype for Business Server が展開されているフォレストを信頼するように構成する必要があります。また、Skype for Business Server 2013 が展開されているフォレストは、各 UM フォレストを信頼するように構成する必要があります。 Exchange UM が複数のフォレストにインストールされている場合は、UM フォレストごとに Exchange Server 統合手順を実行するか、Skype for Business Server ドメインを指定する必要があります。 たとえば、ExchUcUtil.ps1 –Forest:<lync-domain-controller-fqdn>。 

### <a name="use-the-shell-to-run-the-exchucutilps1-script"></a>シェルを使用して ExchUcUtil.ps1 スクリプトを実行する

Skype for Business Server ExchUcUtil.ps1トポロジ内の任意の Exchange サーバーで、このスクリプトを実行します。 シェルを使用してメールボックス サーバーからスクリプトを実行するか、クライアント アクセス サーバーのリモート Windows PowerShell を使用してスクリプトを実行することもできます。 組織のクライアント アクセス サーバーでスクリプトを実行すると、クライアント アクセス サーバーがリモート Windows PowerShell セッションを組織のメールボックス サーバーにプロキシ処理します。
> [!IMPORTANT]
> ExchUcUtil.ps1 スクリプトは、1 つまたは複数の UM IP ゲートウェイを作成します。 スクリプトで作成した 1 つのゲートウェイを除き、すべての UM IP ゲートウェイでの発信呼び出しを無効にする必要があります。 これにはスクリプトを実行する前に作成した UM IP ゲートウェイでの発信呼び出しを無効にすることが含まれます。 UM IP ゲートウェイでの発信呼び出しを無効にするには、「UM IP ゲートウェイで送信呼び出しを無効にする」を参照してください。 
> [!IMPORTANT]
> Exchange 組織管理役割のアクセス許可を保有するか、Exchange 組織管理者セキュリティ グループのメンバーである必要があります。 

1. Exchange 管理シェルを開きます。
2. C:\Windows\System32 プロンプトで **、「cd \<drive letter> :\Program Files\Microsoft\Exchange Server\V15\Scripts>.ExchUcUtil.ps1」** と入力し、Enter キーを押します。

#### <a name="how-do-you-know-this-worked"></a>正常な動作を確認する方法

ExchUcUtul.ps1 スクリプトが正常に完了したことを確認するには、以下を実行します。
- Get-UMIPGateway コマンドレットか EAC を使用し、作成された新しい UM IP ゲートウェイを表示します。
- Get-UMHuntGroup コマンドレットか EAC を使用し、作成された新しい UM ハント グループを表示します。

### <a name="configure-certificates-on-the-server-running-exchange-server-unified-messaging"></a>ユニファイド メッセージングを実行しているサーバーでExchange Serverを構成する
 
「計画」のドキュメントの「Skype for Business Server での Exchange ユニファイド メッセージング統合の計画」の説明に従って Exchange ユニファイド メッセージング (UM) を展開し、組織内の エンタープライズ VoIP ユーザーに Exchange UM 機能を提供する場合は、次の手順を使用して、Exchange UM を実行しているサーバー上で証明書を構成できます。

> [!IMPORTANT]
> 内部証明書の場合、Skype for Business Server を実行しているサーバーと Microsoft Exchange を実行しているサーバーの両方に、相互に信頼できる信頼されたルート証明機関の証明書が必要です。 証明機関 (CA) は、サーバーが信頼できるルート証明機関の証明書ストアに登録されている証明機関のルート証明書を持っている限り、同じ証明機関または別の証明機関のいずれかになります。 

Skype for Business Exchange Server接続するには、サーバー証明書を使用して構成する必要があります。
1. Exchange Server の CA 証明書をダウンロードします。
2. Exchange Server の CA 証明書をインストールします。
3. CA が、Exchange Server の信頼されたルート証明機関一覧にあることを確認します。
4. Exchange Server の証明書要求を作成し、証明書をインストールします。 
5. Exchange Server の証明書を割り当てます。


**CA 証明書をダウンロードするには、**

1. Exchange UM を実行しているサーバーで、[スタート] ボタン、[ファイル名を指定して実行] の順にクリックし、「http:// **\<name of your Issuing CA Server> /certsrv」** と入力して **、[OK]** をクリックします。
2. [タスクの選択] で **、[CA 証明書、証明書チェーン、または CRL のダウンロード] をクリックします**。
3. [CA **証明書、証明書チェーン、または CRL** のダウンロード] で **、Base 64** へのエンコード方法を選択し、[CA 証明書のダウンロード] を **クリックします**。
   > [!NOTE]
   > この手順では、DER (Distinguished Encoding Rules) エンコードを指定することもできます。 DER エンコードを選択する場合は、この手順の次のステップと「**CA 証明書をインストールするには**」のステップ 10 のファイル タイプが .cer ではなく、.p7b になります。 
4. **[ファイルのダウンロード]** ダイアログ ボックスで **[保存]** をクリックし、ファイルをサーバー上のハード ディスクに保存します。(このファイルの拡張子は、前のステップで選択したエンコードに応じて、.cer または .p7b となります。)

**CA 証明書をインストールするには、次の手順を実行します。**

1. Exchange UM を実行しているサーバーで、[スタート] ボタンをクリックし、[ファイル名を指定して実行] をクリックし、[開く] ボックスに **「mmc」** と入力して **、[OK]** をクリックして、Microsoft 管理コンソール (MMC) を開きます。
2. **[ファイル]** メニューの **[スナップインの追加と削除]** をクリックし、**[追加]** をクリックします。
3. **[スタンドアロン スナップインの追加]** ボックスで、**[証明書]** をクリックし、**[追加]** をクリックします。
4. **[証明書スナップイン]** ダイアログ ボックスの **[コンピューター アカウント]** をクリックし、**[次へ]** をクリックします。
5. [コンピューターの **選択** ] ダイアログ ボックスで、ローカル コンピューター **(** このコンソールが実行されているコンピューター) チェック ボックスがオンに設定され、[完了] **をクリックします**。
6. **[閉じる]** をクリックし、**[OK]** をクリックします。 
7. コンソール ツリーで、**[証明書 (ローカル コンピューター)]** を展開し、**[信頼されたルート証明機関]** を展開して **[証明書]** をクリックします。
8. **[証明書]** を右クリックし、**[すべてのタスク]** をクリックして **[インポート]** をクリックします。
9. **[次へ]** をクリックします。 
10. **[参照]** をクリックしてファイルを特定し、**[次へ]** をクリックします。(このファイルの拡張子は、「**CA 証明書をダウンロードするには**」のステップ 3 で選択したエンコードに応じて、.cer または .p7b となります。)
11. [ **すべての証明書を次のストア** に配置する] をクリックします。
12. **[参照]** をクリックし、**[信頼されたルート証明機関]** をクリックします。 
13. **[次へ]** をクリックし、設定を確認して、**[完了]** をクリックします。 


**CA が信頼されたルート CA の一覧に含確認するには、次の手順を実行します。**

1. Exchange UM を実行しているサーバーの MMC で、証明書 (ローカル コンピューター) を展開し、[信頼されたルート証明機関] を展開して、[証明書] をクリックします。
2. 詳細ウィンドウで、CA が、信頼されたルート証明機関の一覧にあることを確認します。


