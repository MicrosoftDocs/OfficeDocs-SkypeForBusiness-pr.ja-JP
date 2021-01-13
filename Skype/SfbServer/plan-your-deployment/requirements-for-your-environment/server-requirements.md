---
title: Skype for Business Server 2015 のサーバー要件
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 8d47b242-b93d-4c2e-a658-23b78bca30b1
description: '概要: このトピックで Skype for Business Server 2015 サーバーを準備します。 ハードウェア、OS、データベース、ソフトウェア、すべてのシステム要件と推奨事項は、サーバー ファームのインストールと展開を正常に行うのに役立ちます。'
ms.openlocfilehash: b1e7e37e46d0f3f547ed843ce2510d8445a34267
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832077"
---
# <a name="server-requirements-for-skype-for-business-server-2015"></a>Skype for Business Server 2015 のサーバー要件
 
**概要:** このトピックで Skype for Business Server 2015 サーバーを準備します。 ハードウェア、OS、データベース、ソフトウェア、すべてのシステム要件と推奨事項は、サーバー ファームのインストールと展開を正常に行うのに役立ちます。

Active Directory、DNS、証明書などの環境要件をお探しの場合は [、Skype for Business Server 2015 ドキュメントの「Environmental requirements for Skype for Business Server 2015」](environmental-requirements.md) を参照してください。
  
お気に入りのように、Skype for Business Server 2015 の展開を開始する前に、いくつかの準備を行う必要があります。 この記事では、以下の計画について説明します。
  
- [Skype for Business Server 2015 のハードウェア](server-requirements.md#Hardware)
  
- [Skype for Business Server 2015 のオペレーティング システム](server-requirements.md#OS)
  
- [Skype for Business Server 2015 で動作するバック エンド データベース](server-requirements.md#DBs)
  
- [Skype for Business Server 2015 の展開前にインストールする必要があるソフトウェア](server-requirements.md#Software)
  
## <a name="hardware-for-skype-for-business-server-2015"></a>Skype for Business Server 2015 のハードウェア
<a name="Hardware"> </a>

トポロジがダウンしました (トポロジがダウンしている場合は [、「Topology Basics for Skype for Business Server 2015」](../../plan-your-deployment/topology-basics/topology-basics.md) トピックを参照してください)、次にサーバーについて考えてみます。 Skype for Business Server 2015 サーバーには 64 ビット ハードウェアが必要です。 ハードウェアに関する推奨事項を以下に示します。 これらは要件ではなく、最適なパフォーマンスを得る上で必要な要件を反映しています。 状況に応じて、より多くの情報が必要かどうかを判断するのに役立つ容量計画ドキュメントが提供されています。
  
フロント エンド サーバー、バック エンド サーバー、Standard Edition サーバー、および常設チャット サーバーの推奨ハードウェア:
  
|**ハードウェア コンポーネント**|**推奨**|
|:-----|:-----|
|CPU  <br/> |64 ビット デュアル プロセッサ、16 コア、2.26 GHz 以上  <br/> Intel Itanium プロセッサは、Skype for Business Server 2015 の役割ではサポートされていません。  <br/> |
|メモリ  <br/> |32 ギガバイト (GB)。  <br/> |
|ディスク  <br/> |いずれも：  <br/> • 少なくとも 72 GB の空きディスク領域を持つ 8 台以上の 1,0000 RPM ハード ディスク ドライブ (RAID 1 を使用するディスク 2 台と RAID 10 を使用する 6 台のディスク)。  <br/> OR  <br/> • ソリッド ステート ドライブ (SSD) は、8 台の 10000 RPM の機械的ディスク ドライブと同じ空き領域と同様のパフォーマンスを提供できます。  <br/> |
|ネットワーク  <br/> |1 Gbps 以上のデュアルポート ネットワーク アダプター 1 つ (2 つのネットワーク アダプターを使用できますが、単一の MAC アドレスと 1 つの IP アドレスでチーム化する必要があります)。  <br/> デュアルまたはマルチホーム構成は、フロントエンド サーバー、バック エンド サーバー、Standard Edition サーバー、および常設チャット サーバーではサポートされていません。 <br/> オペレーティング システムに公開され、サーバー ハードウェアの監視と管理に使用されている限り、DRAC や ILO などの帯域外管理システムを使用できます。 このシナリオはマルチホーム サーバーを構成するのではありません。これはサポートされています。  <br/> |
   
エッジ サーバー、スタンドアロン仲介サーバー、ビデオ相互運用サーバー、およびディレクターの推奨ハードウェア:
  
|**ハードウェア コンポーネント**|**推奨**|
|:-----|:-----|
|CPU  <br/> |64 ビット デュアル プロセッサ、クアッド コア、2.26 GHz 以上。  <br/> Intel Itanium プロセッサは、Skype for Business Server 2015 の役割ではサポートされていません。  <br/> |
|メモリ  <br/> |16 ギガバイト。  <br/> |
|ディスク  <br/> |いずれも：  <br/> • 少なくとも 72 GB の空きディスク領域を持つ 4 台以上の 1,0000 RPM ハード ディスク ドライブ (ディスクは 2x RAID 1 構成にする必要があります)。  <br/> OR  <br/> • ソリッド ステート ドライブ (SSD) は、4 台の 10000 RPM の機械的ディスク ドライブと同じ空き領域と同様のパフォーマンスを提供できます。  <br/> |
|ネットワーク  <br/> |1 Gbps 以上のデュアルポート ネットワーク アダプター 1 つ (2 つのネットワーク アダプターを使用できますが、単一の MAC アドレスと 1 つの IP アドレスでチーム化する必要があります)。  <br/> デュアルまたはマルチホーム構成は **、ビデオ相互** 運用サーバーとディレクターではサポートされていません。 <br/> エッジ サーバーには、1 Gbps 以上のデュアルポート ネットワーク アダプターである 2 つのネットワーク インターフェイス (合計 4 つのペアの場合は 2 つのペアのネットワーク アダプター) が必要です。各ペアは、合計で 2 つのペアについて、1 つの MAC アドレスと 1 つの IP アドレスでチーム化されます。  <br/> スタンドアロン仲介サーバーでは、特定の PSTN IP アドレスの構成を許可する追加のネットワーク インターフェイス カード (NIC) のインストールがサポートされています。  <br/> |
   
## <a name="operating-systems-for-skype-for-business-server-2015"></a>Skype for Business Server 2015 のオペレーティング システム
<a name="OS"> </a>

ハードウェアをインストールしたら、オペレーティング システム (OS) をインストールする必要があります。 これらは、Skype for Business Server 2015 をインストールして正常に使用できる OS です。
  
|||
|:-----|:-----|
|Windows Server 2019 (Skype for Business 累積更新プログラム 9 以降が必要です)。 <br/> |Windows Server 2016 (Skype for Business 累積更新プログラム 5 以降が必要です。 詳細については [、KB4015888 を確認してください](https://support.microsoft.com/help/4015888/how-to-install-skype-for-business-server-2015-on-windows-server-2016))  <br/> ||
|Windows Server 2012更新プログラムがインストールされた R2 Datacenter OS。  <br/> |Windows Server 2012更新プログラムがインストールされている R2 Standard OS をインストールします。  <br/> |
|Windows Server 2012更新プログラムがインストールされている Datacenter OS。  <br/> |Windows Server 2012更新プログラムがインストールされた標準 OS。  <br/> |
   
この一覧に記載されていない場合は、正しく動作しません。Skype for Business Server 2015 の新規インストールでは試用しません。

> [!NOTE]
> Lync Server 2013 では、OS の一時アップグレードはサポートされていません。 別のプールを展開し、別の OS を持つ新しいプールにユーザーを移行する必要があります。 プール内のすべてのサーバーに同じ OS バージョンが必要です。
  
> [!NOTE]
> この一覧にWindows Server 2008 R2気が付いた可能性があります。 これは、SFB に使用Windows Server 2012新しいサーバーには R2 を使用することをお勧めします。 Windows Server 2008 R2 を使用できるのは、Lync Server 2013 が既にインストールされている既存のサーバーが存在し、それらを一時アップグレードする場合のみです。 Windows Server 2008 R2 2015 年 1 月 13 日にメインストリーム サポート ライフサイクルが終了し、2020 年 1 月 14 日にサポート ライフサイクルが終了します。
  
最新の Service Pack に加えて、次の更新プログラムが適切な場所にインストールされていることを確認する必要があります。
  
- このWindows Server 2012、アップグレードの前にサポート技術情報の記事 2858668 をインストールする必要があります。 [ここで取得します](https://support.microsoft.com/kb/2858668/)。
    
- R2 を使用Windows Server 2012、アップグレードの前にサポート技術情報の記事 2982006 をインストールしてください。 [このファイルは、こちらから見つかりました](https://support.microsoft.com/kb/2982006/)。
    
- Windows Server 2008 R2 ボックス (上記の注を参照) にアップグレードする場合は、最初にサポート技術情報の記事 2533623 をインストールします。 [It's at this link](https://support.microsoft.com/kb/2533623/).
    
## <a name="back-end-databases-that-will-work-with-skype-for-business-server-2015"></a>Skype for Business Server 2015 で動作するバック エンド データベース
<a name="DBs"> </a>


Skype for Business Server 2015 Standard Edition をインストールすると、SQL Server 2014 Express (64 ビット版) も自動的にインストールされます。
  
Skype for Business Server 2015 Enterprise Edition はもう少し複雑ですが、サポートされている一覧は以下のとおりです (すべてが 64 ビット版です。32 ビット版は使用しません)。
  
||||||
|:-----|:-----|:-----|:-----|:-----|
|Microsoft SQL Server 2019 Enterprise (64 ビット版)、最新のサービス パックを使用して実行することをお勧めします。 <br/> |Microsoft SQL Server 2017 Enterprise (64 ビット版)、最新のサービス パックを使用して実行することをお勧めします。 <br/> |Microsoft SQL Server 2016 Enterprise (64 ビット版) Service Pack 1 以降を使用し、Skype for Business 累積更新プログラム 7 以降を使用して実行する必要があります[(Skype for Business](https://support.microsoft.com/help/3061064)の累積的な更新プログラムをダウンロード)。  <br/> |Microsoft SQL Server 2014 Enterprise (64 ビット版)、累積的な更新プログラム 6 以降 (累積的な更新プログラム 6 をダウンロード) で実行する[必要があります](https://support.microsoft.com/kb/3031047/)。  <br/> |Microsoft SQL Server 2012 Enterprise (64 ビット版)、最新のサービス パックを使用して実行することをお勧めします。  <br/> |
|Microsoft SQL Server 2019 Standard (64 ビット版)、最新のサービス パックを使用して実行することをお勧めします。 <br/> |Microsoft SQL Server 2017 Standard (64 ビット版)、最新のサービス パックを使用して実行することをお勧めします。 <br/> |Microsoft SQL Server 2016 Standard (64 ビット版) Service Pack 1 以降を使用し、Skype for Business 累積更新プログラム 7 以降を使用して実行する必要があります[(Skype for Business](https://support.microsoft.com/help/3061064)の累積的な更新プログラムをダウンロード)。  <br/> |Microsoft SQL Server 2014 Standard (64 ビット版)、累積的な更新プログラム 6 以降 (累積的な更新プログラム 6 をダウンロード) で実行する[必要があります](https://support.microsoft.com/kb/3031047/)。  <br/> |Microsoft SQL Server 2012 Standard (64 ビット版)、最新のサービス パックを使用して実行することをお勧めします。  <br/> |
   
ここで使用する SQL Serverエディションが表示されな場合は、使用することはできません。
  
- また、監視サーバーの役割用に reporting Services SQL Serverインストールする必要もあります。
- 接続が整っている場合SQL、Skype for Business フロントエンドへの接続は低速リンクではなくローカル接続である必要があります。 
- 2 SQLプール間でのバック エンドの共有はサポートされていません。

### <a name="microsoft-exchange-storage"></a>Microsoft Exchange ストレージ
PowerPoint プレゼンテーションなどの会議コンテンツ ファイルは、添付ファイルとしてアーカイブされます。 Skype for Business アーカイブ データを Exchange コンプライアンス データと一緒に格納する場合は、Exchange を使用して Exchange を展開し、最大記憶域サイズが会議コンテンツ ファイルの記憶域をサポートする必要があります。 Microsoft Exchange 統合オプションを使用してアーカイブを展開および有効化する前に、Exchange を展開する必要があります。 
    
    If you choose to use Exchange storage, you do not need to deploy separate SQL Server databases for archiving, unless you have Skype for Business users who are not homed on your Exchange servers. If you deploy archiving using the Microsoft Exchange integration option, Skype for Business archive data is stored with Exchange compliance data only for the users who are homed on your Exchange servers. 
  
## <a name="hardware-and-software-requirements-for-archiving-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 でのアーカイブのハードウェア要件およびソフトウェア要件
  
アーカイブは定義済みのサーバーの役割ではなく、アーカイブ用に別のサーバーをインストールする必要があります。 統合データ収集エージェントは、すべての Enterprise Edition フロントエンド プールとすべての Standard Edition サーバーに自動的にインストールされ、アクティブ化されます。 トポロジ ビルダーを使用してアーカイブ トポロジを有効にして公開する必要があります。
    
アーカイブでは、会議コンテンツ ファイルの一時記憶域として Skype for Business Server ファイル ストレージを使用します。そのため、アーカイブ用に別のファイル ストアを設定しません。
    
Microsoft メッセージ キューは必要ありません。
    
アーカイブ ストレージのインフラストラクチャを設定する必要があります。 これには、Exchange ストレージまたはアーカイブ ストレージの選択が含SQL Server。   Skype for Business Server Archiving インフラストラクチャの要件は、Skype for Business Server の展開の要件と同じです。 詳細については [、「Skype for Business 環境の要件」を参照してください](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md)。 
  
> [!NOTE]
> Exchange サーバーにホームではないユーザーをサポートする場合、または Microsoft Exchange 統合オプションを使用しない場合は、64 ビットの SQL Server データベースを使用してアーカイブ ストレージを展開する必要があります。 
    
アーカイブを展開および有効化する前SQL Serverプラットフォームをセットアップする必要があります。 トポロジの公開に使用するアカウントに適切な管理権限とアクセス許可がある場合、トポロジを公開するときにアーカイブ データベース (LcsLog) を作成できます。 インストール手順の一部として、データベースを後で作成することもできます。 ドキュメントの詳細についてはSQL Serverドキュメント [をSQL Serverしてください](https://go.microsoft.com/fwlink/p/?linkID=129045)。
    
アーカイブの負荷の増加は、大きな影響を与える可能性があります。 したがって、アーカイブが有効になっているフロント エンド サーバーに十分なディスク領域を確保する必要があります。

### <a name="sql-mirroring-sql-clustering-and-sql-always-on"></a>SQLミラーリング、SQL クラスタリング、および SQL Always On

Skype for Business Server 2015 SQLミラーリングまたは SQL クラスタリングを使用できます。これはサポートされています。 SQL、Skype for Business Server トポロジ ビルダーを使用してセットアップします。 クラスター化のセットアップをSQL場合は、次のSQL Server。
  
サポートされている状態で、SQLのアクティブ/パッシブ構成を使用してください。 パッシブ ノードを他のインスタンスと共有SQLしてください。
  
フェールオーバー クラスタリングには、次の機能を使用できます。
  
2 ノード:
  
- Microsoft SQL Server 2019 Standard (64 ビット版)、最新のサービス パックを使用して実行することをお勧めします。

- Microsoft SQL Server 2017 Standard (64 ビット版)、最新のサービス パックを使用して実行することをお勧めします。

- Microsoft SQL Server 2016 Standard (64 ビット版) Service Pack 1 以降。 最新のサービス パックを使用して実行することをお勧めします。

- Microsoft SQL Server 2014 Standard (64 ビット版)、最新のサービス パックを使用して実行することをお勧めします。
    
-  Microsoft SQL Server 2012 Standard (64 ビット版)、最新のサービス パックを使用して実行することをお勧めします。

16 ノード:

- Microsoft SQL Server 2019 Enterprise (64 ビット版)、最新のサービス パックを使用して実行することをお勧めします。

- Microsoft SQL Server 2017 Enterprise (64 ビット版)、最新のサービス パックを使用して実行することをお勧めします。

- Microsoft SQL Server 2016 Enterprise (64 ビット版) Service Pack 1 以降。 最新のサービス パックを使用して実行することをお勧めします。
  
- Microsoft SQL Server 2014 Enterprise (64 ビット版)、最新のサービス パックを使用して実行することをお勧めします。
    
- Microsoft SQL Server 2012 Enterprise (64 ビット版)、最新のサービス パックを使用して実行することをお勧めします。

> [!IMPORTANT]
> アップグレードの場合は、アップグレード前にフロント エンド サーバーに少なくとも SQL Server 2012 SP1 がインストールされていることを確認する必要があります。 [すぐにダウンロードする場合](https://www.microsoft.com/download/details.aspx?id=35575) は、SP1 へのリンクを次に示します。
  
SQL ミラーリングについて詳しくは、Skype for Business Server 2015 のバック エンド サーバーの高可用性をご覧ください。 Configure SQL Server clustering for Skype for Business Server 2015 has the steps for getting clustering ready. また[](https://technet.microsoft.com/library/hh231721%28v=sql.110%29.aspx)[、2014 年、2012 年、および 2008](https://technet.microsoft.com/library/hh231721.aspx)年の[](https://technet.microsoft.com/library/ms189134%28v=sql.105%29.aspx)SQL のフェールオーバー クラスタリングにもリンクがあります。
  
> [!NOTE]
> 2015 リリースの新機能は、Always On SQLサポートされています。 これはサポートされています。詳細については [、Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md) の「バック エンド サーバーの高可用性」トピックを参照してください。

> [!NOTE]
> SQLミラーリングは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。 Skype for Business Server 2019 では、AlwaysOn 可用性グループ、AlwaysOn フェールオーバー クラスター インスタンス (FCI)、および SQL フェールオーバー クラスタリングの方法が優先されます。  

## <a name="software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment"></a>Skype for Business Server 2015 の展開前にインストールする必要があるソフトウェア
<a name="Software"> </a>

Skype for Business Server 2015 を実行している任意のサーバーにインストールまたは構成する必要がある項目がいくつかあるので、以下に一覧を示します。 その後、特定のサーバーの役割に対する追加の要件になります。

  
 **すべてのサーバー:**
  
|**ソフトウェア/役割**|**詳細**|
|:-----|:-----|
|Windows PowerShell 3.0  <br/> |すべての Skype for Business Server サーバーには、Windows PowerShell 3.0 がインストールされている必要があります。  <br/> • Windows Server 2012 または Windows Server 2012 R2 でインストールを実行している場合は、既にインストールされています。  <br/> • アップグレードを実行している場合は、Windows Server 2008 R2 [Windows Management Framework 3.0](https://www.microsoft.com/download/details.aspx?id=34595) をダウンロードして取得できます。 <br/> **ヒント:** 正しい PowerShell が表示されたら、PowerShell プロンプトにアクセスして入力し、BuildVersion 6.2.9200.0 以降を確認します `$PSVersionTable` 。 これにより、必要な情報が表示されます。  <br/> |
|Microsoft .NET Framework  <br/> |WCF サービスは **、Windows** 機能としてインストールされる機能で、 **サーバー** マネージャーの下にダウンロードする必要はありません。 <br/> • この機能をインストールする場合、または既にインストールされ、確認している場合は、次のように **HTTP** アクティブ化オプションもチェックされ、インストールされていることを確認する必要があります。 <br/> ![.NET Framework 4.5 の機能の下にある HTTP ライセンス認証オプションを示すスクリーンショット。 ](../../media/a4064fa0-fa49-4474-bd98-b9a79ff68f8b.png)HTTP ライセンス認証をインストールするには、他の機能をインストールする必要があるという追加のポップアップが表示される場合でも、心配する必要はありません。 通常は、[OK] をクリックして先に進んでください。 このポップアップが表示されていない場合は、これらの機能が既にインストールされていることを前提として、先に進んでください。  <br/> Microsoft .NET Framework は、通常、Windows Server 2012 R2 または Windows Server 2016 がインストールされている場合にインストールされます。 Skype for Business Server は、次の Microsoft .NET Framework バージョンで動作します。  <br/> • .NET 3.5  <br/> • .NET 4.5  <br/> • .NET 4.6.x  <br/> • .NET 4.7.1 (Skype for Business Server CU 5 以降のリリースの場合)  <br/> • .NET 4.7.2 (Skype for Business Server CU 6 以降のリリースの場合)  <br/>  • .NET 4.8 (Skype for Business Server CU 9 以降のリリースの場合) <br/>  .NET Framework 3.5 は、Windows Server 2008 R2 コンピューターに既定でインストールされる可能性がありますが (アップグレードする前に必ず確認してください)、実際には Windows Server 2012/Windows Server 2012 R2 サーバー上にはありません (新規インストールの場合)。 このファイルを追加するには、インストール ドライブまたはメディア (Windows Server がインストールされた場所、またはインストール ファイルの現在の場所) にアクセスする必要があります。 次に、サーバー マネージャーの機能としてインストールし、インストール メディア (具体的には **\sources\sxs** フォルダー) を指定して、確認を求め、インストールを続行します。 <br/> |
|メディア ファンデーション  <br/> |Windows Server 2016 では、Windows Server 2012 R2 Windows Server 2012 Windows Media フォーマット ランタイムが Microsoft Media Foundation と一緒にインストールされます。  <br/> 会議に使用するフロント エンド サーバーと Standard Edition サーバーはすべて、コール パーク、アナウンス、および応答グループ アプリケーションがアナウンスや音楽のために再生する Windows Media オーディオ (.wma) ファイルを Windows Media フォーマット ランタイムで実行する必要があります。  <br/> |
|Windows Identity Foundation  <br/> |Skype for Business Server 2015 のサーバー間認証シナリオをサポートするには、Windows Identity Foundation 3.5 が必要です。  <br/> • R2 Windows Server 2012 Windows Server 2012、何もダウンロードする必要はありません。 サーバー **マネージャーを開** き、次 **の役割と機能の追加ウィザード。** **Windows Identity Foundation 3.5 は** 、[機能] セクションの下に **一覧表示** されます。 チェックされている場合は、問題ない場合があります。 それ以外の場合は選択し、[次へ] をクリックして [インストール **] ボタンに移動** します。 <br/> |
|リモート サーバー管理ツール  <br/> |役割管理ツール: AD DS および LDS AD管理ツール  <br/> |
   
 **フロントエンド サーバーと Standard Edition サーバーも次の必要があります。**
  
|**ソフトウェア/役割**|**詳細**|
|:-----|:-----|
|インターネット インフォメーション サービス (IIS)  <br/> |IIS は、すべてのフロントエンド サーバーとすべての Standard Edition サーバーで必要です。次のモジュールが選択されています。  <br/> • 一般的な HTTP 機能: 既定のドキュメント、HTTP エラー、静的コンテンツ  <br/> • 正常性と診断: HTTP ログ、ログ ツール、トレース  <br/> • パフォーマンス: 静的コンテンツ圧縮、動的コンテンツ圧縮  <br/> • セキュリティ: 要求フィルター、クライアント証明書マッピング認証、Windows 認証  <br/> • アプリケーション開発: .NET Extensibility 3.5、.NET Extensibility 4.5、ASP.NET 3.5、ASP.NET 4.5、ISAPI 拡張機能、ISAPI フィルター  <br/> • 管理ツール: IIS 管理コンソール、IIS 管理スクリプト、およびツール  <br/> 匿名アクセスも必要ですが、IIS のインストール時に匿名アクセスが必要なので、一覧で選択する場所が用意されません。  <br/> |
|Windows Media フォーマット ランタイム  <br/> | Windows Server 2016、Windows Server 2012、Windows Server 2012 R2 の場合は、サーバー マネージャーに **メディア** ファンデーション機能をインストールする **必要があります**。 これで、実際にはこのインストールなしで Skype for Business Server 2015 のインストールを開始できますが、Skype for Business Server 2015 のインストールを続行する前に、インストールしてからサーバーを再起動するように求めるメッセージが表示されます。 前もって行う方が良い。 <br/> |
|Silverlight  <br/> |Silverlight の最新バージョンは、このリンクから [インストールできます](https://www.microsoft.com/silverlight/)。  <br/> |
   
> [!NOTE] 
> ロード バランサーを使用している場合は、ディレクトリ参照を有効にする必要がある場合があります。 それ以外の場合、空のページはロード バランサーが障害を考慮する可能性があるページを読み込む。 

これを自動化するために実行できる PowerShell スクリプトのサンプルを次に示します。

```PowerShell
Add-WindowsFeature NET-Framework-Core, RSAT-ADDS, Windows-Identity-Foundation, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Dir-Browsing, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, BITS, Desktop-Experience, Telnet-Client
```

> [!NOTE] 
> このコマンドは、ソース ファイルを特定の順序で検索します。 オンラインの場合、コマンドは Windows Update にアクセスします。 ただし、オフラインの場合は、コマンドでソース ファイルを使用できる状態にする必要があります。 PowerShell を使用して役割と機能をインストールする方法の[](https://technet.microsoft.com/library/hh831809.aspx)詳細については、「役割、役割サービス、または機能をインストールまたはアンインストールする」を参照してください。PowerShell コマンドを使用する場合でも、前提条件のインストール後に Windows Update を再度実行することを忘れないでください。

 **ディレクターには、次の条件も必要です。**
  
IIS。次のモジュールが選択されています。
  
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
    
  - .NET Extensibility 3.5
    
  - .NET 拡張機能 4.5
    
  - ASP.NET 3.5
    
  - ASP.NET 4.5
    
  - ISAPI 拡張機能
    
  - ISAPI フィルター
    
(疑問に思うなら、これはフロントエンド サーバーおよび Standard Edition サーバーと同じモジュール セットであり、動的コンテンツ圧縮および管理ツールは残されています)。
  
また、これには次のいくつかの PowerShell コードもあります。
  
```PowerShell
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client
```

 **常設チャット サーバーには、次の機能も必要です。**
  
メッセージ キュー (MSMQ とも呼ばれる)。 これは Windows Server コンポーネントであり、サーバー マネージャーの [機能] セクションでインストールできます。 詳細については、「メッセージ キューのインストールと管理」 [を参照してください](https://technet.microsoft.com/library/cc771474.aspx)。
  
 **最後の考え:**
  
Microsoft Internet Security and Acceleration (ISA) Server クライアント ソフトウェア、または他の Winsock Layered Service Providers (LSP) ソフトウェア (サード パーティ製のファイアウォールやウイルス対策ネットワーク検査ソフトウェアがここに含まれます) は、フロント エンド サーバーまたはスタンドアロン仲介サーバーにインストールしません。 ソフトウェアのインストール時にメディア トラフィックのパフォーマンスが低下しています。
  

