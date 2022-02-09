---
title: ボイス メールExchange Serverユニファイド メッセージングSkype for Business Server構成する
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/11/2019
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 1be9c4f4-fd8e-4d64-9798-f8737b12e2ab
description: '概要: ボイス メールExchange Serverユニファイド メッセージングSkype for Business Server構成します。'
ms.openlocfilehash: b1e16329a72e17eb32fa9eca686bf0bee7a9c939
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62398277"
---
# <a name="configure-exchange-server-unified-messaging-for-skype-for-business-server-voice-mail"></a>ボイス メールExchange Serverユニファイド メッセージングSkype for Business Server構成する
 
**概要:** ボイス Exchange Serverユニファイド メッセージングSkype for Business Server構成します。
  
Skype for Business Serverでは、Exchange Server 2016 または Exchange Server 2013 にボイスメール メッセージを保存できます。これらのボイスメール メッセージは、ユーザーの受信トレイに電子メール メッセージとして表示されます。 

> [!NOTE]
> Exchange Exchange 2019 ではユニファイド メッセージングは使用できなくなりましたが、電話システム を使用してボイスメール メッセージを録音してから、ユーザーの Exchange メールボックスに記録を残す方法もあります。 詳細については[、「プラン クラウド ボイスメール サービス](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md)」を参照してください。
  
Skype for Business Server と Exchange Server 2016 または Exchange Server 2013 の間でサーバー間認証を既に構成している場合は、ユニファイド メッセージングをセットアップする準備ができました。 これを行うには、最初に新しいユニファイド メッセージング ダイヤル プランを作成して、そのユーザーに割り当てるExchange Server。 たとえば、次の 2 つのコマンド (Exchange 管理シェル内から実行) は、次の 3 桁の新しいダイヤル プランを構成Exchange。
  
```powershell
New-UMDialPlan -Name "RedmondDialPlan" -VoIPSecurity "Secured" -NumberOfDigitsInExtension 3 -URIType "SipName" -CountryOrRegionCode 1
Set-UMDialPlan "RedmondDialPlan" -ConfiguredInCountryOrRegionGroups "Anywhere,*,*,*" -AllowedInCountryOrRegionGroups "Anywhere"
```

この例の最初のコマンドでは、VoIPSecurity パラメーターとパラメーター値 "Secured" は、信号チャネルがトランスポート層セキュリティ (TLS) を使用して暗号化された状態を示しています。 URIType "SipName" は、SIP プロトコルを使用してメッセージが送受信されることを指定し、CountryOrRegionCode の 1 は、ダイヤル プランが US に適用されることを指定します。
  
2 番目のコマンドで、ConfiguredInCountryOrRegionGroups パラメーターに渡されるパラメーター値は、このダイヤル プランで使用できる国内のグループを指定します。 パラメーター値 "Anywhere,,\*"\* は、次\*の値を設定します。
  
- グループ名 ("Anywhere")
    
- AllowedNumberString (\*任意の数値文字列が許可されたことを示すワイルドカード文字)
    
- DialNumberString (\*ダイヤルされた番号が許可されたことを示すワイルドカード文字)
    
- TextComment (\*任意のテキスト コマンドが許可されたことを示すワイルドカード文字)
    
> [!NOTE]
> 新しいダイヤル プランを作成すると、既定のメールボックス ポリシーも作成されます。 
  
新しいダイヤル プランを作成して構成した後、新しいダイヤル プランをユニファイド メッセージング サーバーに追加し、そのサーバーの起動モードを変更する必要があります。特に、スタートアップ モードを "Dual" に設定する必要があります。 次の両方のタスクは、管理シェル内Exchange実行できます。
  
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
  
メールボックスを有効にすると、ユーザー kenmyer@litwareinc.com は Exchange ユニファイド メッセージングを使用できるようになります。 ユーザーが管理シェル内から [Test-CsExUMConnectivity](/powershell/module/skype/test-csexumconnectivity) コマンドレットをExchangeして、ユーザーが UM に接続Skype for Business Server確認できます。
  
```powershell
$credential = Get-Credential "litwareinc\kenmyer"
Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential
```

ユニファイド メッセージングが有効化されている 2 番目のユーザーがいる場合は、[Test-CsExUMVoiceMail](/powershell/module/skype/test-csexumvoicemail) コマンドレットを使用して、この 2 番目のユーザーが最初のユーザーにボイスメール メッセージを残すことができるかを確認できます。
  
```powershell
$credential = Get-Credential "litwareinc\pilar"
Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential
```



## <a name="configuring-unified-messaging-on-microsoft-exchange-server"></a>クライアントでのユニファイド メッセージングのMicrosoft Exchange Server 
> [!IMPORTANT]
> Exchange ユニファイド メッセージング (UM) を使用して エンタープライズ VoIP ユーザーに通話応答、Outlook Voice Access、または自動応答サービスを提供する場合は、「[Skype for Business での Exchange](../../plan-your-deployment/integrate-with-exchange/unified-messaging.md) ユニファイド メッセージング統合の計画」を参照し、このセクションの手順に従います。 

ユニファイド メッセージング (UM) Exchangeを使用して動作エンタープライズ VoIPするには、次のタスクを実行する必要があります。

- ユニファイド メッセージング (UM) サービスをExchangeサーバー上の証明書を構成する
  > [!NOTE]
  > すべてのクライアント アクセス サーバーとメールボックス サーバーをすべての UM SIP URI ダイヤル プランに追加します。 指定しない場合、発信呼び出しのルーティングは期待した通り動作しません。 
- 必要に応じて、1 つ以上の UM SIP URI ダイヤル プランとサブスクライバー アクセスの電話番号を作成し、対応する L ダイヤル プランを作成します。

- 次のexchucutil.ps1スクリプトを使用します。
    - UM IP ゲートウェイを作成します。
    - UM ハント グループを作成します。
    - UM Active Directory Skype for Business Serverオブジェクトを読み取るアクセス許可を付与します。
- UM 自動応答オブジェクトを作成します。
- サブスクライバー アクセス オブジェクトを作成します。
- ユーザーごとに SIP URI を作成し、ユーザーを UM SIP URI ダイヤル プランに関連付けします。

### <a name="requirements-and-recommendations"></a>要件と推奨事項

開始する前に、このセクションのドキュメントでは、クライアント アクセスとメールボックスという役割Exchange展開している必要があります。 このMicrosoft Exchange Server、Exchangeサーバー上のサービスとして UM が実行されます。

以下の点にも注意してください。
- UM Exchangeが複数のフォレストにインストールされている場合は、各 UM フォレストExchange Server統合手順を実行する必要があります。 さらに、Skype for Business Server が展開されているフォレストを信頼するように各 UM フォレストを構成する必要があります。また、Skype for Business Server が展開されているフォレストは、各 UM フォレストを信頼するように構成する必要があります。
- 統合手順は、ユニファイド メッセージング Exchange Serverが実行されている役割と、ユニファイド メッセージング サービスを実行しているサーバーの両方Skype for Business Server。 Lync Server 2013 Exchange Serverを実行する前に、ユニファイド メッセージングの統合手順を実行する必要があります。
  > [!NOTE]
  > どのサーバーに対して実行される統合手順と管理者の役割を確認するには、「オンプレミスのユニファイド メッセージングとサーバーを統合するための展開プロセスの概要」を[参照](../../plan-your-deployment/integrate-with-exchange/deployment-overview.md)Skype for Business。 

次のツールは、UM を実行している各サーバー Exchange必要があります。
- Exchange 管理シェル
- exchucutil.ps1 スクリプト。このスクリプトは以下のタスクを実行します。
    - 各ユーザーの UM IP ゲートウェイをSkype for Business Server。
    - 各ゲートウェイのハント グループを作成します。 各ハント グループのパイロット識別子は、ゲートウェイに関連付けられているフロントエンド プールまたは Standard Edition サーバーで使用される UM SIP URI ダイヤル プランを指定します。
    - Active Directory Skype for Business Serverサービスの UM Exchangeを読み取るアクセス許可を付与します。



### <a name="configure-unified-messaging-on-microsoft-exchange-with-exchucutilps1"></a>Microsoft Exchangeでユニファイド メッセージングを構成ExchUCUtil.ps1 

Microsoft Skype for Business Server とユニファイド メッセージング (UM) Exchange統合する場合は、シェルで ExchUcUtil.ps1スクリプトを実行する必要があります。 ExchUcUtil.ps1 スクリプトは次の処理を行います。

- 各サーバー プールの UM IP ゲートウェイSkype for Business Serverします。

> [!IMPORTANT]
> ExchUcUtil.ps1 スクリプトは、1 つまたは複数の UM IP ゲートウェイを作成します。 スクリプトで作成した 1 つのゲートウェイを除き、すべての UM IP ゲートウェイでの発信呼び出しを無効にする必要があります。 これにはスクリプトを実行する前に作成した UM IP ゲートウェイでの発信呼び出しを無効にすることが含まれます。 

- UM IP ゲートウェイごとに UM ハント グループを作成します。 各ハント グループのパイロット識別子は、UM IP ゲートウェイに関連付けられている Skype for Business Server フロントエンド プールまたは Standard Edition サーバーで使用される UM SIP URI ダイヤル プランを指定します。
- UM Skype for Business Server、自動応答、UM IP ゲートウェイ、UM ハント グループなどの Active Directory UM コンテナー オブジェクトを読み取るアクセス許可を付与します。
  > [!IMPORTANT]
  > Skype for Business Server が展開されているフォレストを信頼するように各 UM フォレストを構成し、Skype for Business Server 2013 が展開されているフォレストは、各 UM フォレストを信頼するように構成する必要があります。 UM Exchangeが複数のフォレストにインストールされている場合は、Exchange Server 統合手順を各 UM フォレストに対して実行する必要があります。または、Skype for Business Server ドメインを指定する必要があります。 たとえば、–Forest:ExchUcUtil.ps1を使用します\<lync-domain-controller-fqdn>。 

### <a name="use-the-shell-to-run-the-exchucutilps1-script"></a>シェルを使用して ExchUcUtil.ps1 スクリプトを実行する

組織のExchUcUtil.ps1サーバーで、Exchangeと同じトポロジにあるサーバーで、Skype for Business Server。 シェルを使用してメールボックス サーバーからスクリプトを実行するか、クライアント アクセス サーバーのリモート Windows PowerShell を使用してスクリプトを実行することもできます。 組織のクライアント アクセス サーバーでスクリプトを実行すると、クライアント アクセス サーバーがリモート Windows PowerShell セッションを組織のメールボックス サーバーにプロキシ処理します。
> [!IMPORTANT]
> ExchUcUtil.ps1 スクリプトは、1 つまたは複数の UM IP ゲートウェイを作成します。スクリプトで作成した 1 つのゲートウェイを除き、すべての UM IP ゲートウェイでの発信呼び出しを無効にする必要があります。これにはスクリプトを実行する前に作成した UM IP ゲートウェイでの発信呼び出しを無効にすることが含まれます。UM IP ゲートウェイでの発信呼び出しを無効にするには、「UM IP ゲートウェイで送信呼び出しを無効にする」を参照してください。[!IMPORTANT]
> Exchange 組織管理役割のアクセス許可を保有するか、Exchange 組織管理者セキュリティ グループのメンバーである必要があります。 

1. Exchange 管理シェルを開きます。
2. C:\Windows\System32 プロンプトで、「**cd\<drive letter>:\Program Files\Microsoft\Exchange Server\V15\Scripts>.ExchUcUtil.ps1**」と入力し、Enter キーを押します。

#### <a name="how-do-you-know-this-worked"></a>正常な動作を確認する方法

ExchUcUtul.ps1 スクリプトが正常に完了したことを確認するには、以下を実行します。
- Get-UMIPGateway コマンドレットか EAC を使用し、作成された新しい UM IP ゲートウェイを表示します。
- Get-UMHuntGroup コマンドレットか EAC を使用し、作成された新しい UM ハント グループを表示します。

### <a name="configure-certificates-on-the-server-running-exchange-server-unified-messaging"></a>ユニファイド メッセージングを実行しているサーバー Exchange Server構成する
 
Exchange ユニファイド メッセージング (UM) を展開している場合は、「計画」の「Skype for Business Server での Exchange ユニファイド メッセージング統合の計画」の説明に従って、Exchange UM 機能をエンタープライズ VoIP 組織内のユーザーは、次の手順を使用して、UM を実行しているサーバーで証明書Exchangeできます。

> [!IMPORTANT]
> 内部証明書の場合、Skype for Business Server を実行しているサーバーと Microsoft Exchange を実行しているサーバーの両方に、相互に信頼される信頼されたルート機関証明書が必要です。 証明機関 (CA) は、サーバーが信頼できるルート証明機関の証明書ストアに登録されている証明機関のルート証明書を持っている限り、同じ証明機関または別の証明機関を指定できます。 

サーバー Exchange Server接続するには、サーバー証明書で構成する必要Skype for Business Server。
1. Exchange Server の CA 証明書をダウンロードします。
2. Exchange Server の CA 証明書をインストールします。
3. CA が、Exchange Server の信頼されたルート証明機関一覧にあることを確認します。
4. Exchange Server の証明書要求を作成し、証明書をインストールします。 
5. Exchange Server の証明書を割り当てます。


**CA 証明書をダウンロードするには、次の方法を実行します。**

1. UM を実行しているサーバー Exchange[スタート] をクリックし、[**実行****\<name of your Issuing CA Server>**] をクリックし、「http:///certsrv」と入力し、[OK] をクリックします。
2. [タスクの選択] で、[ **CA 証明書、証明書チェーン、または CRL のダウンロード] をクリックします**。
3. [ **CA 証明書、証明書チェーン、または CRL** をダウンロードする] で、[エンコード方法] を [ **基本 64**] に選択し、[CA 証明書のダウンロード] **をクリックします**。
   > [!NOTE]
   > この手順では、Distinguished Encoding Rules (DER) エンコードを指定できます。 DER エンコードを選択する場合は、この手順の次のステップと「**CA 証明書をインストールするには**」のステップ 10 のファイル タイプが .cer ではなく、.p7b になります。 
4. **[ファイルのダウンロード]** ダイアログ ボックスで **[保存]** をクリックし、ファイルをサーバー上のハード ディスクに保存します。(このファイルの拡張子は、前のステップで選択したエンコードに応じて、.cer または .p7b となります。)

**CA 証明書をインストールするには、次の手順を実行します。**

1. EXCHANGE UM を実行しているサーバーで、[スタート] をクリックして [実行] をクリックし、[開く] ボックスに **mmc** と入力し、[OK] をクリックして、Microsoft 管理コンソール (MMC) を開 **きます**。
2. **[ファイル]** メニューの **[スナップインの追加と削除]** をクリックし、**[追加]** をクリックします。
3. **[スタンドアロン スナップインの追加]** ボックスで、**[証明書]** をクリックし、**[追加]** をクリックします。
4. **[証明書スナップイン]** ダイアログ ボックスの **[コンピューター アカウント]** をクリックし、**[次へ]** をクリックします。
5. [コンピューター **の選択]** ダイアログ ボックスで、[ローカル コンピューター( このコンソールが実行されているコンピューター **)]** チェック ボックスがオンに設定され、[完了] **をクリックします**。
6. **[閉じる]** をクリックし、**[OK]** をクリックします。 
7. コンソール ツリーで、**[証明書 (ローカル コンピューター)]** を展開し、**[信頼されたルート証明機関]** を展開して **[証明書]** をクリックします。
8. **[証明書]** を右クリックし、**[すべてのタスク]** をクリックして **[インポート]** をクリックします。
9. **[次へ]** をクリックします。 
10. **[参照]** をクリックしてファイルを特定し、**[次へ]** をクリックします。(このファイルの拡張子は、「**CA 証明書をダウンロードするには**」のステップ 3 で選択したエンコードに応じて、.cer または .p7b となります。)
11. [すべての **証明書を次のストアに** 配置する] をクリックします。
12. **[参照]** をクリックし、**[信頼されたルート証明機関]** をクリックします。 
13. **[次へ]** をクリックし、設定を確認して、**[完了]** をクリックします。 


**CA が信頼できるルート CA の一覧に含にあることを確認するには、次の手順を実行します。**

1. UM を実行しているサーバー Exchange MMC で [証明書 (ローカル コンピューター]) を展開し、[信頼されたルート証明機関] を展開し、[証明書] をクリックします。
2. 詳細ウィンドウで、CA が、信頼されたルート証明機関の一覧にあることを確認します。