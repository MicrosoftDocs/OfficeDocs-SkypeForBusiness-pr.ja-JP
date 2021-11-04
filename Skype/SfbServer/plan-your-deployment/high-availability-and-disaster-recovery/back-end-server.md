---
title: バック エンド サーバーの高可用性 (Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: c559aacb-4e1d-4e78-9582-41f966ad418d
description: AlwaysOn 可用性グループ、AlwaysOn フェールオーバー クラスター インスタンス、データベース ミラーリング、SQL フェールオーバー クラスタリングなど、Skype for Business Server でサポートされるバック エンド サーバーの高可用性オプションについて説明します。
ms.openlocfilehash: 6020f1a474c450da66fcb6fd5249db39fb0c29be
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60773507"
---
# <a name="back-end-server-high-availability-in-skype-for-business-server"></a>バック エンド サーバーの高可用性 (Skype for Business Server
 
AlwaysOn 可用性グループ、AlwaysOn フェールオーバー クラスター インスタンス、データベース ミラーリング、SQL フェールオーバー クラスタリングなど、Skype for Business Server でサポートされるバック エンド サーバーの高可用性オプションについて説明します。
  
バック エンド サーバーの高可用性を強化するには、次の 4 つのオプションがあります。
  
- データベース ミラーリング
    
- AlwaysOn 可用性グループ
    
- AlwaysOn フェールオーバー クラスター インスタンス (FCI)
    
- SQLフェールオーバー クラスタリング
    
これらのソリューションのいずれかを使用する方法はオプションですが、組織のビジネス継続性を維持するためにお勧めします。 それ以外の場合、単一のデータベース サーバーがダウンすると、データの重大な損失Skype for Business Serverがあります。 
  
トポロジ ビルダーのみを使用してデータベース ミラーリングを設定できます。 AlwaysOn 可用性グループ、AlwaysOn フェールオーバー クラスター インスタンス、または SQL フェールオーバー クラスタリングの場合は、SQL Server を使用して高可用性ソリューションを作成し、トポロジ ビルダーを使用してフロントエンド プールに関連付けられます。
  
障害復旧のために別のフロントエンド プールとペアにされているフロントエンド プールでバック エンド サーバーの高可用性を使用する場合は、両方のプールで同じバック エンド 高可用性ソリューションを使用する必要があります。 
  
## <a name="database-mirroring"></a>データベース ミラーリング

Skype for Business Serverは、次のデータベース ソフトウェアを使用したミラーリングをサポートしています。
  
- SQL Server 2019 では、Enterprise EditionとStandard Edition

- SQL Server 2017 では、Enterprise EditionとStandard Edition

- SQL Server 2016 年、Enterprise EditionとStandard Edition

- SQL Server 2014 では、Enterprise EditionとStandard Edition
    
- SQL Server 2012 SP2 と CU2 は、Enterprise EditionとStandard Edition
    

> [!NOTE]
> SQLミラーリングは 2015 年Skype for Business Server使用できますが、2019 年Skype for Business Serverではサポートされていません。 AlwaysOn 可用性グループ、AlwaysOn フェールオーバー クラスター インスタンス (FCI)、および SQL フェールオーバー クラスタリング方法は、2019 年にサポートされている唯一のSkype for Business Serverです。
    
非同期データベース ミラーリングは、バック エンド サーバーの高可用性に対してサポートSkype for Business Server。 このドキュメントの残りの部分では、データベース ミラーリングとは、特に明示的に指定されていない限り、同期データベース ミラーリングを意味します。 
  
フロントエンド プールにデータベース ミラーリングを展開すると、プール内のすべての Skype for Business Server データベース (このプール内にサーバーの全体管理ストアがある場合はサーバーの全体管理ストアを含む) と、応答グループ アプリケーション データベースとコール パーク アプリケーション データベース (それらのアプリケーションがプールで実行されている場合) がミラーリングされます。 
  
データベース ミラーリングでは、サーバーに共有ストレージを使用する必要はありません。 各サーバーは、データベースのコピーをローカル ストレージに保持しします。 
  
ミラーリング監視を使用する場合と使用しない場合は、データベース ミラーリングを展開できます。 バックエンド サーバーのフェールオーバーが自動的になるので、監視を使用することをお勧めします。 使用しない場合は、管理者が手動でフェールオーバーを実行する必要があります。 監視を展開した場合でも、管理者は必要に応じてバックエンド サーバーのフェールオーバーを手動で開始できます。
  
監視を使用する場合は、バックエンド サーバーの複数のペアに対して 1 つの監視を使用できます。監視とバックエンド サーバーのペアを 1 対 1 で対応させる必要はありません。ただし、バックエンド サーバーの複数のペアに対して 1 つの監視を使用する展開は、ペアごとに異なる監視を使用するトポロジほど復元性が高くありません。 
  
### <a name="guidelines-for-planning-back-end-server-mirroring"></a>バック エンド サーバーミラーリングの計画に関するガイドライン

一般に、2 つのバックエンド サーバー間での SQL ミラーリングを設定するには、以下の要件を満たしている必要があります。
  
- プライマリ サーバーのバージョンのサーバーは、SQL ServerミラーリングをSQL必要があります。
    
- プライマリ、ミラー、およびミラーリング監視 (展開されている場合) の各 SQL Server が同一バージョンである。 
    
- プライマリおよびミラーの各 SQL Server が同一エディションである (ミラーリング監視のエディションは異なっていても構いません)。
    
監視SQLでサポートされているSQLのベスト プラクティスについては、MSDN ライブラリの[「データベース](/sql/database-engine/database-mirroring/database-mirroring-witness)ミラーリング監視」を参照してください。
  
サーバー ミラーリングを構成する前に、まずデータベースのアクセス許可をSQL設定する必要があります。 詳細については、「データベース ミラーリングまたは AlwaysOn 可用性グループのログイン アカウントを設定[する (SQL Server)」を参照してください](/sql/database-engine/database-mirroring/set-up-login-accounts-database-mirroring-always-on-availability)。
  
SQL ミラーリングでは、データベース復旧モードは常に [**完全**] に設定されます。これは、トランザクション ログ サイズを綿密に監視し、トランザクション ログを定期的にバックアップしてバックエンド サーバー上のディスク容量の不足を回避する必要があることを意味します。トランザクション ログのバックアップ頻度は、ログの増加率によって決まります。ログの増加率は、フロントエンド プールのユーザー アクティビティによるデータベース トランザクションによって決まります。Lync 展開ワークロードに対して予想されるトランザクション ログの増加を判断し、それに応じて計画することをお勧めします。次の記事では、SQL バックアップおよびログ管理に関する追加情報を提供しています。
  
> [!IMPORTANT]
> トポロジ ビルダーまたはコマンドレットを使用して SQL ミラーリングをセットアップおよび削除することがサポートされているのは、プライマリ サーバー、ミラー サーバー、監視サーバー (必要な場合) すべてが同じドメインに属している場合のみです。 異なるドメインのサーバーに SQL ミラーリングを設定する場合は、SQL Server のドキュメントを参照してください。 

> [!NOTE]
> SQLミラーリングは 2015 年Skype for Business Server使用できますが、2019 年Skype for Business Serverではサポートされていません。 AlwaysOn 可用性グループ、AlwaysOn フェールオーバー クラスター インスタンス (FCI)、および SQL フェールオーバー クラスタリング方法は、2019 年Skype for Business Serverです。
  
### <a name="recovery-time-for-automatic-back-end-server-failover-with-database-mirroring"></a>データベース ミラーリングによるバック エンド サーバーの自動フェールオーバーの復旧時間

データベース ミラーリングによるバック エンドの自動フェールオーバーの場合、目標復旧時間 (RTO) のエンジニアリング 目標は 5 分です。 同期データベース ミラーリングのため、バック エンド サーバーの障害時のデータ損失は予測されませんが、フロントエンド サーバーとバック エンド サーバーの両方が同時にダウンし、データがサーバー間で移動される場合を除きます。 目標復旧ポイント (RPO) のエンジニアリング目標は 5 分です。
  
### <a name="user-experience-during-back-end-server-failure-with-database-mirroring"></a>データベース ミラーリングを使用したバック エンド サーバーの障害時のユーザー エクスペリエンス

障害の間のユーザー エクスペリエンスは、障害の特徴とトポロジによって異なります。
  
データベース ミラーリングを使用してミラーリング監視を構成し、プリンシパルが失敗した場合、バック エンド サーバーのフェールオーバーは自動的かつ迅速に行われます。 使用中のユーザーがセッションで大きな中断を感じることはありません。
  
監視が構成されていない場合、管理者が手動でフェールオーバーを呼び出すのに時間がかかる場合があります。 その間、アクティブなユーザーが影響を受ける可能性があります。 セッションは通常通り約 30 分間継続します。 プライマリがまだ復元されていない場合、または管理者がバックアップに失敗していない場合、ユーザーは復元モードに切り替わります。つまり、Lync Server で永続的な変更が必要なタスク (連絡先の追加など) を実行できません。
  
プリンシパルとミラーの両方のバックエンド サーバーで障害が発生した場合、またはどちらかのサーバーと監視で障害が発生した場合は、バックエンド サーバーは使用できなくなります (プリンシパルがまだ動作していたとしても)。この場合、使用中のユーザーはしばらくしてから復元モードに切り替えられます。
  
## <a name="alwayson-availability-groups-and-alwayson-failover-cluster-instances"></a>AlwaysOn 可用性グループと AlwaysOn フェールオーバー クラスター インスタンス

Skype for Business Server AlwaysOn 可用性グループはアクティブ/パッシブとしてのみサポートし、アクティブ/アクティブはサポートしない。 
  
AlwaysOn 可用性グループまたは AlwaysOn フェールオーバー クラスター インスタンスを使用するには、まず、SQL Serverを使用して高可用性ソリューションを設定および構成します。 その後、トポロジ ビルダーを使用して、フロントエンド プールに関連付けできます。

Skype for Business Serverデータベース ソフトウェアを使用して AlwaysOn をサポートしています。

- SQL Server 2019 Enterprise Edition

- SQL Server 2019 Standard Editionに関する制限事項については、以下の注を参照してください。

- SQL Server 2017 Enterprise Edition

- SQL Server 2017 Standard Editionに関する制限事項については、以下の注を参照してください。

- SQL Server 2016 Enterprise Edition

- SQL Server 2016 Standard Editionに関する制限事項については、以下の注を参照してください。

- SQL Server 2014 Enterprise Edition
    
- SQL Server 2012 SP2 および CU2 Enterprise Edition

> [!NOTE]
> SQL Server 2019、2017、および 2016 は、2019 年にサポートされているSkype for Business Serverです。

> [!NOTE]
> Always On 可用性 **グループは**、SQL 2016、2017、2019 の標準エディションではサポートされていませんが、Always On フェールオーバー クラスター インスタンスを使用できます。 詳細[については、「Editions and supported features of SQL Server 2016」](/sql/sql-server/editions-and-components-of-sql-server-2016?view=sql-server-2017)を参照してください。
  
> [!IMPORTANT]
> 複数の AlwaysOn 可用性グループ インスタンスのインスタンス名は同じである必要があります。 
  
AlwaysOn 可用性グループを展開する手順については[、「AlwaysOn](../../deploy/deploy-high-availability-and-disaster-recovery/alwayson-availability-group.md)可用性グループをバック エンド サーバーに展開する」を参照Skype for Business Server。
  
## <a name="sql-server-failover-clustering"></a>SQL Serverフェールオーバー クラスタリング

Skype for Business Serverデータベース ソフトウェアSQL Serverフェールオーバー クラスタリングをサポートしています。
  
- SQL Server 2019 では、Enterprise EditionとStandard Edition

- SQL Server 2017 では、Enterprise EditionとStandard Edition

- SQL Server 2016 年、Enterprise EditionとStandard Edition

- SQL Server 2014 では、Enterprise EditionとStandard Edition
    
- SQL Server 2012 SP2 と CU2 は、Enterprise EditionとStandard Edition

フェールオーバー クラスタリングSQLするには、まずフロントエンド プールを展開する前に、SQL Serverクラスターをセットアップして構成する必要があります。 2012 年のフェールオーバー クラスタリングのベスト プラクティスとセットアップ手順については、「SQL Server」を参照してください [https://technet.microsoft.com/library/hh231721.aspx](/sql/sql-server/failover-clusters/install/sql-server-failover-cluster-installation) 。

> [!NOTE]
> SQL Server 2019、2017、および SQL Server 2016 は、2019 年にサポートされているSkype for Business Serverです。
    
フェールオーバー クラスタリングSQLするには、まずフロントエンド プールを展開する前に、SQL Serverクラスターをセットアップして構成する必要があります。 2014 年と 2016 年のフェールオーバー クラスタリングのベスト プラクティスとセットアップ手順については、「SQL Server」を参照してください [https://technet.microsoft.com/library/hh231721.aspx](/sql/sql-server/failover-clusters/install/sql-server-failover-cluster-installation) 。 2008 年のフェールオーバー クラスタリングSQL Serverを参照してください [https://technet.microsoft.com/library/ms189134(v=sql.105).aspx](/previous-versions/sql/sql-server-2008-r2/ms189134(v=sql.105)) 。
  
SQL Server をインストールする際には、データベースの場所とログ ファイルの場所を管理するための SQL Server Management Studio をインストールする必要があります。 SQL Server Management Studio は、SQL Server のインストール時にオプションのコンポーネントとしてインストールされます。
