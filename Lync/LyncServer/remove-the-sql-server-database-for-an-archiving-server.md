---
title: アーカイブ サーバー用の SQL Server データベースの削除
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Remove the SQL Server database for an Archiving server
ms:assetid: 6e8a1fcd-ed09-43b0-82c9-60e7ce116a01
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688087(v=OCS.15)
ms:contentKeyID: 49733686
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a0794d751ae0c469539971d4b29685e2971d865
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847951"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-the-sql-server-database-for-an-archiving-server"></a>アーカイブ サーバー用の SQL Server データベースの削除

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-04_

Microsoft Lync Server 2010 アーカイブサーバーを削除したら、プールデータをホストしている SQL Server データベースを削除できます。 次の手順を使用して、Topology Builder から定義を削除し、データベースサーバーからデータベースとログファイルを削除します。

<div>

## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>トポロジビルダーを使用して SQL Server データベースを削除するには

1.  Lync Server 2013 フロントエンドサーバーで、[トポロジビルダー] を開きます。

2.  [トポロジビルダー] で、[**共有コンポーネント**] に移動し、[ **sql server ストア**] で、削除または再構成されたアーカイブサーバーに関連付けられている sql server インスタンスを右クリックし、[**削除**] をクリックします。

3.  トポロジを公開し、レプリケーションの状態を確認します。

</div>

<div>

## <a name="to-remove-the-database-files-from-the-sql-server"></a>SQL Server からデータベースファイルを削除するには

1.  SQL Server 上のデータベースを削除するには、データベースファイルを削除する SQL Server の [SQL Server のオプション] グループのメンバーである必要があります。

2.  Lync Server 管理シェルを開きます。

3.  コマンドラインで、次のように入力します。
    
        Uninstall-CsDataBase -DatabaseType Archiving -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    ここ\<で\> 、fqdn はデータベースサーバーの完全修飾ドメイン名 (FQDN) であり\<、\>インスタンスは名前付きデータベースインスタンス (定義されている場合) です。

4.  **CsDataBase**コマンドレットで操作の確認を求めるメッセージが表示されたら、情報を読み、 **Y**キーを押します (または、enter **** キーを押すか、enter キーを押して続行します)。または、コマンドレットを停止するか (エラーがある場合)、enter キーを押します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

