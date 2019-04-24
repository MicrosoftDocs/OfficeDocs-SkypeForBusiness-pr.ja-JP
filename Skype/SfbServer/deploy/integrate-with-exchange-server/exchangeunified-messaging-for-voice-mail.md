---
title: Skype for Business Server ボイス メールに対する Exchange Server ユニファイド メッセージングの構成
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/11/2019
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1be9c4f4-fd8e-4d64-9798-f8737b12e2ab
description: '概要: Exchange Server ユニファイド メッセージングの構成 Skype ビジネス サーバーのボイス メールをします。'
ms.openlocfilehash: 60f9398b7a35ad211ede22ee0e0e7f9689bbc8d7
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32216866"
---
# <a name="configure-exchange-server-unified-messaging-for-skype-for-business-server-voice-mail"></a>Skype for Business Server ボイス メールに対する Exchange Server ユニファイド メッセージングの構成
 
**の概要:** Exchange Server ユニファイド メッセージングの構成 Skype ビジネス サーバーのボイス メールにします。
  
ビジネス サーバー用の Skype を使用すると、ボイスメールのメッセージを Exchange Server 2016 または Exchange Server 2013 に格納されています。ボイスメール メッセージは、ユーザーの受信トレイの電子メール メッセージとして表示されます。 

> [!NOTE]
> として以前に Exchange ユニファイド メッセージングは、不要になった使用可能な Exchange 2019 が、電話システムを使用してレコードのボイス メール メッセージと、ユーザーの Exchange メールボックスに記録を残すことができます。 詳細については、[クラウドのボイスメールの計画サービス](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md)を参照してください。
  
ビジネス サーバーと Exchange Server 2016 または Exchange Server 2013 の Skype 間でサーバーからサーバーへの認証を既に構成した場合は、ユニファイド メッセージングを設定する準備がします。 これを行うには、最初に作成し、新しいユニファイド メッセージング ダイヤル プランを Exchange Server に割り当てる必要があります。 などのこれら 2 つのコマンド (Exchange 管理シェル内から実行) は、Exchange の新しい 3 桁のダイヤル プランを構成します。
  
```
New-UMDialPlan -Name "RedmondDialPlan" -VoIPSecurity "Secured" -NumberOfDigitsInExtension 3 -URIType "SipName" -CountryOrRegionCode 1
Set-UMDialPlan "RedmondDialPlan" -ConfiguredInCountryOrRegionGroups "Anywhere,*,*,*" -AllowedInCountryOrRegionGroups "Anywhere"
```

最初では、例、VoIPSecurity パラメーター、およびパラメーター値の [セキュリティで保護された"のコマンドは、トランスポート層セキュリティ (TLS) を使用して信号チャネルが暗号化されているを示しています。 URIType "SipName" は、SIP プロトコルを使用してメッセージが送受信されることを指定し、CountryOrRegionCode の 1 は、ダイヤル プランが米国に適用されることを指定します。
  
2 番目のコマンドで、ConfiguredInCountryOrRegionGroups パラメーターに渡されるパラメーター値は、このダイヤル プランで使用できる国内のグループを指定します。 パラメーターの値"任意の場所、\*、\*、\*"次の設定。
  
- グループ名 ("Anywhere")
    
- AllowedNumberString (\*、任意の数値の文字列を許可することを示すワイルドカード文字)
    
- DialNumberString (\*、すべてのダイヤルの番号を許可することを示すワイルドカード文字)
    
- TextComment (\*、任意のテキスト コマンドを許可することを示すワイルドカード文字)
    
> [!NOTE]
> 新しいダイヤル プランを作成すると、既定のメールボックス ポリシーも作成されます。 
  
作成し、新しいダイヤル プランを構成した後、新しいダイヤル プランにユニファイド メッセージング サーバーとそのサーバーのスタートアップ モードを変更しを追加する必要があります。具体的には、「デュアル」のスタートアップ モードを設定する必要があります。 Exchange 管理シェル内からこれらのタスクの両方を行うことができます。
  
```
Set-UmService -Identity "atl-exchangeum-001.litwareinc.com" -DialPlans "RedmondDialPlan" -UMStartupMode "Dual"
```

ユニファイド メッセージング サーバーの構成が完了したら次に Exchange 証明書がユニファイド メッセージング サービスに適用されることを確認するのには有効にする ExchangeCertificate コマンドレットを実行する必要があります。
  
```
Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "EA5A332496CC05DA69B75B66111C0F78A110D22d" -Services "SMTP","IIS","UM"
```

証明書の割り当てが適切に行われた後、ユニファイド メッセージング サーバー上の MsExchangeUM サービスを停止して、再起動する必要があります。このサービスは、スタートアップ モードを変更した場合はいつでも、停止して再起動する必要があります。
  
ユニファイド メッセージング サーバーの構成が終了すると、UM Call Router を構成できます。
  
```
Set-UMCallRouterSettings -Server "atl-exchange-001.litwareinc.com" -UMStartupMode "Dual" -DialPlans "RedmondDialPlan" 
Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "45BAA32496CC891169B75B9811320F78A1075DDA" -Services "IIS","UMCallRouter"
```

スタートアップ モードが変更されているため、UM Call Router をホストしているコンピューター上で MsExchangeUMCR サービスを停止および再起動する必要があります。
  
ユニファイド メッセージングのセットアップを完了するには、UM メールボックス ポリシーを作成し、そのポリシーを使用して、ユーザーのユニファイド メッセージングを有効にする必要があります。次のようなコマンドを使用して、メールボックス ポリシーを作成できます。
  
```
New-UMMailboxPolicy -Name "RedmondMailboxPolicy" -AllowedInCountryOrRegionGroups "Anywhere"
```

また、次のようなコマンドを使用して、ユーザーのユニファイド メッセージングを有効にできます。
  
```
Enable-UMMailbox -Extensions 100 -SIPResourceIdentifier "kenmyer@litwareinc.com" -Identity "litwareinc\kenmyer" -UMMailboxPolicy "RedmondMailboxPolicy"
```

上のコマンドで、Extensions パラメーターはユーザーの内線番号を表します。この例の場合、ユーザーの内線番号は 100 です。
  
メールボックスを有効にすると、ユーザー kenmyer@litwareinc.com は Exchange ユニファイド メッセージングを使用できるようになります。 コマンドレットを実行して、[テスト CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/test-csexumconnectivity?view=skype-ps)から、Skype のビジネス サーバー管理シェルのユーザーを Exchange UM に接続できることを確認することができます。
  
```
$credential = Get-Credential "litwareinc\kenmyer"
Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential
```

ユニファイド メッセージングが有効化されている 2 番目のユーザーがいる場合は、[Test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/test-csexumvoicemail?view=skype-ps) コマンドレットを使用して、この 2 番目のユーザーが最初のユーザーにボイスメール メッセージを残せることを確認できます。
  
```
$credential = Get-Credential "litwareinc\pilar"
Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential
```



## <a name="configuring-unified-messaging-on-microsoft-exchange-server"></a>Microsoft Exchange Server 上のユニファイド メッセージングを構成します。 
> [!IMPORTANT]
> 呼び出しへの応答、Outlook Voice Access、またはエンタープライズ VoIP ユーザー向けの自動応答サービスを提供する Exchange ユニファイド メッセージング (UM) を使用する場合は、[ビジネスの Skype での Exchange ユニファイド メッセージング統合の計画](../../plan-your-deployment/integrate-with-exchange/unified-messaging.md)を、読み書きし、このセクションの手順です。 

Exchange ユニファイド メッセージング (UM) エンタープライズ VoIP を使用するを構成するには、次のタスクを実行する必要があります。

- Exchange ユニファイド メッセージング (UM) サービスを実行するサーバーに証明書を構成します。
  > [!NOTE]
  > UM SIP URI ダイヤル プランのすべてに、すべてのクライアント アクセス、メールボックス サーバーを追加します。 、発信通話ルーティングされませんが機能しない場合とが必要です。 
- 、必要に応じて 1 つまたは複数 UM SIP URI ダイヤル プラン、およびサブスクライバー アクセスの電話番号を作成し、対応する L のダイヤル プランを作成します。

- Exchucutil.ps1 スクリプトを使用します。
    - UM IP ゲートウェイを作成します。
    - UM ハント グループを作成します。
    - UM の Active Directory ドメイン サービス オブジェクトを読み取るアクセス許可をビジネスのサーバー用の Skype を付与します。
- UM 自動アテンダント オブジェクトを作成します。
- サブスクライバー アクセス オブジェクトを作成します。
- UM SIP URI ダイヤル プランには、各ユーザーと関連付けられたユーザーの SIP URI を作成します。

### <a name="requirements-and-recommendations"></a>要件と推奨事項

このセクションのドキュメントは、次の Exchange の役割を展開している作業を開始する前に: クライアント アクセス、およびメールボックスです。 Microsoft Exchange Server、Exchange UM サービスとして実行これらのサーバーにします。

また、次の点を注意してください。
- Exchange UM がインストールされている場合複数のフォレストで、各 UM のフォレストの Exchange Server の統合の手順を実行しなければなりません。 さらに、各 UM フォレストは、Skype のビジネス サーバーを展開すると、し、フォレストでは、whichSkype ビジネス サーバーの展開を構成する必要が各 UM のフォレストを信頼するフォレストを信頼するように構成しなければなりません。
- 統合の手順は、ユニファイド メッセージング サービスが実行されている、両方の Exchange Server の役割および Skype ビジネス サーバーを実行しているサーバー上で実行されます。 Lync Server 2013 の統合の手順を実行する前に Exchange Server ユニファイド メッセージング統合の手順を実行する必要があります。
  > [!NOTE]
  > 統合手順が、管理者ロールで、どのサーバーで実行されるを参照してください[と統合するための展開プロセスの概要、設置型ユニファイド メッセージングおよびビジネス用の Skype](../../plan-your-deployment/integrate-with-exchange/deployment-overview.md)を参照してください。 

次のツールは、Exchange UM を実行している各サーバーで使用できる必要があります。
- Exchange 管理シェル
- スクリプト exchucutil.ps1、次のタスクを実行します。
    - 各 Skype のビジネス サーバー、UM IP ゲートウェイを作成します。
    - 各ゲートウェイのハント グループを作成します。 各ハント グループのパイロット id は、フロント エンド プールまたは Standard Edition サーバー、ゲートウェイに関連付けられているで使用される UM SIP URI ダイヤル プランを指定します。
    - Skype ビジネス サーバー Exchange UM Active Directory ドメイン サービス内のオブジェクトを読み取るアクセス許可を与えられます。



### <a name="configure-unified-messaging-on-microsoft-exchange-with-exchucutilps1"></a>Configure Unified Messaging on Microsoft Exchange with ExchUCUtil.ps1 

ビジネス サーバー Exchange ユニファイド メッセージング (UM) での Microsoft Skype を統合していると、は、シェルでは、ExchUcUtil.ps1 スクリプトを実行する必要が。 ExchUcUtil.ps1 スクリプトは、次のこと。

- ビジネス サーバー プールの各 Skype の UM IP ゲートウェイを作成します。

> [!IMPORTANT]
> ExchUcUtil.ps1 スクリプトでは、1 つまたは複数の UM IP ゲートウェイを作成します。 スクリプトを作成する 1 つのゲートウェイを除くすべての UM IP ゲートウェイで発信呼び出しを無効にする必要があります。 これには、スクリプトを実行する前に作成された UM IP ゲートウェイに送信呼び出しを無効にすることが含まれます。 

- 各 UM IP ゲートウェイの UM ハント グループを作成します。 各ハント グループのパイロット id は、ビジネス サーバーのフロント エンド プールまたは Standard Edition サーバー、UM IP ゲートウェイに関連付けられているため、Skype で使用する UM SIP URI ダイヤル プランを指定します。
- UM などコンテナー オブジェクトを Active Directory の UM のダイヤル プラン、自動応答、UM IP ゲートウェイ、UM ハント グループを読むビジネス サーバーのアクセス許可の付与 Skype。
  > [!IMPORTANT]
  > Skype のビジネス サーバーが配置され、各 UM のフォレストを信頼するようにビジネス Server 2013 の Skype を配置するフォレストを構成する必要があります、フォレストを信頼するには、各 UM のフォレストを構成しなければなりません。 Exchange UM がインストールされている場合複数のフォレストで、各 UM のフォレストの Exchange Server の統合の手順を行う必要があります。 またはビジネス サーバー ドメインの Skype を指定する必要があります。 たとえば、ExchUcUtil.ps1 – フォレスト: <lync-ドメイン ・ コント ローラー-fqdn>。 

### <a name="use-the-shell-to-run-the-exchucutilps1-script"></a>ExchUcUtil.ps1 スクリプトを実行するのにシェルを使用します。

Skype ビジネス サーバーとして同じトポロジでは、組織内のすべての Exchange サーバー上には、ExchUcUtil.ps1 スクリプトを実行します。 シェルを使用して、メールボックス サーバーからスクリプトを実行するか、クライアント アクセス サーバーでリモートの Windows PowerShell を使用してスクリプトを実行することができます。 組織内のクライアント アクセス サーバー上でスクリプトを実行するクライアント アクセス サーバーは、組織内のメールボックス サーバーへのリモートの Windows PowerShell セッションをプロキシになります。
> [!IMPORTANT]
> ExchUcUtil.ps1 スクリプトでは、1 つまたは複数の UM IP ゲートウェイを作成します。 スクリプトを作成する 1 つのゲートウェイを除くすべての UM IP ゲートウェイで発信呼び出しを無効にする必要があります。 これには、スクリプトを実行する前に作成された UM IP ゲートウェイに送信呼び出しを無効にすることが含まれます。 UM IP ゲートウェイで発信呼び出しを無効にするには、発信呼び出しを UM IP ゲートウェイを無効にするを参照してください。 
> [!IMPORTANT]
> Exchange 組織の管理役割のアクセス許可があるか、スクリプトを実行する Exchange 組織管理者のセキュリティ グループのメンバーである必要があります。 

1. Exchange 管理シェルを開きます。
2. C:\Windows\System32 プロンプトで、入力の**cd \<letter>:\Program Files\Microsoft\Exchange Server\V15\Scripts> をドライブします。ExchUcUtil.ps1**、し、Enter キーを押します。

#### <a name="how-do-you-know-this-worked"></a>どうやってこの方法でしょうか。

ExchUcUtul.ps1 スクリプトが正常に完了したことを確認するには、次の操作を行います。
- Get UMIPGateway コマンドレット、または、EAC を使用すると、新しい UM IP ゲートウェイまたは作成されたゲートウェイを表示します。
- Get UMHuntGroup コマンドレット、または、EAC を使用すると、新しい UM ハント グループまたは作成されたグループを表示します。

### <a name="configure-certificates-on-the-server-running-exchange-server-unified-messaging"></a>Exchange Server ユニファイド メッセージングを実行するサーバーに証明書を構成します。
 
ビジネスのサーバー計画のドキュメントでの Skype での Exchange ユニファイド メッセージング統合のための計画で説明するように Exchange ユニファイド メッセージング (UM) を展開しているし、エンタープライズ VoIP ユーザーに Exchange UM の機能を提供する場合、組織で Exchange UM を実行するサーバーに証明書を構成するのには次の手順を使用できます。

> [!IMPORTANT]
> 内部証明書は、ビジネス サーバーの Skype を実行しているサーバーと Microsoft Exchange を実行しているサーバーの両方する必要があります信頼性のない、相互に信頼されたルート機関の証明書。 証明機関 (CA) できます、同じまたは別の証明機関を信頼されたルート機関の証明書ストアに登録されている証明機関のルートの証明書がサーバーにある限り。 

Skype ビジネス サーバーに接続するためにサーバー証明書を Exchange Server を構成する必要があります。
1. Exchange Server 用の CA 証明書をダウンロードします。
2. Exchange Server 用には、CA 証明書をインストールします。
3. CA が、Exchange Server の Ca の信頼されたルートのリストにあることを確認します。
4. Exchange Server の証明書の要求を作成し、証明書をインストールします。 
5. Exchange Server の証明書を割り当てます。


**CA 証明書をダウンロードするには。**

1. Exchange UM を実行するサーバー、[**スタート] ボタン**、[**実行**] をクリック、タイプ**http://\<発行 CA の Server>/certsrv の名前**、し、[ **OK**] をクリックします。
2. [タスクを選択して、[ **CA 証明書、証明書チェーン、または CRL のダウンロード**] をクリックします。
3. [ **CA 証明書、証明書チェーン、または CRL のダウンロード**の**Base 64 エンコード方法**を選択し、**ダウンロードする CA 証明書**] をクリックします。
   > [!NOTE]
   > この段階での識別のエンコード規則 (DER) エンコーディングを指定することもできます。 DER は、この手順の次の手順でファイルの種類のエンコードを選択し、手順 10 の**証明書の CA をインストールする**場合は、.cer ではなく、.p7b です。 
4. **ファイルのダウンロード**] ダイアログ ボックスで**を保存**] をクリックし、サーバー上のハード ディスクにファイルを保存します。 (ファイルは、.cer またはファイルの拡張子は .p7b、エンコード前の手順で選択したことによってのいずれかです。)

**CA 証明書をインストールするには。**

1. Exchange UM を実行するサーバー上で **[スタート] ボタン**、**実行**をクリックすると、[名前] ボックスに「 **mmc**と入力して、 **[ok]** をクリックし、Microsoft 管理コンソール (MMC) を開きます。
2. [**ファイル**] メニュー **[スナップインの追加と削除]** をクリックし、[**追加**] をクリックします。
3. [**スタンドアロン スナップインの追加**] ボックスで、**証明書**をクリックし、[**追加**] をクリックします。
4. [**証明書スナップイン**] ダイアログ ボックスの [**コンピューター アカウント**] をクリックし、[**次へ**] をクリックします。
5. **[コンピューターの選択**] ダイアログ ボックスであることを確認、**ローカル コンピューター: (このコンソールを実行しているコンピューター)** ] チェック ボックスをオンにして、[**完了**] をクリックします。
6. **[閉じる**] をクリックし、[ **OK**] をクリックします。 
7. コンソール ツリーで、[**証明書 (ローカル コンピューター)** を展開を選択し、**信頼されたルート証明機関**] を展開し、[**証明書**] をクリックします。
8. **証明書**を右クリックし、**すべてのタスク**] をクリックし、[**インポート**] をクリックします。
9. [ **次へ**] をクリックします。 
10. **参照**ファイルを検索する] をクリックし、[**次へ**] をクリックします。 (ファイルは、.cer またはファイルの拡張子は .p7b、 **CA 証明書をダウンロードする**は、手順 3 で選択したエンコード方法によってがあります。
11. 次のストアに**証明書をすべての場所**をクリックします。
12. **[参照**] をクリックし、**信頼されたルート証明機関**を選択します。 
13. **次**の設定を確認する] をクリックし、[**完了**] をクリックします。 


**CA が、信頼されたルート Ca の一覧にあることを確認します。**

1. サーバーで Exchange UM を実行して、[証明書 (ローカル コンピューター) を展開 MMC で信頼されたルート証明機関を展開し、[証明書] をクリックします。
2. 詳細ウィンドウで、CA が信頼された Ca のリストであるを確認します。


