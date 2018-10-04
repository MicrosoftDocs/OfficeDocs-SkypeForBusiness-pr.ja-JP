---
title: Cloud Connector エディションでメディア バイパスを展開する
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0ebba3a4-6124-434c-84aa-32b1cc3345bc
description: クラウド コネクタ版 version 2.0 以降でメディアをバイパスを展開する手順については、このトピックを参照してください。
ms.openlocfilehash: 841a243b236219fc70c99264249567f2eee63081
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2018
ms.locfileid: "25375500"
---
# <a name="deploy-media-bypass-in-cloud-connector-edition"></a>Cloud Connector エディションでメディア バイパスを展開する
 
クラウド コネクタ版 version 2.0 以降でメディアをバイパスを展開する手順については、このトピックを参照してください。 
  
メディア バイ パスにより、公衆交換電話網 (PSTN) の次のホップに直接メディアを送信するクライアント-ゲートウェイまたはセッション ボーダー コント ローラー (SBC)-メディアのパスからクラウドのコネクタのエディションのコンポーネントを削除するとします。 [クラウド コネクタのエディションで使用しないメディアの計画](plan-for-media-bypass-in-cloud-connector-edition.md)を参照してください。
  
## <a name="enable-media-bypass"></a>メディアのバイパスを有効にする

メディア バイパスを有効にするには、メディア バイパス Web サービスの DNS 名を設定し、テナント構成でメディア バイパスをオンにする必要があります。 メディア バイパス Web サービスはそれぞれの仲介サーバーに自動的に展開されます。 テナント管理者はハイブリッド音声サービス (サイト) の名前を指定する必要があります。この名前は、ハイブリッド音声用に登録された SIP ドメインの名前を使用する必要があります。 サービス名は、クラウドのコネクタのすべてのアプライアンスやクライアントの場所に関係なくすべての PSTN のサイト間で同じをする必要があります。 この Web サービスはネットワーク内部のみで利用可能です。
  
テナント管理者は内部実働の Active Directory で DNS A レコードを構成する必要があります。 複雑な複数サイト環境を使っている場合の例を参照してください。[の使用例: メディアが複雑な複数サイトの環境で web サイトの DNS レコードを使用しない](deploy-media-bypass-in-cloud-connector.md#Example)。 DNS レコードは、内部ネットワーク クライアントについてのみ解決します。外部ネットワーク クライアントについては解決しません。
  
DNS を構成したら、Skype for Business 管理者の資格情報で リモート PowerShell を使用して、Skype for Business Online に接続します。 詳細については、 [Windows PowerShell を使用して、オンライン ビジネスの Skype への接続](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx)を参照してください。
  
PowerShell セッションで、次のコマンドを入力してメディア バイパスを有効にします。
  
```
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
$mediabypass = New-CsNetworkMediaBypassConfiguration -AlwaysBypass $true -Enabled $true
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

メディア バイパスの有効化は 2 つのプロセスで行います。 New-CsNetworkMedia コマンドレットでは、新しい構成がすぐに保存されません。メモリ内に設定が作成されるだけです。 このコマンドレットで作成したオブジェクトを変数として保存し、ネットワーク構成の MediaBypassSettings プロパティに割り当てる必要があります。 詳細についてを参照してください[の使用例: メディアが複雑な複数サイトの環境で web サイトの DNS レコードを使用しない](deploy-media-bypass-in-cloud-connector.md#Example)。
  
オンプレミスとオンライン コンポーネント間のレプリケーションには最長で 24 時間かかります。したがって、ユーザーを有効化する前に必要なコマンドを実行しておくことをお勧めします。
  
## <a name="confirm-media-bypass-settings"></a>メディア バイパス設定を確認する

メディア バイパス設定は次の方法で確認できます。 
  
テナント プールにオンライン ・ レプリケーションを確認するには、リモート PowerShell で次のコマンドを実行します。
  
```
Get-CsTenantHybridConfiguration -LocalStore
Get-CsNetworkConfiguration -LocalStore
```

設置型のレプリケーションを確認して、クラウドのコネクタの仲介サーバーに接続、PowerShell で次のコマンドを実行、ことを確認するその Enabled = True と AlwaysBypass = True
  
```
Get-CsNetworkConfiguration -LocalStore
```

クライアント設定を確認するには、ビジネス クライアント用の Skype からサインアウトにもう一度サインインし、クライアントが、サービスの URL を次のように受け取ることを確認します。
  
1. %appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog を開きます。 
    
2. hybridconfigserviceinternalurl を探して、定義した URL とそこに表示されている URL が一致することを確認します。
    
## <a name="change-media-bypass-parameters"></a>メディア バイパス パラメータを変更する

テナント管理者は、次のコマンドレットを実行して、Web サービスの DNS 名を変更できます。
  
```
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
```

> [!IMPORTANT]
> クライアントは、一度サインアウトしてから再びサインインし、新しいサービス名を入手することで、変更を確認できます。 
  
## <a name="temporarily-disable-media-bypass"></a>メディア バイパスを一時的に無効にする

このシナリオは、トラブルシューティングやメンテナンスで役立ちます。サービスを無効にするには、次のコマンドレットを実行します。
  
```
$mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

変更後、すべての Cloud Connector にレプリケートされるまで時間がかかる場合があります。 レプリケーションの状態を確認するには、クラウド コネクタの仲介サーバーに、PowerShell で次のコマンドレットを実行します。 
  
```
Get- CsNetworkConfiguration -LocalStore
```

変更がレプリケートされると、仲介サーバーの Web サービスにより、メディア バイパス サービスに対するクライアント要求の拒否が開始されます。
  
## <a name="disable-media-bypass-permanently"></a>メディア バイパスを完全に無効にする

メディア バイパスを完全に無効にするには、テナント管理者が次のコマンドを実行する必要があります。 
  
```
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl  $null
    $mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false 
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass 
```

さらに、管理者は内部 DNS サーバーからメディア バイパスの Web アドレスを削除する必要があります。 変更を加えたら、クラウドのコネクタのすべてのアプライアンスをレプリケートする変更の時間がかかる可能性があります。 
  
## <a name="example-media-bypass-web-site-dns-records-in-complex-multi-site-environments"></a>例: 複雑なマルチサイト環境でのメディア バイパス Web サイトの DNS レコード
<a name="Example"> </a>

クライアントは、内部 DNS サーバーからメディア バイパス Web サービスの Web アドレスを受信します。 Web サービスの名前は同じにするすべてのコネクタのクラウド アプライアンスおよびクラウド コネクタ PSTN のサイト。 複雑なマルチサイト環境では、地理的な場所ベースのトラフィック管理用の Windows 2016 DNS ポリシーを使用して、クライアントのネットワークにおいてローカルな Web サービスにクライアントをリダイレクトできるようにすることをお勧めします。 
  
Windows 2016 DNS ポリシーの詳細については、[地理的な場所ベースのトラフィックの管理のプライマリ サーバーの DNS ポリシーの使用](https://docs.microsoft.com/en-us/windows-server/networking/dns/deploy/primary-geo-location)を参照してください。
  
地理的な場所ベースのトラフィック管理の Windows 2016 DNS ポリシーを使用して、複数のサイトを持つ会社の構成例を示します。
  
使用しないサービスの名前は、'hybridvoice.adatum.biz' です。
  
アムステルダムのサイトには、4 つのクラウド コネクタ アプライアンスを次のような仲介サーバーの IP アドレスで展開があります。
  
- 192.168.1.45
    
- 192.168.1.46
    
- 192.168.1.47
    
- 192.168.1.48
    
シアトルのサイトには、次の 3 つのクラウド コネクタ アプライアンスを次のような仲介サーバーの IP アドレスで展開があります。
  
- 10.10.1.8
    
- 10.10.1.9
    
- 10.10.1.10
    
地理的な場所ベースのトラフィック管理を使用する場合は、次の手順で DNS サーバーを構成できます。
  
1. アムステルダムとシアトルのサブネットに対する DNS クライアント サブネットを作成します。
    
2. アムステルダムとシアトルの adatum.biz の DNS ゾーン範囲を作成します。
    
3. それぞれの DNS ゾーン範囲で DNS レコードを作成します。
    
    アムステルダム
    
   - タイプ A
    
   - 名前: adatum.biz DNS ゾーンの hybridvoice
    
   - ターゲット: 192.168.1.45
    
     追加の仲介サーバーについてレコードを作成する
    
   - 192.168.1.46
    
   - 192.168.1.47
    
   - 192.168.1.48
    
     調布市調布ヶ丘
    
   - タイプ A
    
   - 名前: adatum.biz DNS ゾーンの hybridvoice
    
   - ターゲット: 10.10.1.8
    
     追加の仲介サーバーについてレコードを作成する
    
   - 10.10.1.9
    
   - 10.10.1.10
    
4. クライアント サブネットを適切なゾーン範囲に接続する DNS ポリシーを作成して、DNS が確実に解決されるようにします。
    
この時点では、hybridvoice.adatum.biz のアムステルダムのサブネットから DNS クエリーを実行しているクライアントは 192.168.1.45、192.168.1.46、192.168.1.47、192.168.1.48 のアドレスを返します。その一方で、シアトルから同様のクエリーを実行しているクライアントは 10.10.1.8、10.10.1.9、10.10.1.10 を返します。

> [!NOTE]
> CCE アプライアンスは、更新された設定を取得するように思える場合、は、アプライアンスをリモート PowerShell を使用してテナントに接続できるかどうかを確認してください。 Get CsHybridPSTNAppliance とアプライアンスの状態を確認するか、Get CcApplianceStatus の状態を確認する CCE ホストで PowerShell を使用するリモート PowerShell を使用できます。

  
## <a name="see-also"></a>この手順は役に立ちましたか? 役に立った場合は、この記事の下でお知らせください。役に立たなかった場合は、わかりにくかった部分をお知らせください。いただいたフィードバックを元に手順を再確認します。
<a name="Example"> </a>

[Cloud Connector エディションでのメディア バイパスを計画する](plan-for-media-bypass-in-cloud-connector-edition.md)
