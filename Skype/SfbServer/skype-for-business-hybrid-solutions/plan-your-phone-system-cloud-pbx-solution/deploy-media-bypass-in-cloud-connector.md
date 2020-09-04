---
title: Cloud Connector エディションでのメディアバイパスの展開
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0ebba3a4-6124-434c-84aa-32b1cc3345bc
description: このトピックでは、Cloud Connector エディションバージョン2.0 以降を使用してメディアバイパスを展開する手順について説明します。
ms.openlocfilehash: eeb566e2a1a16e235813c077d4e4bf6903a467d7
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359313"
---
# <a name="deploy-media-bypass-in-cloud-connector-edition"></a>Cloud Connector エディションでのメディアバイパスの展開
 
> [!Important]
> Cloud Connector エディションは、2021年7月31日、Skype for Business Online と共に廃止されます。 組織が Teams にアップグレードされたら、 [直接ルーティング](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)を使用してオンプレミスのテレフォニーネットワークを teams に接続する方法について説明します。

このトピックでは、Cloud Connector エディションバージョン2.0 以降を使用してメディアバイパスを展開する手順について説明します。 
  
メディアバイパスを使用すると、クライアントはメディアを公衆交換電話網 (PSTN) の次ホップに直接送信できます。ゲートウェイまたはセッションボーダーコントローラー (SBC) を使用して、Cloud Connector Edition コンポーネントをメディアパスから削除します。 [Cloud Connector Edition の「Plan for media バイパス](plan-for-media-bypass-in-cloud-connector-edition.md)」も参照してください。
  
## <a name="enable-media-bypass"></a>メディアのバイパスを有効にする

メディアバイパスを有効にするには、メディアバイパス web サービスの DNS 名を構成し、テナント構成でメディアバイパスを有効にする必要があります。 メディアバイパス web サービスは、すべての仲介サーバーで自動的に展開されます。 テナント管理者はハイブリッド音声サービス (サイト) の名前を選択する必要があります。この名前は、ハイブリッド音声用に登録された SIP ドメインの名前である必要があります。 サービス名は、すべての Cloud Connector アプライアンスと、クライアントの場所に関係なくすべての PSTN サイトで同じである必要があります。 Web サービスは、ネットワーク内部でのみ利用可能である必要があります。
  
テナント管理者は内部運用 Active Directory で DNS A レコードを構成する必要があります。 複雑なマルチサイト環境がある場合は、「 [複雑なマルチサイト環境でのメディアバイパス web サイトの DNS レコード](deploy-media-bypass-in-cloud-connector.md#Example)」の例を参照してください。 DNS レコードは、内部ネットワーククライアントに対してのみ解決する必要があります。外部ネットワーククライアントに対しては解決されません。
  
DNS を構成した後、Skype for Business 管理者の資格情報を使用してリモート PowerShell を使用して、Skype for Business Online に接続します。 詳細については、「 [Windows PowerShell 用にコンピューター](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md) をセットアップする」を参照してください。
  
PowerShell セッションで、次のコマンドを入力してメディアバイパスを有効にします。
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
$mediabypass = New-CsNetworkMediaBypassConfiguration -AlwaysBypass $true -Enabled $true
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

メディアバイパスを有効にするには、2段階のプロセスがあります。 新しい-CsNetworkMedia コマンドレットでは、新しい構成はすぐには保存されません。メモリに設定を作成するだけです。 このコマンドレットで作成したオブジェクトは、変数に保存してから、ネットワーク構成の MediaBypassSettings プロパティに割り当てる必要があります。 詳細については、「 [例: 複雑なマルチサイト環境でのメディアバイパス web サイトの DNS レコード](deploy-media-bypass-in-cloud-connector.md#Example)」を参照してください。
  
オンプレミスとオンラインのコンポーネント間のレプリケーションには最大24時間かかる場合があるため、ユーザーを有効にする前に、必要なコマンドを実行することをお勧めします。
  
## <a name="confirm-media-bypass-settings"></a>メディアバイパス設定の確認

メディアバイパス設定を確認するには、次のようにします。 
  
テナントプールへのオンラインレプリケーションを確認するには、リモート PowerShell で次のコマンドを実行します。
  
```powershell
Get-CsTenantHybridConfiguration -LocalStore
Get-CsNetworkConfiguration -LocalStore
```

オンプレミスレプリケーションを確認するには、Cloud Connector 仲介サーバーに接続し、PowerShell で次のコマンドを実行し、Enabled = True、Always バイパス = True であることを確認します。
  
```powershell
Get-CsNetworkConfiguration -LocalStore
```

クライアント設定を確認するには、Skype for Business クライアントからサインアウトし、もう一度サインインして、クライアントが次のようにサービス URL を受信していることを確認します。
  
1. %Appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog. を開く 
    
2. Hybridconfigserviceinternalurl を検索し、URL が定義したものと一致することを確認します。
    
## <a name="change-media-bypass-parameters"></a>メディアバイパスパラメーターの変更

テナント管理者は、次のコマンドレットを実行することによって、web サービスの DNS 名を変更できます。
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
```

> [!IMPORTANT]
> クライアントは、新しいサービス名を取得して変更を認識するために、サインアウトしてからサインインする必要があります。 
  
## <a name="temporarily-disable-media-bypass"></a>メディアバイパスを一時的に無効にする

このシナリオは、トラブルシューティングや保守に役立つ場合があります。 サービスを無効にするには、次のコマンドレットを実行します。
  
```powershell
$mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

変更後は、変更がすべてのクラウドコネクタにレプリケートされるまでに時間がかかることがあります。 レプリケーションの状態を確認するには、Cloud Connector 仲介サーバーの PowerShell で次のコマンドレットを実行します。 
  
```powershell
Get- CsNetworkConfiguration -LocalStore
```

変更がレプリケートされると、仲介サーバーの web サービスは、メディアバイパスサービスに対するクライアント要求の拒否を開始します。
  
## <a name="disable-media-bypass-permanently"></a>メディアバイパスを完全に無効にする

メディアバイパスを完全に無効にするには、テナント管理者が次のコマンドを実行する必要があります。 
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl  $null
    $mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false 
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass 
```

また、管理者は、内部 DNS サーバーからメディアバイパスの web アドレスを削除する必要があります。 変更後は、すべての Cloud Connector アプライアンスに変更がレプリケートされるまでに少し時間がかかることがあります。 
  
## <a name="example-media-bypass-web-site-dns-records-in-complex-multi-site-environments"></a>例: 複雑なマルチサイト環境でのメディアバイパス web サイトの DNS レコード
<a name="Example"> </a>

クライアントは、内部 DNS サーバーからメディアバイパス web サービスの web アドレスを受け取ります。 Web サービスの名前は、すべての Cloud Connector アプライアンスおよび Cloud Connector PSTN サイトで同じになります。 複雑なマルチサイト環境では、地域の場所に基づいたトラフィック管理に Windows 2016 DNS ポリシーを使用することをお勧めします。そのため、ネットワークにローカルな web サービスにクライアントをリダイレクトすることができます。 
  
Windows 2016 DNS ポリシーの詳細については、「 [プライマリサーバーを使用した地域の場所ベースのトラフィック管理に Dns ポリシーを使用する](https://docs.microsoft.com/windows-server/networking/dns/deploy/primary-geo-location)」を参照してください。
  
次に示すのは、地域の場所ベースのトラフィック管理に Windows 2016 DNS ポリシーを使用している複数のサイトを持つ企業の構成例です。
  
バイパスサービスの名前は ' hybridvoice.adatum.biz ' です。
  
アムステルダムのサイトには、次の仲介サーバー IP アドレスを使用して展開された4つの Cloud Connector アプライアンスがあります。
  
- 192.168.1.45
    
- 192.168.1.46
    
- 192.168.1.47
    
- 192.168.1.48
    
シアトルのサイトには、次の仲介サーバー IP アドレスを使用して展開された3つの Cloud Connector アプライアンスがあります。
  
- 10.10.1.8
    
- 10.10.1.9
    
- 10.10.1.10
    
地域の場所に基づいたトラフィック管理を使用して、DNS サーバーを次のように構成します。
  
1. アムステルダムとシアトルの両方のサブネットの DNS クライアントサブネットを作成します。
    
2. アムステルダムとシアトルの両方について、adatum.biz の DNS ゾーンスコープを作成します。
    
3. Dns ゾーンスコープごとに DNS レコードを作成します。
    
    アムステルダム
    
   - 「A;」と入力します。
    
   - Name: adatum.biz DNS ゾーンの hybridvoice
    
   - ターゲット: 192.168.1.45
    
     追加の仲介サーバー用の追加レコードを作成する
    
   - 192.168.1.46
    
   - 192.168.1.47
    
   - 192.168.1.48
    
     Seattle
    
   - 「A」と入力します。
    
   - Name: hybridvoice in adatum.biz DNS zone
    
   - ターゲット: 10.10.1.8
    
     追加の仲介サーバー用の追加レコードを作成する
    
   - 10.10.1.9
    
   - 10.10.1.10
    
4. クライアントサブネットを適切なゾーンスコープに接続する DNS ポリシーを作成して、必要な DNS 解決を確保します。
    
この時点で、クライアントは hybridvoice.adatum.biz のアムステルダムサブネットからの DNS クエリを作成すると、192.168.1.45、192.168.1.46、192.168.1.47、192.168.1.48 の各アドレスが返されますが、同じクエリフォームがシアトルになっているクライアントは10.10.1.8、10.10.1.9、10.10.1.10 を返します。

> [!NOTE]
> CCE アプライアンスが更新された設定を取得していないように見える場合は、アプライアンスがリモート PowerShell 経由でテナントに接続できるかどうかを確認します。 リモート PowerShell を使用して、CsHybridPSTNAppliance でアプライアンスの状態を確認したり、CCE ホストで PowerShell を使用して、CcApplianceStatus を使用して状態を確認したりできます。

  
## <a name="see-also"></a>関連項目
<a name="Example"> </a>

[Cloud Connector エディションでのメディア バイパスの計画](plan-for-media-bypass-in-cloud-connector-edition.md)
