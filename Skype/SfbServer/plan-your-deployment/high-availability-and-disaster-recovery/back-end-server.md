---
title: Skype for Business Server のバックエンドサーバーの高可用性
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c559aacb-4e1d-4e78-9582-41f966ad418d
description: AlwaysOn 可用性グループ、AlwaysOn フェールオーバークラスターインスタンス、データベースのミラーリング、SQL フェールオーバークラスタリングなど、Skype for Business Server でサポートされているバックエンドサーバーの高可用性オプションについて説明します。
ms.openlocfilehash: a0aeb53aea0ee2eab25875de0fddbfd0fc26d90a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815955"
---
# <a name="back-end-server-high-availability-in-skype-for-business-server"></a>Skype for Business Server のバックエンドサーバーの高可用性
 
AlwaysOn 可用性グループ、AlwaysOn フェールオーバークラスターインスタンス、データベースのミラーリング、SQL フェールオーバークラスタリングなど、Skype for Business Server でサポートされているバックエンドサーバーの高可用性オプションについて説明します。
  
バックエンド サーバーの高可用性を強化するには、以下の 4 つの選択肢があります。
  
- データベース ミラーリング
    
- AlwaysOn 可用性グループ
    
- AlwaysOn フェールオーバークラスターインスタンス (FCI)
    
- SQL フェールオーバー クラスタリング
    
これらのソリューションのいずれかの使用はオプションですが、組織のビジネス継続性を維持するには推奨されます。 そうしないと、1つのデータベースサーバーがダウンすると、大量の Skype for Business Server データが失われる可能性があります。 
  
データベースミラーリングは、トポロジビルダーのみを使用して設定できます。 AlwaysOn 可用性グループ、AlwaysOn フェールオーバークラスターインスタンス、または SQL フェールオーバークラスタリングの場合、SQL Server を使用して高可用性ソリューションを作成した後、トポロジビルダーを使用して、フロントエンドプールに関連付けることができます。
  
バックエンドサーバーの高可用性プールで、障害回復用の別のフロントエンドプールとペアリングされている場合は、両方のプールで同じバックエンドの高可用性ソリューションを使用する必要があります。 
  
## <a name="database-mirroring"></a>データベース ミラーリング

Skype for Business Server は、次のデータベースソフトウェアとのミラーリングをサポートしています。
  
- SQL Server 2019 (Enterprise Edition と Standard Edition の両方)

- SQL Server 2017 (Enterprise Edition と Standard Edition の両方)

- SQL Server 2016 (Enterprise Edition と Standard Edition の両方)

- SQL Server 2014 (Enterprise Edition と Standard Edition の両方)
    
- SQL Server 2012 SP2 と CU2 (Enterprise Edition と Standard Edition の両方)
    

> [!NOTE]
> SQL ミラーリングは、Skype for Business Server 2015 では使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。 AlwaysOn 可用性グループ、AlwaysOn フェールオーバークラスターインスタンス (FCI)、SQL フェールオーバークラスタリングの各方法は、Skype for Business Server 2019 で推奨されます。
    
Skype for Business Server では、バックエンドサーバーの高可用性を実現するための非同期データベースミラーリングはサポートされていません。 これ以降、特に指定がない限り、データベース ミラーリングは同期データベース ミラーリングを意味するものとします。 
  
フロントエンドプールにデータベースミラーリングを展開すると、プール内のすべての Skype for Business Server データベースが、このプールに配置されている場合は中央管理ストア、応答グループアプリケーションデータベース、コールパークと共にミラーリングされます。アプリがプールで実行されている場合は、アプリケーションデータベース。 
  
データベース ミラーリングでは、サーバーに対して共有ストレージを使用する必要はありません。各サーバーは、データベースのコピーをローカル ストレージに保持します。 
  
データベース ミラーリングの展開では、監視を使用することも使用しないこともできます。バックエンド サーバーのフェールオーバーが自動的になるので、監視を使用することをお勧めします。使用しない場合は、管理者が手動でフェールオーバーを実行する必要があります。監視を展開した場合でも、管理者は必要に応じてバックエンド サーバーのフェールオーバーを手動で開始できます。
  
監視を使用する場合は、バックエンド サーバーの複数のペアに対して 1 つの監視を使用できます。監視とバックエンド サーバーのペアを 1 対 1 で対応させる必要はありません。ただし、バックエンド サーバーの複数のペアに対して 1 つの監視を使用する展開は、ペアごとに異なる監視を使用するトポロジほど復元性が高くありません。 
  
### <a name="guidelines-for-planning-back-end-server-mirroring"></a>バックエンド サーバーのミラーリングのガイドライン

一般に、2 つのバックエンド サーバー間での SQL ミラーリングを設定するには、以下の要件を満たしている必要があります。
  
- プライマリサーバーの SQL Server のバージョンでは、SQL のミラーリングがサポートされている必要があります。
    
- プライマリ、ミラー、およびミラーリング監視 (展開されている場合) の各 SQL Server が同一バージョンである。 
    
- プライマリおよびミラーの各 SQL Server が同一エディションである (ミラーリング監視のエディションは異なっていても構いません)。
    
監視ロールでサポートされる SQL バージョンについては、SQL のベストプラクティスについては、MSDN ライブラリの[「データベースミラーリングの監視」](https://go.microsoft.com/fwlink/p/?LinkId=247345)をご覧ください。
  
サーバー ミラーリングを構成する前に、まず SQL データベース アクセス許可を正しく設定する必要があります。 詳細について[は、「データベースミラーリングまたは AlwaysOn 可用性グループ (SQL Server) のログインアカウントの](https://go.microsoft.com/fwlink/p/?LinkId=268454)セットアップ」を参照してください。
  
SQL ミラーリングでは、データベース復旧モードは常に [**完全**] に設定されます。これは、トランザクション ログ サイズを綿密に監視し、トランザクション ログを定期的にバックアップしてバックエンド サーバー上のディスク容量の不足を回避する必要があることを意味します。トランザクション ログのバックアップ頻度は、ログの増加率によって決まります。ログの増加率は、フロントエンド プールのユーザー アクティビティによるデータベース トランザクションによって決まります。Lync 展開ワークロードに対して予想されるトランザクション ログの増加を判断し、それに応じて計画することをお勧めします。次の記事では、SQL バックアップおよびログ管理に関する追加情報を提供しています。
  
> [!IMPORTANT]
> SQL ミラーリングのセットアップと削除を行うためのトポロジビルダーまたはコマンドレットの使用は、プライマリ、ミラー、および監視 (必要な場合) サーバーがすべて同じドメインに属している場合にのみサポートされます。 異なるドメインのサーバーに SQL ミラーリングを設定する場合は、SQL Server のドキュメントを参照してください。 

> [!NOTE]
> SQL ミラーリングは、Skype for Business Server 2015 では使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。 AlwaysOn 可用性グループ、AlwaysOn フェールオーバークラスターインスタンス (FCI)、SQL フェールオーバークラスタリングの各方法は、Skype for Business Server 2019 で推奨されます。
  
### <a name="recovery-time-for-automatic-back-end-server-failover-with-database-mirroring"></a>データベース ミラーリングを使用したバックエンド サーバーの自動フェールオーバーの復旧時間

データベース ミラーリングを使用した自動バックエンド フェールオーバーの場合、目標復旧時間 (RTO) のエンジニアリング目標は 5 分です。同期データベース ミラーリングなので、バックエンド サーバー障害の間にデータ損失が発生する可能性は、サーバー間のデータ移動中にフロント エンド サーバーとバックエンド サーバーの両方が同時にダウンするというまれな状況を除き、ありません。目標復旧ポイント (RPO) のエンジニアリング目標は 5 分です。
  
### <a name="user-experience-during-back-end-server-failure-with-database-mirroring"></a>データベース ミラーリングを使用したバックエンド サーバー障害の間のユーザー エクスペリエンス

障害の間のユーザー エクスペリエンスは、障害の性質とトポロジによって異なります。
  
監視を構成してあり、プリンシパルで障害が発生した場合は、データベース ミラーリングを使用したバックエンド サーバーのフェールオーバーは自動的かつ迅速に行われます。アクティブ ユーザーがセッションで大きな中断を感じることはありません。
  
ミラーリング監視が構成されていない場合は、管理者が手動でフェールオーバーを呼び出すまでに少し時間がかかります。 その間、アクティブなユーザーが影響を受ける可能性があります。 残りのセッションは約30分間は通常どおりに続行されます。 それでもプライマリが復元されない場合、または管理者がバックアップにフェールオーバーしていない場合、ユーザーは回復可能モードに切り替わります。つまり、Lync Server に対する永続的な変更を必要とするタスク (連絡先の追加など) を実行することはできません。
  
プリンシパルとミラーの両方のバックエンド サーバーで障害が発生した場合、またはどちらかのサーバーと監視で障害が発生した場合は、(プリンシパルがまだ動作していても) バックエンド サーバーは使用できなくなります。この場合、アクティブ ユーザーはしばらくしてから復元モードに切り替えられます。
  
## <a name="alwayson-availability-groups-and-alwayson-failover-cluster-instances"></a>AlwaysOn 可用性グループと AlwaysOn フェールオーバー クラスター インスタンス

Skype for Business Server は、アクティブ/パッシブとしてのみ、AlwaysOn 可用性グループをサポートします。アクティブ/アクティブにはなりません。 
  
AlwaysOn 可用性グループまたは AlwaysOn フェールオーバークラスターインスタンスを使用するには、最初に SQL Server を使用して高可用性ソリューションをセットアップし、構成します。 次に、トポロジビルダーを使用して、フロントエンドプールに関連付けます。

Skype for Business Server は、次のデータベースソフトウェアを使用して AlwaysOn をサポートしています。

- SQL Server 2019 Enterprise Edition

- SQL Server 2019 Standard Edition の制限事項については、以下の注を参照してください。

- SQL Server 2017 Enterprise Edition

- SQL Server 2017 Standard Edition の制限事項については、以下の注を参照してください。

- SQL Server 2016 Enterprise Edition

- SQL Server 2016 Standard Edition の制限事項については、以下の注を参照してください。

- SQL Server 2014 Enterprise Edition
    
- SQL Server 2012 SP2 と CU2 Enterprise Edition

> [!NOTE]
> SQL Server 2019、2017、2016は、Skype for Business Server 2019 でサポートされている唯一のバージョンです。

> [!NOTE]
> Always On 可用性グループは、SQL 2016、2017、2019標準エディションではサポートされ**ません**が、フェールオーバークラスターインスタンスでは常に使用できます。 詳細については[、「SQL Server 2016 の各エディションとサポートされる機能](https://docs.microsoft.com/sql/sql-server/editions-and-components-of-sql-server-2016?view=sql-server-2017)」を参照してください。
  
> [!IMPORTANT]
> 複数の AlwaysOn 可用性グループインスタンスのインスタンス名は同じである必要があります。 
  
AlwaysOn 可用性グループを展開する手順については、「 [Skype For Business Server のバックエンドサーバーに Alwayson 可用性グループを展開](../../deploy/deploy-high-availability-and-disaster-recovery/alwayson-availability-group.md)する」を参照してください。
  
## <a name="sql-server-failover-clustering"></a>SQL Server フェールオーバー クラスタリング

Skype for Business Server は、次のデータベースソフトウェアで SQL Server フェールオーバークラスタリングをサポートしています。
  
- SQL Server 2019 (Enterprise Edition と Standard Edition の両方)

- SQL Server 2017 (Enterprise Edition と Standard Edition の両方)

- SQL Server 2016 (Enterprise Edition と Standard Edition の両方)

- SQL Server 2014 (Enterprise Edition と Standard Edition の両方)
    
- SQL Server 2012 SP2 と CU2 (Enterprise Edition と Standard Edition の両方)

SQL フェールオーバークラスタリングを使用するには、まず、フロントエンドプールを展開する前に SQL Server クラスターをセットアップして構成する必要があります。 SQL Server 2012 のフェールオーバークラスタリングのベストプラクティスとセットアップ手順につい[https://technet.microsoft.com/library/hh231721.aspx](https://technet.microsoft.com/library/hh231721.aspx)ては、を参照してください。

> [!NOTE]
> SQL Server 2019、2017、SQL Server 2016 は、Skype for Business Server 2019 でサポートされているバージョンのみです。
    
SQL フェールオーバークラスタリングを使用するには、まず、フロントエンドプールを展開する前に SQL Server クラスターをセットアップして構成する必要があります。 SQL Server 2014 および2016のフェールオーバークラスタリングのベストプラクティスとセットアップ手順につい[https://technet.microsoft.com/library/hh231721.aspx](https://technet.microsoft.com/library/hh231721.aspx)ては、を参照してください。 SQL Server 2008 のフェールオーバークラスタリングについ[https://technet.microsoft.com/library/ms189134(v=sql.105).aspx](https://technet.microsoft.com/library/ms189134%28v=sql.105%29.aspx)ては、を参照してください。
  
SQL Server をインストールする際は、SQL Server Management Studio をインストールしてデータベースとログ ファイルの場所を管理する必要があります。SQL Server Management Studio は、SQL Server のインストール時にオプション コンポーネントとしてインストールされます。
  
