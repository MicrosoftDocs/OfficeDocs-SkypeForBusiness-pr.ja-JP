---
title: アーカイブサーバーの SQL Server データベースを削除する
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove the SQL Server database for an Archiving server
ms:assetid: 6e8a1fcd-ed09-43b0-82c9-60e7ce116a01
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688087(v=OCS.15)
ms:contentKeyID: 49733686
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd5bc1fd60afb77b6e66c9315d605e64ea566c72
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035753"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-the-sql-server-database-for-an-archiving-server"></a>アーカイブサーバーの SQL Server データベースを削除する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-04_

Microsoft Lync Server 2010 アーカイブサーバーを削除した後、プールデータをホストしていた SQL Server データベースを削除することができます。 次の手順を使用して、トポロジビルダーから定義を削除し、データベースサーバーからデータベースとログファイルを削除します。

<div>

## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>トポロジビルダーを使用して SQL Server データベースを削除するには

1.  Lync Server 2013 フロントエンドサーバーで、トポロジビルダーを開きます。

2.  トポロジビルダーで、[**共有コンポーネント**] に移動し、[ **sql server ストア**] をクリックし、削除または再構成したアーカイブサーバーに関連付けられている sql server インスタンスを右クリックして、[**削除**] をクリックします。

3.  トポロジを公開し、レプリケーションの状態を確認します。

</div>

<div>

## <a name="to-remove-the-database-files-from-the-sql-server"></a>SQL Server からデータベース ファイルを削除するには

1.  SQL Server のデータベースを削除するには、データベース ファイルを削除している SQL Server の SQL Server sysadmins グループのメンバーである必要があります。

2.  Lync Server 管理シェルを開きます。

3.  コマンドラインで、次のように入力します。
    
        Uninstall-CsDataBase -DatabaseType Archiving -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    ここ\<で\> 、fqdn はデータベースサーバーの完全修飾ドメイン名 (fqdn)、 \<インスタンス\>は名前付きデータベースインスタンス (定義されている場合) です。

4.  **Uninstall-CsDataBase** コマンドレットから操作を確認するメッセージが表示される場合は、情報を読み、**Y** (または Enter) キーを押して操作を続行するか、**N** キーを押し、次に Enter キーを押してコマンドレットを停止します (問題がある場合)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

