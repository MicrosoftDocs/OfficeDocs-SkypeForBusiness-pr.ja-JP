---
title: フロントエンド プール用の SQL Server データベースの削除
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
ms.openlocfilehash: 853b52c6f6a06d05f106114ab6b59ebc52129fc3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727147"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-the-sql-server-database-for-a-front-end-pool"></a>フロントエンド プール用の SQL Server データベースの削除

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-04_

Microsoft Lync Server 2010 フロントエンドプールを削除するか、プールを再構成して別のデータベースを使用する場合は、プールデータをホストしている SQL Server データベースを削除できます。 次の手順を使用して、Topology Builder から定義を削除し、データベースサーバーからデータベースとログファイルを削除します。

<div>

## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>トポロジビルダーを使用して SQL Server データベースを削除するには

1.  Lync Server 2013 フロントエンドサーバーから、[トポロジビルダー] を開き、既存のトポロジをダウンロードします。

2.  [トポロジビルダー] で、[**共有コンポーネント**] に移動し、[ **sql Server ストア**] で、削除または再構成されたフロントエンドプールに関連付けられている sql server インスタンスを右クリックし、[**削除**] をクリックします。

3.  トポロジを公開し、レプリケーションの状態を確認します。

</div>

<div>

## <a name="to-remove-user-and-application-databases-from-the-sql-server"></a>SQL Server からユーザーデータベースとアプリケーションデータベースを削除するには

1.  SQL Server 上のデータベースを削除するには、データベースファイルを削除する SQL Server の [SQL Server のオプション] グループのメンバーである必要があります。

2.  Lync Server 管理シェルを開く

3.  プールユーザーストアのデータベースを削除するには、次のように入力します。
    
        Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    ここ\<で\> 、fqdn はデータベースサーバーの完全修飾ドメイン名 (FQDN) であり\<、\>インスタンスは名前付きデータベースインスタンス (定義されている場合) です。

4.  プールアプリケーションストアのデータベースを削除するには、次のように入力します。
    
        Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    ここ\<で\> 、fqdn はデータベースサーバーの fqdn で、 \<インスタンス\>は名前付きデータベースインスタンス (定義されている場合) です。

5.  **CsDataBase**コマンドレットで操作の確認を求めるメッセージが表示されたら、情報を読み、 **Y**キーを押します (または、enter キーを押すか、enter キーを押して続行します)。または、コマンドレットを停止するか (エラーがある場合)、enter キー**を押します**。

</div>

</div>

<span> </span>

</div>

</div>

</div>

