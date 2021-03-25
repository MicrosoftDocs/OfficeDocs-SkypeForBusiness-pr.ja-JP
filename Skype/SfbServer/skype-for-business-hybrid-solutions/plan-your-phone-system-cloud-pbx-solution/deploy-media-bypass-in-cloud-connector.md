---
title: Cloud Connector Edition でのメディア バイパスの展開
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
description: このトピックでは、Cloud Connector Edition バージョン 2.0 以降でメディア バイパスを展開する手順について説明します。
ms.openlocfilehash: c9dc79a3079fd27e8901d31abf1a27310d18ed28
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119366"
---
# <a name="deploy-media-bypass-in-cloud-connector-edition"></a>Cloud Connector Edition でのメディア バイパスの展開
 
> [!Important]
> Cloud Connector Edition は、Skype for Business Online と共に 2021 年 7 月 31 日に廃止されます。 組織が Teams にアップグレードしたら、直接ルーティングを使用してオンプレミスのテレフォニー ネットワークを Teams に接続する方法 [について説明します](/MicrosoftTeams/direct-routing-landing-page)。

このトピックでは、Cloud Connector Edition バージョン 2.0 以降でメディア バイパスを展開する手順について説明します。 
  
メディア バイパスを使用すると、クライアントはパブリック 交換電話網 (PSTN) ネクスト ホップ (ゲートウェイまたはセッション ボーダー コントローラー (SBC)) にメディアを直接送信し、メディア パスから Cloud Connector Edition コンポーネントを削除できます。 「Cloud [Connector Edition でメディア バイパスを計画する」も参照してください](plan-for-media-bypass-in-cloud-connector-edition.md)。
  
## <a name="enable-media-bypass"></a>メディアのバイパスを有効にする

メディア バイパスを有効にするには、メディア バイパス Web サービスの DNS 名を構成し、テナント構成でメディア バイパスを有効にする必要があります。 メディア バイパス Web サービスは、すべての仲介サーバーに自動的に展開されます。 テナント管理者は、ハイブリッド 音声サービス (サイト) の名前を選択する必要があります。この名前は、ハイブリッド音声用に登録された SIP ドメインからの名前である必要があります。 サービス名は、クライアントの場所に関係なく、すべてのクラウド コネクタ アプライアンスとすべての PSTN サイトで同じにします。 Web サービスは、ネットワーク上でのみ内部的に利用できる必要があります。
  
テナント管理者は、内部実稼働 Active Directory で DNS A レコードを構成する必要があります。 複雑なマルチサイト環境がある場合は、「例: 複雑なマルチサイト環境でのメディア バイパス Web サイト DNS レコード」の例 [を参照してください](deploy-media-bypass-in-cloud-connector.md#Example)。 DNS レコードは、内部ネットワーク クライアントでのみ解決する必要があります。外部ネットワーク クライアントでは解決されません。
  
DNS を構成したら、Skype for Business Administrator 資格情報を使用してリモート PowerShell を使用して Skype for Business Online に接続します。 詳細については、「コンピューターの[セットアップ」を参照Windows PowerShell。](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  
PowerShell セッションで、次のコマンドを入力してメディア バイパスを有効にします。
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
$mediabypass = New-CsNetworkMediaBypassConfiguration -AlwaysBypass $true -Enabled $true
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

メディア バイパスの有効化は、2 段階のプロセスです。 新New-CsNetworkMediaコマンドレットは、新しい構成を直ちに保存しない。メモリ内に設定が作成されるのみです。 このコマンドレットによって作成されたオブジェクトを変数に保存し、ネットワーク構成の MediaBypassSettings プロパティに割り当てる必要があります。 詳細については、「例: 複雑なマルチサイト環境でのメディア バイパス Web サイト [DNS レコード」を参照してください](deploy-media-bypass-in-cloud-connector.md#Example)。
  
オンプレミスコンポーネントとオンライン コンポーネント間のレプリケーションには最大 24 時間かかる場合があります。そのため、ユーザーを有効にする前に必要なコマンドを実行する必要があります。
  
## <a name="confirm-media-bypass-settings"></a>メディア バイパス設定の確認

メディア バイパス設定は、次のように確認できます。 
  
テナント プールへのオンライン レプリケーションを確認するには、リモート PowerShell で次のコマンドを実行します。
  
```powershell
Get-CsTenantHybridConfiguration -LocalStore
Get-CsNetworkConfiguration -LocalStore
```

オンプレミスレプリケーションを確認するには、クラウド コネクタ仲介サーバーに接続し、PowerShell で次のコマンドを実行し、Enabled=True と AlwaysBypass=True を確認します。
  
```powershell
Get-CsNetworkConfiguration -LocalStore
```

クライアント設定を確認するには、Skype for Business クライアントからサインアウトし、サインインし、クライアントがサービス URL を次のように受信したと確認します。
  
1. %appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog を開きます。 
    
2. hybridconfigserviceinternalurl を検索し、URL が定義した URL と一致する内容を確認します。
    
## <a name="change-media-bypass-parameters"></a>メディア バイパス パラメーターの変更

テナント管理者は、次のコマンドレットを実行して Web サービスの DNS 名を変更できます。
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
```

> [!IMPORTANT]
> クライアントは、新しいサービス名を取得し、変更を認識するためにサインアウトしてサインインする必要があります。 
  
## <a name="temporarily-disable-media-bypass"></a>メディア バイパスを一時的に無効にする

このシナリオは、トラブルシューティングやメンテナンスに役立つ場合があります。 サービスを無効にするには、次のコマンドレットを実行します。
  
```powershell
$mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

変更を行った後、変更がすべてのクラウド コネクタにレプリケートされるのに時間がかかる場合があります。 レプリケーションの状態を確認するには、クラウド コネクタ 仲介サーバーの PowerShell で次のコマンドレットを実行します。 
  
```powershell
Get- CsNetworkConfiguration -LocalStore
```

変更がレプリケートされた後、仲介サーバー上の Web サービスは、メディア バイパス サービスに対するクライアント要求の拒否を開始します。
  
## <a name="disable-media-bypass-permanently"></a>メディア バイパスを完全に無効にする

メディア バイパスを完全に無効にするには、テナント管理者が次のコマンドを実行する必要があります。 
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl  $null
    $mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false 
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass 
```

管理者は、内部 DNS サーバーからメディア バイパス用の Web アドレスを削除する必要があります。 変更を行った後、変更がすべての Cloud Connector アプライアンスにレプリケートされるのに時間がかかる場合があります。 
  
## <a name="example-media-bypass-web-site-dns-records-in-complex-multi-site-environments"></a>例: 複雑な複数サイト環境でのメディア バイパス Web サイト DNS レコード
<a name="Example"> </a>

クライアントは、内部 DNS サーバーからメディア バイパス Web サービスの Web アドレスを受信します。 Web サービスの名前は、すべてのクラウド コネクタ アプライアンスとクラウド コネクタ PSTN サイトで同じになります。 複雑なマルチサイト環境では、Geo-Location ベースのトラフィック管理に Windows 2016 DNS ポリシーを使用することをお勧めします。そのため、クライアントはネットワークのローカルである Web サービスにリダイレクトできます。 
  
Windows 2016 DNS ポリシーの詳細については、「Use DNS Policy for Geo-Location ベースのトラフィック管理とプライマリ サーバー」 [を参照してください](/windows-server/networking/dns/deploy/primary-geo-location)。
  
次に、Windows 2016 DNS ポリシーを使用して複数のサイトを使用する企業の構成例を示Geo-Location示します。
  
バイパス サービスの名前は 'hybridvoice.adatum.biz' です。
  
アムステルダムのサイトには、次の仲介サーバー IP アドレスを使用して 4 つのクラウド コネクタ アプライアンスが展開されています。
  
- 192.168.1.45
    
- 192.168.1.46
    
- 192.168.1.47
    
- 192.168.1.48
    
シアトルのサイトには、次の仲介サーバー IP アドレスを使用して 3 つのクラウド コネクタ アプライアンスが展開されています。
  
- 10.10.1.8
    
- 10.10.1.9
    
- 10.10.1.10
    
このGeo-Locationベースのトラフィック管理を使用して、DNS サーバーは次のように構成されます。
  
1. アムステルダムとシアトルの両方のサブネットの DNS クライアント サブネットを作成します。
    
2. アムステルダムとシアトルの両方 adatum.biz DNS ゾーン スコープを作成します。
    
3. 各 DNS ゾーン スコープに DNS レコードを作成します。
    
    アムステルダム
    
   - タイプ A;
    
   - 名前 : DNS ゾーンの adatum.biz 設定
    
   - ターゲット: 192.168.1.45
    
     追加の仲介サーバーの追加レコードを作成する
    
   - 192.168.1.46
    
   - 192.168.1.47
    
   - 192.168.1.48
    
     シアトル
    
   - タイプ A
    
   - 名前 : DNS ゾーン adatum.biz ハイブリッド
    
   - ターゲット: 10.10.1.8
    
     追加の仲介サーバーの追加レコードを作成する
    
   - 10.10.1.9
    
   - 10.10.1.10
    
4. クライアント サブネットを適切なゾーン スコープに接続する DNS ポリシーを作成して、必要な DNS 解決を確実に行います。
    
この時点で、アムステルダムのサブネットから dns クエリを実行するクライアントは、hybridvoice.adatum.biz 192.168.1.45 を返します。 192.168.1.46、192.168.1.47、192.168.1.47 アドレス、192.168.1.48 アドレス、同じクエリ フォームを作成するクライアントは、10.10.1.8、10.10.1.9、10.10.1.10 を返します。

> [!NOTE]
> CCE アプライアンスが更新された設定を取得していないと思われる場合は、アプライアンスがリモート PowerShell を介してテナントに連絡できるのか確認してください。 リモート PowerShell を使用して、Get-CsHybridPSTNAppliance でアプライアンスの状態を確認したり、CCE ホストで PowerShell を使用して Get-CcApplianceStatus で状態を確認できます。

  
## <a name="see-also"></a>関連項目
<a name="Example"> </a>

[Cloud Connector エディションでのメディア バイパスの計画](plan-for-media-bypass-in-cloud-connector-edition.md)