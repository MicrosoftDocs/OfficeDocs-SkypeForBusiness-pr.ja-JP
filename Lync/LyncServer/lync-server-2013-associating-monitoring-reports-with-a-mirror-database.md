---
title: 'Lync Server 2013: ミラーデータベースとの監視レポートの関連付け'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Associating Monitoring Reports with a mirror database
ms:assetid: 42b797c6-8db8-4ad7-886e-8ddf8deb06f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945624(v=OCS.15)
ms:contentKeyID: 51541467
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 19ff2455d473c83855320555cdffdc2e33001d0d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840906"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="associating-monitoring-reports-with-a-mirror-database-in-lync-server-2013"></a>Lync Server 2013 でのミラーデータベースと監視レポートの関連付け

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-02-07_

監視データベースのミラーを構成してあると、フェイルオーバーが発生した場合にそのミラー データベースがプライマリ データベースを引き継ぎます。 ただし、Lync Server Monitoring レポートを使用してフェールオーバーが発生した場合は、監視レポートがミラーデータベースに接続されていない可能性があります。 これは、監視レポートをインストールするときにプライマリ データベースの場所だけを指定し、ミラー データベースの場所を指定していないためです。

監視レポートがミラー データベースに自動的にフェイルオーバーされるようにするには、監視レポートが使う 2 つのデータベース (通話詳細記録データ用のデータベースと Quality of Experience (QoE) データ用のデータベース) に、ミラー データベースを "フェイルオーバー パートナー" として追加する必要があります (この手順は、監視レポートをインストールした後で実行する必要があります)。フェイルオーバー パートナー情報は、2 つのデータベースが使用する接続文字列の値を手動で編集することで追加できます。この操作を行うには、次の手順に従います。

1.  Internet Explorer を使って **SQL Server Reporting Services** のホーム ページを開きます。Reporting Services のホーム ページの URL には、次の内容が含まれます。
    
      - プレフィックス **http:**。
    
      - Reporting Services がインストールされているコンピューターの完全修飾ドメイン名 (FQDN) (**atl-sql-001.litwareinc.com** など)。
    
      - 文字列 **/レポート\_**。
    
      - 監視レポートがインストールされているデータベース インスタンスの名前 (**archinst** など)。
    
    たとえば、SQL Server Reporting Services がコンピューター atl-sql-001.litwareinc.com にインストールされており、監視レポートでデータベース インスタンス archinst が使われている場合、ホーム ページの URL は次のようになります。
    
    **http://atl-sql-001.litwareinc.com/Reports\_archinst**

2.  Reporting Services のホームページにアクセスしたら、[ **LyncServerReports**] をクリックし、[**レポート\_のコンテンツ**] をクリックします。 この操作を行うと、Lync Server Monitoring レポートの [**レポート\_のコンテンツ**] ページが表示されます。

3.  [**レポート\_のコンテンツ**] ページで、 **cdrdb**データソースをクリックします。

4.  [**CDRDB**] ページの [**プロパティ**] タブで、[**接続文字列**] というテキスト ボックスを探します。現在の接続文字列は、次のとおりです。
    
    **データソース = (ローカル)\\アーキテクチャ inst; 最初のカタログ = LcsCDR**

5.  接続文字列を編集して、ミラー データベースのサーバー名とデータベース インスタンスを含めます。たとえば、サーバーの名前が atl-mirror-001 でミラー データベースが archinst インスタンスにある場合、次の構文を使ってミラー データベースを追加および指定する必要があります。
    
    **フェールオーバーパートナー = atl-mirror-\\001: inst**
    
    編集された接続文字列は、次のようになります。
    
    **データソース = (ローカル)\\アーキテクチャ instフェールオーバーパートナー = atl-ミラー-\\001: inst; 初期カタログ = LcsCDR**

6.  接続文字列を更新したら、[**適用**] をクリックします。

7.  [ **Cdrdb** ] ページで、[**レポート\_コンテンツ**] リンクをクリックします。 [**QMSDB**] データ ソースをクリックして、QoE データベースの接続文字列を編集します。 次に例を示します。
    
    **データソース = (ローカル)\\アーキテクチャ instフェールオーバーパートナー = atl-mirror-\\001: inst、initial Catalog = QoEMetrics**

8.  [**適用**] をクリックします。

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 監視レポートをインストールする](lync-server-2013-installing-lync-server-2013-monitoring-reports.md)  
[Lync Server 2013 で監視レポートを使用する](lync-server-2013-using-monitoring-reports.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

