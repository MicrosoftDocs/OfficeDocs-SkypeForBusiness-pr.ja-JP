---
title: 'Lync Server 2013: 監視のためのコンポーネントとトポロジ'
TOCTitle: 監視のためのコンポーネントとトポロジ
ms:assetid: c1bb36b0-1fb8-4d8e-9cc9-9bef740fe3c6
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg412952(v=OCS.15)
ms:contentKeyID: 48273492
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 における監視のためのコンポーネントとトポロジ

 

_**トピックの最終更新日:** 2012-09-05_

統合データ収集エージェントは、各フロントエンド サーバーに自動的にインストールされてアクティブ化されるので、監視サーバーとして動作するようにサーバーを構成する必要はありません。ただし、監視データ用のバックエンド データ ストアとして機能するデータベースをインストールして構成する必要があります。 Microsoft Lync Server 2013 では、監視用のバックエンド ストアとして、次のデータベースのどれでも使用できます。

  - Microsoft SQL Server 2008 R2 Enterprise Edition

  - Microsoft SQL Server 2008 R2 Standard Edition

  - Microsoft SQL Server 2012 Enterprise Edition

  - Microsoft SQL Server 2012 Standard Edition

これらのデータベースの 64 ビット版を使用する必要があることに注意してください。32 ビット版の SQL Server は監視用のバックエンド ストアとして使用できません。同様に、 Lync Server 2013 は SQL Server 2008 または SQL Server 2012 の Express Edition をサポートしません。 Lync Server 2013 のデータベース要件については、 Lync Server 2013 サポート ガイドのトピック「[Lync Server 2013 でのデータベース ソフトウェアのサポート](lync-server-2013-database-software-support.md)」を参照してください。

監視を展開して構成する前に、SQL Server がインストールされ構成されている必要があることを念頭に置いてください。ただし、展開する必要があるのは SQL Server のみです。監視データベースを事前にセットアップする必要はありません。これらのデータベースは、 Lync Server トポロジを公開するときに自動的に作成されます。

監視データと他の種類のデータで 1 つの SQL Server インスタンスを共有することができます。一般には、通話詳細記録データベース (LcsCdr) と Quality of Experience データベース (QoEMetrics) で同じ SQL インスタンスを共有します。また、2 つの監視データベースを、アーカイブ データベース (LcsLog) として同じ SQL インスタンスに配置するのも一般的です。SQL Server インスタンスに関する実際の唯一の要件は、SQL Server のどのインスタンスについても、次の制限が設けられることです。

  - Lync Server 2013 バックエンド データベースは 1 インスタンス (一般的なルールとして、監視データベースを同じ SQL インスタンスに共存させること、さらには同じコンピューター上に共存させることもお勧めできません。技術的には可能ですが、バックエンド データベースに必要なディスク容量を監視データベースが使い切ってしまうリスクがあります)。

  - 通話詳細記録データベースは 1 インスタンス。

  - Quality of Experience データベースは 1 インスタンス。

  - アーカイブ データベースは 1 インスタンス。

言い換えると、同じ SQL Server インスタンス内に LcsCdr データベースのインスタンスを 2 つ持つことはできません。LcsCdr データベースのインスタンスが複数必要な場合は、SQL Server のインスタンスを複数構成する必要があります。

## 関連項目

#### その他のリソース

[Lync Server 2013 での監視の展開](lync-server-2013-deploying-monitoring.md)

