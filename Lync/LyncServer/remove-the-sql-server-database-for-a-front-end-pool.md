---
title: フロントエンドプールの SQL Server データベースを削除する
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove the SQL Server database for a Front End pool
ms:assetid: 6bb932df-3ed7-49b6-ae17-61e4c6a5fe82
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688084(v=OCS.15)
ms:contentKeyID: 49733681
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a69972d355ad2870445af14ccfeb097f1d8a6dcb
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42189400"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-the-sql-server-database-for-a-front-end-pool"></a>フロントエンドプールの SQL Server データベースを削除する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-04_

Microsoft Lync Server 2010 フロントエンドプールを削除するか、または別のデータベースを使用するようにプールを再構成すると、プールデータをホストしていた SQL Server データベースを削除することができます。 次の手順を使用して、トポロジビルダーから定義を削除し、データベースサーバーからデータベースとログファイルを削除します。

<div>

## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>トポロジビルダーを使用して SQL Server データベースを削除するには

1.  Lync Server 2013 フロントエンドサーバーから、トポロジビルダーを開き、既存のトポロジをダウンロードします。

2.  [トポロジビルダー] で、[**共有コンポーネント**] に移動し、[ **sql server ストア**] を選択して、削除または再構成したフロントエンドプールに関連付けられている SQL server インスタンスを右クリックし、[**削除**] をクリックします。

3.  トポロジを公開し、レプリケーションの状態を確認します。

</div>

<div>

## <a name="to-remove-user-and-application-databases-from-the-sql-server"></a>SQL Server からユーザーおよびアプリケーション データベースを削除するには

1.  SQL Server のデータベースを削除するには、データベース ファイルを削除している SQL Server の SQL Server sysadmins グループのメンバーである必要があります。

2.  Lync Server 管理シェルを開く

3.  プール ユーザー ストアのデータベースを削除するには、次のように入力します。
    
        Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    ここ\<で\> 、fqdn はデータベースサーバーの完全修飾ドメイン名 (fqdn)、 \<インスタンス\>は名前付きデータベースインスタンス (定義されている場合) です。

4.  プール アプリケーション ストアのデータベースを削除するには、次のように入力します。
    
        Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    ここ\<で\> 、fqdn はデータベースサーバーの fqdn、 \<インスタンス\>は名前付きデータベースインスタンス (定義されている場合) です。

5.  **Uninstall-CsDataBase** コマンドレットから操作を確認するメッセージが表示される場合は、情報を読み、**Y** (または Enter) キーを押して操作を続行するか、**N** キーを押し、次に Enter キーを押してコマンドレットを停止します (問題がある場合)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

