---
title: Skype Exchange Serverユニファイド メッセージングの構成
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
description: '概要: Skype Exchange Serverユニファイド メッセージングを構成する方法について説明します。'
ms.openlocfilehash: 24bad46103433f6af9caebbe1894b1b3b2aa83d9
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109823"
---
# <a name="configure-exchange-server-unified-messaging-for-skype-for-business-server-voice-mail"></a>Skype Exchange Serverユニファイド メッセージングの構成
 
**概要:** Skype Exchange Serverユニファイド メッセージングを構成します。
  
Skype for Business Server を使用すると、ボイスメール メッセージを 2016 年または 2013 年Exchange ServerにExchange Serverできます。これらのボイスメール メッセージは、ユーザーの受信トレイに電子メール メッセージとして表示されます。 

> [!NOTE]
> 以前に知られている Exchange ユニファイド メッセージングは、Exchange 2019 では使用できなくなりましたが、電話システムを使用してボイスメール メッセージを録音してから、ユーザーの Exchange メールボックスに記録を残す方法を使用できます。 詳細については [、「Plan Cloud ボイスメール サービス](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) 」を参照してください。
  
Skype for Business Server と Exchange Server 2016 または Exchange Server 2013 の間でサーバー間認証を既に構成している場合は、ユニファイド メッセージングをセットアップする準備ができました。 これを行うには、最初に新しいユニファイド メッセージング ダイヤル プランを作成して、そのユーザーに割り当てるExchange Server。 たとえば、次の 2 つのコマンド (Exchange 管理シェル内から実行) は、Exchange の新しい 3 桁のダイヤル プランを構成します。
  
```powershell
New-UMDialPlan -Name "RedmondDialPlan" -VoIPSecurity "Secured" -NumberOfDigitsInExtension 3 -URIType "SipName" -CountryOrRegionCode 1
Set-UMDialPlan "RedmondDialPlan" -ConfiguredInCountryOrRegionGroups "Anywhere,*,*,*" -AllowedInCountryOrRegionGroups "Anywhere"
```

この例の最初のコマンドでは、VoIPSecurity パラメーターとパラメーター値 "Secured" は、信号チャネルがトランスポート層セキュリティ (TLS) を使用して暗号化された状態を示しています。 URIType "SipName" は、SIP プロトコルを使用してメッセージが送受信されることを指定し、CountryOrRegionCode の 1 は、ダイヤル プランが US に適用されることを指定します。
  
2 番目のコマンドで、ConfiguredInCountryOrRegionGroups パラメーターに渡されるパラメーター値は、このダイヤル プランで使用できる国内のグループを指定します。 パラメーター値 "Anywhere, \* \* , , " \* は、次の値を設定します。
  
- グループ名 ("Anywhere")
    
- AllowedNumberString ( , 任意の数値文字列が許可されたことを示 \* すワイルドカード文字)
    
- DialNumberString ( 、 任意のダイヤルされた番号が許可 \* されたことを示すワイルドカード文字)
    
- TextComment ( 、 任意のテキスト コマンドが許可 \* されたことを示すワイルドカード文字)
    
> [!NOTE]
> 新しいダイヤル プランを作成すると、既定のメールボックス ポリシーも作成されます。 
  
新しいダイヤル プランを作成して構成した後、新しいダイヤル プランをユニファイド メッセージング サーバーに追加し、そのサーバーの起動モードを変更する必要があります。特に、スタートアップ モードを "Dual" に設定する必要があります。 これらの両方のタスクは、Exchange 管理シェル内から実行できます。
  
```powershell
Set-UmService -Identity "atl-exchangeum-001.litwareinc.com" -DialPlans "RedmondDialPlan" -UMStartupMode "Dual"
```

ユニファイド メッセージング サーバーが構成された後、次に Enable-ExchangeCertificate コマンドレットを実行して、Exchange 証明書がユニファイド メッセージング サービスに適用されていることを確認します。
  
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
  
メールボックスを有効にすると、ユーザー kenmyer@litwareinc.com は Exchange ユニファイド メッセージングを使用できるようになります。 Skype for Business Server 管理シェル内から [Test-CsExUMConnectivity](/powershell/module/skype/test-csexumconnectivity?view=skype-ps) コマンドレットを実行して、ユーザーが Exchange UM に接続できる状態を確認できます。
  
```powershell
$credential = Get-Credential "litwareinc\kenmyer"
Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential
```

ユニファイド メッセージングが有効化されている 2 番目のユーザーがいる場合は、[Test-CsExUMVoiceMail](/powershell/module/skype/test-csexumvoicemail?view=skype-ps) コマンドレットを使用して、この 2 番目のユーザーが最初のユーザーにボイスメール メッセージを残すことができるかを確認できます。
  
```powershell
$credential = Get-Credential "litwareinc\pilar"
Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential
```



## <a name="configuring-unified-messaging-on-microsoft-exchange-server"></a>クライアントでのユニファイド メッセージングのMicrosoft Exchange Server 
> [!IMPORTANT]
> Exchange ユニファイド メッセージング (UM) を使用して エンタープライズ VoIP ユーザーに通話応答、Outlook Voice Access、または自動応答サービスを提供する場合は [、「Plan for Exchange Unified Messaging integration in Skype for Business」](../../plan-your-deployment/integrate-with-exchange/unified-messaging.md)を参照し、このセクションの指示に従います。 

Exchange ユニファイド メッセージング (UM) を構成して、エンタープライズ VoIPを実行するには、次のタスクを実行する必要があります。

- Exchange ユニファイド メッセージング (UM) サービスを実行しているサーバーで証明書を構成する
  > [!NOTE]
  > すべてのクライアント アクセス サーバーとメールボックス サーバーをすべての UM SIP URI ダイヤル プランに追加します。 指定しない場合、発信呼び出しのルーティングは期待した通り動作しません。 
- 必要に応じて、1 つ以上の UM SIP URI ダイヤル プランとサブスクライバー アクセスの電話番号を作成し、対応する L ダイヤル プランを作成します。

- 次のexchucutil.ps1スクリプトを使用します。
    - UM IP ゲートウェイを作成します。
    - UM ハント グループを作成します。
    - SKYPE for Business Server に UM Active Directory ドメイン サービス オブジェクトを読み取るアクセス許可を付与します。
- UM 自動応答オブジェクトを作成します。
- サブスクライバー アクセス オブジェクトを作成します。
- ユーザーごとに SIP URI を作成し、ユーザーを UM SIP URI ダイヤル プランに関連付けします。

### <a name="requirements-and-recommendations"></a>要件と推奨事項

開始する前に、このセクションのドキュメントでは、Exchange の役割であるクライアント アクセスとメールボックスが展開されている必要があります。 このMicrosoft Exchange Server Exchange UM は、これらのサーバー上でサービスとして実行されます。

以下の点にも注意してください。
- Exchange UM が複数のフォレストにインストールされている場合、各 UM フォレストExchange Server統合手順を実行する必要があります。 さらに、Skype for Business Server が展開されているフォレストを信頼するように各 UM フォレストを構成し、Skype for Business Server が展開されているフォレストは、各 UM フォレストを信頼するように構成する必要があります。
- 統合手順は、ユニファイド メッセージング Exchange Serverが実行されているサーバーと、Skype for Business Server を実行しているサーバーの両方で実行されます。 Lync Server 2013 Exchange Serverを実行する前に、ユニファイド メッセージングの統合手順を実行する必要があります。
  > [!NOTE]
  > どのサーバーに対して実行される統合手順と管理者の役割を確認するには、「オンプレミスユニファイド メッセージングと Skype for Business を統合するための展開プロセスの概要」  [を参照してください](../../plan-your-deployment/integrate-with-exchange/deployment-overview.md)。 

Exchange UM を実行している各サーバーで次のツールを使用できる必要があります。
- Exchange 管理シェル
- exchucutil.ps1 スクリプト。このスクリプトは以下のタスクを実行します。
    - Skype for Business Server ごとに UM IP ゲートウェイを作成します。
    - 各ゲートウェイのハント グループを作成します。 各ハント グループのパイロット識別子は、ゲートウェイに関連付けられているフロントエンド プールまたは Standard Edition サーバーで使用される UM SIP URI ダイヤル プランを指定します。
    - Active Directory ドメイン サービスで Exchange UM オブジェクトを読み取るアクセス許可を Skype for Business Server に付与します。



### <a name="configure-unified-messaging-on-microsoft-exchange-with-exchucutilps1"></a>Microsoft Exchange でユニファイド メッセージングを構成するには、ExchUCUtil.ps1 

Microsoft Skype for Business Server と Exchange ユニファイド メッセージング (UM) を統合する場合は、シェルで ExchUcUtil.ps1スクリプトを実行する必要があります。 ExchUcUtil.ps1 スクリプトは次の処理を行います。

- Skype for Business Server プールごとに UM IP ゲートウェイを作成します。

> [!IMPORTANT]
> ExchUcUtil.ps1 スクリプトは、1 つまたは複数の UM IP ゲートウェイを作成します。 スクリプトで作成した 1 つのゲートウェイを除き、すべての UM IP ゲートウェイでの発信呼び出しを無効にする必要があります。 これにはスクリプトを実行する前に作成した UM IP ゲートウェイでの発信呼び出しを無効にすることが含まれます。 

- UM IP ゲートウェイごとに UM ハント グループを作成します。 各ハント グループのパイロット識別子は、UM IP ゲートウェイに関連付けられている Skype for Business Server フロント エンド プールまたは Standard Edition サーバーで使用される UM SIP URI ダイヤル プランを指定します。
- Skype for Business Server に、UM ダイヤル プラン、自動応答、UM IP ゲートウェイ、UM ハント グループなどの Active Directory UM コンテナー オブジェクトを読み取るアクセス許可を付与します。
  > [!IMPORTANT]
  > 各 UM フォレストは、Skype for Business Server が展開されているフォレストを信頼するように構成する必要があります。また、Skype for Business Server 2013 が展開されているフォレストは、各 UM フォレストを信頼するように構成する必要があります。 Exchange UM が複数のフォレストにインストールされている場合、Exchange Server統合手順を UM フォレストごとに実行するか、Skype for Business Server ドメインを指定する必要があります。 たとえば、ExchUcUtil.ps1 –Forest:<lync-domain-controller-fqdn>。 

### <a name="use-the-shell-to-run-the-exchucutilps1-script"></a>シェルを使用して ExchUcUtil.ps1 スクリプトを実行する

Skype for Business Server ExchUcUtil.ps1トポロジ内にある組織内の Exchange サーバーで、このスクリプトを実行します。 シェルを使用してメールボックス サーバーからスクリプトを実行するか、クライアント アクセス サーバーのリモート Windows PowerShell を使用してスクリプトを実行することもできます。 組織のクライアント アクセス サーバーでスクリプトを実行すると、クライアント アクセス サーバーがリモート Windows PowerShell セッションを組織のメールボックス サーバーにプロキシ処理します。
> [!IMPORTANT]
> ExchUcUtil.ps1 スクリプトは、1 つまたは複数の UM IP ゲートウェイを作成します。 スクリプトで作成した 1 つのゲートウェイを除き、すべての UM IP ゲートウェイでの発信呼び出しを無効にする必要があります。 これにはスクリプトを実行する前に作成した UM IP ゲートウェイでの発信呼び出しを無効にすることが含まれます。 UM IP ゲートウェイでの発信呼び出しを無効にするには、「UM IP ゲートウェイで送信呼び出しを無効にする」を参照してください。 
> [!IMPORTANT]
> Exchange 組織管理役割のアクセス許可を保有するか、Exchange 組織管理者セキュリティ グループのメンバーである必要があります。 

1. Exchange 管理シェルを開きます。
2. C:\Windows\System32 プロンプトで **\<drive letter> 、「cd:\Program Files\Microsoft\Exchange Server\V15\Scripts>.ExchUcUtil.ps1」** と入力し、Enter キーを押します。

#### <a name="how-do-you-know-this-worked"></a>正常な動作を確認する方法

ExchUcUtul.ps1 スクリプトが正常に完了したことを確認するには、以下を実行します。
- Get-UMIPGateway コマンドレットか EAC を使用し、作成された新しい UM IP ゲートウェイを表示します。
- Get-UMHuntGroup コマンドレットか EAC を使用し、作成された新しい UM ハント グループを表示します。

### <a name="configure-certificates-on-the-server-running-exchange-server-unified-messaging"></a>ユニファイド メッセージングを実行しているサーバー Exchange Server構成する
 
「計画」のドキュメントの「Skype for Business Server での Exchange ユニファイド メッセージング統合の計画」で説明したように、Exchange ユニファイド メッセージング (UM) を展開し、組織内の エンタープライズ VoIP ユーザーに Exchange UM 機能を提供する場合は、次の手順を使用して、Exchange UM を実行しているサーバー上で証明書を構成できます。

> [!IMPORTANT]
> 内部証明書の場合、Skype for Business Server を実行しているサーバーと Microsoft Exchange を実行しているサーバーの両方に、相互に信頼される信頼できるルート機関証明書が必要です。 証明機関 (CA) は、サーバーが信頼できるルート証明機関の証明書ストアに登録されている証明機関のルート証明書を持っている限り、同じ証明機関または別の証明機関を指定できます。 

Skype Exchange Serverに接続するには、サーバー証明書を使用して構成する必要があります。
1. Exchange Server の CA 証明書をダウンロードします。
2. Exchange Server の CA 証明書をインストールします。
3. CA が、Exchange Server の信頼されたルート証明機関一覧にあることを確認します。
4. Exchange Server の証明書要求を作成し、証明書をインストールします。 
5. Exchange Server の証明書を割り当てます。


**CA 証明書をダウンロードするには、次の方法を実行します。**

1. Exchange UM を実行しているサーバーで、[スタート] をクリックし、[**実行**] をクリックし、「http:// **\<name of your Issuing CA Server> /certsrv」** と入力し **、[OK] をクリックします**。
2. [タスクの選択] で **、[CA 証明書、証明書チェーン、または CRL のダウンロード] をクリックします**。
3. [CA **証明書、証明書チェーン、または CRL** のダウンロード] で、[ベース **64** へのエンコード方法] を選択し、[CA 証明書のダウンロード]**をクリックします**。
   > [!NOTE]
   > この手順では、識別エンコード ルール (DER) エンコードを指定することもできます。 DER エンコードを選択する場合は、この手順の次のステップと「**CA 証明書をインストールするには**」のステップ 10 のファイル タイプが .cer ではなく、.p7b になります。 
4. **[ファイルのダウンロード]** ダイアログ ボックスで **[保存]** をクリックし、ファイルをサーバー上のハード ディスクに保存します。(このファイルの拡張子は、前のステップで選択したエンコードに応じて、.cer または .p7b となります。)

**CA 証明書をインストールするには、次の手順を実行します。**

1. Exchange UM を実行しているサーバーで、[スタート] をクリックして [実行] をクリックし、[開く] ボックスに **mmc** と入力し **、[OK]** をクリックして、Microsoft 管理コンソール (MMC) を開きます。
2. **[ファイル]** メニューの **[スナップインの追加と削除]** をクリックし、**[追加]** をクリックします。
3. **[スタンドアロン スナップインの追加]** ボックスで、**[証明書]** をクリックし、**[追加]** をクリックします。
4. **[証明書スナップイン]** ダイアログ ボックスの **[コンピューター アカウント]** をクリックし、**[次へ]** をクリックします。
5. [コンピューター **の選択]** ダイアログ ボックスで、[ローカル コンピューター( このコンソールが実行されているコンピューター **) ]** チェック ボックスがオンに設定され、[完了] をクリックします。 
6. **[閉じる]** をクリックし、**[OK]** をクリックします。 
7. コンソール ツリーで、**[証明書 (ローカル コンピューター)]** を展開し、**[信頼されたルート証明機関]** を展開して **[証明書]** をクリックします。
8. **[証明書]** を右クリックし、**[すべてのタスク]** をクリックして **[インポート]** をクリックします。
9. **[次へ]** をクリックします。 
10. **[参照]** をクリックしてファイルを特定し、**[次へ]** をクリックします。(このファイルの拡張子は、「**CA 証明書をダウンロードするには**」のステップ 3 で選択したエンコードに応じて、.cer または .p7b となります。)
11. [すべての **証明書を次のストアに** 配置する] をクリックします。
12. **[参照]** をクリックし、**[信頼されたルート証明機関]** をクリックします。 
13. **[次へ]** をクリックし、設定を確認して、**[完了]** をクリックします。 


**CA が信頼できるルート CA の一覧に含にあることを確認するには、次の手順を実行します。**

1. Exchange UM を実行しているサーバーで、MMC で [証明書 (ローカル コンピューター]) を展開し、[信頼されたルート証明機関] を展開し、[証明書] をクリックします。
2. 詳細ウィンドウで、CA が、信頼されたルート証明機関の一覧にあることを確認します。