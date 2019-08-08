---
title: Skype for Business Server ボイス メールに対する Exchange Server ユニファイド メッセージングの構成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/11/2019
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1be9c4f4-fd8e-4d64-9798-f8737b12e2ab
description: '概要: Skype for Business Server ボイスメール用に Exchange Server ユニファイドメッセージングを構成します。'
ms.openlocfilehash: 514b2159c3836aee4bd6bcfad2b85311280277c4
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36238008"
---
# <a name="configure-exchange-server-unified-messaging-for-skype-for-business-server-voice-mail"></a>Skype for Business Server ボイス メールに対する Exchange Server ユニファイド メッセージングの構成
 
**概要:** Skype for Business Server ボイスメール用に Exchange Server ユニファイドメッセージングを構成します。
  
Skype for Business Server を使用すると、ボイスメールメッセージを Exchange Server 2016 または Exchange Server 2013 に保存することができます。これらのボイスメールメッセージは、ユーザーの受信トレイにメールメッセージとして表示されます。 

> [!NOTE]
> 以前に認識されていた exchange ユニファイドメッセージングは Exchange 2019 では利用できなくなりましたが、電話システムを使ってボイスメールメッセージを録音し、ユーザーの Exchange メールボックスに記録を残すことができます。 詳細については、「[クラウドボイスメールサービスの計画](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md)」を参照してください。
  
Skype for Business Server と Exchange Server 2016 または Exchange Server 2013 の間にサーバー間認証を既に構成している場合は、ユニファイドメッセージングを設定することができます。 そのためには、まず Exchange Server で新しいユニファイドメッセージングダイヤルプランを作成して割り当てる必要があります。 たとえば、次の2つのコマンド (Exchange 管理シェル内から実行) では、Exchange 用の新しい3桁のダイヤルプランを構成します。
  
```
New-UMDialPlan -Name "RedmondDialPlan" -VoIPSecurity "Secured" -NumberOfDigitsInExtension 3 -URIType "SipName" -CountryOrRegionCode 1
Set-UMDialPlan "RedmondDialPlan" -ConfiguredInCountryOrRegionGroups "Anywhere,*,*,*" -AllowedInCountryOrRegionGroups "Anywhere"
```

この例の最初のコマンドでは、VoIPSecurity パラメーターとパラメーター値 "セキュリティ保護" は、シグナリングチャネルがトランスポート層セキュリティ (TLS) を使用して暗号化されていることを示します。 URIType "SipName" は、SIP プロトコルを使用してメッセージが送受信されることを指定し、CountryOrRegionCode の 1 は、ダイヤル プランが米国に適用されることを指定します。
  
2 番目のコマンドで、ConfiguredInCountryOrRegionGroups パラメーターに渡されるパラメーター値は、このダイヤル プランで使用できる国内のグループを指定します。 "Anywhere、\*,\*\*" というパラメーター値は、次のように設定します。
  
- グループ名 ("Anywhere")
    
- Allowed連番文字列 (\*任意の数字文字列が許可されていることを示すワイルドカード文字)
    
- [ダイヤル番号]\*文字列 (およびダイヤルされた番号が許可されていることを示すワイルドカード文字)
    
- TextComment (\*任意のテキストコマンドが許可されていることを示すワイルドカード文字)
    
> [!NOTE]
> 新しいダイヤル プランを作成すると、既定のメールボックス ポリシーも作成されます。 
  
新しいダイヤルプランを作成して構成した後、新しいダイヤルプランをユニファイドメッセージングサーバーに追加し、そのサーバーのスタートアップモードを変更する必要があります。特に、スタートアップモードを "デュアル" に設定する必要があります。 Exchange 管理シェルでは、次の2つのタスクを実行できます。
  
```
Set-UmService -Identity "atl-exchangeum-001.litwareinc.com" -DialPlans "RedmondDialPlan" -UMStartupMode "Dual"
```

ユニファイドメッセージングサーバーの構成が完了したら、次に、Import-exchangecertificate コマンドレットを実行して、Exchange 証明書がユニファイドメッセージングサービスに適用されていることを確認します。
  
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
  
メールボックスを有効にすると、ユーザー kenmyer@litwareinc.com は Exchange ユニファイド メッセージングを使用できるようになります。 Skype for Business Server 管理シェル内から[テスト用の CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/test-csexumconnectivity?view=skype-ps)コマンドレットを実行することで、ユーザーが Exchange UM に接続できることを確認できます。
  
```
$credential = Get-Credential "litwareinc\kenmyer"
Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential
```

ユニファイド メッセージングが有効化されている 2 番目のユーザーがいる場合は、[Test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/test-csexumvoicemail?view=skype-ps) コマンドレットを使用して、この 2 番目のユーザーが最初のユーザーにボイスメール メッセージを残せることを確認できます。
  
```
$credential = Get-Credential "litwareinc\pilar"
Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential
```



## <a name="configuring-unified-messaging-on-microsoft-exchange-server"></a>Microsoft Exchange Server でのユニファイドメッセージングの構成 
> [!IMPORTANT]
> Exchange ユニファイドメッセージング (UM) を使用して、通話の応答、Outlook Voice Access、またはエンタープライズ Voip サービスを提供する場合は、「 [Skype For business での Exchange ユニファイドメッセージングの統合を計画](../../plan-your-deployment/integrate-with-exchange/unified-messaging.md)する」を参照してください。手順については、こちらを参照してください。 

エンタープライズ Voip と連携するように Exchange ユニファイドメッセージング (UM) を構成するには、次の作業を行う必要があります。

- Exchange ユニファイドメッセージング (UM) サービスを実行しているサーバーで証明書を構成する
  > [!NOTE]
  > すべてのクライアントアクセスとメールボックスサーバーを UM SIP のすべての URI ダイヤルプランに追加します。 そうしないと、発信通話のルーティングが予期したとおりに機能しません。 
- 必要に応じて、サブスクライバーアクセス用電話番号と共に1つまたは複数の UM SIP URI ダイヤルプランを作成して、対応する L dial プランを作成します。

- 次のような操作を実行するために exchucutil スクリプトを使います。
    - UM IP ゲートウェイを作成します。
    - UM ハントグループを作成します。
    - UM Active Directory ドメインサービスオブジェクトを読み取るための Skype for Business Server 権限を付与します。
- UM 自動応答オブジェクトを作成します。
- サブスクライバーアクセスオブジェクトを作成します。
- ユーザーごとに SIP URI を作成し、UM SIP URI ダイヤルプランを使用してユーザーを関連付けます。

### <a name="requirements-and-recommendations"></a>要件と推奨事項

始める前に、このセクションのドキュメントでは、クライアントアクセスとメールボックスという Exchange ロールが展開されていることを前提としています。 Microsoft Exchange Server では、Exchange UM はこれらのサーバーでサービスとして実行されます。

次の点にも注意してください。
- Exchange UM が複数のフォレストにインストールされている場合は、各 UM フォレストで Exchange Server の統合手順を実行する必要があります。 さらに、各 UM フォレストが、Skype for Business Server が展開されているフォレストを信頼するように構成されている必要があります。また、Skype for Business Server が展開されているフォレストが各 UM フォレストを信頼するように構成されている必要があります。
- 統合手順は、ユニファイドメッセージングサービスが実行されている Exchange Server の役割と、Skype for Business Server を実行しているサーバーで実行されます。 Lync Server 2013 の統合手順を実行する前に、Exchange Server ユニファイドメッセージング統合の手順を実行する必要があります。
  > [!NOTE]
  > どのサーバーに対して実行される統合手順と管理者の役割を確認するには、「[展開プロセスの概要」でオンプレミスのユニファイドメッセージングと Skype For business を統合](../../plan-your-deployment/integrate-with-exchange/deployment-overview.md)する方法について説明します。 

Exchange UM を実行している各サーバーでは、次のツールを使用できる必要があります。
- Exchange 管理シェル
- スクリプト exchucutil は、次のタスクを実行します。
    - 各 Skype for Business Server 用に UM IP ゲートウェイを作成します。
    - 各ゲートウェイのハントグループを作成します。 各ハントグループのパイロット識別子は、ゲートウェイに関連付けられているフロントエンドプールまたは Standard Edition サーバーで使用される UM SIP URI ダイヤルプランを指定します。
    - Active Directory ドメインサービスの Exchange UM オブジェクトを読み取るための Skype for Business Server 権限を付与します。



### <a name="configure-unified-messaging-on-microsoft-exchange-with-exchucutilps1"></a>Configure Unified Messaging on Microsoft Exchange with ExchUCUtil.ps1 

Microsoft Skype for Business Server を Exchange ユニファイドメッセージング (UM) と統合する場合は、シェルで ExchUcUtil というスクリプトを実行する必要があります。 ExchUcUtil スクリプトは、次の操作を実行します。

- 各 Skype for Business Server プール用に UM IP ゲートウェイを作成します。

> [!IMPORTANT]
> ExchUcUtil スクリプトは、1つ以上の UM IP ゲートウェイを作成します。 スクリプトで作成された1つのゲートウェイを除き、すべての UM IP ゲートウェイで発信通話を無効にする必要があります。 これには、スクリプトを実行する前に作成された UM IP ゲートウェイでの発信通話の無効化が含まれます。 

- UM IP ゲートウェイごとに UM ハントグループを作成します。 各ハントグループのパイロット識別子は、UM IP ゲートウェイに関連付けられている Skype for Business Server のフロントエンドプールまたは Standard Edition サーバーで使用される UM SIP URI ダイヤルプランを指定します。
- UM ダイヤルプラン、自動応答、UM IP ゲートウェイ、UM ハントグループなどの Active Directory UM コンテナーオブジェクトを読み取るための Skype for Business Server 権限を付与します。
  > [!IMPORTANT]
  > 各 UM フォレストは、Skype for Business Server が展開されているフォレストを信頼するように構成する必要があります。また、Skype for Business Server 2013 が展開されているフォレストは、各 UM フォレストを信頼するように構成されている必要があります。 Exchange UM が複数のフォレストにインストールされている場合は、UM フォレストごとに Exchange Server の統合手順を実行するか、Skype for Business Server ドメインを指定する必要があります。 たとえば、ExchUcUtil は、<lync-ドメインコントローラー-fqdn>] のようになります。 

### <a name="use-the-shell-to-run-the-exchucutilps1-script"></a>Shell を使用して ExchUcUtil を実行します。 ps1 スクリプト

組織内のすべての Exchange server で、Skype for Business Server と同じトポロジを使用している場合は、ExchUcUtil スクリプトを実行します。 シェルを使用してメールボックスサーバーからスクリプトを実行することも、クライアントアクセスサーバーでリモート Windows PowerShell を使用してスクリプトを実行することもできます。 組織内のクライアントアクセスサーバーでスクリプトを実行すると、クライアントアクセスサーバーは、リモートの Windows PowerShell セッションを組織内のメールボックスサーバーにプロキシします。
> [!IMPORTANT]
> ExchUcUtil スクリプトは、1つ以上の UM IP ゲートウェイを作成します。 スクリプトで作成された1つのゲートウェイを除き、すべての UM IP ゲートウェイで発信通話を無効にする必要があります。 これには、スクリプトを実行する前に作成された UM IP ゲートウェイでの発信通話の無効化が含まれます。 UM IP ゲートウェイでの発信通話を無効にするには、「UM IP ゲートウェイでの発信通話の無効化」を参照してください。 
> [!IMPORTANT]
> スクリプトを実行するには、Exchange 組織管理役割のアクセス許可、または Exchange 組織管理者セキュリティグループのメンバーである必要があります。 

1. Exchange 管理シェルを開きます。
2. C:\Windows\System32 プロンプトで、 ** \<cd ドライブ文字>: Files\Microsoft\Exchange Server\V15\Scripts> を入力します。「ExchUcUtil**」と入力し、enter キーを押します。

#### <a name="how-do-you-know-this-worked"></a>これが機能したことを知る方法を教えてください。

ExchUcUtul. ps1 スクリプトが正常に完了したことを確認するには、次の操作を行います。
- Get-UMIPGateway コマンドレットまたは EAC を使用して、作成された新しい UM IP ゲートウェイまたはゲートウェイを表示します。
- Get-UMHuntGroup コマンドレットまたは EAC を使用して、作成された新しい UM ハントグループまたはグループを表示します。

### <a name="configure-certificates-on-the-server-running-exchange-server-unified-messaging"></a>Exchange Server ユニファイドメッセージングを実行しているサーバーで証明書を構成する
 
計画ドキュメントの「Skype for Business Server での Exchange ユニファイドメッセージングの統合を計画する」の説明に従って、Exchange ユニファイドメッセージング (UM) を展開している場合、Exchange UM 機能を組織内のエンタープライズボイスユーザーに提供する必要があります。組織では、次の手順を使用して、Exchange UM を実行しているサーバー上で証明書を構成することができます。

> [!IMPORTANT]
> 内部証明書については、Skype for Business Server を実行しているサーバーと、Microsoft Exchange を実行しているサーバーの両方が相互に信頼されている信頼できるルート証明書を持っている必要があります。 証明機関 (CA) は、信頼されたルート機関の証明書ストアに証明機関のルート証明書が登録されている限り、同じまたは別の証明機関とすることができます。 

Skype for Business Server に接続するには、Exchange Server がサーバー証明書を使用して構成されている必要があります。
1. Exchange サーバーの CA 証明書をダウンロードします。
2. Exchange サーバーの CA 証明書をインストールします。
3. CA が Exchange Server の信頼されているルート Ca のリストに含まれていることを確認します。
4. Exchange Server の証明書要求を作成して、証明書をインストールします。 
5. Exchange Server の証明書を割り当てます。


**CA 証明書をダウンロードするには:**

1. Exchange UM を実行しているサーバーで [**スタート**] をクリックし、[**実行**] をクリックし**て、\<http://の発行 CA> サーバーの名前**を入力し、[ **OK]** をクリックします。
2. [タスクの選択] で、[ **CA 証明書、証明書チェーン、または CRL をダウンロード**します] をクリックします。
3. **Ca 証明書、証明書チェーン、または CRL**をダウンロード**するに**は、[エンコード方法] を [ベース 64] に、[**ca 証明書のダウンロード**] をクリックします。
   > [!NOTE]
   > この手順では、識別エンコード規則 (DER) のエンコードを指定することもできます。 DER エンコードを選択した場合は、この手順の次の手順のファイルの種類と、 **CA 証明書をインストールする**手順10については .cer ではなく. p7b を使用します。 
4. [**ファイルのダウンロード**] ダイアログボックスで、[**保存**] をクリックし、サーバーのハードディスクにファイルを保存します。 (前の手順で選んだエンコードに応じて、ファイル拡張子は .cer または. p7b のいずれかになります)。

**CA 証明書をインストールするには、次の操作を行います。**

1. Exchange UM を実行しているサーバーで、[**スタート**]、[実行]、[名前を指定**** して**実行**] の順にクリックし、[ **OK**] をクリックして、Microsoft 管理コンソール (mmc) を開きます。
2. [**ファイル**] メニューで、[スナップインの**追加と削除**] をクリックし、[**追加**] をクリックします。
3. [**スタンドアロンスナップ**インの追加] ボックスで、[**証明書**] をクリックし、[**追加**] をクリックします。
4. [**証明書スナップイン**] ダイアログ ボックスの [**コンピューター アカウント**] をクリックし、[**次へ**] をクリックします。
5. **[コンピューターの選択**] ダイアログボックスで、[**ローカルコンピューター: (このコンソールが実行されているコンピューター)** ] チェックボックスがオンになっていることを確認し、[**完了**] をクリックします。
6. [**閉じる**] をクリックし、[ **OK**] をクリックします。 
7. コンソールツリーで、[**証明書 (ローカルコンピューター)**]、[**信頼されたルート証明機関**] の順に展開し、[**証明書**] をクリックします。
8. [**証明書**] を右クリックし、[**すべてのタスク**] をクリックして、[**インポート**] をクリックします。
9. [ **次へ**] をクリックします。 
10. [**参照**] をクリックしてファイルを指定し、[**次へ**] をクリックします。 (手順3で選択したエンコード方法によって、 **CA 証明書をダウンロードする**場合は、.cer または. p7b のファイル拡張子のいずれかが表示されます。
11. [**証明書をすべて**次のストアに配置する] をクリックします。
12. [**参照**] をクリックし、[**信頼されたルート証明機関**] を選びます。 
13. [**次へ**] をクリックして設定を確認し、[**完了**] をクリックします。 


**CA が信頼できるルート Ca のリストに含まれていることを確認するには、次の操作を行います。**

1. Exchange UM を実行しているサーバーで、MMC で [証明書 (ローカルコンピューター)]、[信頼されたルート証明機関] の順に展開し、[証明書] をクリックします。
2. [詳細] ウィンドウで、CA が信頼できる Ca の一覧にあることを確認します。


