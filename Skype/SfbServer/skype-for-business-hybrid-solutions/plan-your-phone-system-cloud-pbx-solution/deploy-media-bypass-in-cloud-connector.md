---
title: Cloud Connector エディションでメディア バイパスを展開する
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
description: このトピックでは、クラウドコネクタエディションバージョン2.0 以降でメディアのバイパスを展開する手順について説明します。
ms.openlocfilehash: 771d3a7294fde38b032e4cd9a281f70156280d3a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802347"
---
# <a name="deploy-media-bypass-in-cloud-connector-edition"></a>Cloud Connector エディションでメディア バイパスを展開する
 
このトピックでは、クラウドコネクタエディションバージョン2.0 以降でメディアのバイパスを展開する手順について説明します。 
  
メディアのバイパスを使用すると、クライアントは、公衆交換電話網 (PSTN) の次ホップ (ゲートウェイまたはセッションボーダーコントローラー (SBC)) にメディアを直接送信し、メディアパスからクラウドコネクタエディションコンポーネントを削除することができます。 「[クラウドコネクタエディションでのメディアバイパスの計画](plan-for-media-bypass-in-cloud-connector-edition.md)」もご覧ください。
  
## <a name="enable-media-bypass"></a>メディアのバイパスを有効にする

メディアバイパスを有効にするには、メディアバイパス web サービスの DNS 名を構成し、テナント構成でメディアバイパスを有効にする必要があります。 メディアバイパスの web サービスは、すべての仲介サーバーで自動的に展開されます。 テナント管理者は、ハイブリッドボイスサービス (サイト) の名前を選択する必要があります。この名前は、ハイブリッドボイスに登録されている SIP ドメインから取得する必要があります。 サービス名は、クライアントの場所に関係なく、すべてのクラウドコネクタのアプライアンスとすべての PSTN サイトで同じである必要があります。 Web サービスは、ネットワーク上でのみ利用可能である必要があります。
  
テナント管理者は、内部の運用 Active Directory で DNS A レコードを構成する必要があります。 複雑なマルチサイト環境がある場合は、「[複雑なマルチサイト環境での web サイトの DNS レコードのバイパス](deploy-media-bypass-in-cloud-connector.md#Example)」の例を参照してください。 DNS レコードは、内部ネットワーククライアントに対してのみ解決されます。外部ネットワーククライアントに対しては解決されません。
  
DNS を構成したら、Skype for Business 管理者の資格情報で リモート PowerShell を使用して、Skype for Business Online に接続します。 詳細については、「 [Windows PowerShell 用にコンピューターをセットアップする](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)」を参照してください。
  
PowerShell セッションで、次のコマンドを入力してメディア バイパスを有効にします。
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
$mediabypass = New-CsNetworkMediaBypassConfiguration -AlwaysBypass $true -Enabled $true
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

メディアのバイパスを有効にするには、2つの手順を実行します。 新しい-CsNetworkMedia コマンドレットでは、新しい構成はすぐに保存されません。メモリ内の設定のみを作成します。 このコマンドレットによって作成されたオブジェクトは、変数に保存してから、ネットワーク構成の MediaBypassSettings プロパティに割り当てる必要があります。 詳細については、「[例: 複雑なマルチサイト環境での web サイトの DNS レコードのバイパス](deploy-media-bypass-in-cloud-connector.md#Example)」を参照してください。
  
オンプレミスとオンライン コンポーネント間のレプリケーションには最長で 24 時間かかります。したがって、ユーザーを有効化する前に必要なコマンドを実行しておくことをお勧めします。
  
## <a name="confirm-media-bypass-settings"></a>メディア バイパス設定を確認する

メディア バイパス設定は次の方法で確認できます。 
  
テナントプールへのオンラインレプリケーションを確認するには、リモート PowerShell で次のコマンドを実行します。
  
```powershell
Get-CsTenantHybridConfiguration -LocalStore
Get-CsNetworkConfiguration -LocalStore
```

オンプレミスのレプリケーションを確認するには、クラウドコネクタの仲介サーバーに接続し、PowerShell で次のコマンドを実行し、有効であることを確認します。
  
```powershell
Get-CsNetworkConfiguration -LocalStore
```

クライアント設定を確認するには、Skype for Business クライアントからサインアウトし、もう一度サインインして、クライアントが次のようにサービス URL を受信したことを確認します。
  
1. %appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog を開きます。 
    
2. hybridconfigserviceinternalurl を探して、定義した URL とそこに表示されている URL が一致することを確認します。
    
## <a name="change-media-bypass-parameters"></a>メディア バイパス パラメータを変更する

テナント管理者は、次のコマンドレットを実行して、Web サービスの DNS 名を変更できます。
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
```

> [!IMPORTANT]
> クライアントは、一度サインアウトしてから再びサインインし、新しいサービス名を入手することで、変更を確認できます。 
  
## <a name="temporarily-disable-media-bypass"></a>メディア バイパスを一時的に無効にする

このシナリオは、トラブルシューティングやメンテナンスで役立ちます。サービスを無効にするには、次のコマンドレットを実行します。
  
```powershell
$mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

変更後、すべての Cloud Connector にレプリケートされるまで時間がかかる場合があります。 レプリケーションの状態を確認するには、クラウドコネクタ仲介サーバー上の PowerShell で次のコマンドレットを実行します。 
  
```powershell
Get- CsNetworkConfiguration -LocalStore
```

変更がレプリケートされると、仲介サーバーの Web サービスにより、メディア バイパス サービスに対するクライアント要求の拒否が開始されます。
  
## <a name="disable-media-bypass-permanently"></a>メディア バイパスを完全に無効にする

メディア バイパスを完全に無効にするには、テナント管理者が次のコマンドを実行する必要があります。 
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl  $null
    $mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false 
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass 
```

さらに、管理者は内部 DNS サーバーからメディア バイパスの Web アドレスを削除する必要があります。 変更を行った後は、変更がすべてのクラウドコネクタのアプライアンスに複製されるまでに時間がかかることがあります。 
  
## <a name="example-media-bypass-web-site-dns-records-in-complex-multi-site-environments"></a>例: 複雑なマルチサイト環境でのメディア バイパス Web サイトの DNS レコード
<a name="Example"> </a>

クライアントは、内部 DNS サーバーからメディア バイパス Web サービスの Web アドレスを受信します。 Web サービスの名前は、すべてのクラウドコネクタのアプライアンスとクラウドコネクタの PSTN サイトで同じになります。 複雑なマルチサイト環境では、地理的な場所ベースのトラフィック管理用の Windows 2016 DNS ポリシーを使用して、クライアントのネットワークにおいてローカルな Web サービスにクライアントをリダイレクトできるようにすることをお勧めします。 
  
Windows 2016 DNS ポリシーの詳細については、「[プライマリサーバーを使用した地理的な場所に基づくトラフィック管理に DNS ポリシーを使用する](https://docs.microsoft.com/windows-server/networking/dns/deploy/primary-geo-location)」を参照してください。
  
地理的な場所ベースのトラフィック管理の Windows 2016 DNS ポリシーを使用して、複数のサイトを持つ会社の構成例を示します。
  
バイパスサービスの名前は ' hybridvoice.adatum.biz ' です。
  
アムステルダムのサイトには、次の仲介サーバー IP アドレスを使用して、4つのクラウドコネクタのアプライアンスが展開されています。
  
- 192.168.1.45
    
- 192.168.1.46
    
- 192.168.1.47
    
- 192.168.1.48
    
シアトルのサイトには、次の仲介サーバー IP アドレスを使用して展開された、3つのクラウドコネクタのアプライアンスが含まれています。
  
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
> CCE アプライアンスが更新された設定になっていないように見える場合は、アプライアンスがリモート PowerShell 経由でテナントに接続できるかどうかを確認します。 リモート PowerShell を使用して、CsHybridPSTNAppliance でアプライアンスの状態を確認するか、または CCE ホストの PowerShell を使用して、CcApplianceStatus を使って状態を確認することができます。

  
## <a name="see-also"></a>関連項目
<a name="Example"> </a>

[Cloud Connector エディションでのメディア バイパスの計画](plan-for-media-bypass-in-cloud-connector-edition.md)
