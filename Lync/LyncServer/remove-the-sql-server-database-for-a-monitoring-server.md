---
title: 監視サーバーの SQL Server データベースを削除する
TOCTitle: 監視サーバーの SQL Server データベースを削除する
ms:assetid: aed5e394-d63e-4ad4-af40-f12d3a044344
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ721848(v=OCS.15)
ms:contentKeyID: 49887101
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 監視サーバーの SQL Server データベースを削除する

 

_**トピックの最終更新日:** 2012-10-04_

Microsoft Lync Server 2010  監視サーバーを削除したら、サーバー データをホストしていた SQL Server データベースを削除できます。以下の手順で、 トポロジ ビルダー内の定義を削除し、その後、データベース サーバーからデータベース ファイルとログ ファイルを削除します。

## トポロジ ビルダーを使用して SQL Server データベースを削除するには

1.  Lync Server 2013 フロントエンド サーバーで、 トポロジ ビルダーを開きます。

2.  トポロジ ビルダーで、\[**共有コンポーネント**\]、\[**SQL Server ストア**\] の順に移動し、削除または再構成した 監視サーバーと関連付けられた SQL Server インスタンスを右クリックし、\[**削除**\] をクリックします。

3.  トポロジを公開し、レプリケーションの状態を確認します。

## SQL Server からデータベース ファイルを削除するには

1.  SQL Server ベースのサーバーにあるデータベースを削除するためには、削除しようとしているデータベース ファイルがある SQL Server ベースのサーバーの SQL Server sysadmins グループのメンバーでなければなりません。

2.  Lync Server 管理シェルを開きます。

3.  コマンドラインで、次のように入力します。
    
        Uninstall-CsDataBase -DatabaseType Monitoring -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    ここで、 *\<FQDN\>* はデータベース サーバーの完全修飾ドメイン名 (FQDN)、 *\<instance\>* はオプションの名前付きデータベース インスタンスです。

4.  **Uninstall-CsDataBase** コマンドレットから操作を確認するメッセージが表示される場合は、情報を読み、 **Y** (または Enter) キーを押して操作を続行するか、 **N** キーを押し、次に Enter キーを押してコマンドレットを停止します (問題がある場合)。

