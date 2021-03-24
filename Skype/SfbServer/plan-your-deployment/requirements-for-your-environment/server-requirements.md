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
ms.openlocfilehash: d1a80fd991b8fe078f2a53d73e7f37eb66903220
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104043"
---
# <a name="server-requirements-for-skype-for-business-server-2015"></a>Skype for Business Server 2015 のサーバー要件
 
**概要:** このトピックでは、Skype for Business Server 2015 サーバーを準備します。 ハードウェア、OS、データベース、ソフトウェア、すべてのシステム要件と推奨事項は、サーバー ファームのインストールと展開を正常に行うのに役立ちます。

Active Directory、DNS、証明書などの環境要件を探している場合は [、Skype for Business Server 2015](environmental-requirements.md) ドキュメントの環境要件を確認できます。
  
ご期待の通り、Skype for Business Server 2015 の展開を開始する前に準備を行う必要があります。 この記事では、以下の計画について説明します。
  
- [Skype for Business Server 2015 のハードウェア](server-requirements.md#Hardware)
  
- [Skype for Business Server 2015 のオペレーティング システム](server-requirements.md#OS)
  
- [Skype for Business Server 2015 で動作するバック エンド データベース](server-requirements.md#DBs)
  
- [Skype for Business Server 2015 展開の前にインストールする必要があるソフトウェア](server-requirements.md#Software)
  
## <a name="hardware-for-skype-for-business-server-2015"></a>Skype for Business Server 2015 のハードウェア
<a name="Hardware"> </a>

トポロジがダウンしたので (そうしない場合は [、「Topology Basics for Skype for Business Server 2015」](../../plan-your-deployment/topology-basics/topology-basics.md) を参照してください)、次はサーバーについて考える時間です。 Skype for Business Server 2015 サーバーには、64 ビット ハードウェアが必要です。 ハードウェアに関する推奨事項を以下に示します。 これらは要件ではなく、最適なパフォーマンスに必要な要件を反映しています。 状況に応じて、これ以上必要かどうかを判断するのに役立つ容量計画のドキュメントがあります。
  
フロント エンド サーバー、バック エンド サーバー、Standard Edition サーバー、および常設チャット サーバーの推奨ハードウェア:
  
|**ハードウェア コンポーネント**|**推奨**|
|:-----|:-----|
|CPU  <br/> |64 ビット デュアル プロセッサ、16 進数コア、2.26 ギガヘルツ (GHz) 以上。  <br/> Intel Itanium プロセッサは、Skype for Business Server 2015 の役割ではサポートされていません。  <br/> |
|メモリ  <br/> |32 ギガバイト (GB)。  <br/> |
|ディスク  <br/> |いずれも：  <br/> • 少なくとも 72 GB の空きディスク領域を持つ 8 台以上の 1,0000 RPM ハード ディスク ドライブ (RAID 1 と RAID 10 を使用して RAID 1 と 6 を使用するディスクの 2 つ)。  <br/> OR  <br/> • ソリッド ステート ドライブ (SSD) は、8 10000 RPM のメカニカル ディスク ドライブと同じ空き領域と同様のパフォーマンスを提供できます。  <br/> |
|ネットワーク  <br/> |1 つのデュアル ポート ネットワーク アダプター、1 Gbps 以上 (2 つのネットワーク アダプターを使用できますが、単一の MAC アドレスと 1 つの IP アドレスでチーム化する必要があります)。  <br/> デュアルまたはマルチホーム構成は、フロントエンドサーバー、バック エンド サーバー、Standard Edition サーバー、および常設チャット サーバーではサポートされていません。 <br/> オペレーティング システムに公開され、サーバー ハードウェアの監視と管理に使用されている限り、DRAC や ILO などの帯域外管理システムを使用できます。 このシナリオは、マルチホーム サーバーを構成するのではありません。サポートされています。  <br/> |
   
エッジ サーバー、スタンドアロン仲介サーバー、ビデオ相互運用サーバー、およびディレクターの推奨ハードウェア:
  
|**ハードウェア コンポーネント**|**推奨**|
|:-----|:-----|
|CPU  <br/> |64 ビット デュアル プロセッサ、クアッド コア、2.26 ギガヘルツ (GHz) 以上。  <br/> Intel Itanium プロセッサは、Skype for Business Server 2015 の役割ではサポートされていません。  <br/> |
|メモリ  <br/> |16 ギガバイト。  <br/> |
|ディスク  <br/> |いずれも：  <br/> • 少なくとも 72 GB の空きディスク領域を持つ 4 台以上の 1,0000 RPM ハード ディスク ドライブ (ディスクは 2x RAID 1 構成にする必要があります)。  <br/> OR  <br/> • ソリッド ステート ドライブ (SSD) は、4 台の 10000 RPM メカニカル ディスク ドライブと同じ空き領域と同様のパフォーマンスを提供できます。  <br/> |
|ネットワーク  <br/> |1 つのデュアル ポート ネットワーク アダプター、1 Gbps 以上 (2 つのネットワーク アダプターを使用できますが、単一の MAC アドレスと 1 つの IP アドレスでチーム化する必要があります)。  <br/> ビデオ相互運用機能サーバーとディレクターでは、デュアルまたはマルチホーム構成はサポートされていません。 <br/> エッジ サーバーには、デュアル ポート ネットワーク アダプターである 2 つのネットワーク インターフェイスが必要です。1 Gbps 以上 (または 2 つのペアのネットワーク アダプター、合計 4 つのペアで、各ペアが 1 つの MAC アドレスと 1 つの IP アドレスでチーム化され、合計 2 組)。  <br/> スタンドアロン仲介サーバーでは、特定の PSTN IP アドレスの構成を許可する追加のネットワーク インターフェイス カード (NIC) のインストールがサポートされています。  <br/> |
   
## <a name="operating-systems-for-skype-for-business-server-2015"></a>Skype for Business Server 2015 のオペレーティング システム
<a name="OS"> </a>

ハードウェアをインストールしたら、オペレーティング システム (OS) をインストールする必要があります。 これらは、Skype for Business Server 2015 をインストールして正常に使用できる OS です。
  
|||
|:-----|:-----|
|Windows Server 2019 (Skype for Business 累積的な更新プログラム 9 以降が必要です)。 <br/> |Windows Server 2016 (Skype for Business 累積的な更新プログラム 5 以降が必要です。 詳細については [、KB4015888 を確認してください](https://support.microsoft.com/help/4015888/how-to-install-skype-for-business-server-2015-on-windows-server-2016)。  <br/> ||
|Windows Server 2012更新プログラムがインストールされている R2 データセンター OS を使用します。  <br/> |Windows Server 2012更新プログラムがインストールされた R2 Standard OS を使用します。  <br/> |
|Windows Server 2012更新プログラムがインストールされたデータセンター OS を使用します。  <br/> |Windows Server 2012更新プログラムがインストールされた標準 OS を使用します。  <br/> |
   
この一覧に含まれなかった場合は、正しく動作しません。Skype for Business Server 2015 の新しいインストールでは試してみないで下さい。

> [!NOTE]
> OS の一時アップグレードは、Lync Server 2013 ではサポートされていません。 別のプールを展開し、別の OS を使用して新しいプールにユーザーを移行する必要があります。 プール内のすべてのサーバーに同じ OS バージョンが必要です。
  
> [!NOTE]
> このリストにWindows Server 2008 R2が見当たっている可能性があります。 これは、SFB に使用Windows Server 2012すべての新しいサーバーに対して R2 を使用することをお勧めします。 Lync Server 2013 が既にインストールされている既存のサーバーがインストールされている場合にのみ、Windows Server 2008 R2 を使用する必要があります。 Windows Server 2008 R2 2015 年 1 月 13 日にメインストリーム サポート ライフサイクルの終わりに達し、2020 年 1 月 14 日にサポート ライフサイクルの終了に達します。
  
最新のサービス パックに加えて、次の更新プログラムが適切な場所にインストールされていることを確認する必要があります。
  
- このWindows Server 2012、アップグレードの前に KB 記事 2858668 をインストールする必要があります。 [ここで取得します](https://support.microsoft.com/kb/2858668/)。
    
- R2 をインストールWindows Server 2012アップグレードする前に、KB 記事 2982006 をインストールしてください。 [これは、ここで見つかりました](https://support.microsoft.com/kb/2982006/).
    
- [メモ] ボックスでWindows Server 2008 R2する場合は、最初に KB 記事 2533623 をインストールします。 [これは、このリンクです](https://support.microsoft.com/kb/2533623/)。
    
## <a name="back-end-databases-that-will-work-with-skype-for-business-server-2015"></a>Skype for Business Server 2015 で動作するバック エンド データベース
<a name="DBs"> </a>


Skype for Business Server 2015 Standard Edition をインストールすると、SQL Server 2014 Express (64 ビット 版) も自動的にインストールされます。
  
Skype for Business Server 2015 Enterprise Edition はもう少し複雑ですが、サポートされている一覧は以下のとおりです (すべてが 64 ビット 版です。32 ビット エディションは使用しません)。
  
||||||
|:-----|:-----|:-----|:-----|:-----|
|Microsoft SQL Server 2019 Enterprise (64 ビット 版) を使用し、最新のサービス パックを使用して実行することをお勧めします。 <br/> |Microsoft SQL Server 2017 Enterprise (64 ビット 版) を使用し、最新のサービス パックを使用して実行することをお勧めします。 <br/> |Microsoft SQL Server 2016 Enterprise (64 ビット 版) を Service Pack 1 以降で実行し、Skype for Business 累積的な更新プログラム 7 以降で実行する必要があります[(Skype for Business](https://support.microsoft.com/help/3061064)累積的な更新プログラムのダウンロード)。  <br/> |Microsoft SQL Server 2014 Enterprise (64 ビット 版) を使用し、累積的な更新プログラム 6 以降で実行する必要があります (累積的な更新[プログラム 6](https://support.microsoft.com/kb/3031047/)をダウンロードします)。  <br/> |Microsoft SQL Server 2012 Enterprise (64 ビット 版) を使用し、最新のサービス パックを使用して実行することをお勧めします。  <br/> |
|Microsoft SQL Server 2019 Standard (64 ビット 版) を使用し、最新のサービス パックを使用して実行することをお勧めします。 <br/> |Microsoft SQL Server 2017 Standard (64 ビット 版) を使用し、最新のサービス パックを使用して実行することをお勧めします。 <br/> |Microsoft SQL Server 2016 Standard (64 ビット 版) を Service Pack 1 以降で使用し、Skype for Business 累積的な更新プログラム 7 以降で実行する必要があります[(Skype for Business 累積的](https://support.microsoft.com/help/3061064)な更新プログラムをダウンロード)。  <br/> |Microsoft SQL Server 2014 Standard (64 ビット 版) を使用し、累積的な更新プログラム 6 以降で実行する必要があります (累積的な更新[プログラム 6](https://support.microsoft.com/kb/3031047/)をダウンロード)。  <br/> |Microsoft SQL Server 2012 Standard (64 ビット 版) を使用し、最新のサービス パックを使用して実行することをお勧めします。  <br/> |
   
ここで使用するエディションSQL Server表示しない場合は、使用することはできません。
  
- また、監視サーバーの役割用にレポート SQL Serverをインストールする必要もあります。
- 接続がSQL場合、Skype for Business フロントエンドへの接続はローカルであり、低速リンクでは接続しない必要があります。 
- 2 つSQLプール間でのバック エンドの共有はサポートされていません。

### <a name="microsoft-exchange-storage"></a>Microsoft Exchange ストレージ
PowerPoint プレゼンテーションなどの会議コンテンツ ファイルは、添付ファイルとしてアーカイブされます。 Exchange コンプライアンス データを使用して Skype for Business アーカイブ データを格納する場合は、Exchange の展開に Exchange を使用し、最大記憶域サイズが会議コンテンツ ファイルのストレージをサポートしている必要があります。 Microsoft Exchange 統合オプションを使用してアーカイブを展開および有効化する前に、Exchange を展開する必要があります。 
    
    If you choose to use Exchange storage, you do not need to deploy separate SQL Server databases for archiving, unless you have Skype for Business users who are not homed on your Exchange servers. If you deploy archiving using the Microsoft Exchange integration option, Skype for Business archive data is stored with Exchange compliance data only for the users who are homed on your Exchange servers. 
  
## <a name="hardware-and-software-requirements-for-archiving-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 でのアーカイブのハードウェアとソフトウェアの要件
  
アーカイブは定義されたサーバーの役割ではなく、アーカイブ用に別のサーバーをインストールする必要があります。 統合データ収集エージェントは、すべての Enterprise Edition フロントエンド プールとすべての Standard Edition Server に自動的にインストールされ、アクティブ化されます。 トポロジ ビルダーを使用してアーカイブ トポロジを有効にして公開する必要があります。
    
アーカイブでは、Skype for Business Server ファイル ストレージを使用して会議コンテンツ ファイルを一時的に保存しますので、アーカイブ用に別のファイル ストアを設定しません。
    
Microsoft メッセージ キューは必須ではありません。
    
ストレージをアーカイブするインフラストラクチャをセットアップする必要があります。 これには、Exchange ストレージまたはアーカイブ ストレージの選択が含SQL Server。   Skype for Business Server アーカイブ インフラストラクチャ要件は、Skype for Business Server の展開と同じです。 詳細については [、「Skype for Business 環境の要件」を参照してください](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md)。 
  
> [!NOTE]
> Exchange サーバーにホームではないユーザーをサポートするには、または Microsoft Exchange 統合オプションを使用しない場合は、64 ビット のデータベースを使用してアーカイブ ストレージを展開SQL Serverがあります。 
    
アーカイブを展開および有効化する前SQL Serverプラットフォームをセットアップする必要があります。 トポロジの公開に使用するアカウントに適切な管理権限とアクセス許可がある場合、トポロジを公開するときにアーカイブ データベース (LcsLog) を作成できます。 インストール手順の一部として、データベースを後で作成することもできます。 詳細については、SQL Serverドキュメント [をSQL Serverしてください](/sql/sql-server/)。
    
アーカイブの負荷が大きい場合があります。 したがって、アーカイブが有効になっているフロント エンド サーバーのディスク領域が十分に確保されている必要があります。

### <a name="sql-mirroring-sql-clustering-and-sql-always-on"></a>SQL ミラーリング、SQLクラスタリング、および Always On SQLの設定

Skype for Business Server 2015 SQLミラーリングまたはSQLクラスタリングを使用できます。サポートされています。 SQL Skype for Business Server トポロジ ビルダーを介してミラーリングをセットアップします。 クラスター化のセットアップをSQL場合は、この設定を使用SQL Server。
  
サポートされているのと同様に、SQLのアクティブ/パッシブ構成を使用してください。 パッシブ ノードを他のインスタンスと共有SQLします。
  
フェールオーバー クラスタリングには、次の機能を使用できます。
  
2 ノード:
  
- Microsoft SQL Server 2019 Standard (64 ビット 版) を使用し、最新のサービス パックを使用して実行することをお勧めします。

- Microsoft SQL Server 2017 Standard (64 ビット 版) を使用し、最新のサービス パックを使用して実行することをお勧めします。

- Microsoft SQL Server 2016 Standard (64 ビット 版) と Service Pack 1 以降。 最新のサービス パックを使用して実行することをお勧めします。

- Microsoft SQL Server 2014 Standard (64 ビット 版) を使用し、最新のサービス パックを使用して実行することをお勧めします。
    
-  Microsoft SQL Server 2012 Standard (64 ビット 版) を使用し、最新のサービス パックを使用して実行することをお勧めします。

16 ノード:

- Microsoft SQL Server 2019 Enterprise (64 ビット 版) を使用し、最新のサービス パックを使用して実行することをお勧めします。

- Microsoft SQL Server 2017 Enterprise (64 ビット 版) を使用し、最新のサービス パックを使用して実行することをお勧めします。

- Microsoft SQL Serverパック 1 以降の 2016 Enterprise (64 ビット 版) を使用します。 最新のサービス パックを使用して実行することをお勧めします。
  
- Microsoft SQL Server 2014 Enterprise (64 ビット 版) を使用し、最新のサービス パックを使用して実行することをお勧めします。
    
- Microsoft SQL Server 2012 Enterprise (64 ビット 版) を使用し、最新のサービス パックを使用して実行することをお勧めします。

> [!IMPORTANT]
> アップグレードの場合は、アップグレード前にフロント エンド サーバーに少なくとも 2012 SP1 SQL Serverがインストールされていることを確認する必要があります。 [すぐにダウンロードする場合](https://www.microsoft.com/download/details.aspx?id=35575) は、SP1 へのリンクを次に示します。
  
ミラーリングの詳細を読むSQL、Skype for Business Server 2015 の「バック エンド サーバーの高可用性」を参照してください。 Skype SQL Server 2015 のクラスター化を構成するには、クラスタリングの準備を行う手順があります。 また[、2014、2012、および 2008](/sql/sql-server/failover-clusters/install/sql-server-failover-cluster-installation)[](/previous-versions/sql/sql-server-2012/hh231721(v=sql.110))のSQLフェールオーバー クラスタリングに関するリンクも[追加されています](/previous-versions/sql/sql-server-2008-r2/ms189134(v=sql.105))。
  
> [!NOTE]
> 2015 リリースの新機能は、Always On SQLサポートです。 この機能はサポートされています。詳細については [、「Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md) のバック エンド サーバーの高可用性」を参照してください。

> [!NOTE]
> SQLミラーリングは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。 AlwaysOn 可用性グループ、AlwaysOn フェールオーバー クラスター インスタンス (FCI)、および SQL フェールオーバー クラスタリング方法は、Skype for Business Server 2019 で優先されます。  

## <a name="software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment"></a>Skype for Business Server 2015 展開の前にインストールする必要があるソフトウェア
<a name="Software"> </a>

Skype for Business Server 2015 を実行しているサーバーに対してインストールまたは構成する必要があるものがあります。以下に示します。 その後、特定のサーバー の役割に対する追加の要件が適用されます。

  
 **すべてのサーバー:**
  
|**ソフトウェア/役割**|**詳細**|
|:-----|:-----|
|Windows PowerShell 3.0  <br/> |すべての Skype for Business Server サーバーには、Windows PowerShell 3.0 がインストールされている必要があります。  <br/> • R2 または R2 Windows Server 2012または Windows Server 2012でインストールを実行している場合は、既にインストール済みなので、設定されています。  <br/> • アップグレードを実行している場合は、Windows Server 2008 R2 [3.0](https://www.microsoft.com/download/details.aspx?id=34595) Windows Management Frameworkダウンロードして取得できます。 <br/> **ヒント:** 正しい PowerShell がインストールされたら、PowerShell プロンプトにアクセスして入力して、ビルドバージョン 6.2.9200.0 以降を確認します `$PSVersionTable` 。 これにより、必要な情報が表示されます。  <br/> |
|Microsoft .NET Framework  <br/> |WCF サービスは **、Windows 機能** としてインストールされる機能で、サーバー マネージャー **の下では**、ダウンロードは不要です。 <br/> • この機能をインストールする場合、または既にインストール済みで確認している場合は、次のように **HTTP ライセンス** 認証オプションもチェックおよびインストールされていることを確認する必要があります。 <br/> ![[4.5 機能] の下.NET Framework HTTP ライセンス認証オプションを示すスクリーンショット。 ](../../media/a4064fa0-fa49-4474-bd98-b9a79ff68f8b.png)HTTP ライセンス認証をインストールするには、他に何かインストールする必要があるというポップアップが表示される場合は、心配しないでください。 通常は、[OK] をクリックして先に進んでください。 このポップアップが表示されていない場合は、それらのポップアップが既にインストールされていることを前提として、先に進んでください。  <br/> Microsoft .NET Framework R2 または Windows Server 2016 のインストール時Windows Server 2012通常インストールされます。 Skype for Business Server は、次の Microsoft .NET Frameworkで動作します。  <br/> • .NET 3.5  <br/> • .NET 4.5  <br/> • .NET 4.6.x  <br/> • .NET 4.7.1 (Skype for Business Server CU 5 以降のリリース)  <br/> • .NET 4.7.2 (Skype for Business Server CU 6 以降のリリース)  <br/>  • .NET 4.8 (Skype for Business Server CU 9 以降のリリース) <br/>  .NET Framework 3.5 は、Windows Server 2008 R2 コンピューターに既定でインストールされる可能性があります (アップグレードする前に必ず確認してください)、実際には Windows Server 2012/Windows Server 2012 R2 サーバーにはインストールされません (新しいインストールの場合)。 それを追加するには、インストール ドライブまたはメディア (Windows Server がインストールされた場所、またはインストール ファイルの現在の場所) にアクセスする必要があります。 次に、サーバー マネージャーから機能としてインストールし、それを求めるときにインストール メディア (特に **\sources\sxs** フォルダー) をポイントし、インストールを続行します。 <br/> |
|Media Foundation  <br/> |Windows Server 2016 では、R2 Windows Server 2012およびWindows Server 2012 Windows Media Format ランタイムが Microsoft Media Foundation と一緒にインストールされます。  <br/> 会議に使用されるすべてのフロントエンド サーバーと Standard Edition サーバーでは、通話パーク、アナウンス、および応答グループ アプリケーションがアナウンスや音楽のために再生する Windows Media Audio (.wma) ファイルを Windows Media Format ランタイムで実行する必要があります。  <br/> |
|Windows Identity Foundation  <br/> |Skype for Business Server 2015 のサーバー間認証シナリオをサポートするには、Windows Identity Foundation 3.5 が必要です。  <br/> • R2 Windows Server 2012およびWindows Server 2012、何もダウンロードする必要はありません。 サーバー **マネージャーを開** き、サーバー マネージャーに **移動役割と機能の追加ウィザード。** **Windows Identity Foundation 3.5 は** 、[機能] セクションの下に **一覧表示** されます。 チェックされている場合は、良い方法です。 それ以外の場合は、それを選択し、[次へ] をクリックして [インストール] **ボタンに移動** します。 <br/> |
|リモート サーバー管理ツール  <br/> |役割管理ツール: DS AD LDS AD使用する  <br/> |
   
 **フロントエンド サーバーと Standard Edition サーバーにも、次の機能が必要です。**
  
|**ソフトウェア/役割**|**詳細**|
|:-----|:-----|
|インターネット インフォメーション サービス (IIS)  <br/> |IIS は、すべてのフロント エンド サーバーとすべての Standard Edition サーバーで必要とされ、次のモジュールが選択されています。  <br/> • 一般的な HTTP 機能: 既定のドキュメント、HTTP エラー、静的コンテンツ  <br/> • 正常性と診断: HTTP ログ、ログ ツール、トレース  <br/> • パフォーマンス: 静的コンテンツ圧縮、動的コンテンツ圧縮  <br/> • セキュリティ: 要求フィルター、クライアント証明書マッピング認証、Windows 認証  <br/> • アプリケーション開発: .NET 拡張機能 3.5、.NET 拡張機能 4.5、ASP.NET 3.5、ASP.NET 4.5、ISAPI 拡張機能、ISAPI フィルター  <br/> • 管理ツール: IIS 管理コンソール、IIS 管理スクリプト、およびツール  <br/> 匿名アクセスも必要ですが、IIS をインストールするときにそれを取得する必要があります。そのため、一覧で選択する場所が用意されません。  <br/> |
|Windows Media フォーマット ランタイム  <br/> | Windows Server 2016、Windows Server 2012、Windows Server 2012 R2 の場合は、Media **Foundation** 機能をサーバー マネージャーにインストールする **必要があります**。 これで、Skype for Business Server 2015 のインストールをこのインストールなしで実際に開始できますが、Skype for Business Server 2015 のインストールが続行される前に、インストールしてサーバーを再起動するように求めるメッセージが表示されます。 前もって行う方が良いです。 <br/> |
|Silverlight  <br/> |Silverlight の最新バージョンは、このリンクから [インストールできます](https://www.microsoft.com/silverlight/)。  <br/> |
   
> [!NOTE] 
> ロード バランサーを使用している場合は、ディレクトリ参照を有効にする必要がある場合があります。 それ以外の場合は、空のページがロードされ、ロード バランサーで障害が発生したと見なされる可能性があります。 

これを自動化するために実行できる PowerShell スクリプトの例を次に示します。

```PowerShell
Add-WindowsFeature NET-Framework-Core, RSAT-ADDS, Windows-Identity-Foundation, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Dir-Browsing, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, BITS, Desktop-Experience, Telnet-Client
```

> [!NOTE] 
> コマンドは、ソース ファイルを特定の順序で検索します。 オンラインの場合、コマンドは Windows Update にアクセスします。 ただし、オフラインの場合は、ソース ファイルをコマンドで使用できる状態にする必要があります。 PowerShell を使用して役割と機能をインストールする方法の[](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831809(v=ws.11))詳細については、「役割、役割サービス、機能のインストールまたはアンインストール」を参照してください。PowerShell コマンドを使用する場合でも、前提条件をインストールした後に Windows Update を再度実行することを忘れないでください。

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
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client
```

 **常設チャット サーバーには、次の機能も必要です。**
  
MSMQ とも呼ばれるメッセージ キュー。 これは Windows Server コンポーネントであり、サーバー マネージャーの [機能] セクションでインストールできます。 詳細については、「メッセージ キューのインストールと管理」 [を参照してください](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc771474(v=ws.11))。
  
 **最後の考え:**
  
Microsoft Internet Security and Acceleration (ISA) Server クライアント ソフトウェア、または他の Winsock Layered Service Providers (LSP) ソフトウェア (サード パーティ製のファイアウォールやウイルス対策ネットワーク検査ソフトウェアがここに含まれる) を、フロントエンド サーバーまたはスタンドアロン仲介サーバーにインストールしなけらばならな。 そのソフトウェアのインストール時にメディア トラフィックのパフォーマンスが低下しています。
