---
title: フロントエンド プールの SQL Server データベースの削除
TOCTitle: フロントエンド プールの SQL Server データベースの削除
ms:assetid: 6bb932df-3ed7-49b6-ae17-61e4c6a5fe82
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ688084(v=OCS.15)
ms:contentKeyID: 49886988
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# フロントエンド プールの SQL Server データベースの削除

 

_**トピックの最終更新日:** 2012-10-04_

Microsoft Lync Server 2010 の フロント エンド プールを削除するか、異なるデータベースを使用するように再構成した後は、このプールのデータをホストしていた SQL Server データベースを削除できます。トポロジ ビルダーから該当する定義を削除し、データベース サーバーからデータベースとログ ファイルを削除するには、以下の手順を実行します。

## トポロジ ビルダーを使用して SQL Server データベースを削除するには

1.  Lync Server 2013 のフロントエンド サーバーから トポロジ ビルダーを開き、既存のトポロジをダウンロードします。

2.  トポロジ ビルダーで、\[**共有コンポーネント**\]、\[**SQL Server ストア**\] の順に移動し、削除または再構成したフロント エンド プールと関連付けられた SQL Server インスタンスを右クリックし、\[**削除**\] をクリックします。

3.  トポロジを公開し、レプリケーションの状態を確認します。

## SQL Server からユーザーおよびアプリケーション データベースを削除するには

1.  SQL Server のデータベースを削除するには、データベース ファイルを削除している SQL Server の SQL Server sysadmins グループのメンバーである必要があります。

2.  Lync Server 管理シェルを開きます。

3.  プール ユーザー ストアのデータベースを削除するには、次のように入力します。
    
        Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    ここで、\<FQDN\> はデータベース サーバーの完全修飾ドメイン名 (FQDN)、\<instance\> は名前付きデータベース インスタンス (定義されている場合) です。

4.  プール アプリケーション ストアのデータベースを削除するには、次のように入力します。
    
        Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    ここで、\<FQDN\> はデータベース サーバーの FQDN、\<instance\> は名前付きデータベース インスタンス (定義されている場合) です。

5.  **Uninstall-CsDataBase** コマンドレットから操作を確認するメッセージが表示される場合は、情報を読み、**Y** (または Enter) キーを押して操作を続行するか、**N** キーを押し、次に Enter キーを押してコマンドレットを停止します (問題がある場合)。

