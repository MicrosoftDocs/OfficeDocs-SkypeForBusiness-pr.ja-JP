---
title: アーカイブ サーバー用の SQL Server データベースを削除する
TOCTitle: アーカイブ サーバー用の SQL Server データベースを削除する
ms:assetid: 6e8a1fcd-ed09-43b0-82c9-60e7ce116a01
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ688087(v=OCS.15)
ms:contentKeyID: 49886993
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# アーカイブ サーバー用の SQL Server データベースを削除する

 

_**トピックの最終更新日:** 2012-10-04_

Microsoft Lync Server 2010  アーカイブ サーバーを削除した後、プール データをホストしていた SQL Server データベースを削除できます。次の手順を使用して、トポロジ ビルダーから定義を削除し、その後、データベース サーバーからデータベース ファイルとログ ファイルを削除します。

## トポロジ ビルダーを使用して SQL Server データベースを削除するには

1.  Lync Server 2013 フロントエンド サーバーで、トポロジ ビルダーを開きます。

2.  トポロジ ビルダーで、\[**共有コンポーネント**\]、\[**SQL Server ストア**\] の順に移動し、削除または再構成したアーカイブ サーバーと関連付けられた SQL Server インスタンスを右クリックし、\[**削除**\] をクリックします。

3.  トポロジを公開し、レプリケーションの状態を確認します。

## SQL Server からデータベース ファイルを削除するには

1.  SQL Server のデータベースを削除するには、データベース ファイルを削除している SQL Server の SQL Server sysadmins グループのメンバーである必要があります。

2.  Lync Server 管理シェルを開きます。

3.  コマンドラインで、次のように入力します。
    
        Uninstall-CsDataBase -DatabaseType Archiving -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    ここで、\<FQDN\> はデータベース サーバーの完全修飾ドメイン名 (FQDN)、\<instance\> は名前付きデータベース インスタンス (定義されている場合) です。

4.  **Uninstall-CsDataBase** コマンドレットから操作を確認するメッセージが表示される場合は、情報を読み、**Y** (または Enter) キーを押して操作を続行するか、**N** キーを押し、次に Enter キーを押してコマンドレットを停止します (問題がある場合)。

