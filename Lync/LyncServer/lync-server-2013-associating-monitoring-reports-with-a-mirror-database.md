---
title: 監視レポートとミラー データベースの関連付け
TOCTitle: 監視レポートとミラー データベースの関連付け
ms:assetid: 42b797c6-8db8-4ad7-886e-8ddf8deb06f9
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ945624(v=OCS.15)
ms:contentKeyID: 52056585
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 監視レポートとミラー データベースの関連付け

 

_**トピックの最終更新日:** 2014-02-07_

監視データベースのミラーを構成してあると、フェイルオーバーが発生した場合にそのミラー データベースがプライマリ データベースを引き継ぎます。ただし、Lync Server の監視レポートを使っていてフェイルオーバーが発生した場合、監視レポートがミラー データベースに接続しないことがあります。これは、監視レポートをインストールするときにプライマリ データベースの場所だけを指定し、ミラー データベースの場所を指定していないためです。

監視レポートがミラー データベースに自動的にフェイルオーバーされるようにするには、監視レポートが使う 2 つのデータベース (通話詳細記録データ用のデータベースと Quality of Experience (QoE) データ用のデータベース) に、ミラー データベースを "フェイルオーバー パートナー" として追加する必要があります (この手順は、監視レポートをインストールした後で実行する必要があります)。フェイルオーバー パートナー情報は、2 つのデータベースが使用する接続文字列の値を手動で編集することで追加できます。これを行うには、次の手順に従います。

1.  Internet Explorer を使って **SQL Server Reporting Services** のホーム ページを開きます。Reporting Services のホーム ページの URL には、次の内容が含まれます。
    
      - プレフィックス **http:**
    
      - Reporting Services がインストールされているコンピューターの完全修飾ドメイン名 (FQDN) (**atl-sql-001.litwareinc.com** など)
    
      - 文字列 **/Reports\_**
    
      - 監視レポートがインストールされているデータベース インスタンスの名前 (**archinst** など)
    
    たとえば、SQL Server Reporting Services がコンピューター atl-sql-001.litwareinc.com にインストールされ、監視レポートでデータベース インスタンス archinst が使われる場合、ホーム ページの URL は次のようになります。
    
    **http://atl-sql-001.litwareinc.com/Reports\_archinst**

2.  Reporting Services ホーム ページにアクセスしたら、\[**LyncServerReports**\]、\[**Reports\_Content**\] の順にクリックします。Lync Server 監視レポートの \[**Reports\_Content**\] ページに移動します。

3.  \[**Reports\_Content**\] ページで、\[**CDRDB**\] データ ソースをクリックします。

4.  \[**CDRDB**\] ページの \[**プロパティ**\] タブで、\[**接続文字列**\] というテキスト ボックスを探します。現在の接続文字列は、次のとおりです。
    
    **Data source=(local)\\archinst;initial catalog=LcsCDR**

5.  接続文字列を編集して、ミラー データベースのサーバー名とデータベース インスタンスを含めます。たとえば、サーバーの名前が atl-mirror-001 でミラー データベースが archinst インスタンスにある場合、次の構文を使ってミラー データベースを追加および指定する必要があります。
    
    **Failover Partner=atl-mirror-001\\archinst**
    
    編集された接続文字列は、次のようになります。
    
    **Data source=(local)\\archinst;Failover Partner=atl-mirror-001\\archinst;initial catalog=LcsCDR**

6.  接続文字列を更新したら、\[**適用**\] をクリックします。

7.  \[**CDRDB**\] ページで、\[**Reports\_Content**\] リンクをクリックします。\[**QMSDB**\] データ ソースをクリックして、QoE データベースの接続文字列を編集します。次に例を示します。
    
    **Data source=(local)\\archinst;Failover Partner=atl-mirror-001\\archinst;initial catalog=QoEMetrics**

8.  \[**適用**\] をクリックします。

## 関連項目

#### 概念

[Lync Server 2013 監視レポートのインストール](lync-server-2013-installing-lync-server-2013-monitoring-reports.md)  
[Lync Server 2013 での監視レポートの使用](lync-server-2013-using-monitoring-reports.md)

