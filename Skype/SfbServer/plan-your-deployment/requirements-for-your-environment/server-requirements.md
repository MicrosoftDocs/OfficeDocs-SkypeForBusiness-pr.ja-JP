---
title: Skype for Business Server 2015 のサーバー要件
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 8d47b242-b93d-4c2e-a658-23b78bca30b1
description: '概要: このトピックを使用すると、Skype for Business Server 2015 サーバーを準備することができます。ここにはハードウェア、OS、データベース、ソフトウェア、すべてのシステム要件と推奨が掲載されており、サーバー ファームのインストールと展開を正常に実行できるようになります。'
ms.openlocfilehash: dfcde40c8084279dca39e830a84ad6e9631530dd
ms.sourcegitcommit: 98c0d578f5ebbe884a5965ccaba131ee4dd84185
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/05/2018
ms.locfileid: "19046021"
---
# <a name="server-requirements-for-skype-for-business-server-2015"></a>Skype for Business Server 2015 のサーバー要件
 
**概要:** このトピックを使用すると、Skype for Business Server 2015 サーバーを準備することができます。ここにはハードウェア、OS、データベース、ソフトウェア、すべてのシステム要件と推奨が掲載されており、サーバー ファームのインストールと展開を正常に実行できるようになります。
  
ご想像のとおり、Skype をビジネス サーバー 2015 の展開を開始する前にいくつかの準備があります。 この記事では次の計画について、順を追って説明します。
  
- [Skype for Business Server 2015 のハードウェア](server-requirements.md#Hardware)
  
- [ビジネス サーバー 2015 の Skype のオペレーティング ・ システム](server-requirements.md#OS)
  
- [Skype for Business Server 2015 で動作するバックエンド データベース](server-requirements.md#DBs)
  
- [Skype for Business Server 2015 の展開前にインストールすべきソフトウェア](server-requirements.md#Software)
  
## <a name="hardware-for-skype-for-business-server-2015"></a>Skype for Business Server 2015 のハードウェア
<a name="Hardware"> </a>

これでダウン、トポロジがある場合、ない場合は、[トポロジの基本的な](../../plan-your-deployment/topology-basics/topology-basics.md)ビジネス サーバー 2015 の Skype のトピックを確認できます) は、サーバーについて考える時間が。 Skype ビジネス サーバー 2015 のサーバーには、64 ビットのハードウェアが必要となります。 推奨されるハードウェアをこの後に示します。 これらの要件、操作は、最適なパフォーマンスのために必要な要件を反映します。 状況に応じて、これを超えるものが必要であるかどうかの判断に役立つ、処理能力の計画に関するドキュメントも用意されています。
  
フロント エンド サーバー、バック エンド サーバー、Standard Edition サーバー、および永続的なチャット サーバーのハードウェアを推奨します。
  
|**ハードウェア コンポーネント**|**推奨**|
|:-----|:-----|
|CPU  <br/> |64 ビット デュアル プロセッサ、6 コア、2.26 GHz 以上。  <br/> サーバー 2015 のビジネス ロールの Skype は、Intel Itanium プロセッサがサポートされていません。  <br/> |
|メモリ  <br/> |32 ギガバイト (GB)  <br/> |
|ディスク  <br/> |次のいずれか:  <br/> •	10,000 RPM のハード ディスク ドライブで 72 GB 以上の空きディスク領域があるものを 8 台以上 (RAID 1 を使用する 2 台のディスクと、RAID 10 を使用する 6 台のディスク)。  <br/> または  <br/> •	10000 RPM の機械的ディスク ドライブ 8 台と同じ空き領域および同等のパフォーマンスを持つソリッド ステート ドライブ (SSD)。  <br/> |
|ネットワーク  <br/> |1 Gbps 以上のデュアルポート ネットワーク アダプター 1 つ (2 つのネットワーク アダプターを使用できるが、その場合は 1 つの MAC アドレスと 1 つの IP アドレスのチーミングが必要)。  <br/> デュアルまたはマルチホーム構成では、サーバーをフロント エンド サーバー、バック エンド サーバー、Standard Edition でサポートされて**いません**し、永続的なチャット サーバー。 <br/> オペレーティング システムに公開されて、サーバー ハードウェアの監視と管理に使用されていない限り、DRAC や ILO などのアウト オブ バンド管理システムを持つことができます。このシナリオは、マルチ ホーム サーバーの構成要素ではなく、サポートされています。<br/> |
   
エッジ トランスポート サーバー、スタンドアロンの仲介サーバー、ビデオの相互運用機能サーバー、およびディレクターのハードウェアを推奨します。
  
|**ハードウェア コンポーネント**|**推奨**|
|:-----|:-----|
|CPU  <br/> |64 ビット デュアル プロセッサ、クアッド コア、2.26 GHz 以上  <br/> サーバー 2015 のビジネス ロールの Skype は、Intel Itanium プロセッサがサポートされていません。  <br/> |
|メモリ  <br/> |16 GB  <br/> |
|ディスク  <br/> |次のいずれか:  <br/> •	10,000 RPM のハード ディスク ドライブで 72 GB 以上の空きディスク領域があるものを 4 台以上 (ディスクは 2 x RAID 1 構成である必要がある)。  <br/> または  <br/> •	10000 RPM の機械的ディスク ドライブ 4 台と同じ空き領域および同等のパフォーマンスを持つソリッド ステート ドライブ (SSD)。  <br/> |
|ネットワーク  <br/> |1 Gbps 以上のデュアルポート ネットワーク アダプター 1 つ (2 つのネットワーク アダプターを使用できるが、その場合は 1 つの MAC アドレスと 1 つの IP アドレスのチーミングが必要)。  <br/> デュアルまたはマルチホームの構成は、ビデオの相互運用機能のサーバーやディレクターではサポート**されません**。 <br/> エッジ サーバーには、1 Gbps 以上のデュアルポート ネットワーク アダプターである 2 つのネットワーク インターフェイス (つまり 2 ペア (合計 4 つ) のネットワーク アダプター。この合計 2 つのペアでは、各ペアが 1 つの MAC アドレスと 1 つの IP アドレスでチームになっている) が必要です。  <br/> スタンドアロンの仲介サーバーの追加のネットワーク インターフェイス カード (Nic) が特定の PSTN の IP アドレスの構成を許可するインストールはサポートされています。  <br/> |
   
## <a name="operating-systems-for-skype-for-business-server-2015"></a>ビジネス サーバー 2015 の Skype のオペレーティング ・ システム
<a name="OS"> </a>

ハードウェアがある場合に、オペレーティング システム (OS) をインストールするのにはする必要があります。 これらは、OS をインストールして正常にビジネス サーバー 2015 の Skype を使用することがあります。
  
|||
|:-----|:-----|
|Windows Server 2016  <br/> ||
|Windows Server 2012 では、R2 データ センター OS を必要なすべての更新プログラムがインストールされているとします。  <br/> |Windows Server 2012 R2 標準的な OS に必要なすべての更新プログラムをインストールします。  <br/> |
|必要なすべての更新プログラムがインストールされている Windows Server 2012 データ センター OS です。  <br/> |Windows Server 2012 標準的な OS に必要なすべての更新プログラムをインストールします。  <br/> |
   
この一覧にない場合は、正常に動作しません、再試行してくださいしない Skype の新規インストールのビジネス サーバー 2015。
  
> [!NOTE]
> Windows Server 2008 R2 がこの一覧に含まれていないことにお気付きでしょうか。これは、SFB に使用するすべての新しいサーバーには、Windows Server 2012 R2 が推奨されるためです。Windows Server 2008 R2 を使用するのは、Lync Server 2013 がインストールされている既存のサーバーがあり、そのインプレース アップグレードを行う場合のみにしてください。Windows Server 2008 R2 のメインストリーム サポート期間は、2015 年 1 月 13 日に終了しています。 
  
最新のサービス パック以外にも、関連性がある場合は次の更新プログラムをインストールする必要があります。
  
- Windows Server 2012 では、アップグレードの前に、サポート技術情報 2858668 の更新プログラムをインストールする必要があります。 [ここでそれを取得](https://support.microsoft.com/en-us/kb/2858668/)します。
    
- Windows Server 2012 R2 を使用している場合は、アップグレードの前に、サポート技術情報 2982006 の更新プログラムをインストールしてください。 [それはこちらから](https://support.microsoft.com/en-us/kb/2982006/)。
    
- Windows Server 2008 R2 ボックス上でアップグレードする場合は (前述の注意事項を参照)、まずサポート技術情報 2533623 の更新プログラムをインストールする必要があります。 [このリンクになっている](https://support.microsoft.com/en-us/kb/2533623/)。
    
## <a name="back-end-databases-that-will-work-with-skype-for-business-server-2015"></a>Skype for Business Server 2015 で動作するバックエンド データベース
<a name="DBs"> </a>

ビジネス サーバー 2015 の Standard Edition を Skype をインストールすると、SQL Server 2014 の高速必要があります (64 ビット版) は同様に自動的にインストールします。
  
ビジネス サーバー 2015 エンタープライズ エディションの Skype は、少し複雑ですが、サポートされているリストの下にある (64 ビット版ではすべて、見るとわかるようにしてくださいしない 32 ビット エディションを使用)。
  
||||
|:-----|:-----|:-----|
|Microsoft SQL Server 2014 エンタープライズ (64 ビット版) とは、累積的な更新 6 またはそれ以降 ([累積的な更新 6 をダウンロード](https://support.microsoft.com/en-us/kb/3031047/)) を実行しなければなりません。  <br/> |Microsoft SQL Server 2012 エンタープライズ (64 ビット版) とは、最新の service pack を実行するをお勧めします。  <br/> |Microsoft SQL Server 2008 R2 エンタープライズ (64 ビット版) とは、最新の service pack を実行するをお勧めします。  <br/> |
|Microsoft SQL Server 2014 標準 (64 ビット版) とは、累積的な更新 6 またはそれ以降 ([累積的な更新 6 をダウンロード](https://support.microsoft.com/en-us/kb/3031047/)) を実行しなければなりません。  <br/> |Microsoft SQL Server 2012 標準 (64 ビット版) で最新のサービス パックの実行をお勧めします。  <br/> |Microsoft SQL Server 2008 R2 標準 (64 ビット版) で最新のサービス パックの実行を推奨します。  <br/> |
   
ここで使用する SQL Server のエディションが表示されない場合は使用できません。
  
> [!NOTE]
> 監視サーバーの役割、SQL Server レポート サービスをインストールする必要がありますしようとしているもが、この post-RTM までに常に SQL をサポートしようとしていないかを知る必要があります。 
  
### <a name="sql-mirroring-sql-clustering-and-sql-always-on"></a>SQL ミラーリング、SQL クラスタリング、および SQL AlwaysOn

ビジネス サーバー 2015 の Skype での SQL のミラーリングまたは SQL のクラスタ リングを使用することは、サポートされています。 SQL ミラーリングの設定を Skype ビジネス サーバー トポロジ ビルダーをします。 SQL クラスターを設定することに専心する場合は、SQL Server でそれを行います。
  
サポート内容であるために、SQL がクラスターのアクティブ/パッシブ構成があることを確認してください。 他の任意の SQL インスタンスには、パッシブ ノードを共有しません。
  
フェールオーバー クラスタリングでは、次の OS を使用できます。
  
2 ノードの場合:
  
- Microsoft SQL Server 2014 標準 (64 ビット版) で最新のサービス パックの実行をお勧めします。
    
-  Microsoft SQL Server 2012 標準 (64 ビット版) で最新のサービス パックの実行をお勧めします。
    
- Microsoft SQL Server 2008 R2 標準 (64 ビット版) で最新のサービス パックの実行をお勧めします。
    
16 ノードの場合:
  
- Microsoft SQL Server 2014 エンタープライズ (64 ビット版) とは、最新の service pack を実行するをお勧めします。
    
- Microsoft SQL Server 2012 エンタープライズ (64 ビット版) とは、最新の service pack を実行するをお勧めします。
    
- Microsoft SQL Server 2008 R2 エンタープライズ (64 ビット版) とは、最新の service pack を実行するをお勧めします。
    
> [!IMPORTANT]
> アップグレードのたく以上があるフロント エンド サーバーに SQL Server 2012 SP1 がインストールされているアップグレードの準備の確認をします。 SP1 をすぐにダウンロードする場合に[ここ](https://www.microsoft.com/en-us/download/details.aspx?id=35575)をします。
  
SQL のミラーリングの詳細を参照する場合は、ビジネス サーバー 2015 トピックの Skype にバック エンド サーバーの高可用性があります。 ビジネス サーバー 2015 の Skype には準備が整ってクラスタ リングを取得するための手順については、SQL Server のクラスタ リングを構成します。 さらにリンクで[2014](https://technet.microsoft.com/en-us/library/hh231721.aspx)、 [2012 年 5](https://technet.microsoft.com/en-us/library/hh231721%28v=sql.110%29.aspx)、および[2008](https://technet.microsoft.com/en-us/library/ms189134%28v=sql.105%29.aspx)の SQL でのクラスタ リング フェイル オーバーします。
  
> [!NOTE]
> このリリースの新しい機能として、SQL AlwaysOn がサポートされます。 サポートされているし、詳細を確認できる[ビジネス サーバー 2015 の Skype のバック エンド サーバーの高可用性](../../plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md)のトピックについてです。
  
## <a name="software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment"></a>Skype for Business Server 2015 の展開前にインストールすべきソフトウェア
<a name="Software"> </a>

インストールまたはビジネス サーバー 2015 年の Skype を実行するサーバーを構成する必要がありますしようとしているものがあり、以下記載されています。 その後に、特定のサーバーの役割に関するその他の要件を示しています。
  
 **すべてのサーバー:**
  
|**ソフトウェア/役割**|**詳細**|
|:-----|:-----|
|Windows PowerShell 3.0  <br/> |これらのサーバーのすべての Skype では、Windows PowerShell 3.0 がインストールされている必要があります。  <br/> • Windows Server 2012 または Windows Server 2012 R2 のインストールを実行している場合、設定するとしているは既にあるためです。  <br/> • Windows Server 2008 R2 にアップグレードを実行している場合、それを取得する[Windows Management Framework 3.0](https://www.microsoft.com/en-us/download/details.aspx?id=34595)をダウンロードできます。 <br/> **ヒント:** したら正しい PowerShell で、BuildVersion 6.2.9200.0 であることを確認後に、PowerShell でメッセージが表示や入力`$PSVersionTable`。 これによって、必要な情報が得られます。  <br/> |
|Microsoft .NET Framework  <br/> |WCF サービスは、インストールした**サーバー マネージャー**で、[Windows 機能としてないダウンロードのために必要な**機能**です。 <br/> • をする必要があります、 **HTTP アクティブ化**のオプションのもがチェックされ、インストールされて、それをチェックする場合は既にインストールされている場合や、この機能をインストールすると、次のようにします。 <br/> ![[.NET Framework 4.5 の機能] の HTTP アクティブ化のオプションを表示するスクリーン ショットです。](../../media/a4064fa0-fa49-4474-bd98-b9a79ff68f8b.png)も気にしないで他のものがインストールされるように HTTP アクティブ化をインストールする必要ことを示すその他のポップアップを取得します。 これは通常の動作のため、[OK] をクリックして先に進みます。 このメッセージが表示されない場合、これらの機能は既にインストールされていると見なして、先に進みます。  <br/> 通常 Microsoft.NET Framework がインストールされている Windows Server 2012 R2 または Windows Server 2016 がインストールされている場合。 Skype ビジネス サーバーは、次の Microsoft.NET Framework のバージョンで動作します。  <br/> • .NET 3.5  <br/> • .NET 4.5  <br/> • .NET 4.6.x  <br/> • .NET 4.7 (ビジネス サーバー CU 5 またはそれ以降のリリースの Skype)  <br/>  .NET Framework 3.5 は既定では Windows Server 2008 R2 コンピューターにインストールする可能性があります (必ず確認してくださいアップグレードする前に) が、実際にするの新しいインストールの場合) または Windows Server 2012 R2 の Windows Server 2012 サーバー上にします。 それを追加するにはインストール ドライブまたはメディアへのアクセスを必要があります (Windows サーバーをインストールして、元の場所またはファイルをインストールされるようになりました)。 その後、先に進んで、サーバー マネージャーの機能としてインストールし、要求されたらインストール メディア (具体的には **\sources\sxs** フォルダー) を指定して、インストールを続行します。 <br/> |
|メディア ファンデーション  <br/> |Windows Server 2016、Windows Server 2012 と Windows Server 2012 R2 の Windows Media フォーマット ランタイムは、Microsoft メディア ファンデーションをインストールします。  <br/> 会議のために使用される、すべてのフロント エンド サーバーと Standard Edition サーバーでは、アナウンスや音楽のコール パーク、アナウンス、および応答グループ アプリケーションを再生する Windows Media オーディオ (.wma) ファイルを実行する、Windows Media フォーマット ランタイムが必要です。  <br/> |
|Windows Identity Foundation  <br/> |ビジネス サーバー 2015 の Skype のサーバーからサーバーへの認証シナリオをサポートするために Windows アイデンティティ基盤の 3.5 が必要です。  <br/> • Windows Server 2012 と Windows Server 2012 R2 の場合は、何もダウンロードする必要はありません。 **サーバー マネージャー**を開いて、[**役割と機能の追加ウィザード**] に進みます。 [**機能**] セクションの一覧に [**Windows Identity Foundation 3.5**] が表示されています。 オンの場合は完了です。 オンになっていない場合は、これを選択して [次へ] をクリックし、[**インストール**] をアクティブにします。 <br/> |
|リモート サーバー管理ツール  <br/> |役割管理ツール: AD DS および AD LDS ツール  <br/> |
   
 **フロント エンド サーバーと Standard Edition サーバーも必要があります。**
  
|**ソフトウェア/役割**|**詳細**|
|:-----|:-----|
|インターネット インフォメーション サービス (IIS)  <br/> |選択されている次のモジュールとは、すべてのフロント エンド サーバーとすべての Standard Edition サーバーでは、IIS が必要です。  <br/> • 一般的な HTTP 機能: 既定のドキュメントでは、HTTP エラーの場合は、静的なコンテンツ  <br/> • 状態と診断: HTTP のログ、トレース ログ ツール  <br/> • パフォーマンス: コンテンツの圧縮は静的、動的コンテンツの圧縮  <br/> • セキュリティ: 要求のフィルタ リング、クライアント証明書マッピング認証、Windows 認証  <br/> • アプリケーションの開発: .NET 3.5 の機能拡張、.NET 4.5 の機能拡張、ASP.NET 3.5 ASP.NET 4.5 では、ISAPI 拡張機能、ISAPI フィルター  <br/> • 管理ツール: IIS 管理コンソール、IIS 管理スクリプトおよびツール  <br/> 私たちは、匿名アクセスが必要なもが得ることができるリストの選択をする場所がないため、IIS をインストールするときにも注意してください。  <br/> |
|Windows Media フォーマット ランタイム  <br/> | Windows Server 2016、Windows Server 2012 では、Windows Server 2012 R2 の**サーバー マネージャー**で、**メディア ファンデーション**機能をインストールする必要があります。 ここで、実際にビジネス サーバー 2015 をインストールせずにこの 1 つに、Skype を起動できますが、インストールを求められることでしょう. ビジネス サーバー 2015 の Skype の前に、サーバーのインストールの再起動を続行し、 この作業は、前もって行っておくことをお勧めします。 <br/> |
|Silverlight  <br/> |[このリンク](https://www.microsoft.com/silverlight/)で、最新バージョンの Silverlight をインストールすることができます。  <br/> |
   
> [!NOTE] 
> ロード バランサーを使用している場合は、ディレクトリの参照を有効にする必要もあります。 それ以外の場合空白のページをロードするロード バランサーは、障害を検討してください。 

作業の簡素化のために、この処理を自動化するサンプル PowerShell スクリプトを次に示します。

```
Add-WindowsFeature NET-Framework-Core, RSAT-ADDS, Windows-Identity-Foundation, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Dir-Browsing, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, BITS, Desktop-Experience, Telnet-Client
```

> [!NOTE] 
> コマンドは、特定の順序でソース ファイルを検索します。 オンラインの場合、このコマンドは Windows Update にアクセスします。 一方、オフラインの場合は、このコマンドがソース ファイルにアクセスできるようにする必要があります。 PowerShell を使用して、役割と機能をインストールするには、[インストールまたはアンインストールの役割、役割サービス、または機能](https://technet.microsoft.com/en-us/library/hh831809.aspx)を参照してくださいの詳細については忘れずに Windows の更新プログラムを再実行の前提条件をインストールした後、PowerShell コマンドを使用する場合でも。

 **ダイレクタが必要もあります。**
  
次のモジュールを選択した IIS:
  
- HTTP 共通機能
    
  - 既定のドキュメント
    
  - HTTP エラー
    
  - 静的コンテンツ
    
- 状態と診断
    
  - HTTP ログ
    
  - ログ ツール
    
  - 追跡
    
- パフォーマンス
    
  - 静的コンテンツ圧縮
    
- セキュリティ
    
  - 要求のフィルタリング
    
  - クライアント証明書マッピング認証
    
  - Windows 認証
    
- アプリケーション開発
    
  - .NET 拡張機能 3.5
    
  - .NET 拡張機能 4.5
    
  - ASP.NET 3.5
    
  - ASP.NET 4.5
    
  - ISAPI 拡張機能
    
  - ISAPI フィルター
    
(ご参考までに場合は、同じモジュールが動的コンテンツの圧縮を使用して、フロント エンド サーバーと Standard Edition サーバーとして設定し、管理ツールは省略)
  
また、同様に役立つ PowerShell コードを次に示します。
  
```
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client
```

 **永続的なチャット サーバーも必要があります。**
  
メッセージ キュー (別名 MSMQ)。 Windows Server コンポーネントとそれをインストールするには、サーバー マネージャーの [機能] セクションの下。 詳細を確認する場合について、これをチェック アウト[をインストールしてメッセージ キューを管理](https://technet.microsoft.com/en-us/library/cc771474.aspx)します。
  
 **最後の確認事項:**
  
インストールしてください Microsoft インターネット セキュリティとアクセラレータ (ISA) Server クライアント ソフトウェア、または他の Winsock 複数層サービス プロバイダー (LSP) ソフトウェア (すべてのサードパーティ製のファイアウォールまたはネットワークのアンチ ウイルス検査ソフトウェアはここで指定)フロント エンド サーバーまたはスタンドアロンの仲介サーバーのいずれかです。 不適切なメディアのトラフィックのパフォーマンスは、そのソフトウェアのインストール時に確認されています。
  

