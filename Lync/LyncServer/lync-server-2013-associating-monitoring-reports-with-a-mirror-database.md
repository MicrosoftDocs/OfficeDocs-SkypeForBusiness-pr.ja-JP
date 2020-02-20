---
title: 'Lync Server 2013: 監視レポートとミラーデータベースの関連付け'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Associating Monitoring Reports with a mirror database
ms:assetid: 42b797c6-8db8-4ad7-886e-8ddf8deb06f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945624(v=OCS.15)
ms:contentKeyID: 51541467
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 48dbf5530a071bc1f23f9d2c05d82e151f51f645
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149166"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="associating-monitoring-reports-with-a-mirror-database-in-lync-server-2013"></a>Lync Server 2013 での監視レポートとミラーデータベースの関連付け

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-02-07_

監視データベースのミラーを構成すると、フェールオーバーが発生した場合に、ミラーデータベースがプライマリデータベースとして引き継がれます。 ただし、Lync Server の監視レポートを使用し、フェールオーバーが発生した場合は、監視レポートがミラーデータベースに接続されていない可能性があります。 これは、監視レポートをインストールするときに、プライマリデータベースの場所のみを指定するからです。ミラーデータベースの場所を指定する必要はありません。

ミラーデータベースに自動的にフェールオーバーするように監視レポートを取得するには、監視レポートで使用される2つのデータベースに対してミラーデータベースを "フェールオーバーパートナー" として追加する必要があります (1 つは通話詳細レコードデータ、もう一方のデータベースは、Experience (QoE) データ)。 (この手順は、監視レポートをインストールした後に実行する必要があります。)フェールオーバーパートナー情報を追加するには、これら2つのデータベースで使用される接続文字列値を手動で編集します。 これを行うには、次の手順を実行します。

1.  Internet Explorer を使用して、 **SQL Server Reporting Services**のホームページを開きます。 Reporting Services のホームページの URL には次のものが含まれます。
    
      - **Http:** プレフィックス。
    
      - Reporting Services がインストールされているコンピューターの完全修飾ドメイン名 (FQDN) (たとえば、 **atl-sql-001.litwareinc.com**)。
    
      - 文字列 **/レポート\_**。
    
      - 監視レポートがインストールされているデータベースインスタンスの名前 (例: **arch inst**)。
    
    たとえば、コンピューター atl-sql-001.litwareinc.com に SQL Server Reporting Services がインストールされており、監視レポートでデータベースインスタンスアーキテクチャを使用している場合、ホームページの URL は次のようになります。
    
    **http://atl-sql-001.litwareinc.com/Reports\_archinst**

2.  Reporting Services のホームページにアクセスした後、[ **LyncServerReports**] をクリックしてから、[**レポート\_のコンテンツ**] をクリックします。 これにより、Lync Server 監視レポートの [**レポート\_のコンテンツ**] ページに移動します。

3.  [**レポート\_のコンテンツ**] ページで、 **cdrdb**データソースをクリックします。

4.  **Cdrdb**ページの [**プロパティ**] タブで、[**接続文字列**] というラベルのテキストボックスを検索します。 現在の接続文字列は次のようになります。
    
    **データソース = (ローカル)\\アーキテクチャ inst; 最初のカタログ = LcsCDR**

5.  接続文字列を編集して、ミラーデータベースのサーバー名とデータベースインスタンスを含めます。 たとえば、サーバーが atl-ws-01 という名前で、ミラーデータベースが arch inst インスタンス内にある場合は、次の構文を使用してミラーデータベースを指定する必要があります。
    
    **フェールオーバーパートナー = atl-ミラー-\\001**
    
    編集された接続文字列は、次のようになります。
    
    **データソース = (ローカル)\\アーキテクチャ instフェールオーバーパートナー = atl-ミラー-\\001、初期カタログ = LcsCDR**

6.  接続文字列を更新した後、[**適用**] をクリックします。

7.  [ **Cdrdb** ] ページで、[**レポート\_コンテンツ**] リンクをクリックします。 **Qmsdb**データソースをクリックし、qmsdb データベースの接続文字列を編集します。 次に例を示します。
    
    **データソース = (ローカル)\\アーキテクチャ instフェールオーバーパートナー = atl-ミラー-\\001 (初期カタログ = QoEMetrics**

8.  [**適用**] をクリックします。

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 監視レポートのインストール](lync-server-2013-installing-lync-server-2013-monitoring-reports.md)  
[Lync Server 2013 での監視レポートの使用](lync-server-2013-using-monitoring-reports.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

