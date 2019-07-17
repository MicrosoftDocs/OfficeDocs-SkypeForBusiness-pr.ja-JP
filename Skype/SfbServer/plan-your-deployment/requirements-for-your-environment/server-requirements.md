---
title: Skype for Business Server 2015 のサーバー要件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 8d47b242-b93d-4c2e-a658-23b78bca30b1
description: '概要: このトピックを使用して、Skype for Business Server 2015 サーバーを準備します。 ハードウェア、OS、データベース、ソフトウェア、すべてのシステム要件と推奨事項は、サーバーファームのインストールと展開を成功させるのに役立ちます。'
ms.openlocfilehash: 368c719ac4e61b62ab4c52c50433bf6cc996c886
ms.sourcegitcommit: c554b09527817dc3e06b10509f6668b42ccc5cb9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/17/2019
ms.locfileid: "35758950"
---
# <a name="server-requirements-for-skype-for-business-server-2015"></a>Server requirements for Skype for Business Server 2015
 
**概要:** このトピックを使用すると、Skype for Business Server 2015 サーバーを準備することができます。ここにはハードウェア、OS、データベース、ソフトウェア、すべてのシステム要件と推奨が掲載されており、サーバー ファームのインストールと展開を正常に実行できるようになります。

Active Directory、DNS、証明書などの環境要件を探している場合は、 [Skype For Business Server 2015 ドキュメントの環境要件](environmental-requirements.md)を確認できます。
  
Skype for Business Server 2015 の展開を開始する前に、いくつかの準備を行う必要があります。 この記事では次の計画について、順を追って説明します。
  
- [Skype for Business Server 2015 のハードウェア](server-requirements.md#Hardware)
  
- [Skype for Business Server 2015 のオペレーティングシステム](server-requirements.md#OS)
  
- [Skype for Business Server 2015 で動作するバックエンド データベース](server-requirements.md#DBs)
  
- [Skype for Business Server 2015 の展開前にインストールすべきソフトウェア](server-requirements.md#Software)
  
## <a name="hardware-for-skype-for-business-server-2015"></a>Skype for Business Server 2015 のハードウェア
<a name="Hardware"> </a>

トポロジを下げている場合 ( [Skype For Business Server 2015 トピックのトポロジの基礎](../../plan-your-deployment/topology-basics/topology-basics.md)を確認できます)、サーバーについて考えてみましょう。 Skype for Business Server 2015 サーバーには、64ビットのハードウェアが必要です。 推奨されるハードウェアをこの後に示します。 これらは必須ではありませんが、最適なパフォーマンスを得るために必要な要件を反映しています。 状況に応じて、これを超えるものが必要であるかどうかの判断に役立つ、処理能力の計画に関するドキュメントも用意されています。
  
フロントエンドサーバー、バックエンドサーバー、標準エディションサーバー、および常設チャットサーバーに推奨されるハードウェア:
  
|**ハードウェア コンポーネント**|**推奨**|
|:-----|:-----|
|CPU  <br/> |64 ビット デュアル プロセッサ、6 コア、2.26 GHz 以上。  <br/> Skype for Business Server 2015 ロールでは、Intel Itanium プロセッサはサポートされていません。  <br/> |
|メモリ  <br/> |32 ギガバイト (GB)  <br/> |
|ディスク  <br/> |次のいずれか:  <br/> • 1万 RPM 以上のハードディスクドライブ (少なくとも 72 GB のディスク空き容量 (RAID 10 を使用している2台のディスクと、RAID 10 を使用した6個のディスク)  <br/> または  <br/> •ソリッドステートドライブ (Ssd) では、8 1万 RPM 機械的ディスクドライブと同じ空き領域と同様のパフォーマンスを提供できます。  <br/> |
|ネットワーク  <br/> |1 Gbps 以上のデュアルポート ネットワーク アダプター 1 つ (2 つのネットワーク アダプターを使用できるが、その場合は 1 つの MAC アドレスと 1 つの IP アドレスのチーミングが必要)。  <br/> フロントエンドサーバー、バックエンドサーバー、標準エディションサーバー、常設チャットサーバーでは、デュアルホーム構成またはマルチホーム構成はサポートされ**ません**。 <br/> オペレーティング システムに公開されて、サーバー ハードウェアの監視と管理に使用されていない限り、DRAC や ILO などのアウト オブ バンド管理システムを持つことができます。このシナリオは、マルチ ホーム サーバーの構成要素ではなく、サポートされています。<br/> |
   
エッジサーバー、スタンドアロン仲介サーバー、ビデオ相互運用サーバー、およびディレクターに推奨されるハードウェア:
  
|**ハードウェア コンポーネント**|**推奨**|
|:-----|:-----|
|CPU  <br/> |64 ビット デュアル プロセッサ、クアッド コア、2.26 GHz 以上  <br/> Skype for Business Server 2015 ロールでは、Intel Itanium プロセッサはサポートされていません。  <br/> |
|メモリ  <br/> |16 GB  <br/> |
|ディスク  <br/> |次のいずれか:  <br/> • 4 GB 以上の 1万 RPM ハードディスクドライブ (少なくとも 72 GB の空きディスク領域が必要です (ディスクは2倍の RAID 1 構成にする必要があります)。  <br/> または  <br/> •ソリッドステートドライブ (Ssd) では、4 1万 RPM 機械的ディスクドライブと同じ空き領域と同様のパフォーマンスを提供できます。  <br/> |
|ネットワーク  <br/> |1 Gbps 以上のデュアルポート ネットワーク アダプター 1 つ (2 つのネットワーク アダプターを使用できるが、その場合は 1 つの MAC アドレスと 1 つの IP アドレスのチーミングが必要)。  <br/> ビデオ相互運用サーバーとディレクターでは、デュアルホーム構成またはマルチホーム構成はサポートされ**ません**。 <br/> エッジ サーバーには、1 Gbps 以上のデュアルポート ネットワーク アダプターである 2 つのネットワーク インターフェイス (つまり 2 ペア (合計 4 つ) のネットワーク アダプター。この合計 2 つのペアでは、各ペアが 1 つの MAC アドレスと 1 つの IP アドレスでチームになっている) が必要です。  <br/> スタンドアロンの仲介サーバーでは、特定の PSTN IP アドレスの構成を許可するために、追加のネットワークインターフェイスカード (Nic) をインストールすることがサポートされています。  <br/> |
   
## <a name="operating-systems-for-skype-for-business-server-2015"></a>Skype for Business Server 2015 のオペレーティングシステム
<a name="OS"> </a>

ハードウェアを用意したら、オペレーティングシステム (OS) をインストールする必要があります。 以下は、Skype for Business Server 2015 をインストールして正常に使用できるようにする OS です。
  
|||
|:-----|:-----|
|Windows Server 2019 (Skype for Business の累積更新プログラム9以降が必要です)。 <br/> |Windows Server 2016 (Skype for Business の累積更新プログラム5以降が必要です。 詳細については、 [KB4015888](https://support.microsoft.com/en-gb/help/4015888/how-to-install-skype-for-business-server-2015-on-windows-server-2016)を参照してください)  <br/> ||
|必須の更新プログラムがすべてインストールされている Windows Server 2012 R2 Datacenter OS。  <br/> |必要な更新プログラムがすべてインストールされている Windows Server 2012 R2 Standard OS。  <br/> |
|必要な更新プログラムがすべてインストールされている Windows Server 2012 Datacenter OS。  <br/> |必須の更新プログラムがすべてインストールされている Windows Server 2012 Standard OS。  <br/> |
   
このリストにない場合は、正常に動作しません。 Skype for Business Server 2015 の新しいインストールでは試してください。
  
> [!NOTE]
> Windows Server 2008 R2 がこの一覧に表示されない場合があります。 これは、すべての新しいサーバーが SFB に使用されるように Windows Server 2012 R2 を推奨するためです。 既存のサーバーに Lync Server 2013 がインストールされている場合にのみ、Windows Server 2008 R2 を使用する必要があります。これは、インプレースアップグレードを実行することを目的としています。 Windows Server 2008 R2 は、1/13/2015 のメインストリームサポートライフサイクルの終わりに達しました。これは、1/14/2020 のサポートライフサイクルの終わりに到達します。
  
最新のサービス パック以外にも、関連性がある場合は次の更新プログラムをインストールする必要があります。
  
- Windows Server 2012 では、アップグレードの前に、サポート技術情報 2858668 の更新プログラムをインストールする必要があります。 [こちらからダウンロードして](https://support.microsoft.com/en-us/kb/2858668/)ください。
    
- Windows Server 2012 R2 を使用している場合は、アップグレードの前に、サポート技術情報 2982006 の更新プログラムをインストールしてください。 [こちらをご覧](https://support.microsoft.com/en-us/kb/2982006/)ください。
    
- Windows Server 2008 R2 ボックス上でアップグレードする場合は (前述の注意事項を参照)、まずサポート技術情報 2533623 の更新プログラムをインストールする必要があります。 [これはこのリンク](https://support.microsoft.com/en-us/kb/2533623/)です。
    
## <a name="back-end-databases-that-will-work-with-skype-for-business-server-2015"></a>Skype for Business Server 2015 で動作するバックエンド データベース
<a name="DBs"> </a>

Skype for Business Server 2015 Standard Edition をインストールすると、SQL Server 2014 Express (64 ビット版) が自動的にインストールされます。
  
Skype for Business Server 2015 Enterprise Edition は少し複雑ですが、サポートされている一覧は以下のとおりです (すべては64ビット版ですが、32ビットエディションは使用しないでください)。
  
||||||
|:-----|:-----|:-----|:-----|:-----|
|Microsoft SQL Server 2019 Enterprise (64 ビット版)、最新の service pack を使用して実行することをお勧めします。 <br/> |Microsoft SQL Server 2017 Enterprise (64 ビット版)、最新の service pack を使用して実行することをお勧めします。 <br/> |Microsoft SQL Server 2016 Enterprise (64 ビット版) Service Pack 1 以降を使用して、Skype for Business の累積更新プログラム7以降で実行する必要があります ([skype For Business 累積更新プログラムをダウンロード](https://support.microsoft.com/en-us/help/3061064)してください)。  <br/> |Microsoft SQL Server 2014 Enterprise (64 ビット版)、累積更新プログラム6以降を実行する必要があります ([累積更新プログラム6をダウンロード](https://support.microsoft.com/en-us/kb/3031047/)してください)。  <br/> |Microsoft SQL Server 2012 Enterprise (64 ビット版)、最新の service pack を使用して実行することをお勧めします。  <br/> |
|Microsoft SQL Server 2019 Standard (64 ビット版)、最新のサービスパックを使用して実行することをお勧めします。 <br/> |Microsoft SQL Server 2017 Standard (64 ビット版)、最新のサービスパックを使用して実行することをお勧めします。 <br/> |Microsoft SQL Server 2016 Standard (64 ビット版) Service Pack 1 以降がインストールされています。 Skype for Business 累積更新プログラム7以降で実行する必要があります ([skype For Business 累積更新プログラムをダウンロード](https://support.microsoft.com/en-us/help/3061064)してください)。  <br/> |Microsoft SQL Server 2014 Standard (64 ビット版)、累積更新プログラム6以降を実行する必要があります ([累積更新プログラム6をダウンロード](https://support.microsoft.com/en-us/kb/3031047/)してください)。  <br/> |Microsoft SQL Server 2012 Standard (64 ビット版)、最新のサービスパックを使用して実行することをお勧めします。  <br/> |
   
使用したい SQL Server エディションがここに表示されていない場合は、使用できません。
  
> [!NOTE]
> また、監視サーバーの役割の SQL Server Reporting Services をインストールする必要もあります。

### <a name="microsoft-exchange-storage"></a>Microsoft Exchange ストレージ
Meeting content files, such as PowerPoint presentations, are archived as attachments. Skype for Business アーカイブデータを Exchange のコンプライアンスデータと共に保存する場合は、exchange を exchange に展開して、最大記憶域サイズが会議コンテンツファイルのストレージをサポートしていることを確認する必要があります。 Microsoft Exchange 統合オプションを使用して、アーカイブを展開して有効にする前に、Exchange を展開する必要があります。 
    
    If you choose to use Exchange storage, you do not need to deploy separate SQL Server databases for archiving, unless you have Skype for Business users who are not homed on your Exchange servers. If you deploy archiving using the Microsoft Exchange integration option, Skype for Business archive data is stored with Exchange compliance data only for the users who are homed on your Exchange servers. 
  
## <a name="hardware-and-software-requirements-for-archiving-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 のアーカイブに関するハードウェアおよびソフトウェア要件
  
アーカイブは定義されたサーバーの役割ではなく、アーカイブ用に個別のサーバーをインストールする必要はありません。 統合されたデータ収集エージェントは、すべての Enterprise Edition フロントエンドプールおよびすべての Standard Edition サーバーに自動的にインストールされ、ライセンス認証されます。 トポロジ ビルダーを使用して、アーカイブ トポロジを有効にして発行する必要があります。
    
アーカイブでは、会議コンテンツファイルを一時的に保存するために Skype for Business Server ファイルストレージを使用するため、アーカイブ用に別のファイルストアを設定する必要はありません。
    
Microsoft メッセージキューは必要ありません。
    
アーカイブ ストレージ用のインフラストラクチャを設定する必要があります。 これには、SQL Server を使用した Exchange またはアーカイブストレージの選択が含まれます。   Skype for Business Server のアーカイブインフラストラクチャの要件は、Skype for Business Server の展開の場合と同じです。 詳細については、「 [Skype For business 環境の要件](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md)」を参照してください。 
  
> [!NOTE]
> Exchange server を使用していないユーザーをサポートする場合、または Microsoft Exchange の統合オプションを使用しない場合は、64ビットの SQL Server データベースを使用してアーカイブストレージを展開する必要があります。 
    
アーカイブを展開して有効にする前に、SQL Server プラットフォームをセットアップする必要があります。 トポロジの公開に使用するアカウントに適切な管理権限とアクセス許可がある場合、トポロジを公開するときにアーカイブ データベース (LcsLog) を作成できます。 インストール手順の一部を含め、データベースを後で作成することもできます。 SQL Server の詳細については、 [Sql server のマニュアル](https://go.microsoft.com/fwlink/p/?linkID=129045)を参照してください。
    
アーカイブに関する負荷の増加は、重大な問題になる可能性があります。 そのため、アーカイブが有効になっているフロントエンドサーバーでは、ディスクの空き容量が十分であることを確認する必要があります。

### <a name="sql-mirroring-sql-clustering-and-sql-always-on"></a>SQL ミラーリング、SQL クラスタリング、および SQL AlwaysOn

Skype for Business Server 2015 で SQL ミラーリングまたは SQL クラスタリングを使用できますが、サポートされています。 SQL ミラーリングは、Skype for Business Server トポロジビルダーを通じて設定されます。 SQL クラスタリングのセットアップを意図している場合は、SQL Server で行います。
  
サポートされているため、SQL クラスタリング用のアクティブ/パッシブ構成があることを確認してください。 パッシブノードを他の SQL インスタンスと共有しないでください。
  
フェールオーバー クラスタリングでは、次の OS を使用できます。
  
2 ノードの場合:
  
- Microsoft SQL Server 2019 Standard (64 ビット版)、最新のサービスパックを使用して実行することをお勧めします。

- Microsoft SQL Server 2017 Standard (64 ビット版)、最新のサービスパックを使用して実行することをお勧めします。

- Microsoft SQL Server 2016 Standard (64 ビット版)、Service Pack 1 以降。 最新のサービスパックを使用して実行することをお勧めします。

- Microsoft SQL Server 2014 Standard (64 ビット版)、最新のサービスパックを使用して実行することをお勧めします。
    
-  Microsoft SQL Server 2012 Standard (64 ビット版)、最新のサービスパックを使用して実行することをお勧めします。

16 ノードの場合:

- Microsoft SQL Server 2019 Enterprise (64 ビット版)、最新の service pack を使用して実行することをお勧めします。

- Microsoft SQL Server 2017 Enterprise (64 ビット版)、最新の service pack を使用して実行することをお勧めします。

- Microsoft SQL Server 2016 Enterprise (64 ビット版)、Service Pack 1 以降。 最新のサービスパックを使用して実行することをお勧めします。
  
- Microsoft SQL Server 2014 Enterprise (64 ビット版)、最新の service pack を使用して実行することをお勧めします。
    
- Microsoft SQL Server 2012 Enterprise (64 ビット版)、最新の service pack を使用して実行することをお勧めします。

> [!IMPORTANT]
> アップグレードの場合は、アップグレードする前に、フロントエンドサーバー上で少なくとも SQL Server 2012 SP1 がインストールされていることを確認する必要があります。 今すぐダウンロードしたい場合は、SP1 へ[のリンクが](https://www.microsoft.com/en-us/download/details.aspx?id=35575)表示されます。
  
SQL ミラーリングの詳細を確認する必要がある場合は、Skype for Business Server 2015 のトピック「バックエンドサーバーの高可用性」を参照してください。 Skype for Business Server 2015 用の SQL Server クラスタリングを構成するには、クラスタリングを準備する手順があります。 SQL のフェールオーバークラスタリング、 [2014](https://technet.microsoft.com/en-us/library/hh231721.aspx)、 [2012](https://technet.microsoft.com/en-us/library/hh231721%28v=sql.110%29.aspx)、 [2008](https://technet.microsoft.com/en-us/library/ms189134%28v=sql.105%29.aspx)のリンクもあります。
  
> [!NOTE]
> 2015リリースの新機能は、常に SQL をサポートしています。 サポートされています。詳細については、「 [Skype For Business Server 2015 のバックエンドサーバーの高可用性](../../plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md)機能」を参照してください。

> [!NOTE]
> SQL ミラーリングは、Skype for Business Server 2015 では使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。 AlwaysOn 可用性グループ、AlwaysOn フェールオーバークラスターインスタンス (FCI)、SQL フェールオーバークラスタリングの各方法は、Skype for Business Server 2019 で推奨されます。  

## <a name="software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment"></a>Skype for Business Server 2015 の展開前にインストールすべきソフトウェア
<a name="Software"> </a>

Skype for Business Server 2015 を実行しているサーバーに対してインストールまたは構成する必要があるものはいくつかあります。また、次の一覧に記載されています。 その後に、特定のサーバーの役割に関するその他の要件を示しています。
  
 **すべてのサーバー:**
  
|**ソフトウェア/役割**|**詳細**|
|:-----|:-----|
|Windows PowerShell 3.0  <br/> |すべての Skype for Business Server サーバーには、Windows PowerShell 3.0 がインストールされている必要があります。  <br/> • Windows Server 2012 または Windows Server 2012 R2 でインストールを行っている場合は、既に設定されているために設定されています。  <br/> • Windows Server 2008 R2 でアップグレードを実行している場合は、 [Windows Management Framework 3.0](https://www.microsoft.com/en-us/download/details.aspx?id=34595)をダウンロードして入手できます。 <br/> **ヒント:** 適切な PowerShell を用意したら、PowerShell プロンプトに移動して入力`$PSVersionTable`し、それがビルドバージョン6.2.9200.0 であることを確認します。 これにより、必要な情報が表示されます。  <br/> |
|Microsoft .NET Framework  <br/> |WCF サービスは、Windows 機能としてインストールされている**機能**ですが、[**サーバーマネージャー**] ではダウンロードの必要はありません。 <br/> •この機能がインストールされているかどうかを確認する必要がある場合、または既にインストールされていて確認している場合は、次のように**HTTP アクティブ化**オプションがオンになっていることを確認する必要があります。 <br/> ![.NET Framework 4.5 機能の [HTTP アクティブ化] オプションを示すスクリーンショット。](../../media/a4064fa0-fa49-4474-bd98-b9a79ff68f8b.png)追加のポップアップが表示された場合でも、HTTP ライセンス認証をインストールするには、他のいくつかの項目をインストールする必要があります。 これは通常の動作のため、[OK] をクリックして先に進みます。 このメッセージが表示されない場合、これらの機能は既にインストールされていると見なして、先に進みます。  <br/> Microsoft .NET Framework は、通常、Windows Server 2012 R2 または Windows Server 2016 がインストールされている場合にインストールされます。 Skype for Business Server は、次の Microsoft .NET Framework バージョンで動作します。  <br/> • .NET 3.5  <br/> • .NET 4.5  <br/> • .NET 4.6. x  <br/> • .NET 4.7.1 以上 (Skype for Business Server CU 5 以降のリリース)  <br/>  .NET Framework 3.5 は、Windows Server 2008 R2 コンピューターに既定でインストールされている可能性があります (アップグレード前に必ず確認してください)。ただし、実際には、Windows server 2012/Windows Server 2012 R2 サーバーにはありません (新規インストールの場合)。 アプリを追加するには、インストールドライブまたはメディア (Windows Server のインストール元の場所、またはインストールファイルの場所) にアクセスする必要があります。 その後、先に進んで、サーバー マネージャーの機能としてインストールし、要求されたらインストール メディア (具体的には **\sources\sxs** フォルダー) を指定して、インストールを続行します。 <br/> |
|メディア ファンデーション  <br/> |Windows server 2016、windows server 2012、windows Server 2012 R2 の場合、Windows Media Format Runtime は Microsoft メディアファンデーションと共にインストールされます。  <br/> 会議に使われるすべてのフロントエンドサーバーおよび標準エディションのサーバーでは、Windows Media Format Runtime を使用して、コールパーク、お知らせ、および応答グループアプリケーションがお知らせや音楽を再生するための Windows media Audio (.wma) ファイルを実行する必要があります。  <br/> |
|Windows Identity Foundation  <br/> |Skype for Business Server 2015 のサーバー間認証シナリオをサポートするには、Windows Id ファンデーション3.5 が必要です。  <br/> • Windows Server 2012 および Windows Server 2012 R2 の場合、何もダウンロードする必要はありません。 **サーバー マネージャー**を開いて、[**役割と機能の追加ウィザード**] に進みます。 [**機能**] セクションの一覧に [**Windows Identity Foundation 3.5**] が表示されています。 このチェックボックスがオンになっている場合は、問題ありません。 オンになっていない場合は、これを選択して [次へ] をクリックし、[**インストール**] をアクティブにします。 <br/> |
|リモート サーバー管理ツール  <br/> |役割管理ツール: AD DS および AD LDS ツール  <br/> |
   
 **フロントエンドサーバーと Standard Edition サーバーにも次のものが必要です。**
  
|**ソフトウェア/役割**|**詳細**|
|:-----|:-----|
|インターネット インフォメーション サービス (IIS)  <br/> |IIS は、すべてのフロントエンドサーバー、およびすべての標準エディションのサーバーで、次のモジュールが選択されている必要があります。  <br/> •一般的な HTTP 機能: 既定のドキュメント、HTTP エラー、静的コンテンツ  <br/> •正常性と診断: HTTP ログ、ログツール、トレース  <br/> •パフォーマンス: 静的なコンテンツの圧縮、動的なコンテンツの圧縮  <br/> •セキュリティ: フィルターの要求、クライアント証明書のマッピング認証、Windows 認証  <br/> •アプリケーション開発: .NET 機能拡張3.5、.NET 機能拡張4.5、ASP.NET 3.5、ASP.NET 4.5、ISAPI 拡張、ISAPI フィルター  <br/> •管理ツール: IIS 管理コンソール、IIS 管理スクリプト、ツール  <br/> また、匿名アクセスも必要になることに注意してください。ただし、IIS をインストールするときには、一覧でその項目を選択する場所がありません。  <br/> |
|Windows Media フォーマット ランタイム  <br/> | Windows Server 2016、Windows Server 2012、および Windows Server 2012 R2 の場合は、**サーバーマネージャー**で**メディアファンデーション**機能をインストールする必要があります。 この時点では、Skype for business Server 2015 のインストールはこの方法で実行することはできませんが、skype for Business Server 2015 のインストールが続行される前に、インストールしてサーバーを再起動するように求められます。 この作業は、前もって行っておくことをお勧めします。 <br/> |
|Silverlight  <br/> |[このリンク](https://www.microsoft.com/silverlight/)から最新バージョンの Silverlight をインストールできます。  <br/> |
   
> [!NOTE] 
> ロードバランサーを使用している場合は、ディレクトリの参照を有効にする必要がある場合もあります。 そうしないと、読み込みバランサーで障害が発生している可能性がある空白ページが読み込まれます。 

作業の簡素化のために、この処理を自動化するサンプル PowerShell スクリプトを次に示します。

```
Add-WindowsFeature NET-Framework-Core, RSAT-ADDS, Windows-Identity-Foundation, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Dir-Browsing, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, BITS, Desktop-Experience, Telnet-Client
```

> [!NOTE] 
> このコマンドは、特定の順序でソースファイルを探します。 オンラインの場合、このコマンドは Windows Update にアクセスします。 一方、オフラインの場合は、このコマンドがソース ファイルにアクセスできるようにする必要があります。 PowerShell を使用して役割と機能をインストールする方法について詳しくは、「[役割、役割サービス、または機能をインストールまたはアンインストール](https://technet.microsoft.com/en-us/library/hh831809.aspx)する」を参照してください。必要に応じて、powershell コマンドを使用する場合でも、Windows Update を再実行してください。

 **ディレクターも次のことを行う必要があります。**
  
次のモジュールを選択した IIS:
  
- HTTP 共通機能
    
  - 既定のドキュメント
    
  - HTTP エラー
    
  - 静的コンテンツ
    
- 状態と診断
    
  - HTTP ログ
    
  - ログ ツール
    
  - トレース
    
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
    
(ご不明な点がある場合は、動的なコンテンツ圧縮と管理ツールが表示された状態で、フロントエンドサーバーと標準エディションサーバーと同じモジュールセットになります)。
  
また、同様に役立つ PowerShell コードを次に示します。
  
```
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client
```

 **常設チャットサーバーにも、次のものが必要です。**
  
メッセージ キュー (別名 MSMQ)。 これは Windows Server コンポーネントであり、サーバーマネージャーの [機能] セクションにインストールできます。 これについて詳しくは、「[メッセージキューをインストールして管理](https://technet.microsoft.com/en-us/library/cc771474.aspx)する」をご覧ください。
  
 **最後の確認事項:**
  
Microsoft インターネットセキュリティとアクセラレータ (ISA) サーバークライアントソフトウェア、またはその他の Winsock レイヤードサービスプロバイダ (LSP) ソフトウェア (サードパーティ製のファイアウォールまたはウイルス対策ネットワーク検査ソフトウェア) をインストールしないでください。任意のフロントエンドサーバーまたはスタンドアロンの仲介サーバー。 メディアトラフィックの低品質は、そのソフトウェアがインストールされているときに表示されます。
  

