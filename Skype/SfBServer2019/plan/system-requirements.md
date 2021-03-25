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
description: '概要: このトピックを使用して、Skype for Business Server 2019 サーバーとドメイン インフラストラクチャを準備します。 ハードウェア、OS、データベース、ソフトウェア、すべてのシステム要件と推奨事項、および証明書 DNS、ファイル共有、Active Directory 情報は、サーバー ファームの正常なインストールと展開を確実に行うのに役立ちます。'
ms.openlocfilehash: cd2c262b6a600138e4b8f93216c24ecdf170d75c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51112123"
---
# <a name="system-requirements-for-skype-for-business-server-2019"></a>Skype for Business Server 2019 のシステム要件
 
**概要:** このトピックで Skype for Business Server 2019 をインストールする準備をします。 ここでは、ハードウェア、OS、ソフトウェア、データベース、証明書、Active Diretory、DNS、およびファイル共有について説明します。 サーバー ファームの正常なインストールと展開を確実に行うのに役立つ、すべてのシステム要件と推奨事項がここに示されています。
  
ご期待の通り、Skype for Business Server 2019 の展開を開始する前に準備を行う必要があります。 この記事では、以下の計画について説明します。
  
- [ハードウェア](system-requirements.md#Hardware)
  
- [オペレーティング システム](system-requirements.md#OS)
  
- [ソフトウェア](system-requirements.md#Software)

- [バック エンド SQL データベース](system-requirements.md#DBs)
  
- [Active Directory](system-requirements.md#AD)
  
- [ドメイン ネーム システム (DNS)](system-requirements.md#DNS)
  
- [証明書](system-requirements.md#Certs)
  
- [ファイル共有](system-requirements.md#Fileshare)

  
## <a name="hardware-for-skype-for-business-server-2019"></a>Skype for Business Server 2019 のハードウェア
<a name="Hardware"> </a>

トポロジがダウンした後 (そうしない場合は [、「Topology Basics for Skype for Business Server 2019」](../../SfbServer/plan-your-deployment/topology-basics/topology-basics.md) を参照してください)、サーバーについて考える時間です。 Skype for Business Server 2019 サーバーには、64 ビット ハードウェアが必要です。 ハードウェアに関する推奨事項を以下に示します。 これらは要件ではなく、最適なパフォーマンスに必要な要件を反映しています。 状況に応じて、これ以上必要かどうかを判断するのに役立つ容量計画のドキュメントがあります。
  
Standard Edition サーバーの推奨ハードウェア:

|**ハードウェア コンポーネント**|**推奨**|
|:-----|:-----|
|CPU  <br/> |Intel Xeon E5-2673 v3 デュアル プロセッサ、6 コア、2.4 ギガヘルツ (GHz) 以上。  <br/> Intel Itanium プロセッサは、Skype for Business Server 2019 の役割ではサポートされていません。  <br/> |
|メモリ  <br/> |32 ギガバイト (GB)。  <br/> |
|ディスク  <br/> |いずれも：  <br/> • 少なくとも 72 GB の空きディスク領域を持つ 8 台以上の 1,0000 RPM ハード ディスク ドライブ (RAID 1 と RAID 10 を使用して RAID 1 と 6 を使用するディスクの 2 つ)。  <br/> OR  <br/> • ソリッド ステート ドライブ (SSD) は、8 10000 RPM のメカニカル ディスク ドライブと同じ空き領域と同様のパフォーマンスを提供できます。  <br/> |
|ネットワーク  <br/> |1 つのデュアル ポート ネットワーク アダプター、1 Gbps 以上 (2 つのネットワーク アダプターを使用できますが、単一の MAC アドレスと 1 つの IP アドレスでチーム化する必要があります)。  <br/> デュアルまたはマルチホーム構成は、フロントエンドサーバー、バック エンド サーバー、および Standard Edition サーバーではサポートされていません。 <br/> オペレーティング システムに公開され、サーバー ハードウェアの監視と管理に使用されている限り、DRAC や ILO などの帯域外管理システムを使用できます。 このシナリオは、マルチホーム サーバーを構成するのではありません。サポートされています。  <br/> |


フロント エンド サーバーとバック エンド サーバーの推奨ハードウェア:
  
|**ハードウェア コンポーネント**|**推奨**|
|:-----|:-----|
|CPU  <br/> |Intel Xeon E5-2673 v3 デュアル プロセッサ、6 コア、2.4 ギガヘルツ (GHz) 以上。 <br/> Intel Itanium プロセッサは、Skype for Business Server 2019 の役割ではサポートされていません。  <br/> |
|メモリ  <br/> |64 ギガバイト (GB)。  <br/> |
|ディスク  <br/> |いずれも：  <br/> • 少なくとも 72 GB の空きディスク領域を持つ 8 台以上の 1,0000 RPM ハード ディスク ドライブ (RAID 1 と RAID 10 を使用して RAID 1 と 6 を使用するディスクの 2 つ)。  <br/> OR  <br/> • ソリッド ステート ドライブ (SSD) は、8 10000 RPM のメカニカル ディスク ドライブと同じ空き領域と同様のパフォーマンスを提供できます。  <br/> |
|ネットワーク  <br/> |1 つのデュアル ポート ネットワーク アダプター、1 Gbps 以上 (2 つのネットワーク アダプターを使用できますが、単一の MAC アドレスと 1 つの IP アドレスでチーム化する必要があります)。  <br/> デュアルまたはマルチホーム構成は、フロントエンドサーバー、バック エンド サーバー、および Standard Edition サーバーではサポートされていません。 <br/> オペレーティング システムに公開され、サーバー ハードウェアの監視と管理に使用されている限り、DRAC や ILO などの帯域外管理システムを使用できます。 このシナリオは、マルチホーム サーバーを構成するのではありません。サポートされています。  <br/> |
   
エッジ サーバー、スタンドアロン仲介サーバー、およびディレクターの推奨ハードウェア:
  
|**ハードウェア コンポーネント**|**推奨**|
|:-----|:-----|
|CPU  <br/> |Intel Xeon E5-2673 v3 デュアル プロセッサ、6 コア、2.4 ギガヘルツ (GHz) 以上。  <br/> Intel Itanium プロセッサは、Skype for Business Server 2019 の役割ではサポートされていません。  <br/> |
|メモリ  <br/> |32 ギガバイト。  <br/> |
|ディスク  <br/> |いずれも：  <br/> • 少なくとも 72 GB の空きディスク領域を持つ 4 台以上の 1,0000 RPM ハード ディスク ドライブ (ディスクは 2x RAID 1 構成にする必要があります)。  <br/> OR  <br/> • ソリッド ステート ドライブ (SSD) は、4 台の 10000 RPM メカニカル ディスク ドライブと同じ空き領域と同様のパフォーマンスを提供できます。  <br/> |
|ネットワーク  <br/> |1 つのデュアル ポート ネットワーク アダプター、1 Gbps 以上 (2 つのネットワーク アダプターを使用できますが、単一の MAC アドレスと 1 つの IP アドレスでチーム化する必要があります)。  <br/> ビデオ相互運用機能サーバーとディレクターでは、デュアルまたはマルチホーム構成はサポートされていません。 <br/> エッジ サーバーには、デュアル ポート ネットワーク アダプターである 2 つのネットワーク インターフェイスが必要です。1 Gbps 以上 (または 2 つのペアのネットワーク アダプター、合計 4 つのペアで、各ペアが 1 つの MAC アドレスと 1 つの IP アドレスでチーム化され、合計 2 組)。  <br/> スタンドアロン仲介サーバーでは、特定の PSTN IP アドレスの構成を許可する追加のネットワーク インターフェイス カード (NIC) のインストールがサポートされています。  <br/> |


> [!NOTE]
> サーバーの役割に関係なく、Skype for Business Server 2019 の次のハードウェア設定も推奨します (購入したハードウェアのブランドによって異なる場合があります。詳細については、製造元のドキュメントを参照してください)。
> - BIOS 構成 - NUMA から FLAT に設定する必要があります。
> - Hyperthreading を有効にする。
> - RSS キューの設定は 8 キューに設定する必要があります。

   
## <a name="operating-systems-for-skype-for-business-server-2019"></a>Skype for Business Server 2019 のオペレーティング システム
<a name="OS"> </a>

ハードウェアをインストールしたら、インストールするオペレーティング システム (OS) をインストールし、Skype for Business Server 2019 を正常に使用できる必要があります。
  
|||
|:-----|:-----|
|Windows Server 2019 <br/> |
|Windows Server 2016 <br/> ||
||
   
ここに示されているオペレーティング システム以外の機能は正しく動作しません。Skype for Business Server 2019 のインストールを試してみないで下さい。 たとえば、Server Core オプションは一覧に表示されないので、サポートされていません。

> [!NOTE]
> OS の一時アップグレードは、Lync Server 2013 ではサポートされていません。 別のプールを展開し、別の OS を使用して新しいプールにユーザーを移行する必要があります。 プール内のすべてのサーバーに同じ OS バージョンが必要です。

> [!NOTE]
> 
> Windows Server 2019 コンピューターに Windows 管理センター 2019 をインストールする場合は、リッスンするポートを求めるメッセージが表示されます。 ポート 443 を選択することもできますが、そのコンピューターに Skype for Business Server 2019 がインストールされている場合、または Skype for Business Server 2019 がインストールされている場合は、別のポート番号を選択する必要があります。
> 
>なぜこのような場合ですか? Windows Admin Center 2019 がポート 443 で実行されている場合、Skype for Business コントロール パネルを使用してサーバーに接続したり、サーバーで実行されている内部 Web サービス (アドレス帳 Web サービス、自動検出サービス、WebTicket サービスなど) に接続したりできません。  実際には、内部 Web サービスの URL に接続できない場合があります。 Windows Admin Center 2019 を Skype for Business Server 2019 のサーバーに置く必要がある場合は、別のポートを選択してください。
> 

  
## <a name="software-that-should-be-installed-before-a-skype-for-business-server-2019-deployment"></a>Skype for Business Server 2019 展開の前にインストールする必要があるソフトウェア
<a name="Software"> </a>

Skype for Business Server 2019 を実行しているサーバーに対してインストールまたは構成する必要があるものがあります。 以下に、特定のサーバー の役割に関する追加の要件を示します。

> [!IMPORTANT]
> Skype For Business 2019 は .Net Framework 4.8 をサポートしています。 
  
 **すべてのサーバー:**
  
|**ソフトウェア/役割**|**詳細**|
|:-----|:-----|
|Windows PowerShell 3.0  <br/> |すべての Skype for Business Server サーバーには、Windows PowerShell 3.0 がインストールされている必要があります。  <br/> • これは、Windows Server 2016 で既定でインストールする必要があります。<br/> |
|Microsoft .NET Framework  <br/> |WCF サービスは **、Windows** 機能としてインストールされる機能で、サーバーマネージャーの下で、最初はダウンロードは必要ない。 <br/> • この機能をインストールする場合、または既にインストール済みで確認している場合は **、HTTP ライセンス** 認証オプションも次のようにチェックしてインストールされていることを確認する必要があります。 <br/> ![[4.5 機能] の下.NET Framework HTTP ライセンス認証オプションを示すスクリーンショット。](../../SfbServer/media/a4064fa0-fa49-4474-bd98-b9a79ff68f8b.png) <br/> HTTP ライセンス認証をインストールするには、他に何かインストールする必要があるというポップアップが表示される場合は、心配しないでください。 これは通常の動作です。[OK] をクリックして先に進んでください。 このポップアップが表示されていない場合は、これらのポップアップが既にインストール済みと仮定して先に進んでください。  <br/> Microsoft .NET Frameworkは、通常、Windows Server 2016 がインストールされている場合にインストールされます。 Skype for Business Server では、Microsoft .NET Framework 4.7 または 4.8 が必要なので、おそらく更新する必要があります。 更新プログラムは、こちらから確認 [できます。](https://support.microsoft.com/help/3186497/the-net-framework-4-7-offline-installer-for-windows/)<br/> |
|Media Foundation  <br/> |Windows Server 2016 の場合、Windows Media Format ランタイムは Microsoft Media Foundation と一緒にインストールされます。  <br/> 会議に使用されるすべてのフロントエンド サーバーと Standard Edition サーバーでは、通話パーク、アナウンス、および応答グループ アプリケーションがアナウンスや音楽のために再生する Windows Media Audio (.wma) ファイルを Windows Media Format ランタイムで実行する必要があります。  <br/> |
|Windows Identity Foundation  <br/> |Skype for Business Server 2019 のサーバー間認証シナリオをサポートするには、Windows Identity Foundation 3.5 が必要です。  <br/> • Windows Server 2016 では、何もダウンロードする必要はありません。 サーバー **マネージャーを開** き、サーバー マネージャーに **移動役割と機能の追加ウィザード。** **Windows Identity Foundation 3.5 は** 、[機能] セクションの下に **一覧表示** されます。 選択されている場合は、適切です。 それ以外の場合は、それを選択し、[ **次へ] をクリック** して [インストール] **ボタンに移動** します。 <br/> |
|リモート サーバー管理ツール  <br/> |役割管理ツール: DS AD LDS AD使用する  <br/> |
   
 **フロントエンド サーバーと Standard Edition サーバーにも、次の機能が必要です。**
  
|**ソフトウェア/役割**|**詳細**|
|:-----|:-----|
|インターネット インフォメーション サービス (IIS)  <br/> |IIS は、すべてのフロント エンド サーバーとすべての Standard Edition サーバーで必要とされ、次のモジュールが選択されています。  <br/> • 一般的な HTTP 機能: 既定のドキュメント、HTTP エラー、静的コンテンツ  <br/> • 正常性と診断: HTTP ログ、ログ ツール、トレース  <br/> • パフォーマンス: 静的コンテンツ圧縮、動的コンテンツ圧縮  <br/> • セキュリティ: 要求フィルター、クライアント証明書マッピング認証、Windows 認証  <br/> • アプリケーション開発: .NET 拡張機能 3.5、.NET 拡張機能 4.5、ASP.NET 3.5、ASP.NET 4.5、ISAPI 拡張機能、ISAPI フィルター  <br/> • 管理ツール: IIS 管理コンソール、IIS 管理スクリプト、およびツール  <br/> 匿名アクセスも必要ですが、IIS をインストールするときにそれを取得します。そのため、一覧で選択する場所が用意されません。  <br/> |
|Windows Media フォーマット ランタイム  <br/> | Windows Server 2016 の場合は、サーバー マネージャーに **Media Foundation** 機能をインストールする **必要があります**。 これを行わずに Skype for Business Server 2019 のインストールを実際に開始できますが、Skype for Business Server 2019 のインストールが続行される前に、インストールしてサーバーを再起動するように求めるメッセージが表示されます。 前もって行う方が良いです。 <br/> |
|Silverlight  <br/> |Silverlight の最新バージョンは、こちらからインストール [できます](https://www.microsoft.com/silverlight/)。  <br/> |
   
これを自動化するために実行できる PowerShell スクリプトの例を次に示します。
  
```PowerShell
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Windows-Identity-Foundation, Server-Media-Foundation, Telnet-Client, BITS, ManagementOData, Web-Mgmt-Console, Web-Metabase, Web-Lgcy-Mgmt-Console, Web-Lgcy-Scripting, Web-WMI, Web-Scripting-Tools, Web-Mgmt-Service
```

 **ディレクターには、次の情報も必要です。**
  
IIS で、次のモジュールが選択されています。
  
- HTTP 共通機能
    
  - 既定のドキュメント
    
  - HTTP エラー
    
  - 静的コンテンツ
    
- 状態と診断
    
  - HTTP ログ
    
  - ログ ツール
    
  - トレース
    
- パフォーマンス
    
  - 静的なコンテンツの圧縮
    
- セキュリティ
    
  - 要求のフィルタリング
    
  - クライアント証明書マッピング認証
    
  - Windows 認証
    
- アプリケーション開発
    
  - .NET 拡張 3.5
    
  - .NET 拡張機能 4.5
    
  - ASP.NET 3.5
    
  - ASP.NET 4.5
    
  - ISAPI 拡張機能
    
  - ISAPI フィルター
    
(疑問に思う場合は、フロント エンド サーバーと Standard Edition サーバーと同じモジュールセットであり、動的コンテンツ圧縮および管理ツールは残されています)。
  
また、これには以下の PowerShell コードもあります。
  
```PowerShell
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, Telnet-Client
```

## <a name="back-end-databases-that-will-work-with-skype-for-business-server-2019"></a>Skype for Business Server 2019 で動作するバック エンド データベース
<a name="DBs"> </a>

Skype for Business Server 2019 Standard Edition をインストールする場合は、2016 Express (64 ビット 版) SQL Server 2016 年版をインストールする必要があります。

Skype for Business Server 2019 Enterprise Edition では、以下に示す完全な SQL Server が必要になります (64 ビット版のみ、32 ビット エディションは使用しません)。
  
||||
|:-----|:-----|:-----|
|Microsoft SQL Server 2019 (64 ビット 版) で、最新の更新プログラムを使用して実行する必要があります。  <br/> |Microsoft SQL Server 2017 (64 ビット 版)、最新の更新プログラムを使用して実行する必要があります。  <br/> |
Microsoft SQL Server 2016 (64 ビット 版)、最新の更新プログラムを使用して実行する必要があります。|
 |

ここで使用するエディションSQL Server表示しない場合は、使用することはできません。
  
> [!NOTE]
> また、監視サーバーの役割SQL Serverレポート サービスをインストールする必要があります。 
  
### <a name="sql-clustering-and-sql-always-on"></a>SQLクラスタリング、および Always On SQLの設定

SQL Skype for Business Server 2019 でのクラスタリングがサポートされています。 クラスター化をセットアップするSQL、この設定は[クラスター化] でSQL Server。
  
サポートされているクラスターのアクティブ/パッシブ構成SQL確認してください。 パッシブ ノードを他のインスタンスと共有SQLします。
  
フェールオーバー クラスタリングには、次の機能を使用できます。
  
2 ノード:
  
- Microsoft SQL Server 2019 Standard (64 ビット 版) を使用し、最新のサービス パックを使用して実行することをお勧めします。
- Microsoft SQL Server 2017 Standard (64 ビット 版) を使用し、最新のサービス パックを使用して実行することをお勧めします。
- Microsoft SQL Server 2016 Standard (64 ビット 版) を使用し、最新のサービス パックを使用して実行することをお勧めします。

16 ノード:
  
- Microsoft SQL Server 2019 Enterprise (64 ビット 版) を使用し、最新のサービス パックを使用して実行することをお勧めします。
- Microsoft SQL Server 2017 Enterprise (64 ビット 版) を使用し、最新のサービス パックを使用して実行することをお勧めします。
- Microsoft SQL Server 2016 Enterprise (64 ビット 版) を使用し、最新のサービス パックを使用して実行することをお勧めします。

SQL常時オンがサポートされています。詳細については [、「Skype for Business Server 2019](../../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md)のバック エンド サーバー高可用性」を参照してください。
  

###  <a name="additional-server-installation-recommendations"></a>サーバーのインストールに関するその他の推奨事項:
  
Microsoft Internet Security and Acceleration (ISA) Server クライアント ソフトウェア、または他の Winsock Layered Service Providers (LSP) ソフトウェア (サード パーティ製のファイアウォールやウイルス対策ネットワーク検査ソフトウェアがここに含まれる) を、フロントエンド サーバーまたはスタンドアロン仲介サーバーにインストールしなけらばならな。 そのソフトウェアをインストールすると、メディア トラフィックのパフォーマンスが低下しています。
  

## <a name="active-directory"></a>Active Directory
<a name="AD"> </a>

サーバーとサービスの構成データの多くが Skype for Business Server 2019 サーバーの全体管理ストアに格納されているが、Active Directory には以下の情報が保存されています。
  
|**Active Directory オブジェクト**|**オブジェクトの種類**|
|:-----|:-----|
|スキーマ拡張  <br/> |ユーザー オブジェクトの拡張  <br/> |
||以前にサポートされているバージョンとの下位互換性を維持するための Skype for Business Server 2015 および Lync Server 2013 の拡張機能  <br/> |
|データ  <br/> |ユーザーの SIP URI と他のユーザー設定  <br/> |
||アプリケーションの連絡先オブジェクト (応答グループ アプリケーションや会議応答アプリケーションなど)  <br/> |
||下位互換性について公開されたデータ  <br/> |
||サーバーの全体管理ストアのサービス コントロール ポイント (SCP)  <br/> |
||Kerberos 認証のアカウント (オプションのコンピューター オブジェクト)  <br/> |
   
### <a name="os-for-domain-controllers"></a>ドメイン コントローラー用 OS

次のドメイン コントローラー オペレーティング システムを使用できます。
  
- Windows Server 2019

- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
Skype for Business Server 2019 を展開するドメインのドメイン機能レベルと、Skype for Business Server 2019 を展開するフォレストのフォレスト機能レベルは、次の 1 つである必要があります。
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
これらの環境で読み取り専用ドメイン コントローラーを使用できますか? 確かに、書き込み可能なドメイン コントローラーが利用可能である限り。
  
Skype for Business Server 2019 では、単一ラベルドメインがサポートされません。 それらは何ですか? contoso.local というラベルのルート ドメインがある場合は、問題ありません。 ローカルという名前のルート ドメインがある場合、そのドメインは機能し、その結果サポートされません。 この点についてもう少し詳しくは、この [サポート技術情報の記事で書かれています](https://support.microsoft.com/kb/300684/)。
  
Skype for Business Server 2019 では、ドメイン名の変更もサポートされていません。 実際にドメインの名前を変更する必要がある場合は、Skype for Business Server 2019 をアンインストールし、ドメイン名の変更を行い、Skype for Business Server 2019 を再インストールする必要があります。
  
最後に、DS 環境でロックダウンされたドメインを処理AD、問題は問題ない場合があります。 Skype for Business Server 2019 をロックダウンされた DS 環境に展開する方法の詳細については、「展開AD」を参照してください。
  
### <a name="ad-topologies"></a>AD トポロジ

Skype for Business Server 2019 でサポートされるトポロジは次のとおりです。
  
- 単一のドメインを含む単一のフォレスト
    
- 単一のツリーと複数のドメインを含む単一のフォレスト
    
- 複数のツリーと不整合の名前空間を含む単一のフォレスト
    
- 中央フォレスト トポロジの複数のフォレスト
    
- リソース フォレスト トポロジの複数のフォレスト
    
- Exchange Online を使用した Skype for Business リソース フォレスト トポロジ内の複数のフォレスト
    
- Skype for Business Online と Azure Active Directory Connect を使用したリソース フォレスト トポロジ内の複数のフォレスト
    
環境に含めるトポロジや、Skype for Business Server 2019 をインストールする前にセットアップする必要があるトポロジを判断するのに役立つ図と説明があります。 簡単に行う場合は、キーも含めて次の操作を行います。
  
![これは、Skype for Business トポロジ図で使用されるアイコンのキーです。](../../SfbServer/media/cc0dbc17-cf81-4b79-bf99-4614cc6828a0.png)
  
#### <a name="single-forest-with-single-domain"></a>単一のドメインを含む単一のフォレスト

![1 つのドメインを持つ Active Directory 単一フォレストの図](../../SfbServer/media/24921a0b-3a3e-4bad-8427-49300e2e3f7a.png)
  
これより簡単ではありません。これは単一のドメイン フォレスト、一般的なトポロジです。
  
#### <a name="single-forest-with-a-single-tree-and-multiple-domains"></a>単一のツリーと複数のドメインを含む単一のフォレスト

![単一のフォレスト、単一ツリー、および mutiple ドメインの図](../../SfbServer/media/63b9f0dd-6bac-4ba9-ae68-8be032d09dcb.png)
  
この図は、もう一度 1 つのフォレストを示していますが、1 つ以上の子ドメインも含みます (この特定の例には 3 つがあります)。 そのため、ユーザーが作成するドメインは、Skype for Business Server 2019 が展開されているドメインとは異なる場合があります。 なぜこのことを心配するのですか? Skype for Business Server フロントエンド プールを展開する場合は、そのプール内のすべてのサーバーが 1 つのドメイン内にある必要があります。 Windows ユニバーサル管理者グループの Skype for Business Server サポートを使用して、ドメイン間の管理を行います。
  
上の図では、1 つのドメインのユーザーが、同じドメインまたは異なるドメインの Skype for Business Server プールにアクセスできるのを確認できます 。これらのユーザーが子ドメインに存在する場合でも、
  
#### <a name="single-forest-with-multiple-trees-and-disjoint-namespaces"></a>複数のツリーと不整合の名前空間を含む単一のフォレスト

![単一のフォレスト、複数のツリー、および不結合の名前空間の図](../../SfbServer/media/5ede77a1-f5d2-499c-a2c8-d02f3c2f7cd7.png)
  
1 つのフォレストがあるが、そのフォレスト内には複数のドメインが含まれるこの図と同様のトポロジが用意されている場合があります。その中には複数のドメインが含ADがあります。 この例では、Skype for Business Server 2019 にアクセスする 3 つの異なるドメインのユーザーが含まれるため、この図は優れた図です。 実線は、自分のドメイン内の Skype for Business Server プールにアクセスしているのに対し、破線は別のツリー内のプールに移動する場合を示します。
  
ご覧のように、同じドメイン、同じツリー、または別のツリーのユーザーは、プールに正常にアクセスできます。
  
#### <a name="multiple-forests-in-a-central-forest-topology"></a>中央フォレスト トポロジの複数のフォレスト

![中央フォレスト トポロジ図の複数のフォレスト](../../SfbServer/media/fec40746-4254-4c84-86b9-aad4a616ea2f.png)
  
Skype for Business Server 2019 は、中央フォレスト トポロジで構成された複数のフォレストをサポートします。 それが自分の持っているものか分からない場合、トポロジの中央フォレストは、その中のオブジェクトを使用して他のフォレストのユーザーを表し、フォレスト内のすべてのユーザーのユーザー アカウントをホストします。
  
これはどのように機能しますか? ディレクトリ同期製品 (Forefront Identity Manager、FIM など) は、組織のユーザー アカウントをその存在全体にわたって管理します。 アカウントがフォレストから作成または削除されると、その変更は中央フォレストの対応する連絡先に同期されます。
  
明らかに、AD インフラストラクチャが配置されている場合は、このトポロジへの移行は容易ではない可能性がありますが、既に存在している場合や、フォレスト インフラストラクチャを計画している場合は、この方法をお選びください。 1 つのフォレスト内で Skype for Business Server 2019 の展開を一元化し、ユーザーは任意のフォレスト内の他のユーザーの存在を検索、通信、および表示できます。 すべてのユーザー連絡先の更新は、同期ソフトウェアで自動的に処理されます。
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology"></a>Skype for Business リソース フォレスト トポロジ内の複数のフォレスト
<a name="BKMK_multipleforestopology"> </a>

![リソース フォレスト トポロジ図内の複数のフォレスト](../../SfbServer/media/41efa3b6-d9e6-47df-992b-fefcfc39a80d.png)
  
リソース フォレスト トポロジもサポートされています。フォレストは、サーバー アプリケーションの実行専用の場所です (たとえば、Microsoft Exchange Server Skype for Business Server 2019)。 このリソース フォレストは、アクティブなユーザー オブジェクトの同期表現もホストしますが、ログオンが有効なユーザー アカウントはありません。 したがって、リソース フォレストは、ユーザー オブジェクトが存在する他のフォレストの共有サービス環境であり、リソース フォレストとのフォレスト レベルの信頼関係を持ちます。
  
このExchange Server Skype for Business Server と同じリソース フォレストまたは別のフォレストに展開できます。
  
この種類のトポロジで Skype for Business Server 2019 を展開するには、ユーザー フォレスト内のユーザー アカウントごとに、リソース フォレストに無効なユーザー オブジェクトを 1 つ作成します (Microsoft Exchange Server が環境内に既に存在する場合は、これを行う可能性があります)。 次に、ユーザー アカウントのライフサイクルを通じてユーザー アカウントを管理するには、ディレクトリ同期ツール (Forefront Identity Manager や FIM など) が必要です。
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology-with-exchange-online"></a>Exchange Online を使用した Skype for Business リソース フォレスト トポロジ内の複数のフォレスト
<a name="BKMK_multipleforestopology"> </a>

このトポロジは、「Skype for Business リソース フォレスト トポロジの複数のフォレスト」で説明されている [トポロジに似ています](system-requirements.md#BKMK_multipleforestopology)。
  
このトポロジでは、1 つ以上のユーザー フォレストが作成され、Skype for Business Server が専用のリソース フォレストに展開されます。 Exchange Server同じリソース フォレストまたは別のフォレストにオンプレミスで展開し、Exchange Online とのハイブリッド用に構成したり、Exchange Online がオンプレミス アカウント用に電子メール サービスを提供したりすることもできます。 このトポロジで使用できる図はありません。
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-skype-for-business-online-and-azure-active-directory-connect"></a>Skype for Business Online と Azure Active Directory Connect を使用したリソース フォレスト トポロジ内の複数のフォレスト
<a name="BKMK_multipleforestopology"> </a>

![2 つのAD、1 つのユーザー フォレストと 1 つのリソース フォレストを表示します。 2 つのフォレストには信頼関係があります。 これらは Azure AD Connect を使用して Microsoft 365 と同期されます。 すべてのユーザーは、Microsoft 365 経由で Skype for Business に対して有効になっています。](../../SfbServer/media/6d54558d-8786-4ebf-90f6-55ae3fdb5ae7.jpg)
  
このシナリオでは、リソース フォレスト トポロジを持つ複数のフォレストがオンプレミスにあります。 Active Directory フォレスト間には完全な信頼関係があります。 Azure Active Directory Connect ツールを使用して、オンプレミスのユーザー フォレストと Microsoft 365 または Microsoft 365 または 365 Office同期します。
  
 また、組織は Microsoft 365 または Office 365 を持ち [、Azure Active Directory Connect](/azure/active-directory/connect/active-directory-aadconnect) を使用してオンプレミス アカウントを Microsoft 365 または Office 365 と同期します。 Skype for Business が有効になっているユーザーは、Microsoft 365 または Office Skype for Business Online を介して有効になります。 Skype for Business Server はオンプレミスで展開されません。
  
シングル サインオン認証は、ユーザー フォレスト内にある Active Directory フェデレーション サービス ファームによって提供されます。
  
このシナリオでは、Exchange オンプレミス、Exchange Online、ハイブリッド Exchange ソリューションの展開、または Exchange が展開されていない場合にサポートされます。 (この図は Exchange オンプレミスのみを示していますが、他の Exchange ソリューションも完全にサポートされています)。
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-hybrid-skype-for-business"></a>ハイブリッド Skype for Business を使用したリソース フォレスト トポロジ内の複数のフォレスト
<a name="BKMK_multipleforestopology"> </a>

このシナリオでは、1 つ以上のオンプレミス ユーザー フォレストが作成され、Skype for Business は専用のリソース フォレストに展開され、Skype for Business Online とのハイブリッド モード用に構成されます。 Exchange Server同じリソース フォレストまたは別のフォレストにオンプレミスで展開し、Exchange Online とのハイブリッド用に構成できます。 または、電子メール サービスは、オンプレミス アカウント用に Exchange Online によって排他的に提供される場合があります。
  
詳細については [、「Configure a multi-forest environment for hybrid Skype for Business」を参照してください](../../SfbHybrid/hybrid/configure-a-multi-forest-environment-for-hybrid.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)。
  
## <a name="domain-name-system-dns"></a>ドメイン ネーム システム (DNS)
<a name="DNS"> </a>

Skype for Business Server 2019 では、次の理由により DNS が必要です。
  
- DNS を使用すると、Skype for Business Server 2019 は内部サーバーまたはプールを検出でき、サーバー間通信が可能になります。
    
- DNS を使用すると、クライアント コンピューターは SIP トランザクションに使用されているフロントエンド プールまたは Standard Edition サーバーを検出できます。
    
- 会議の単純な URL を、それらの会議をホストするサーバーに関連付ける。
    
- DNS を使用すると、外部ユーザーとクライアント コンピューターは、インスタント メッセージング (IM) または会議のためにエッジ サーバーまたは HTTP リバース プロキシに接続できます。
    
- これにより、ログインしていない統合コミュニケーション (UC) デバイスが、Device Update Web サービスを実行しているフロントエンド プールまたは Standard Edition サーバーを検出して、更新プログラムを取得してログを送信できます。
    
- DNS を使用すると、モバイル クライアントは、ユーザーがデバイス設定で URL を手動で入力する必要なしに、Web サービス リソースを自動的に検出できます。
    
- DNS 負荷分散で使用されます。
    
Skype for Business Server 2019 は国際化ドメイン名 (IDN) をサポートしません。
  
また、DNS の名前は、Skype for Business Server 2019 で使用されている任意のサーバーで構成されているコンピューター名と同一である点に注意することが非常に重要です。 具体的には、環境内にショートネームを含めず、トポロジ ビルダー用の FQDN が必要です。
  
これは、既にドメインに参加している任意のコンピューターに対して論理的なようですが、ドメインに参加していないエッジ サーバーがある場合は、既定の短い名前で、ドメイン サフィックスはありません。 DNS またはエッジ サーバー、または Skype for Business Server 2019 サーバーまたはプールのどちらでも、そうでなくしてください。
  
Unicode 文字やアンダースコアは使用しません。 標準文字 (A-Z、a-z、0-9、ハイフン) は、外部 DNS とパブリックの証明書機関でサポートされています (証明書内の SN に FQDN を割り当てる必要があります。覚えておく必要があります)。そのため、最初からこの名前を付けて名前を付けても、多くの問題が発生します。
  
ネットワークの DNS 要件の詳細については、「計画」のドキュメントの「 [ネットワーク](../../SfbServer/plan-your-deployment/network-requirements/network-requirements.md) 」セクションを参照してください。
  
## <a name="certificates"></a>証明書
<a name="Certs"> </a>

展開する前に実行できる最も重要な点の 1 つは、証明書の順序を確認する方法です。 Skype for Business Server 2019 には、トランスポート層セキュリティ (TLS) および相互トランスポート層セキュリティ (MTLS) 接続用の公開キー基盤 (PKI) が必要です。 基本的に、標準化された方法で安全に通信するために、Skype for Business Server は認証局 (CA) によって発行された証明書を使用します。
  
次に、Skype for Business Server 2019 で証明書を使用する機能の一部を示します。
  
- クライアントとサーバー間の TLS 接続
    
- サーバー間の MTLS 接続
    
- パートナーの自動 DNS 検出を使用するフェデレーション
    
- インスタント メッセージング (IM) 用のリモート ユーザー アクセス
    
- 音声/ビデオ (AV) セッション、アプリケーション共有、および会議への外部ユーザー アクセス
    
- Web アプリケーションと Outlook Web Access (OWA) の会話
    
したがって、証明書の計画は必ず必要です。 次に、証明書を要求する際に注意する必要があるいくつかの一覧を見てみます。
  
- すべてのサーバー証明書がサーバーの承認 (サーバー EKU) をサポートしている必要がある。
    
- すべてのサーバー証明書に CRL 配布ポイント (CDP) を含める必要がある。
    
- すべての証明書は、オペレーティング システムでサポートされている署名アルゴリズムを使用して署名する必要があります。 Skype for Business Server 2019 は、SHA-1 および SHA-2 スイートのダイジェスト サイズ (224、256、384、512 ビット) をサポートし、オペレーティング システム要件を満たすか、または超えています。
    
- 自動登録は、Skype for Business Server 2019 を実行している内部サーバーでサポートされています。
    
- 自動登録は、Skype for Business Server 2019 エッジ サーバーではサポートされていません。
    
> [!NOTE]
> RSASSA-PSS 署名アルゴリズムの使用はサポートされていないため、ログインおよび通話転送の問題などのエラーにつながる可能性があります。 
  
- 1024、2048、および 4096 の暗号化キーの長さがサポートされています。 キーの長さは 2048 以上をお勧めします。
    
- 既定のダイジェスト (ハッシュ署名) アルゴリズムは RSA です。 またECDH_P256、ECDH_P384、ECDH_P521アルゴリズムもサポートされています。
    
これは多くのことを考えるべきであり、CA から証明書を要求するさまざまな快適さレベルがあります。 計画を可能な限り簡単に行う方法については、以下のガイダンスをご覧ください。
  
### <a name="certificates-for-your-internal-servers"></a>内部サーバーの証明書

ほとんどの内部サーバーに対して証明書が必要になります。多くの場合、内部 CA (ドメインにある CA) から証明書を取得します。 必要に応じて、外部 CA (インターネット上にある証明書) からこれらの証明書を要求できます。 どのパブリック CA にアクセスする必要があるのか疑問に思う場合は、ユニファイド コミュニケーション証明書パートナーの一覧 [を確認](../../SfbPartnerCertification/certification/services-ssl.md) できます。
  
また、Skype for Business Server 2019 が他のアプリケーションやサーバー (Skype for Business Server 2019 など) と通信するときにも証明書が必要Microsoft Exchange Server。 これは明らかに、これらの他のアプリやサーバーがサポートされている方法で使用できる証明書である必要があります。 Skype for Business Server 2019 および他の Microsoft 製品は、サーバー間の認証と承認のためのオープン承認 (OAuth) プロトコルをサポートしています。 この点に興味がある場合は、OAuth と Skype for Business Server 2019 の追加の計画に関する記事があります。
  
Skype for Business Server 2019 には、SHA-256 暗号化ハッシュ関数を使用して署名された (不要な) 証明書のサポートも含まれています。 SHA-256 を使用して外部アクセスをサポートするには、SHA-256 を使用してパブリック CA によって外部証明書を発行する必要があります。
  
わかりやすくするために、Standard Edition サーバー、フロントエンド プール、その他の役割の証明書要件を次の表に入れ、架空の contoso.com を例として使用します (おそらく、環境に別の機能を使用している可能性があります)。 これらはすべて標準の Web サーバー証明書で、プライベート キーはエクスポートできません。 次の点に注意する必要があります。
  
- 証明書ウィザードを使用して証明書を要求すると、サーバー拡張キー使用法 (EKU) が自動的に構成されます。
    
- 各証明書の表示名は、コンピューター ストアで一意である必要があります。
    
- 以下のサンプル名に従って、DNS で sipinternal.contoso.com または sipexternal.contoso.com を構成している場合は、証明書のサブジェクト代替名 (SAN) に追加する必要があります。
    
Standard Edition サーバーの証明書:
  
|**証明書**|**サブジェクト名/共通名**|**サブジェクト名の別名**|**例**|**コメント**|
|:-----|:-----|:-----|:-----|:-----|
|既定値  <br/> |プールの FQDN  <br/> |プールの FQDN とサーバーの FQDN  <br/> SIP ドメインが複数あり、自動クライアント構成が有効にされている場合は、証明書ウィザードで、サポートされている各 SIP ドメイン FQDN が検出され、追加されます。  <br/> このプールがクライアントの自動ログオン サーバーであり、グループ ポリシーで厳密なドメイン ネーム システム (DNS) マッチングが必要となる場合は、sip.sipdomain のエントリ (存在するそれぞれの SIP 用) も必要となります。  <br/> |SN=se01.contoso.com;SAN=se01.contoso.com  <br/> このプールがクライアントの自動ログオン サーバーであり、グループ ポリシーで厳密な DNS マッチングが必要となる場合は、SAN=sip.contoso.com、SAN=sip.fabrikam.com も必要となります。  <br/> |Standard Edition サーバーでは、サーバーの FQDN はプール FQDN と同じです。  <br/> このウィザードでは、セットアップ時に指定した SIP ドメインが検出され、サブジェクト名の別名に自動的に追加されます。  <br/> この証明書は、サーバー間認証にも使用できます。  <br/> |
|内部 Web  <br/> |サーバーの FQDN  <br/> |次のうちのすべて:  <br/> • 内部 Web FQDN (サーバーの FQDN と同じです)  <br/> AND  <br/> • 単純な URL を満たす  <br/> • ダイヤルインの簡単な URL  <br/> • 管理者の簡単な URL  <br/> OR  <br/> • 単純な URL のワイルドカード エントリ  <br/> |SN=se01.contoso.com;SAN=se01.contoso.com;SAN=meet.contoso.com;SAN=meet.fabrikam.com;SAN=dialin.contoso.com;SAN=admin.contoso.com  <br/> ワイルドカード証明書使用時:  <br/> SN=se01.contoso.com;SAN=se01.contoso.com;SAN= \* .contoso.com  <br/> |トポロジ ビルダーで内部 Web FQDN を上書きできない。  <br/> 複数の Meet 単純な URL がある場合は、すべての URL を SAN として含める必要があります。  <br/> 簡易 URL エントリにはワイルドカード エントリがサポートされます。  <br/> |
|外部 Web  <br/> |サーバーの FQDN  <br/> |次のうちのすべて:  <br/> • 外部 Web FQDN  <br/> AND  <br/> • ダイヤルインの簡単な URL  <br/> • SIP ドメインごとの単純な URL を満たす  <br/> OR  <br/> • 単純な URL のワイルドカード エントリ  <br/> |SN=se01.contoso.com;SAN=webcon01.contoso.com;SAN=meet.contoso.com;SAN=meet.fabrikam.com;SAN=dialin.contoso.com  <br/> ワイルドカード証明書使用時:  <br/> SN=se01.contoso.com;SAN=webcon01.contoso.com;SAN= \* .contoso.com  <br/> |会議の簡易 URL が複数存在する場合、それらすべてをサブジェクト名の別名として含める必要があります。  <br/> 簡易 URL エントリにはワイルドカード エントリがサポートされます。  <br/> |
   
フロントエンド プール内のフロントエンド サーバーの証明書:
  
|**証明書**|**サブジェクト名/共通名**|**サブジェクト名の別名**|**例**|**コメント**|
|:-----|:-----|:-----|:-----|:-----|
|既定値  <br/> |プールの FQDN  <br/> |プールの FQDN とサーバーの FQDN  <br/> SIP ドメインが複数あり、自動クライアント構成が有効にされている場合は、証明書ウィザードで、サポートされている各 SIP ドメイン FQDN が検出され、追加されます。  <br/> このプールがクライアントの自動ログオン サーバーであり、グループ ポリシーで厳密なドメイン ネーム システム (DNS) マッチングが必要となる場合は、sip.sipdomain のエントリ (存在するそれぞれの SIP 用) も必要となります。  <br/> |SN=eepool.contoso.com;SAN=eepool.contoso.com;SAN=ee01.contoso.com  <br/> このプールがクライアントの自動ログオン サーバーであり、グループ ポリシーで厳密な DNS マッチングが必要となる場合は、SAN=sip.contoso.com、SAN=sip.fabrikam.com も必要となります。  <br/> |このウィザードでは、セットアップ時に指定した SIP ドメインが検出され、サブジェクト名の別名に自動的に追加されます。  <br/> この証明書は、サーバー間認証にも使用できます。  <br/> |
|内部 Web  <br/> |プールの FQDN  <br/> |次のうちのすべて:  <br/> • 内部 Web FQDN (サーバーの FQDN と同じではない)  <br/> • サーバー FQDN  <br/> • Skype for Business プール FQDN  <br/> AND  <br/> • 単純な URL を満たす  <br/> • ダイヤルインの簡単な URL  <br/> • 管理者の簡単な URL  <br/> OR  <br/> • 単純な URL のワイルドカード エントリ  <br/> |SN=ee01.contoso.com;SAN=ee01.contoso.com;SAN=meet.contoso.com;SAN=meet.fabrikam.com;SAN=dialin.contoso.com;SAN=admin.contoso.com  <br/> ワイルドカード証明書使用時:  <br/> SN=ee01.contoso.com;SAN=ee01.contoso.com;SAN= \* .contoso.com  <br/> |会議の簡易 URL が複数存在する場合、それらすべてをサブジェクト名の別名として含める必要があります。  <br/> 簡易 URL エントリにはワイルドカード エントリがサポートされます。  <br/> |
|外部 Web  <br/> |プールの FQDN  <br/> |次のうちのすべて:  <br/> • 外部 Web FQDN  <br/> AND  <br/> • ダイヤルインの簡単な URL  <br/> • 管理者の簡単な URL  <br/> OR  <br/> • 単純な URL のワイルドカード エントリ  <br/> |SN=ee01.contoso.com;SAN=webcon01.contoso.com;SAN=meet.contoso.com;SAN=meet.fabrikam.com;SAN=dialin.contoso.com  <br/> ワイルドカード証明書使用時:  <br/> SN=ee01.contoso.com;SAN=webcon01.contoso.com;SAN= \* .contoso.com  <br/> |会議の簡易 URL が複数存在する場合、それらすべてをサブジェクト名の別名として含める必要があります。  <br/> 簡易 URL エントリにはワイルドカード エントリがサポートされます。  <br/> |
   
ディレクターの証明書:
  
|**証明書**|**サブジェクト名/共通名**|**サブジェクト名の別名**|**例**|
|:-----|:-----|:-----|:-----|
|既定値  <br/> |ディレクター プール  <br/> |ディレクター の FQDN、ディレクター プールの FQDN。  <br/> このプールがクライアントの自動ログオン サーバーであり、グループ ポリシーで厳密な DNS 一致が必要な場合は、sip.sipdomain (SIP ドメインごとに) のエントリも必要です。  <br/> |pool.contoso.com;SAN=dir01.contoso.com  <br/> このディレクター プールがクライアントの自動ログオン サーバーであり、グループ ポリシーで厳密な DNS マッチングが必要となる場合は、SAN=sip.contoso.com、SAN=sip.fabrikam.com も必要となります。  <br/> |
|内部 Web  <br/> |サーバーの FQDN  <br/> |次のうちのすべて:  <br/> • 内部 Web FQDN (サーバーの FQDN と同じです)  <br/> • サーバー FQDN  <br/> • Skype for Business プール FQDN  <br/> AND  <br/> • 単純な URL を満たす  <br/> • ダイヤルインの簡単な URL  <br/> • 管理者の簡単な URL  <br/> OR  <br/> • 単純な URL のワイルドカード エントリ  <br/> |SN=dir01.contoso.com;SAN=dir01.contoso.com;SAN=meet.contoso.com;SAN=meet.fabrikam.com;SAN=dialin.contoso.com;SAN=admin.contoso.com  <br/> ワイルドカード証明書使用時:  <br/> SN=dir01.contoso.com;SAN=dir01.contoso.com SAN= \* .contoso.com  <br/> |
|外部 Web  <br/> |サーバーの FQDN  <br/> |次のうちのすべて:  <br/> • 外部 Web FQDN  <br/> AND  <br/> • SIP ドメインごとの単純な URL を満たす  <br/> • ダイヤルインの簡単な URL  <br/> OR  <br/> • 単純な URL のワイルドカード エントリ  <br/> |ディレクターの外部 Web FQDN は、フロント エンド プールまたはフロント エンド サーバーとは異なる必要があります。  <br/> SN=dir01.contoso.com;SAN=directorwebcon01.contoso.com SAN=meet.contoso.com;SAN=meet.fabrikam.com;SAN=dialin.contoso.com  <br/> ワイルドカード証明書使用時:  <br/> SN=dir01.contoso.com;SAN=directorwebcon01.contoso.com SAN= \* .contoso.com  <br/> |
   
スタンドアロン仲介サーバーの証明書:
  
|**証明書**|**サブジェクト名/共通名**|**サブジェクト名の別名**|**例**|
|:-----|:-----|:-----|:-----|
|既定値  <br/> |プールの FQDN  <br/> |プールの FQDN  <br/> プール メンバー サーバーの FQDN  <br/> |SN=medsvr-pool.contoso.net。SAN=medsvr-pool.contoso.net。SAN=medsvr01.contoso.net  <br/> |
   
存続可能ブランチ アプライアンスの証明書 (具体的には、存続可能ブランチ アプライアンス 2015 for Skype for Business Server 2019):
  
|**証明書**|**サブジェクト名/共通名**|**サブジェクト名の別名**|**例**|
|:-----|:-----|:-----|:-----|
|既定値  <br/> |アプライアンスの FQDN  <br/> |SIP。\<sipdomain\> (SIP ドメインごとに必要なエントリは 1 つのみです)  <br/> |SN=sba01.contoso.net;SAN=sip.contoso.com;SAN=sip.fabrikam.com  <br/> |
   
### <a name="certificates-for-external-user-access-edge"></a>外部ユーザー アクセス用の証明書 (Edge)

Skype for Business Server 2019では、アクセスおよび Web 会議エッジの外部インターフェイスに対する 1 つのパブリック証明書と、エッジ サーバー経由で提供される音声ビデオ認証サービスの使用がサポートされています。 エッジ内部インターフェイスは、通常、内部 CA によって発行されたプライベート証明書を使用しますが、必要に応じて、信頼できる CA からのパブリック証明書も使用できます。
  
リバース プロキシ (RP) もパブリック証明書を使用し、RP からクライアントへの通信、および HTTP (またはより正確には HTTP 上の TLS) を使用して RP から内部サーバーへの通信を暗号化します。
  
### <a name="certificates-for-mobility"></a>モビリティの証明書

モビリティを展開し、モバイル クライアントの自動検出をサポートしている場合は、モバイル クライアントからの安全な接続をサポートするために、証明書に追加のサブジェクト代替名エントリを含める必要があります。
  
次の証明書の自動検出には SAN 名が必要です。
  
- ディレクター プール
    
- フロント エンド プール
    
- リバース プロキシ
    
詳細については、以下の表に示します。
  
これは少し事前計画が良い場所ですが、モビリティを展開せずに Skype for Business Server 2019 を展開した場合や、環境に証明書が既に存在する場合は後で考え出される場合があります。 通常、内部 CA を介して再発行するのは非常に簡単ですが、パブリック CA からのパブリック証明書を使用すると、もう少し高い可能性があります。
  
それが見ている場合で、SIP ドメインが多い場合 (SANS を追加するコストが高くなります)、HTTPS を使用する代わりに、最初の自動検出サービス要求に HTTP を使用するようにリバース プロキシを構成できます (これは既定の構成です)。 モビリティ [の計画に関する](../../SfbServer/plan-your-deployment/mobility.md) 記事には、この詳細があります。
  
ディレクター プールとフロントエンド プール証明書の要件:
  
|**説明**|**SAN エントリ**|
|:-----|:-----|
|内部自動検出サービスの URL  <br/> |SAN=lyncdiscoverinternal。\<sipdomain\>  <br/> |
|外部自動検出サービスの URL  <br/> |SAN=lyncdiscover。\<sipdomain\>  <br/> |
   
代わりに SAN= を使用できます \* 。\<sipdomain\>
  
リバース プロキシ (パブリック CA) 証明書の要件:
  
|**説明**|**SAN エントリ**|
|:-----|:-----|
|外部自動検出サービスの URL  <br/> |SAN=lyncdiscover。\<sipdomain\>  <br/> |
   
この SAN は、リバース プロキシの SSL リスナーに割り当てられている証明書に割り当てる必要があります。
  
> [!NOTE]
> リバース プロキシ リスナーは、外部 Web サービス URL の SANS を持つ必要があります。 ディレクターを展開した場合、SAN=skypewebextpool01.contoso.com と dirwebexternal.contoso.com が使用されます (これはオプションです)。 
  
## <a name="file-share"></a>ファイル共有
<a name="Fileshare"> </a>

Skype for Business Server 2019 では、すべてのファイル ストレージに同じファイル共有を使用できます。 次のことを念頭に置く必要があります。
  
- ファイル共有は、直接接続ストレージ (DAS) または記憶域ネットワーク (SAN) 上にある必要があります。これには、分散ファイル システム (DFS) と、ファイル ストア用の独立ディスク (RAID) の冗長配列が含まれます。 DFS for Windows Server 2012については、この [DFS ページを参照してください](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj127250(v=ws.11))。
    
- ファイル共有の共有クラスターをお勧めします。 既に 1 つを使用している場合は、Windows Server 2012以上のバージョンをクラスター化する必要があります。

> [!Note]
> **最新の Windows の理由** 以前のバージョンでは、すべての機能を有効にする適切なアクセス許可がない場合があります。 クラスター管理者を使用してファイル共有を作成できます。 詳細については、このサポート [記事「クラスターでファイル共有を作成](https://support.microsoft.com/help/224967) する方法」を参照してください。
    
> [!CAUTION]
> ネットワーク接続ストレージ (NAS) をファイル共有として使用する機能はサポートされていないので、上記のいずれかのオプションを使用してください。 このサポート制限は、デバイスの共有ファイル システムにアクセスする Windows Server ベースのコンピューターにファイル システムの適応性を提供する必要がある NAS デバイスの可変設計によって発生します。
