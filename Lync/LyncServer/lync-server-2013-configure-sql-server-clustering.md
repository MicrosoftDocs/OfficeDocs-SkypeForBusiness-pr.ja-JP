---
title: 'Lync Server 2013: SQL Server のクラスター化の構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure SQL Server clustering
ms:assetid: d7b52ef1-573c-48ed-bb94-34e37b49645c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn383982(v=OCS.15)
ms:contentKeyID: 56472032
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 59c02a5ab417a17c7c81b2c495ce96e6948aebc7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42179894"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-sql-server-clustering-for-lync-server-2013"></a>Lync Server 2013 の SQL Server クラスタリングを構成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-01-10_

Microsoft Lync Server 2013 は、SQL Server 2012 および SQL Server 2008 R2 のクラスタリングをサポートしています。 サポートされている機能の詳細については、「 [Lync Server 2013 のデータベースソフトウェアサポート](lync-server-2013-database-software-support.md)」を参照してください。

Enterprise Edition フロントエンドサーバーとバックエンドデータベースをインストールして展開する前に、SQL Server クラスターをセットアップして構成する必要があります。 SQL Server 2012 のフェールオーバークラスタリングのベストプラクティスとセットアップ手順につい<https://technet.microsoft.com/library/hh231721.aspx>ては、「」を参照してください。 SQL Server 2008 のフェールオーバークラスタリングについ<https://technet.microsoft.com/library/ms189134(v=sql.105).aspx>ては、「」を参照してください。

SQL Server をインストールする際には、データベースの場所とログ ファイルの場所を管理するための SQL Server Management Studio をインストールする必要があります。 SQL Server Management Studio は、SQL Server のインストール時にオプションのコンポーネントとしてインストールされます。

<div>


> [!IMPORTANT]  
> SQL Server ベースのサーバーにデータベースをインストールおよび展開するには、データベース ファイルをインストールする SQL Server ベースのサーバーの SQL Server の sysadmins グループのメンバーである必要があります。 SQL Server の sysadmin グループのメンバーではない場合は、データベース ファイルを展開するまで、そのグループに追加してもらうように要求する必要があります。 sysadmin グループのメンバーになれない場合、SQL Server のデータベース管理者にデータベースを構成および展開するためのスクリプトを提供する必要があります。 手順を実行するために必要な正しいユーザー権限とアクセス許可の詳細については、「 <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Lync server 2013 の SQL Server の展開権限</A>」を参照してください。



</div>

<div>

## <a name="to-configure-sql-server-clustering"></a>SQL Server クラスタリングを構成するには

1.  SQL Server クラスタリングのインストールと構成が完了したら、sql server インスタンスの仮想クラスター名 (「SQL Server のクラスター化のセットアップ」で構成されている) とインスタンスを使用して、SQL Server ストアをトポロジビルダーで定義します。SQL Server データベースの名前。 単一の SQL Server ベースのサーバーとは異なり、クラスター化された SQL Server ベースのサーバーには仮想ノードの完全修飾ドメイン名 (FQDN) を使用します。
    
    <div>
    

    > [!NOTE]  
    > 個々の Windows Server クラスターノードは、トポロジビルダー用に構成する必要はありません。 仮想 SQL Server のクラスター名のみを使用します。

    
    </div>

2.  トポロジビルダーを使用してデータベースを展開している場合は、SQL Server sysadmin グループのメンバーである必要があります。 SQL Server sysadmin グループのメンバーであっても、ドメイン内に権限がない (たとえば、SQL Server データベース管理者の役割) 場合は、データベースを作成する権限がありますが、Lync Server で必要な情報を読み取ることはできません。 Lync Server の展開に必要なユーザー権限とアクセス許可の詳細については、「 [Lync server 2013 の SQL Server の展開権限](lync-server-2013-deployment-permissions-for-sql-server.md)」を参照してください。

3.  SQL Server Management Studio を使用して、データベース フォルダーとログ ファイル フォルダーの既定値が、SQL Server クラスター内の共有ディスクに正しくマッピングされていることを確認してください。 これは、トポロジ ビルダーを使用してデータベースを使用する予定がある場合に必要な手順です。
    
    <div>
    

    > [!NOTE]  
    > SQL Server Management Studio をインストールしていなかった場合は、SQL Server のインストールを再実行し、管理ツールを既存の SQL Server 展開の追加機能として選択することでインストールできます。

    
    </div>

4.  トポロジビルダーまたは Windows PowerShell コマンドレットのいずれかを使用して、SQL Server ベースのサーバーのデータベースをインストールします。 トポロジビルダーを使用するには、次の手順を使用します。 Windows PowerShell コマンドレットを使用するには、「 [lync server 2013 での Lync Server 管理シェルを使用したデータベースのインストール](lync-server-2013-database-installation-using-lync-server-management-shell.md)」を参照してください。

</div>

<div>

## <a name="to-create-databases-using-topology-builder"></a>トポロジビルダーを使用してデータベースを作成するには

1.  トポロジ ビルダーを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server トポロジ ビルダー**] の順にクリックします。
    
    <div>
    

    > [!WARNING]  
    > 次の手順では、トポロジビルダーでトポロジを定義して構成していることを前提としています。 トポロジの定義の詳細については、「<A href="lync-server-2013-defining-and-configuring-the-topology.md">Lync Server 2013 でのトポロジの定義と構成</A>」を参照してください。 トポロジ ビルダーを使用してトポロジを公開し、データベースを構成するには、正しいユーザー権限およびグループ メンバーシップを持つユーザーとしてログオンする必要があります。 必要な権限およびグループメンバーシップの詳細については、「 <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Lync server 2013 の SQL Server の展開権限</A>」を参照してください。

    
    </div>

2.  トポロジビルダーで、トポロジを公開するときに、[**データベースの作成**] ページで [**詳細設定**] をクリックします。

3.  **[データベース ファイルの場所の選択]** ページには、SQL Server クラスターへのデータベース ファイルの展開方法を決定する 2 つのオプションがあります。次のどちらかを選択します。
    
      - **データベースファイルの場所を自動的に決定します。** この選択では、アルゴリズムを使用して、SQL Server ベースのサーバー上のドライブ構成に基づいてデータベースログとデータファイルの場所を特定します。 これらのファイルは、最適なパフォーマンスを実現するための方法で配布されます。
    
      - [既定の SQL Server インスタンスを使用する]。 このオプションを選択すると、SQL Server インスタンスの設定に従ってログおよびデータ ファイルがインストールされます。 SQL Server にデータベース ファイルを展開した後、特定の SQL Server の構成要件でパフォーマンスが最適となるよう、SQL Server データベースの管理者がファイルの場所を変更する場合があります。

4.  トポロジの公開を完了し、操作中にエラーが発生しなかったことを確認してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

