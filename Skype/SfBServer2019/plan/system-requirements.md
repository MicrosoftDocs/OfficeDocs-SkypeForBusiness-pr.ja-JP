---
title: Skype for Business Server 2019 のシステム要件
ms.reviewer: ''
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: ''
description: '概要: このトピックでは、Skype for Business Server 2019 のサーバーとドメインインフラストラクチャを準備します。 ハードウェア、OS、データベース、ソフトウェア、証明書 DNS、ファイル共有、および Active Directory 情報と共に、すべてのシステム要件と推奨事項に加えて、サーバーファームのインストールと展開が正常に行われるようにします。'
ms.openlocfilehash: 8bb12fa9f5d0cd0144604f21d311c50f7f63b0f4
ms.sourcegitcommit: 000515147632c6278bcda4505a1038014dda8e2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "44232378"
---
# <a name="system-requirements-for-skype-for-business-server-2019"></a>Skype for Business Server 2019 のシステム要件
 
**概要:** このトピックを使用して Skype for Business Server 2019 のインストールを準備します。 ハードウェア、OS、ソフトウェア、データベース、証明書、Active diretory、DNS、および該当について説明します。 すべてのシステム要件と推奨事項は、サーバーファームのインストールと展開を成功させるために役立ちます。
  
予想されるように、Skype for Business Server 2019 の展開を開始する前に行う必要がある準備があります。 この記事では、次の計画について順を追って説明します。
  
- [ハードウェア](system-requirements.md#Hardware)
  
- [オペレーティングシステム](system-requirements.md#OS)
  
- [ソフトウェア](system-requirements.md#Software)

- [バックエンド SQL データベース](system-requirements.md#DBs)
  
- [Active Directory](system-requirements.md#AD)
  
- [ドメイン ネーム システム (DNS)](system-requirements.md#DNS)
  
- [証明書](system-requirements.md#Certs)
  
- [ファイル共有](system-requirements.md#Fileshare)

  
## <a name="hardware-for-skype-for-business-server-2019"></a>Skype for business Server 2019 のハードウェア
<a name="Hardware"> </a>

トポロジを停止した後 (必要でない場合は、「 [Skype For Business Server 2019」のトピックの「トポロジの基本](../../SfbServer/plan-your-deployment/topology-basics/topology-basics.md)」を参照してください)、サーバーについて考えてみましょう。 Skype for Business Server 2019 サーバーでは、64ビットのハードウェアが必要です。 ハードウェアに関する推奨事項は以下のとおりです。 これらは要件ではありませんが、最適なパフォーマンスを得るために必要な要件を反映しています。 状況によっては、これ以上の必要があるかどうかを判断するのに役立つ容量計画のドキュメントが用意されています。
  
Standard Edition サーバーの推奨ハードウェア:

|**ハードウェア コンポーネント**|**推奨**|
|:-----|:-----|
|CPU  <br/> |Intel Xeon E5-2673 v3 デュアルプロセッサ、6コア、2.4 ghz 以上。  <br/> Intel Itanium プロセッサは、Skype for Business Server 2019 の役割ではサポートされていません。  <br/> |
|メモリ  <br/> |32 gb  <br/> |
|ディスク  <br/> |いずれも：  <br/> • 1万 RPM のハードディスクドライブのうち、少なくとも 72 GB のディスクの空き領域 (raid 1 を使用している2台のディスク、および RAID 10 を使用する2つのディスク)。  <br/> または  <br/> •ソリッドステートドライブ (Ssd) は、8 1万 RPM メカニカルディスクドライブと同じ空き領域と同じパフォーマンスを提供することができます。  <br/> |
|ネットワーク  <br/> |1 Gbps 以上のデュアルポートネットワークアダプター (2 つのネットワークアダプターを使用できますが、1つの MAC アドレスと1つの IP アドレスをチーミングする必要があります)。  <br/> デュアルまたはマルチホーム構成は、フロントエンドサーバー、バックエンドサーバー、および Standard Edition サーバーではサポートされて**いません**。 <br/> オペレーティングシステムに公開されておらず、サーバーハードウェアを監視および管理するためにも使用されている限り、DRAC や ILO などの帯域外管理システムを使用できます。 このシナリオは、複数のホームサーバーを構成するものではなく、サポートされています。  <br/> |


フロントエンドサーバーおよびバックエンドサーバーに推奨されるハードウェア:
  
|**ハードウェア コンポーネント**|**推奨**|
|:-----|:-----|
|CPU  <br/> |Intel Xeon E5-2673 v3 デュアルプロセッサ、6コア、2.4 ghz 以上。 <br/> Intel Itanium プロセッサは、Skype for Business Server 2019 の役割ではサポートされていません。  <br/> |
|メモリ  <br/> |64 gb  <br/> |
|ディスク  <br/> |いずれも：  <br/> • 1万 RPM のハードディスクドライブのうち、少なくとも 72 GB のディスクの空き領域 (raid 1 を使用している2台のディスク、および RAID 10 を使用する2つのディスク)。  <br/> または  <br/> •ソリッドステートドライブ (Ssd) は、8 1万 RPM メカニカルディスクドライブと同じ空き領域と同じパフォーマンスを提供することができます。  <br/> |
|ネットワーク  <br/> |1 Gbps 以上のデュアルポートネットワークアダプター (2 つのネットワークアダプターを使用できますが、1つの MAC アドレスと1つの IP アドレスをチーミングする必要があります)。  <br/> デュアルまたはマルチホーム構成は、フロントエンドサーバー、バックエンドサーバー、および Standard Edition サーバーではサポートされて**いません**。 <br/> オペレーティングシステムに公開されておらず、サーバーハードウェアを監視および管理するためにも使用されている限り、DRAC や ILO などの帯域外管理システムを使用できます。 このシナリオは、複数のホームサーバーを構成するものではなく、サポートされています。  <br/> |
   
エッジサーバー、スタンドアロン仲介サーバー、およびディレクターの推奨ハードウェア:
  
|**ハードウェア コンポーネント**|**推奨**|
|:-----|:-----|
|CPU  <br/> |Intel Xeon E5-2673 v3 デュアルプロセッサ、6コア、2.4 ghz 以上。  <br/> Intel Itanium プロセッサは、Skype for Business Server 2019 の役割ではサポートされていません。  <br/> |
|メモリ  <br/> |32 gb  <br/> |
|ディスク  <br/> |いずれも：  <br/> •4台以上の 1万 RPM ハードディスクドライブ (少なくとも 72 GB の空きディスク領域がある) (ディスクは2倍の RAID 1 構成である必要があります)。  <br/> または  <br/> •ソリッドステートドライブ (Ssd) は、4 1万 RPM メカニカルディスクドライブと同じ空き領域と同じパフォーマンスを提供することができます。  <br/> |
|ネットワーク  <br/> |1 Gbps 以上のデュアルポートネットワークアダプター (2 つのネットワークアダプターを使用できますが、1つの MAC アドレスと1つの IP アドレスをチーミングする必要があります)。  <br/> デュアルまたはマルチホーム構成は、ビデオ相互運用サーバーとディレクターではサポートされて**いません**。 <br/> エッジサーバーでは、2つのネットワークインターフェイス (または、1 Gbps 以上のデュアルポートネットワークアダプター、つまり合計4つのネットワークアダプターが1つの MAC アドレスと1つの IP アドレスでチーミングされ、合計2つのペア) が必要です。  <br/> スタンドアロンの仲介サーバーでは、特定の PSTN IP アドレスの構成を許可するために追加のネットワークインターフェイスカード (Nic) をインストールすることがサポートされています。  <br/> |


> [!NOTE]
> サーバーの役割に関係なく、Skype for Business Server 2019 については次のハードウェア設定もお勧めします (これは購入したハードウェアのブランドによって異なる場合があります。詳細については、製造元のドキュメントを参照してください)。
> - BIOS 構成は、NUMA からフラットに設定する必要があります。
> - ハイパースレッディングを有効にします。
> - RSS キューの設定は8キューに設定する必要があります。

   
## <a name="operating-systems-for-skype-for-business-server-2019"></a>Skype for Business Server 2019 のオペレーティングシステム
<a name="OS"> </a>

ハードウェアの準備が整ったら、Skype for Business Server 2019 をインストールして正常に使用できるようにするために、オペレーティングシステム (OS) をインストールする必要があります。
  
|||
|:-----|:-----|
|Windows Server 2019 <br/> |
|Windows Server 2016 <br/> ||
||
   
ここに記載されているオペレーティングシステム以外のすべての機能は正しく動作しません。Skype for Business Server 2019 のインストールには試しないでください。 たとえば、Server Core オプションがリストされていないため、サポートされていません。

> [!NOTE]
> Lync Server 2013 では、OS の一括アップグレードはサポートされていません。 別のプールを展開し、別の OS を使用してユーザーを新しいプールに移行する必要があります。 プール内のすべてのサーバーの OS バージョンは同じである必要があります。

> [!NOTE]
> 
> Windows Server 2019 コンピューターに Windows 管理センター2019をインストールしている場合は、リッスンするポートを求めるメッセージが表示されます。 Liklihood は、ポート443を選択することもありますが、そのマシンに Skype for Business Server 2019 がインストールされている場合、または Skype for business Server 2019 がインストールされている場合は、別のポート番号を選択する必要があります。
> 
>その場合はなぜですか。 Windows 管理センター2019がポート443で実行されている場合、Skype for Business コントロールパネルを使用してサーバーに接続することはできません。また、サーバー上で実行されている内部 web サービス (アドレス帳 Web サービス、自動検出サービス、WebTicket サービスなど) に接続することもできません。  実際、内部の Web サービス URL に接続することはできません。 別のポートを選択してください。必要な場合は、Windows 管理センター2019を Skype for Business Server 2019 を使用してサーバーに配置する必要があります。
> 

  
## <a name="software-that-should-be-installed-before-a-skype-for-business-server-2019-deployment"></a>Skype for Business Server 2019 の展開前にインストールする必要があるソフトウェア
<a name="Software"> </a>

Skype for Business Server 2019 を実行しているすべてのサーバーについて、インストールまたは構成する必要がある事柄がいくつかあります。 以下に、特定のサーバーの役割の追加要件を示します。

> [!IMPORTANT]
> Skype For Business 2019 は、.Net Framework 4.8 をサポートしています。 
  
 **すべてのサーバー:**
  
|**ソフトウェア/役割**|**詳細**|
|:-----|:-----|
|Windows PowerShell 3.0  <br/> |すべての Skype for Business Server サーバーには、Windows PowerShell 3.0 がインストールされている必要があります。  <br/> •これは、Windows Server 2016 を使用して既定でインストールする必要があります。<br/> |
|Microsoft .NET Framework  <br/> |WCF サービスは、Windows の機能としてインストールされている**機能**です。**サーバーマネージャー**では、最初はダウンロードは必要ありません。 <br/> •この機能をインストールするとき、または既にインストールされていてチェックしているときには、次のように**HTTP アクティブ化**オプションもチェックされ、インストールされていることを確認する必要があります。 <br/> ![.NET Framework 4.5 機能の下の HTTP アクティブ化オプションを示すスクリーンショット。](../../SfbServer/media/a4064fa0-fa49-4474-bd98-b9a79ff68f8b.png) <br/> HTTP ライセンス認証をインストールするには、他にもいくつかの設定をインストールする必要があることを示す追加のポップアップが表示されても心配しないでください。 これは通常のことです。[OK] をクリックして、前に進みます。 このポップアップが表示されない場合は、これらの項目が既にインストールされていて、先に進んでいると見なすことができます。  <br/> Microsoft .NET Framework は、通常、Windows Server 2016 がインストールされている場合にインストールされます。 Skype for Business Server には Microsoft .NET Framework 4.7 または4.8 が必要です。そのためには、更新が必要になる場合があります。 この更新プログラムは[こちら](https://support.microsoft.com/help/3186497/the-net-framework-4-7-offline-installer-for-windows/)から入手できます。<br/> |
|メディアファンデーション  <br/> |Windows Server 2016 では、Windows Media フォーマットランタイムが Microsoft Media Foundation と共にインストールされます。  <br/> 会議に使用されるすべてのフロントエンドサーバーおよび Standard Edition サーバーでは、windows Media フォーマットランタイムを使用して、コールパーク、アナウンス、および応答グループアプリケーションがアナウンスと音楽を再生する Windows media Audio (.wma) ファイルを実行する必要があります。  <br/> |
|Windows Identity Foundation  <br/> |Skype for Business Server 2019 のサーバー間認証シナリオをサポートするには、Windows Identity Foundation 3.5 が必要です。  <br/> • Windows Server 2016 の場合、何もダウンロードする必要はありません。 **サーバーマネージャー**を開き、[**役割と機能の追加ウィザード]** に進みます。 **Windows Identity Foundation 3.5**は、[**機能**] セクションの下に一覧表示されます。 選択されている場合は、問題ありません。 それ以外の場合は、それを選択し、[**次**へ] をクリックして [**インストール**] ボタンに移動します <br/> |
|リモート サーバー管理ツール  <br/> |役割管理ツール: AD DS および AD LDS ツール  <br/> |
   
 **フロントエンドサーバーおよび Standard Edition サーバーにも次のものが必要です。**
  
|**ソフトウェア/役割**|**詳細**|
|:-----|:-----|
|インターネット インフォメーション サービス (IIS)  <br/> |すべてのフロントエンドサーバーとすべての Standard Edition サーバーで、次のモジュールが選択されている場合は、IIS が必要です。  <br/> •共通の HTTP 機能: 既定のドキュメント、HTTP エラー、静的コンテンツ  <br/> •正常性と診断: HTTP ログ、ログツール、トレース  <br/> •パフォーマンス: 静的なコンテンツの圧縮、動的なコンテンツの圧縮  <br/> •セキュリティ: 要求フィルター、クライアント証明書マッピング認証、Windows 認証  <br/> •アプリケーション開発: .NET 拡張3.5、.NET の拡張性4.5、ASP.NET 3.5、ASP.NET 4.5、ISAPI Extensions、ISAPI フィルター  <br/> •管理ツール: IIS 管理コンソール、IIS 管理スクリプトおよびツール  <br/> 匿名アクセスも必要であることに注意してください。ただし、IIS をインストールするときには、リストでそのファイルを選択する場所がないことにご注意ください。  <br/> |
|Windows Media フォーマット ランタイム  <br/> | Windows Server 2016 の場合は、**サーバーマネージャー**で**メディアファンデーション**機能をインストールする必要があります。 実際には、Skype for business Server 2019 のインストールを実行することはできませんが、skype for Business Server 2019 のインストールが続行される前に、インストールするかどうかを確認するメッセージが表示されます。その後、サーバーを再起動する必要があります。 事前にこれを行うことをお勧めします。 <br/> |
|Silverlight  <br/> |[ここで](https://www.microsoft.com/silverlight/)は、最新バージョンの Silverlight をインストールできます。  <br/> |
   
これを支援するために、以下のサンプル PowerShell スクリプトを実行して、これを自動化することができます。
  
```PowerShell
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Windows-Identity-Foundation, Server-Media-Foundation, Telnet-Client, BITS, ManagementOData, Web-Mgmt-Console, Web-Metabase, Web-Lgcy-Mgmt-Console, Web-Lgcy-Scripting, Web-WMI, Web-Scripting-Tools, Web-Mgmt-Service
```

 **ディレクターにも次のものが必要です。**
  
IIS。次のモジュールが選択されています。
  
- HTTP 共通機能
    
  - 既定のドキュメント
    
  - HTTP エラー
    
  - 静的コンテンツ
    
- 状態と診断
    
  - HTTP ログ
    
  - ログ ツール
    
  - ・
    
- パフォーマンス
    
  - 静的なコンテンツの圧縮
    
- セキュリティ
    
  - 要求のフィルタリング
    
  - クライアント証明書マッピング認証
    
  - Windows 認証
    
- アプリケーション開発
    
  - .NET 拡張機能3.5
    
  - .NET 拡張機能 4.5
    
  - ASP.NET 3.5
    
  - ASP.NET 4.5
    
  - ISAPI 拡張機能
    
  - ISAPI フィルター
    
(疑問点がある場合は、フロントエンドサーバーと Standard Edition サーバーと同じモジュールセットを使用して、動的コンテンツ圧縮と管理ツールを残しておきます)。
  
これについては、次の PowerShell コードを参照してください。
  
```PowerShell
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, Telnet-Client
```

## <a name="back-end-databases-that-will-work-with-skype-for-business-server-2019"></a>Skype for Business Server 2019 で動作するバックエンドデータベース
<a name="DBs"> </a>

Skype for Business Server 2019 Standard Edition をインストールすると、SQL Server 2016 Express (64 ビット版) がインストールされます。

以下に示すように、Skype for Business Server 2019 Enterprise Edition は完全な SQL Server を必要とします (64 ビット版のみ。32ビットエディションは使用しないでください)。
  
||||
|:-----|:-----|:-----|
|Microsoft SQL Server 2019 (64 ビット版)。最新の更新プログラムを使用して実行する必要があります。  <br/> |Microsoft SQL Server 2017 (64 ビット版)。最新の更新プログラムを使用して実行する必要があります。  <br/> |
Microsoft SQL Server 2016 (64 ビット版)。最新の更新プログラムを使用して実行する必要があります。|
 |

使用する SQL Server エディションが表示されていない場合は、これを使用することはできません。
  
> [!NOTE]
> また、監視サーバーの役割用の SQL Server Reporting Services もインストールする必要があります。 
  
### <a name="sql-clustering-and-sql-always-on"></a>SQL クラスタリング、および SQL Always On

Skype for Business Server 2019 を使用した SQL クラスタリングがサポートされています。 SQL クラスタリングをセットアップする場合は、SQL Server で行います。
  
サポートされている SQL クラスタリングのアクティブ/パッシブ構成を使用していることを確認してください。 パッシブノードは他の SQL インスタンスと共有しないでください。
  
フェールオーバークラスタリングには、次のものを含めることができます。
  
2ノード:
  
- Microsoft SQL Server 2019 Standard (64 ビット版)。最新のサービスパックを使用して実行することをお勧めします。
- Microsoft SQL Server 2017 Standard (64 ビット版)。最新のサービスパックを使用して実行することをお勧めします。
- Microsoft SQL Server 2016 Standard (64 ビット版)。最新のサービスパックを使用して実行することをお勧めします。

16ノード:
  
- Microsoft SQL Server 2019 Enterprise (64 ビット版)。最新のサービスパックを使用して実行することをお勧めします。
- Microsoft SQL Server 2017 Enterprise (64 ビット版)。最新のサービスパックを使用して実行することをお勧めします。
- Microsoft SQL Server 2016 Enterprise (64 ビット版)。最新のサービスパックを使用して実行することをお勧めします。

SQL Always On がサポートされています。これについては、「 [Skype For Business server 2019 のバックエンドサーバーの高可用性](../../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md)」を参照してください。
  

###  <a name="additional-server-installation-recommendations"></a>その他のサーバーインストールの推奨事項:
  
任意のフロントエンドサーバーまたはスタンドアロンの仲介サーバーに対して、Microsoft インターネットセキュリティとアクセラレータ (ISA) サーバークライアントソフトウェア、またはその他のすべての Winsock レイヤードサービスプロバイダー (LSP) ソフトウェア (サードパーティ製のファイアウォールまたはウイルス対策ネットワーク検査ソフトウェア) をインストールしないでください。 ソフトウェアがインストールされていると、メディアトラフィックのパフォーマンスの低下が見られます。
  

## <a name="active-directory"></a>Active Directory
<a name="AD"> </a>

サーバーおよびサービスの構成データの多くは Skype for Business Server 2019 Central Management store に格納されていますが、Active Directory に保存されているものもあります。
  
|**Active Directory オブジェクト**|**オブジェクトの種類**|
|:-----|:-----|
|スキーマ拡張  <br/> |ユーザー オブジェクトの拡張  <br/> |
||以前サポートされていたバージョンとの下位互換性を維持するための Skype for Business Server 2015 および Lync Server 2013 の拡張機能  <br/> |
|データ  <br/> |ユーザーの SIP URI と他のユーザー設定  <br/> |
||アプリケーションの連絡先オブジェクト (応答グループアプリケーションや会議アテンダントアプリケーションなど)  <br/> |
||下位互換性について公開されたデータ  <br/> |
||中央管理ストアのサービスコントロールポイント (SCP)  <br/> |
||Kerberos 認証のアカウント (オプションのコンピューター オブジェクト)  <br/> |
   
### <a name="os-for-domain-controllers"></a>ドメインコントローラーの OS

次のドメインコントローラーオペレーティングシステムを使用できます。
  
- Windows Server 2019

- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
Skype for business Server 2019 を展開するドメインのドメイン機能レベルと、Skype for Business Server 2019 を展開するフォレストの機能レベルは、次のいずれかである必要があります。
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
これらの環境には読み取り専用ドメインコントローラーがありますか。 書き込み可能なドメインコントローラーも利用できる限り、確認してください。
  
Skype for Business Server 2019 では、単一のラベルが付いたドメインをサポートしていないことを理解しておくことが重要です。 どのようなものですか。 Contoso というラベルが付けられたルートドメインがある場合は、問題なく動作します。 ローカルという名前のルートドメインのみを使用している場合、これは動作しないので、結果としてサポートされていません。 詳細については、[このサポート技術情報の記事に](https://support.microsoft.com/kb/300684/)記載されています。
  
Skype for Business Server 2019 では、ドメイン名の変更もサポートされていません。 実際にドメインの名前を変更する必要がある場合は、Skype for Business Server 2019 をアンインストールし、ドメイン名を変更した後、Skype for Business Server 2019 を再インストールする必要があります。
  
最後に、ロックダウンされた AD DS 環境があるドメインを取り扱うことがあります。 「展開」のドキュメントの「Skype for Business Server 2019 を、ロックダウンされた AD DS 環境に展開する方法について詳しく説明しています。
  
### <a name="ad-topologies"></a>AD トポロジ

Skype for Business Server 2019 でサポートされているトポロジは次のとおりです。
  
- 単一のドメインを含む単一のフォレスト
    
- 単一のツリーと複数のドメインを含む単一のフォレスト
    
- 複数のツリーと不整合の名前空間を含む単一のフォレスト
    
- 中央フォレスト トポロジの複数のフォレスト
    
- リソース フォレスト トポロジの複数のフォレスト
    
- Exchange Online を使用した Skype for Business リソースフォレストトポロジの複数フォレスト
    
- Skype for Business Online および Azure Active Directory Connect を使用するリソースフォレストトポロジの複数フォレスト
    
ここでは、環境内にあるトポロジを判断するのに役立つ図と説明、または Skype for Business Server 2019 をインストールする前にセットアップする必要があるものについて説明します。 簡単にするために、キーも含めています。
  
![は、Skype for Business トポロジの図で使用されるアイコンの鍵となります。](../../SfbServer/media/cc0dbc17-cf81-4b79-bf99-4614cc6828a0.png)
  
#### <a name="single-forest-with-single-domain"></a>単一のドメインを含む単一のフォレスト

![単一のドメインを含む Active Directory 単一フォレストの図](../../SfbServer/media/24921a0b-3a3e-4bad-8427-49300e2e3f7a.png)
  
これよりも簡単に表示できません。単一のドメインフォレスト、共通トポロジ。
  
#### <a name="single-forest-with-a-single-tree-and-multiple-domains"></a>単一のツリーと複数のドメインを含む単一のフォレスト

![単一のフォレスト、単一のツリー、および複数ドメインの図](../../SfbServer/media/63b9f0dd-6bac-4ba9-ae68-8be032d09dcb.png)
  
この図は1つのフォレストを示していますが、1つ以上の子ドメインも持っています (この例では3つあります)。 そのため、ユーザーが作成されるドメインは、Skype for Business Server 2019 が展開されているドメインとは異なる場合があります。 このことを気にするのはなぜですか。 Skype for Business Server のフロントエンドプールを展開するときは、そのプール内のすべてのサーバーが単一のドメイン内に存在する必要があることを覚えておくことが重要です。 Windows ユニバーサル管理者グループの Skype for Business Server のサポートを通じて、クロスドメイン管理を行うことができます。
  
上記の図では、あるドメインのユーザーが、同じドメインまたは別のドメインから、それらのユーザーが子ドメインにある場合でも、Skype for Business Server プールにアクセスできることがわかります。
  
#### <a name="single-forest-with-multiple-trees-and-disjoint-namespaces"></a>複数のツリーと不整合の名前空間を含む単一のフォレスト

![単一フォレスト、複数ツリー、および不整合の名前空間の図](../../SfbServer/media/5ede77a1-f5d2-499c-a2c8-d02f3c2f7cd7.png)
  
この図と同様のトポロジがあり、フォレストが1つあり、そのフォレスト内に複数のドメインがあり、それぞれ別の AD 名前空間を使用する場合があります。 この図では、Skype for Business Server 2019 にアクセスする3つの異なるドメインにユーザーが含まれているので、この図を使用することをお勧めします。 実線は、自分のドメインにある Skype for Business Server プールにアクセスしていることを示します。点線は、異なるツリーでプールに送られることを示しています。
  
ご覧のとおり、同じドメイン、同じツリー、または別のツリー内のユーザーは、プールに正常にアクセスすることができます。
  
#### <a name="multiple-forests-in-a-central-forest-topology"></a>中央フォレスト トポロジの複数のフォレスト

![中央フォレストトポロジ図の複数のフォレスト](../../SfbServer/media/fec40746-4254-4c84-86b9-aad4a616ea2f.png)
  
Skype for Business Server 2019 は、中央フォレストトポロジで構成された複数のフォレストをサポートします。 この点について理解していない場合は、トポロジ内の中央フォレストは、他のフォレスト内のユーザーを表すために it 内のオブジェクトを使用し、フォレスト内のユーザーのユーザーアカウントをホストします。
  
これはどのように動作しますか? ディレクトリ同期製品 (Forefront Identity Manager、FIM など) は、組織のユーザーアカウントをその存在を通して管理します。 フォレストからアカウントを作成または削除すると、その変更は中央フォレスト内の対応する連絡先に同期されます。
  
AD インフラストラクチャが適切に設定されている場合は、このトポロジに移行するのが簡単ではないかもしれませんが、既にある場合、またはフォレストインフラストラクチャを計画している場合は、この方法が適しています。 Skype for Business Server 2019 の展開を単一のフォレスト内で集中管理することができますが、ユーザーは任意のフォレスト内の他のユーザーの検索、通信、およびプレゼンスの表示ができます。 すべてのユーザー連絡先の更新は、同期ソフトウェアで自動的に処理されます。
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology"></a>Skype for Business リソースフォレストトポロジの複数のフォレスト
<a name="BKMK_multipleforestopology"> </a>

![リソースフォレストのトポロジ図における複数のフォレスト](../../SfbServer/media/41efa3b6-d9e6-47df-992b-fefcfc39a80d.png)
  
リソースフォレストトポロジもサポートされています。ここで、フォレストは、Microsoft Exchange Server および Skype for Business Server 2019 などのサーバーアプリケーションを実行するための専用になっています。 このリソースフォレストは、アクティブなユーザーオブジェクトの同期表現もホストしますが、ログオンが有効なユーザーアカウントはホストしません。 そのため、リソースフォレストは、ユーザーオブジェクトが存在する他のフォレストの共有サービス環境であり、リソースフォレストとのフォレストレベルの信頼関係があります。
  
Exchange Server は、Skype for Business Server と同じリソースフォレストまたは別のフォレストに展開できます。
  
この種類のトポロジで Skype for Business Server 2019 を展開するには、ユーザーフォレスト内の各ユーザーアカウントに対してリソースフォレストに1つの無効なユーザーオブジェクトを作成します (Microsoft Exchange Server が既に環境内にある場合は、このようにすることができます)。 その後、ユーザーアカウントをライフサイクルを通じて管理するディレクトリ同期ツール (Forefront Identity Manager、FIM など) が必要です。
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology-with-exchange-online"></a>Exchange Online を使用した Skype for Business リソースフォレストトポロジの複数フォレスト
<a name="BKMK_multipleforestopology"> </a>

このトポロジは、「 [Skype For business リソースフォレストトポロジの複数フォレスト](system-requirements.md#BKMK_multipleforestopology)」で説明されているトポロジに似ています。
  
このトポロジでは、1つ以上のユーザーフォレストがあり、Skype for Business Server は専用のリソースフォレストに展開されています。 Exchange Server は、社内の同じリソースフォレストまたは異なるフォレストに展開でき、Exchange Online とのハイブリッド用に構成されている場合や、電子メールサービスがオンプレミスのアカウントに対して Exchange Online で排他的に提供される場合があります。 このトポロジで使用できる図はありません。
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-skype-for-business-online-and-azure-active-directory-connect"></a>Skype for Business Online および Azure Active Directory Connect を使用するリソースフォレストトポロジの複数フォレスト
<a name="BKMK_multipleforestopology"> </a>

![2つの AD フォレスト、1つのユーザーフォレスト、1つのリソースフォレストを示します。 2つのフォレストには、信頼関係があります。 これらのユーザーは、Azure AD Connect を使用して Microsoft 365 と同期されます。 すべてのユーザーは、Microsoft 365 を使用して Skype for Business に対して有効になっています。](../../SfbServer/media/6d54558d-8786-4ebf-90f6-55ae3fdb5ae7.jpg)
  
このシナリオでは、社内に複数のフォレストがあり、リソースフォレストトポロジがあります。 Active Directory フォレスト間に完全な信頼関係があります。 Azure Active Directory Connect ツールは、オンプレミスのユーザーフォレストと Microsoft 365 または Office 365 間でアカウントを同期するために使用されます。
  
 また、組織には Microsoft 365 または Office 365 があり、 [Azure Active Directory Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)を使用してオンプレミスアカウントを microsoft 365 または office 365 と同期させます。 Skype for business が有効になっているユーザーは、Microsoft 365 または Office 365 と Skype for Business Online を介して有効になります。 Skype for Business Server がオンプレミスで展開されていません。
  
シングルサインオン認証は、ユーザーフォレストにある Active Directory フェデレーションサービスファームによって提供されます。
  
このシナリオでは、exchange on-premises、Exchange Online、ハイブリッド Exchange ソリューションを展開するか、または Exchange をまったく展開しないようにすることがサポートされています。 (図は Exchange オンプレミスのみを示していますが、他の Exchange ソリューションも完全にサポートされています。)
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-hybrid-skype-for-business"></a>ハイブリッド Skype for Business を使用するリソースフォレストトポロジ内の複数のフォレスト
<a name="BKMK_multipleforestopology"> </a>

このシナリオでは、1つまたは複数のオンプレミスのユーザーフォレストが存在し、Skype for Business が専用のリソースフォレストに展開され、Skype for business Online とのハイブリッドモード用に構成されています。 Exchange Server は、オンプレミスのと同じリソースフォレストまたは異なるフォレストに展開できます。また、Exchange Online とのハイブリッド用に構成されている場合もあります。 または、社内アカウントの Exchange Online のみが電子メールサービスを提供することがあります。
  
詳細については、「[ハイブリッド Skype For business の複数フォレスト環境の構成](../../SfbServer/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/configure-a-multi-forest-environment-for-hybrid.md)」を参照してください。
  
## <a name="domain-name-system-dns"></a>ドメイン ネーム システム (DNS)
<a name="DNS"> </a>

次の理由で、Skype for Business Server 2019 には DNS が必要です。
  
- DNS を使用すると、Skype for Business Server 2019 は内部サーバーまたはプールを検出できるようになり、サーバー間の通信が可能になります。
    
- DNS により、クライアントコンピューターは SIP トランザクションに使用されているフロントエンドプールまたは Standard Edition サーバーを検出できるようになります。
    
- 会議の単純な Url を、それらの会議をホストしているサーバーに関連付けます。
    
- DNS を使用すると、外部ユーザーとクライアントコンピューターは、インスタントメッセージング (IM) または会議用のエッジサーバーまたは HTTP リバースプロキシに接続できます。
    
- ログインしていない統合コミュニケーション (UC) デバイスでは、デバイス更新 web サービスを実行しているフロントエンドプールまたは Standard Edition サーバーで、更新プログラムを取得してログを送信することができます。
    
- DNS を使用すると、モバイルクライアントは、ユーザーが自分のデバイス設定で Url を手動で入力する必要がなく、web サービスリソースを自動的に検出できます。
    
- DNS 負荷分散で使用されます。
    
Skype for Business Server 2019 は、国際化ドメイン名 (Idn) をサポートしていないことに注意することが重要です。
  
また、DNS では、Skype for Business Server 2019 で使用されているサーバーに構成されているコンピューター名と同じ名前にする必要があります。 具体的には、環境内に短縮名を含めることはできません。また、トポロジビルダーの Fqdn を指定する必要があります。
  
これは、既にドメインに参加しているコンピューターでは論理のように見えますが、エッジサーバーがドメインに参加していない場合は、ドメインサフィックスを持たない短い名前の既定値を持つことができます。 そのような場合は、DNS またはエッジサーバー、あるいはその他の Skype for Business Server 2019 サーバーまたはプールのいずれかに該当しないことを確認してください。
  
必ずしも Unicode 文字またはアンダースコアは使用しないでください。 標準文字 (A ~ Z、a ~ z、0-9、ハイフン) は、外部 DNS と公開証明機関によってサポートされています (証明書の SN に Fqdn を割り当てる必要があるため、覚えておくことが重要です)。このため、最初から名前を覚えておくと、多くのトラブルが発生します。
  
ネットワークの DNS 要件の詳細については、「計画」のドキュメントの「[ネットワーク](../../SfbServer/plan-your-deployment/network-requirements/network-requirements.md)」セクションを参照してください。
  
## <a name="certificates"></a>証明書
<a name="Certs"> </a>

を展開する前に実行できる最も重要なことの1つは、証明書が順番になっていることを確認することです。 Skype for Business Server 2019 は、トランスポート層セキュリティ (TLS) および相互トランスポート層セキュリティ (MTLS) 接続用の公開キー基盤 (PKI) を必要とします。 基本的には、標準化された方法で安全に通信するために、Skype for Business Server は、証明機関 (CAs) によって発行された証明書を使用します。
  
以下に、Skype for Business Server 2019 が証明書を使用する場合のいくつかの点を示します。
  
- クライアントとサーバー間の TLS 接続
    
- サーバー間の MTLS 接続
    
- パートナーの自動 DNS 検出を使用するフェデレーション
    
- インスタント メッセージング (IM) 用のリモート ユーザー アクセス
    
- 音声ビデオ (AV) セッション、アプリケーション共有、および会議への外部ユーザーアクセス
    
- Web アプリケーションと Outlook Web Access (OWA) との会話
    
したがって、証明書の計画が必要です。 次に、証明書を要求するときに考慮する必要があるいくつかの項目の一覧を見てみましょう。
  
- すべてのサーバー証明書がサーバーの承認 (サーバー EKU) をサポートしている必要がある。
    
- すべてのサーバー証明書に CRL 配布ポイント (CDP) を含める必要がある。
    
- すべての証明書は、オペレーティングシステムでサポートされている署名アルゴリズムを使用して署名する必要があります。 Skype for Business Server 2019 は、ダイジェストサイズ (224、256、384、および512ビット) の SHA-1 および SHA-1 スイートをサポートしており、オペレーティングシステムの要件を満たしているか、それを超えています。
    
- Skype for Business Server 2019 を実行している内部サーバーでは、自動登録がサポートされています。
    
- Skype for Business Server 2019 エッジサーバーでは、自動登録がサポートされていません。
    
> [!NOTE]
> RSASSA-PSS 署名アルゴリズムを使用することはサポートされていません。その他の問題の中では、ログイン時にエラーが発生し、転送の問題が発生する可能性があります。 
  
- 1024、2048、4096の暗号化キーの長さがサポートされています。 2048以上のキーの長さは推奨されています。
    
- 既定のダイジェスト、つまりハッシュ署名は RSA です。 ECDH_P256、ECDH_P384、および ECDH_P521 の各アルゴリズムもサポートされています。
    
このことはよく考えられており、CA からの証明書を要求することにより、さまざまなレベルの安心感があります。 可能な限り簡単に計画を立てるために、次に示す追加のガイダンスが提供されます。
  
### <a name="certificates-for-your-internal-servers"></a>内部サーバーの証明書

ほとんどの内部サーバーで証明書が必要になります。多くの場合、内部 CA (ドメインにある CA) から証明書を取得します。 必要な場合は、外部 CA (インターネット上にある CA) からこれらの証明書を要求できます。 アクセス先のパブリック CA がわからない場合は、[統合コミュニケーション証明書パートナー](/SkypeForBusiness/certification/services-ssl)の一覧を確認できます。
  
また、Skype for Business Server 2019 が、Microsoft Exchange Server などの他のアプリケーションやサーバーと通信するときにも証明書が必要になります。 これは当然ですが、これらの他のアプリやサーバーがサポートされている方法で使用できる証明書である必要があります。 Skype for Business Server 2019 およびその他の Microsoft 製品は、サーバー間の認証と承認のために Open Authorization (OAuth) プロトコルをサポートしています。 これに関心がある場合は、OAuth および Skype for business Server 2019 に関する追加の計画に関する記事があります。
  
また、Skype for Business Server 2019 には、SHA-256 暗号化ハッシュ関数を使用して署名された証明書を (必要とせずに) サポートしています。 256を使用して外部アクセスをサポートするには、外部証明書を、SHA-1-256 を使用してパブリック CA から発行する必要があります。
  
わかりやすくするために、Standard Edition サーバー、フロントエンドプール、およびその他の役割の証明書要件を次の表に示します。ここでは、架空の contoso.com を使用して例を示します (環境によっては他のものを使用している可能性があります)。 これらはすべて標準の web サーバー証明書で、エクスポートできない秘密キーが含まれています。 その他の注意事項:
  
- サーバー拡張キー使用法 (EKU) は、証明書ウィザードを使用して証明書を要求するときに自動的に構成されます。
    
- 各証明書のフレンドリ名は、コンピューターストア内で一意である必要があります。
    
- 以下のサンプル名に従って、DNS で sipinternal.contoso.com または sipexternal.contoso.com を構成した場合は、証明書のサブジェクトの別名 (SAN) に追加する必要があります。
    
Standard Edition サーバーの証明書:
  
|**証明書**|**サブジェクト名/共通名**|**サブジェクト名の別名**|**例**|**コメント**|
|:-----|:-----|:-----|:-----|:-----|
|既定値  <br/> |プールの FQDN  <br/> |プールの FQDN およびサーバーの FQDN  <br/> SIP ドメインが複数あり、自動クライアント構成が有効にされている場合は、証明書ウィザードで、サポートされている各 SIP ドメイン FQDN が検出され、追加されます。  <br/> このプールがクライアントの自動ログオン サーバーであり、グループ ポリシーで厳密なドメイン ネーム システム (DNS) マッチングが必要となる場合は、sip.sipdomain のエントリ (存在するそれぞれの SIP 用) も必要となります。  <br/> |SN = se01。SAN = se01  <br/> このプールがクライアントの自動ログオン サーバーであり、グループ ポリシーで厳密な DNS マッチングが必要となる場合は、SAN=sip.contoso.com、SAN=sip.fabrikam.com も必要となります。  <br/> |Standard Edition サーバーでは、サーバーの FQDN はプールの FQDN と同じです。  <br/> このウィザードでは、セットアップ時に指定した SIP ドメインが検出され、サブジェクト名の別名に自動的に追加されます。  <br/> この証明書は、サーバー間認証に使用することもできます。  <br/> |
|内部 Web  <br/> |サーバーの FQDN  <br/> |次のうちのすべて:  <br/> •内部 web FQDN (サーバーの FQDN と同じ)  <br/> AND  <br/> •簡単な Url を満たす  <br/> •ダイヤルインの簡易 URL  <br/> •管理者の簡易 URL  <br/> または  <br/> •簡易 Url のワイルドカードエントリ  <br/> |SN = se01。SAN = se01。SAN = contoso .com。SAN = fabrikam .comSAN = ダイヤルイン。SAN = 管理  <br/> ワイルドカード証明書使用時:  <br/> SN = se01。SAN = se01。SAN = \* . contoso.com  <br/> |トポロジビルダーで内部 web FQDN を上書きすることはできません。  <br/> 複数の会議の簡易 Url がある場合は、それらすべてを San として含める必要があります。  <br/> 簡易 URL エントリにはワイルドカード エントリがサポートされます。  <br/> |
|外部 Web  <br/> |サーバーの FQDN  <br/> |次のうちのすべて:  <br/> •外部 web FQDN  <br/> AND  <br/> •ダイヤルインの簡易 URL  <br/> • SIP ドメインごとに単純な Url を満たす  <br/> または  <br/> •簡易 Url のワイルドカードエントリ  <br/> |SN = se01。SAN = webcon01。SAN = contoso .com。SAN = fabrikam .comSAN = ダイヤルイン .com  <br/> ワイルドカード証明書使用時:  <br/> SN = se01。SAN = webcon01。SAN = \* . contoso.com  <br/> |会議の簡易 URL が複数存在する場合、それらすべてをサブジェクト名の別名として含める必要があります。  <br/> 簡易 URL エントリにはワイルドカード エントリがサポートされます。  <br/> |
   
フロントエンドプール内のフロントエンドサーバーの証明書:
  
|**証明書**|**サブジェクト名/共通名**|**サブジェクト名の別名**|**例**|**コメント**|
|:-----|:-----|:-----|:-----|:-----|
|既定値  <br/> |プールの FQDN  <br/> |プールの FQDN およびサーバーの FQDN  <br/> SIP ドメインが複数あり、自動クライアント構成が有効にされている場合は、証明書ウィザードで、サポートされている各 SIP ドメイン FQDN が検出され、追加されます。  <br/> このプールがクライアントの自動ログオン サーバーであり、グループ ポリシーで厳密なドメイン ネーム システム (DNS) マッチングが必要となる場合は、sip.sipdomain のエントリ (存在するそれぞれの SIP 用) も必要となります。  <br/> |SN = eepool。SAN = eepool、SAN = ee01  <br/> このプールがクライアントの自動ログオン サーバーであり、グループ ポリシーで厳密な DNS マッチングが必要となる場合は、SAN=sip.contoso.com、SAN=sip.fabrikam.com も必要となります。  <br/> |このウィザードでは、セットアップ時に指定した SIP ドメインが検出され、サブジェクト名の別名に自動的に追加されます。  <br/> この証明書は、サーバー間認証に使用することもできます。  <br/> |
|内部 Web  <br/> |プールの FQDN  <br/> |次のうちのすべて:  <br/> •内部 web FQDN (サーバーの FQDN と同じではない)  <br/> •サーバーの FQDN  <br/> • Skype for Business プールの FQDN  <br/> AND  <br/> •簡単な Url を満たす  <br/> •ダイヤルインの簡易 URL  <br/> •管理者の簡易 URL  <br/> または  <br/> •簡易 Url のワイルドカードエントリ  <br/> |SN = ee01。SAN = ee01。SAN = contoso .com。SAN = fabrikam .comSAN = ダイヤルイン。SAN = 管理  <br/> ワイルドカード証明書使用時:  <br/> SN = ee01。SAN = ee01。SAN = \* . contoso.com  <br/> |会議の簡易 URL が複数存在する場合、それらすべてをサブジェクト名の別名として含める必要があります。  <br/> 簡易 URL エントリにはワイルドカード エントリがサポートされます。  <br/> |
|外部 Web  <br/> |プールの FQDN  <br/> |次のうちのすべて:  <br/> •外部 web FQDN  <br/> AND  <br/> •ダイヤルインの簡易 URL  <br/> •管理者の簡易 URL  <br/> または  <br/> •簡易 Url のワイルドカードエントリ  <br/> |SN = ee01。SAN = webcon01。SAN = contoso .com。SAN = fabrikam .comSAN = ダイヤルイン .com  <br/> ワイルドカード証明書使用時:  <br/> SN = ee01。SAN = webcon01。SAN = \* . contoso.com  <br/> |会議の簡易 URL が複数存在する場合、それらすべてをサブジェクト名の別名として含める必要があります。  <br/> 簡易 URL エントリにはワイルドカード エントリがサポートされます。  <br/> |
   
ディレクターの証明書:
  
|**証明書**|**サブジェクト名/共通名**|**サブジェクト名の別名**|**例**|
|:-----|:-----|:-----|:-----|
|既定値  <br/> |ディレクター プール  <br/> |ディレクターの FQDN、ディレクタープールの FQDN。  <br/> このプールがクライアントの自動ログオンサーバーであり、グループポリシーで厳密な DNS マッチングが必要な場合は、microsoft.rtc.management.xds.sipdomain のエントリも必要です (SIP ドメインごとに)。  <br/> |pool.contoso.com;SAN = dir01  <br/> このディレクター プールがクライアントの自動ログオン サーバーであり、グループ ポリシーで厳密な DNS マッチングが必要となる場合は、SAN=sip.contoso.com、SAN=sip.fabrikam.com も必要となります。  <br/> |
|内部 Web  <br/> |サーバーの FQDN  <br/> |次のうちのすべて:  <br/> •内部 web FQDN (サーバーの FQDN と同じ)  <br/> •サーバーの FQDN  <br/> • Skype for Business プールの FQDN  <br/> AND  <br/> •簡単な Url を満たす  <br/> •ダイヤルインの簡易 URL  <br/> •管理者の簡易 URL  <br/> または  <br/> •簡易 Url のワイルドカードエントリ  <br/> |SN = dir01。SAN = dir01。SAN = contoso .com。SAN = fabrikam .comSAN = ダイヤルイン。SAN = 管理  <br/> ワイルドカード証明書使用時:  <br/> SN = dir01。SAN = dir01 SAN = \* . contoso.com  <br/> |
|外部 Web  <br/> |サーバーの FQDN  <br/> |次のうちのすべて:  <br/> •外部 web FQDN  <br/> AND  <br/> • SIP ドメインごとに単純な Url を満たす  <br/> •ダイヤルインの簡易 URL  <br/> または  <br/> •簡易 Url のワイルドカードエントリ  <br/> |ディレクターの外部 web FQDN は、フロントエンドプールまたはフロントエンドサーバーとは別のものにする必要があります。  <br/> SN = dir01。SAN = directorwebcon01、SAN = 「contoso .com」SAN = fabrikam .comSAN = ダイヤルイン .com  <br/> ワイルドカード証明書使用時:  <br/> SN = dir01。SAN = directorwebcon01 SAN = \* . contoso.com  <br/> |
   
スタンドアロンの仲介サーバーの証明書:
  
|**証明書**|**サブジェクト名/共通名**|**サブジェクト名の別名**|**例**|
|:-----|:-----|:-----|:-----|
|既定値  <br/> |プールの FQDN  <br/> |プールの FQDN  <br/> プールメンバーサーバーの FQDN  <br/> |SN = medsvr-pool.contoso.net;SAN = medsvr-pool.contoso.net;SAN = medsvr01  <br/> |
   
存続可能 Branch Appliance の証明書 (特に、存続可能 Branch Appliance 2015 for Skype for Business Server 2019):
  
|**証明書**|**サブジェクト名/共通名**|**サブジェクト名の別名**|**例**|
|:-----|:-----|:-----|:-----|
|既定値  <br/> |アプライアンスの FQDN  <br/> |SIP。 \<microsoft.rtc.management.xds.sipdomain \> (SIP ドメインごとに1つのエントリのみが必要)  <br/> |SN = sba01;SAN = sip。SAN: fabrikam. .com  <br/> |
   
### <a name="certificates-for-external-user-access-edge"></a>外部ユーザーアクセスの証明書 (エッジ)

Skype for Business Server 2019 では、アクセスおよび web 会議エッジの外部インターフェイスに対する**単一のパブリック証明書**の使用と、エッジサーバー経由で提供される音声ビデオ認証サービスをサポートしています。 通常、エッジ内部インターフェイスは内部 CA から発行されたプライベート証明書を使用しますが、必要に応じて、信頼された CA からのパブリック証明書も使用できます。
  
リバースプロキシ (RP) は、パブリック証明書を使用することもできます。また、RP からクライアントへの通信を暗号化し、HTTP (より正確に HTTP 経由の TLS) を使用して、RP を内部サーバーに送信します。
  
### <a name="certificates-for-mobility"></a>モビリティ用の証明書

Mobility を展開していて、モバイルクライアントの自動検出をサポートしている場合は、モバイルクライアントからのセキュリティで保護された接続をサポートするために、証明書に追加のサブジェクト代替名エントリを含める必要があります。
  
次の証明書では、自動検出のために SAN 名が必要になります。
  
- ディレクター プール
    
- フロント エンド プール
    
- リバース プロキシ
    
詳細は以下の表に記載されています。
  
これは、計画が少し前になっていても、モビリティを展開することを伴わずに Skype for Business Server 2019 を展開した場合に、後で環境に証明書を持っているときに発生することがあります。 通常、内部 CA を経由してそれらを再発行するのは非常に簡単ですが、パブリック CA からのパブリック証明書を使用すると、もう少し上がることができます。
  
これが表示されている場合に、多数の SIP ドメインがある場合 (SAN をより高価に追加することになります)、HTTPS (既定の構成) ではなく、初期自動検出サービス要求に HTTP を使用するようにリバースプロキシを構成できます。 この詳細については、「 [Plan For Mobility](../../SfbServer/plan-your-deployment/mobility.md) 」の記事を参照してください。
  
ディレクタープールおよびフロントエンドプールの証明書の要件:
  
|**説明**|**SAN エントリ**|
|:-----|:-----|
|内部自動検出サービス URL  <br/> |SAN = lyncdiscoverinternal。 \<microsoft.rtc.management.xds.sipdomain\>  <br/> |
|外部自動検出サービス URL  <br/> |SAN = lyncdiscover。 \<microsoft.rtc.management.xds.sipdomain\>  <br/> |
   
また、SAN = を使用することもでき \* ます。 \<microsoft.rtc.management.xds.sipdomain\>
  
リバースプロキシ (パブリック CA) の証明書の要件:
  
|**説明**|**SAN エントリ**|
|:-----|:-----|
|外部自動検出サービス URL  <br/> |SAN = lyncdiscover。 \<microsoft.rtc.management.xds.sipdomain\>  <br/> |
   
この SAN は、リバースプロキシ上の SSL リスナーに割り当てられている証明書に割り当てる必要があります。
  
> [!NOTE]
> リバースプロキシリスナーには、外部 Web サービスの URL 用の San があります。 たとえば、ディレクターが展開されている場合は、SAN = skypewebextpool01 および dirwebexternal.contoso.com があります (オプション)。 
  
## <a name="file-share"></a>ファイル共有
<a name="Fileshare"> </a>

Skype for Business Server 2019 は、すべてのファイルストレージに同じファイル共有を使用できます。 次の点に注意する必要があります。
  
- ファイル共有は直接接続ストレージ (DAS) または記憶域エリアネットワーク (SAN) のどちらかに配置する必要があります。これには、分散ファイルシステム (DFS) と、ファイルストア用の独立したディスク (RAID) の冗長配列が含まれています。 Windows Server 2012 の DFS の詳細については、[この dfs ページ](https://technet.microsoft.com/library/jj127250.aspx)を参照してください。
    
- 共有クラスターには、ファイル共有を使用することをお勧めします。 既に使用している場合は、Windows Server 2012 またはそれ以降のバージョンをクラスター化する必要があります。

> [!Note]
> **最新の Windows の利点** 以前のバージョンには、すべての機能を有効にするための適切な権限がない場合があります。 クラスターアドミニストレーターを使用して、ファイル共有を作成できます。 詳細については、このサポート記事「[クラスターでファイル共有を作成する方法」を](https://support.microsoft.com/help/224967)参照してください。
    
> [!CAUTION]
> ネットワーク接続ストレージ (NAS) をファイル共有として使用することはサポートされていないため、上記のオプションのいずれかを使用してください。 このサポートの制限は、デバイスの共有ファイルシステムにアクセスする Windows Server ベースのコンピューターにファイルシステムの適応性を提供する必要がある、NAS デバイスの変数設計が原因で発生します。
  







