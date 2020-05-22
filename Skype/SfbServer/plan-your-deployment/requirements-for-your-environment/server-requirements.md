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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 8d47b242-b93d-4c2e-a658-23b78bca30b1
description: '概要: このトピックを使用して、Skype for Business Server 2015 サーバーを準備します。 ハードウェア、OS、データベース、ソフトウェア、すべてのシステム要件と推奨事項は、サーバーファームのインストールと展開を成功させるために役立ちます。'
ms.openlocfilehash: 02ccebca4eebef84638992dd88ba45040e733d19
ms.sourcegitcommit: b1f7f1435c5e72c2eea4069fbb0bea29b197cb80
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/21/2020
ms.locfileid: "44342457"
---
# <a name="server-requirements-for-skype-for-business-server-2015"></a>Skype for Business Server 2015 のサーバー要件
 
**概要:** このトピックを使用して、Skype for Business Server 2015 のサーバーを準備します。 ハードウェア、OS、データベース、ソフトウェア、すべてのシステム要件と推奨事項は、サーバーファームのインストールと展開を成功させるために役立ちます。

Active Directory、DNS、証明書などの環境要件を探している場合は、 [Skype For Business Server 2015 doc の環境要件](environmental-requirements.md)を調べることができます。
  
予想されるように、Skype for Business Server 2015 の展開を開始する前に行う必要がある準備があります。 この記事では、次の計画について順を追って説明します。
  
- [Skype for business Server 2015 のハードウェア](server-requirements.md#Hardware)
  
- [Skype for Business Server 2015 のオペレーティングシステム](server-requirements.md#OS)
  
- [Skype for Business Server 2015 で動作するバックエンドデータベース](server-requirements.md#DBs)
  
- [Skype for Business Server 2015 の展開前にインストールする必要があるソフトウェア](server-requirements.md#Software)
  
## <a name="hardware-for-skype-for-business-server-2015"></a>Skype for business Server 2015 のハードウェア
<a name="Hardware"> </a>

これでトポロジが整いました (そうでない場合は、「 [Skype For Business Server 2015 のトポロジの基礎](../../plan-your-deployment/topology-basics/topology-basics.md)」を参照してください)、サーバーについて考えてみましょう。 Skype for Business Server 2015 サーバーでは、64ビットのハードウェアが必要になります。 ハードウェアに関する推奨事項は以下のとおりです。 これらは要件ではありませんが、最適なパフォーマンスを得るために必要な要件を反映しています。 状況によっては、これ以上の必要があるかどうかを判断するのに役立つ容量計画のドキュメントが用意されています。
  
フロントエンドサーバー、バックエンドサーバー、Standard Edition サーバー、および常設チャットサーバーの推奨ハードウェア:
  
|**ハードウェア コンポーネント**|**推奨**|
|:-----|:-----|
|CPU  <br/> |64ビットデュアルプロセッサ、16ビットコア、2.26 ghz 以上。  <br/> Intel Itanium プロセッサは、Skype for Business Server 2015 の役割ではサポートされていません。  <br/> |
|メモリ  <br/> |32 gb  <br/> |
|ディスク  <br/> |いずれも：  <br/> • 1万 RPM のハードディスクドライブのうち、少なくとも 72 GB のディスクの空き領域 (raid 1 を使用している2台のディスク、および RAID 10 を使用する2つのディスク)。  <br/> または  <br/> •ソリッドステートドライブ (Ssd) は、8 1万 RPM メカニカルディスクドライブと同じ空き領域と同じパフォーマンスを提供することができます。  <br/> |
|ネットワーク  <br/> |1 Gbps 以上のデュアルポートネットワークアダプター (2 つのネットワークアダプターを使用できますが、1つの MAC アドレスと1つの IP アドレスをチーミングする必要があります)。  <br/> デュアルまたはマルチホーム構成は、フロントエンドサーバー、バックエンドサーバー、Standard Edition サーバー、および常設チャットサーバーではサポートされて**いません**。 <br/> オペレーティングシステムに公開されておらず、サーバーハードウェアを監視および管理するためにも使用されている限り、帯域外管理システム (DRAC や ILO など) があります。 このシナリオは、複数のホームサーバーを構成するものではなく、サポートされています。  <br/> |
   
エッジサーバー、スタンドアロン仲介サーバー、ビデオ相互運用サーバー、およびディレクターの推奨ハードウェア:
  
|**ハードウェア コンポーネント**|**推奨**|
|:-----|:-----|
|CPU  <br/> |64ビットデュアルプロセッサ、クアッドコア、2.26 ghz またはそれ以上。  <br/> Intel Itanium プロセッサは、Skype for Business Server 2015 の役割ではサポートされていません。  <br/> |
|メモリ  <br/> |16 gb  <br/> |
|ディスク  <br/> |いずれも：  <br/> •4台以上の 1万 RPM ハードディスクドライブ (少なくとも 72 GB の空きディスク領域がある) (ディスクは2倍の RAID 1 構成である必要があります)。  <br/> または  <br/> •ソリッドステートドライブ (Ssd) は、4 1万 RPM メカニカルディスクドライブと同じ空き領域と同じパフォーマンスを提供することができます。  <br/> |
|ネットワーク  <br/> |1 Gbps 以上のデュアルポートネットワークアダプター (2 つのネットワークアダプターを使用できますが、1つの MAC アドレスと1つの IP アドレスをチーミングする必要があります)。  <br/> デュアルまたはマルチホーム構成は、ビデオ相互運用サーバーとディレクターではサポートされて**いません**。 <br/> エッジサーバーでは、2つのネットワークインターフェイス (または、1 Gbps 以上のデュアルポートネットワークアダプター、つまり合計4つのネットワークアダプターが1つの MAC アドレスと1つの IP アドレスでチーミングされ、合計2つのペア) が必要です。  <br/> スタンドアロンの仲介サーバーでは、追加のネットワークインターフェイスカード (Nic) をインストールして、特定の PSTN IP アドレスの構成を許可することができます。  <br/> |
   
## <a name="operating-systems-for-skype-for-business-server-2015"></a>Skype for Business Server 2015 のオペレーティングシステム
<a name="OS"> </a>

ハードウェアの準備が整ったら、オペレーティングシステム (OS) をインストールする必要があります。 これらの OS は、Skype for Business Server 2015 をインストールして、正常に使用できるようにします。
  
|||
|:-----|:-----|
|Windows Server 2019 (Skype for Business の累積更新プログラム9以降が必要です)。 <br/> |Windows Server 2016 (Skype for Business の累積的な更新プログラム5以降が必要です。 詳細については、「 [KB4015888](https://support.microsoft.com/help/4015888/how-to-install-skype-for-business-server-2015-on-windows-server-2016)」を参照してください)  <br/> ||
|Windows Server 2012 R2 Datacenter OS。必要な更新プログラムがすべてインストールされています。  <br/> |すべての必須更新プログラムがインストールされた Windows Server 2012 R2 Standard OS。  <br/> |
|必要な更新プログラムがすべてインストールされた Windows Server 2012 Datacenter OS。  <br/> |すべての必須更新プログラムがインストールされた Windows Server 2012 Standard OS。  <br/> |
   
このリストに含まれていない場合は、正しく動作しません。新たに Skype for Business Server 2015 をインストールしてください。

> [!NOTE]
> Lync Server 2013 では、OS の一括アップグレードはサポートされていません。 別のプールを展開し、別の OS を使用してユーザーを新しいプールに移行する必要があります。 プール内のすべてのサーバーの OS バージョンは同じである必要があります。
  
> [!NOTE]
> Windows Server 2008 R2 がこの一覧に含まれていないことに気付いたかもしれません。 これは、すべての新しいサーバーを SFB に使用するために Windows Server 2012 R2 を推奨しているためです。 既に Lync Server 2013 がインストールされている既存のサーバーがあり、その一括アップグレードを実行する場合は、Windows Server 2008 R2 を使用する必要があります。 Windows Server 2008 R2 は、1/13/2015 のメインストリームサポートライフサイクルの終わりに達し、1/14/2020 のサポートライフサイクルの終わりに到達します。
  
最新の service pack に加えて、次の更新プログラムがインストールされているかどうかを確認する必要があります。
  
- Windows Server 2012 の場合は、アップグレード前にサポート技術情報の記事2858668をインストールする必要があります。 [ここで取得](https://support.microsoft.com/kb/2858668/)します。
    
- Windows Server 2012 R2 を使用している場合は、アップグレードの前に KB の記事2982006をインストールしてください。 [ここ](https://support.microsoft.com/kb/2982006/)にあります。
    
- Windows Server 2008 R2 ボックス (上記の注を参照) をアップグレードする場合は、KB の記事2533623を最初にインストールする必要があります。 [このリンクは次のように](https://support.microsoft.com/kb/2533623/)なります。
    
## <a name="back-end-databases-that-will-work-with-skype-for-business-server-2015"></a>Skype for Business Server 2015 で動作するバックエンドデータベース
<a name="DBs"> </a>


Skype for Business Server 2015 Standard Edition をインストールすると、SQL Server 2014 Express (64-bit edition) が自動的にインストールされます。
  
Skype for Business Server 2015 Enterprise Edition は少し複雑ですが、サポートされているリストは以下のとおりです (すべては64ビットエディションです。32ビットエディションは使用しないでください)。
  
||||||
|:-----|:-----|:-----|:-----|:-----|
|Microsoft SQL Server 2019 Enterprise (64 ビット版)。最新のサービスパックを使用して実行することをお勧めします。 <br/> |Microsoft SQL Server 2017 Enterprise (64 ビット版)。最新のサービスパックを使用して実行することをお勧めします。 <br/> |Microsoft SQL Server 2016 Enterprise (64 ビット版) Service Pack 1 以降のバージョンでは、Skype for business の累積的な更新プログラム7以降を使用して実行する必要があります ([skype For business の累積的な更新プログラムをダウンロード](https://support.microsoft.com/help/3061064)してください)。  <br/> |Microsoft SQL Server 2014 Enterprise (64 ビット版)。累積更新プログラム6以降で実行する必要があります ([累積更新プログラム6をダウンロード](https://support.microsoft.com/kb/3031047/)してください)。  <br/> |Microsoft SQL Server 2012 Enterprise (64 ビット版)。最新のサービスパックを使用して実行することをお勧めします。  <br/> |
|Microsoft SQL Server 2019 Standard (64 ビット版)。最新のサービスパックを使用して実行することをお勧めします。 <br/> |Microsoft SQL Server 2017 Standard (64 ビット版)。最新のサービスパックを使用して実行することをお勧めします。 <br/> |Microsoft SQL Server 2016 Standard (64 ビット版) Service Pack 1 以降のバージョンでは、Skype for business の累積的な更新プログラム7以降を使用して実行する必要があります ([skype For business の累積的な更新プログラムをダウンロード](https://support.microsoft.com/help/3061064)してください)。  <br/> |Microsoft SQL Server 2014 Standard (64 ビット版)。累積更新プログラム6以降で実行する必要があります ([累積更新プログラム6をダウンロード](https://support.microsoft.com/kb/3031047/)してください)。  <br/> |Microsoft SQL Server 2012 Standard (64 ビット版)。最新のサービスパックを使用して実行することをお勧めします。  <br/> |
   
使用する SQL Server エディションが表示されていない場合は、これを使用することはできません。
  
- また、監視サーバーの役割用の SQL Server Reporting Services をインストールする必要もあります。
- 適切に接続された SQL バックエンドの場合、Skype for Business フロントエンドへの接続は、低速リンクではなくローカルである必要があります。 
- 2つ以上のプール間で SQL バックエンドを共有することはサポートされていません。

### <a name="microsoft-exchange-storage"></a>Microsoft Exchange ストレージ
PowerPoint プレゼンテーションなどの会議コンテンツ ファイルは、添付ファイルとしてアーカイブされます。 Skype for Business アーカイブデータを Exchange コンプライアンスデータと共に保存する場合は、exchange を exchange の展開に使用して、最大記憶域サイズが会議コンテンツファイルの格納をサポートするようにする必要があります。 Microsoft Exchange 統合オプションを使用してアーカイブを展開および有効化する前に、Exchange を展開する必要があります。 
    
    If you choose to use Exchange storage, you do not need to deploy separate SQL Server databases for archiving, unless you have Skype for Business users who are not homed on your Exchange servers. If you deploy archiving using the Microsoft Exchange integration option, Skype for Business archive data is stored with Exchange compliance data only for the users who are homed on your Exchange servers. 
  
## <a name="hardware-and-software-requirements-for-archiving-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 でのアーカイブのハードウェアおよびソフトウェア要件
  
アーカイブは定義済みのサーバーの役割ではありません。アーカイブ用に別のサーバーをインストールする必要はありません。 統合データ収集エージェントは、すべての Enterprise Edition フロントエンドプールおよびすべての Standard Edition サーバーで自動的にインストールされ、アクティブ化されます。 トポロジビルダーを使用して、アーカイブトポロジを有効にし、発行する必要があります。
    
アーカイブでは、会議コンテンツファイルを一時的に保存するために Skype for Business Server のファイルストレージを使用するので、アーカイブ用に別のファイルストアを設定する必要はありません。
    
Microsoft メッセージキューは必須ではありません。
    
アーカイブストレージのインフラストラクチャをセットアップする必要があります。 これには、Exchange または SQL Server を使用したアーカイブストレージのどちらかを選択することも含まれます。   Skype for Business Server のアーカイブインフラストラクチャの要件は、Skype for business Server の展開の場合と同じです。 詳細については、「 [Skype For business 環境の要件](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md)」を参照してください。 
  
> [!NOTE]
> Exchange サーバーに所属していないユーザーをサポートする場合、または Microsoft Exchange 統合オプションを使用しない場合は、64ビットの SQL Server データベースを使用してアーカイブストレージを展開する必要があります。 
    
アーカイブを展開して有効にする前に、SQL Server プラットフォームをセットアップする必要があります。 トポロジの公開に使用するアカウントに適切な管理権限とアクセス許可がある場合、トポロジを公開するときにアーカイブ データベース (LcsLog) を作成できます。 インストール手順の一部として、データベースを後で作成することもできます。 SQL Server の詳細については、 [Sql server のドキュメント](https://go.microsoft.com/fwlink/p/?linkID=129045)を参照してください。
    
アーカイブの負荷が増加することは重要です。 そのため、アーカイブが有効になっているフロントエンドサーバーのディスク容量が十分であることを確認する必要があります。

### <a name="sql-mirroring-sql-clustering-and-sql-always-on"></a>SQL ミラーリング、SQL クラスタリング、および SQL Always On

Skype for Business Server 2015 で SQL ミラーリングまたは SQL クラスタリングを使用することはできますが、サポートされています。 SQL ミラーリングは、Skype for Business Server トポロジビルダーを使用してセットアップします。 SQL クラスタリングの設定を意図している場合は、SQL Server で行います。
  
SQL クラスタリングのアクティブ/パッシブ構成がサポートされていることを確認してください。 パッシブノードは他の SQL インスタンスと共有しないでください。
  
フェールオーバークラスタリングには、次のものを含めることができます。
  
2ノード:
  
- Microsoft SQL Server 2019 Standard (64 ビット版)。最新のサービスパックを使用して実行することをお勧めします。

- Microsoft SQL Server 2017 Standard (64 ビット版)。最新のサービスパックを使用して実行することをお勧めします。

- Microsoft SQL Server 2016 Standard (64-bit edition) Service Pack 1 以降。 最新のサービスパックを使用して実行することをお勧めします。

- Microsoft SQL Server 2014 Standard (64 ビット版)。最新のサービスパックを使用して実行することをお勧めします。
    
-  Microsoft SQL Server 2012 Standard (64 ビット版)。最新のサービスパックを使用して実行することをお勧めします。

16ノード:

- Microsoft SQL Server 2019 Enterprise (64 ビット版)。最新のサービスパックを使用して実行することをお勧めします。

- Microsoft SQL Server 2017 Enterprise (64 ビット版)。最新のサービスパックを使用して実行することをお勧めします。

- Microsoft SQL Server 2016 Enterprise (64 ビット版) Service Pack 1 以降。 最新のサービスパックを使用して実行することをお勧めします。
  
- Microsoft SQL Server 2014 Enterprise (64 ビット版)。最新のサービスパックを使用して実行することをお勧めします。
    
- Microsoft SQL Server 2012 Enterprise (64 ビット版)。最新のサービスパックを使用して実行することをお勧めします。

> [!IMPORTANT]
> アップグレードの場合は、アップグレードの前にフロントエンドサーバー上で少なくとも SQL Server 2012 SP1 がインストールされていることを確認する必要があります。 すぐにダウンロードする必要がある場合は、SP1 へ[のリンクをここに示し](https://www.microsoft.com/download/details.aspx?id=35575)ます。
  
SQL ミラーリングの詳細については、「Skype for Business Server 2015 のバックエンドサーバーの高可用性」を参照してください。 Skype for Business Server 2015 用の SQL Server クラスタリングを構成するには、クラスタリングを準備する手順を実行します。 また、SQL のフェールオーバークラスタリングに関するその他のリンクもあります。 [2014](https://technet.microsoft.com/library/hh231721.aspx)、 [2012](https://technet.microsoft.com/library/hh231721%28v=sql.110%29.aspx)、 [2008](https://technet.microsoft.com/library/ms189134%28v=sql.105%29.aspx)。
  
> [!NOTE]
> 2015リリースの新機能では、SQL Always On がサポートされています。 これについては、「 [Back End server high availability In Skype For Business server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md) 」を参照してください。

> [!NOTE]
> SQL ミラーリングは Skype for business Server 2015 で利用できますが、Skype for business Server 2019 ではサポートされなくなりました。 AlwaysOn 可用性グループ、AlwaysOn フェールオーバークラスターインスタンス (FCI)、および SQL フェールオーバークラスタリングの方法は、Skype for Business Server 2019 で推奨されています。  

## <a name="software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment"></a>Skype for Business Server 2015 の展開前にインストールする必要があるソフトウェア
<a name="Software"> </a>

Skype for Business Server 2015 を実行しているすべてのサーバーについてインストールまたは構成する必要があることがあります。また、以下に一覧表示されています。 その後、特定のサーバーの役割に対する追加の要件があります。

  
 **すべてのサーバー:**
  
|**ソフトウェア/役割**|**詳細**|
|:-----|:-----|
|Windows PowerShell 3.0  <br/> |すべての Skype for Business Server サーバーには、Windows PowerShell 3.0 がインストールされている必要があります。  <br/> • Windows Server 2012 または Windows Server 2012 R2 上でインストールを実行している場合は、既に設定されているため、設定しています。  <br/> • Windows Server 2008 R2 でアップグレードする場合は、 [Windows Management Framework 3.0](https://www.microsoft.com/download/details.aspx?id=34595)をダウンロードして入手できます。 <br/> **ヒント:** 適切な PowerShell を用意したら、PowerShell プロンプトに進み、「」と入力して、それが BuildVersion 6.2.9200.0 以降であることを確認 `$PSVersionTable` します。 これにより、必要な情報が表示されます。  <br/> |
|Microsoft .NET Framework  <br/> |WCF サービスは、Windows 機能としてインストールされている**機能**です。**サーバーマネージャー**ではダウンロードは必要ありません。 <br/> •この機能をインストールするとき、または既にインストールされていて確認する際には、次のように、 **HTTP アクティブ化**オプションもチェックされ、インストールされていることを確認する必要があります。 <br/> ![.NET Framework 4.5 機能の下の HTTP アクティブ化オプションを示すスクリーンショット。 ](../../media/a4064fa0-fa49-4474-bd98-b9a79ff68f8b.png)HTTP ライセンス認証をインストールするには、他にもいくつかの設定をインストールする必要があることを示す追加のポップアップが表示されても心配しないでください。 これで正常です。 [OK] をクリックして、先に進みます。 このポップアップが表示されない場合は、それらが既にインストールされていると仮定し、先に進んでください。  <br/> Microsoft .NET Framework は、通常、Windows Server 2012 R2 または Windows Server 2016 がインストールされている場合にインストールされます。 Skype for Business Server は、次の Microsoft .NET Framework バージョンで動作します。  <br/> • .NET 3.5  <br/> • .NET 4.5  <br/> • .NET 4.6. x  <br/> • .NET 4.7.1 (Skype for Business Server CU 5 以降のリリース)  <br/> • .NET 4.7.2 (Skype for Business Server CU 6 以降のリリース)  <br/>  • .NET 4.8 (Skype for Business Server CU 9 以降のリリース) <br/>  .NET Framework 3.5 は、Windows Server 2008 R2 コンピューターに既定でインストールされる可能性がありますが (アップグレードの前に必ず確認してください)、実際には Windows Server 2012/Windows Server 2012 R2 サーバー (新規インストールの場合) にはありません。 を追加するには、インストールドライブまたはメディア (Windows Server のインストール元、またはインストールファイルが保存されている場所) にアクセスする必要があります。 その後、サーバーマネージャから機能としてインストールし、インストールメディア (具体的には**\sources\sxs**フォルダー) を指定し、インストールを続行します。 <br/> |
|メディアファンデーション  <br/> |Windows Server 2016、windows server 2012、Windows server 2012 R2 では、Windows Media フォーマットランタイムが Microsoft Media Foundation と共にインストールされます。  <br/> 会議に使用されるすべてのフロントエンドサーバーおよび Standard Edition サーバーでは、windows Media フォーマットランタイムを使用して、コールパーク、アナウンス、および応答グループアプリケーションがアナウンスと音楽を再生する Windows media Audio (.wma) ファイルを実行する必要があります。  <br/> |
|Windows Identity Foundation  <br/> |Skype for Business Server 2015 のサーバー間認証シナリオをサポートするには、Windows Identity Foundation 3.5 が必要です。  <br/> • Windows Server 2012 および Windows Server 2012 R2 の場合は、何もダウンロードする必要はありません。 **サーバーマネージャー**を開き、[**役割と機能の追加ウィザード]** に進みます。 **Windows Identity Foundation 3.5**は、[**機能**] セクションの下に一覧表示されます。 このチェックボックスがオンになっている場合は、問題ありません。 それ以外の場合は、それを選択し、[次へ] をクリックして [**インストール**] ボタンに移動します <br/> |
|リモート サーバー管理ツール  <br/> |役割管理ツール: AD DS および AD LDS ツール  <br/> |
   
 **フロントエンドサーバーおよび Standard Edition サーバーにも次のものが必要です。**
  
|**ソフトウェア/役割**|**詳細**|
|:-----|:-----|
|インターネット インフォメーション サービス (IIS)  <br/> |すべてのフロントエンドサーバーとすべての Standard Edition サーバーで、次のモジュールが選択されている場合は、IIS が必要です。  <br/> •共通の HTTP 機能: 既定のドキュメント、HTTP エラー、静的コンテンツ  <br/> •正常性と診断: HTTP ログ、ログツール、トレース  <br/> •パフォーマンス: 静的なコンテンツの圧縮、動的なコンテンツの圧縮  <br/> •セキュリティ: 要求フィルター、クライアント証明書マッピング認証、Windows 認証  <br/> •アプリケーション開発: .NET 拡張3.5、.NET の拡張性4.5、ASP.NET 3.5、ASP.NET 4.5、ISAPI Extensions、ISAPI フィルター  <br/> •管理ツール: IIS 管理コンソール、IIS 管理スクリプトおよびツール  <br/> また、匿名アクセスも必要であることにも注意してください。ただし、IIS をインストールするときには、リストでそのことを選択する場所がありません。  <br/> |
|Windows Media フォーマット ランタイム  <br/> | Windows Server 2016、Windows Server 2012、および Windows Server 2012 R2 の場合は、**サーバーマネージャー**で**メディアファンデーション**機能をインストールする必要があります。 これで、実際には Skype for business Server 2015 のインストールをこのように実行することはできませんが、skype for Business Server 2015 のインストールが続行される前に、インストールするかどうかを確認するメッセージが表示されます。その後、サーバーを再起動する必要があります。 時間の前にすることをお勧めします。 <br/> |
|Silverlight  <br/> |[このリンク](https://www.microsoft.com/silverlight/)では、最新バージョンの Silverlight をインストールできます。  <br/> |
   
> [!NOTE] 
> ロードバランサーを使用している場合は、ディレクトリの参照を有効にする必要がある場合もあります。 それ以外の場合は、空のページがロードバランサーによってエラーを考慮する可能性があります。 

これを支援するために、以下のサンプル PowerShell スクリプトを実行して、これを自動化することができます。

```PowerShell
Add-WindowsFeature NET-Framework-Core, RSAT-ADDS, Windows-Identity-Foundation, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Dir-Browsing, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, BITS, Desktop-Experience, Telnet-Client
```

> [!NOTE] 
> このコマンドは、特定の順序でソースファイルを検索します。 オンラインの場合、コマンドは Windows Update にアクセスします。 ただし、オフラインの場合は、ソースファイルがコマンドで使用できることを確認する必要があります。 PowerShell を使用して役割および機能をインストールする方法の詳細については、「[インストールまたはアンインストールの役割、役割サービス、または機能](https://technet.microsoft.com/library/hh831809.aspx)」を参照してください。必要なコンポーネントをインストールした後、powershell コマンドを使用しても、Windows Update を再度実行してください。

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
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client
```

 **常設チャットサーバーには次のものも必要です。**
  
メッセージキュー。これは MSMQ とも呼ばれます。 これは Windows Server コンポーネントであり、サーバーマネージャーの [機能] セクションにインストールできます。 詳細については、「[メッセージキューをインストールおよび管理](https://technet.microsoft.com/library/cc771474.aspx)する」を参照してください。
  
 **最後の考え:**
  
任意のフロントエンドサーバーまたはスタンドアロンの仲介サーバーに対して、Microsoft インターネットセキュリティとアクセラレータ (ISA) サーバークライアントソフトウェア、またはその他のすべての Winsock レイヤードサービスプロバイダー (LSP) ソフトウェア (サードパーティ製のファイアウォールまたはウイルス対策ネットワーク検査ソフトウェア) をインストールしないでください。 ソフトウェアがインストールされていると、メディアトラフィックのパフォーマンスの低下が見られます。
  

