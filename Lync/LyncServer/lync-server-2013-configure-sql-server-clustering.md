---
title: 'Lync Server 2013: SQL Server クラスタリングを構成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure SQL Server clustering
ms:assetid: d7b52ef1-573c-48ed-bb94-34e37b49645c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn383982(v=OCS.15)
ms:contentKeyID: 56472032
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 279c6581d0a56193c094c3dd7b9638fd74e2e60c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840336"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-sql-server-clustering-for-lync-server-2013"></a>Lync Server 2013 用の SQL Server クラスタリングを構成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-01-10_

Microsoft Lync Server 2013 は、SQL Server 2012 と SQL Server 2008 R2 のクラスタリングをサポートしています。 サポートされる機能の詳細については、「 [Lync Server 2013 でのデータベースソフトウェアのサポート](lync-server-2013-database-software-support.md)」を参照してください。

Enterprise Edition フロントエンドサーバーとバックエンドデータベースをインストールして展開する前に、SQL Server クラスターをセットアップして構成する必要があります。 SQL Server 2012 のフェールオーバークラスタリングのベストプラクティスとセットアップ手順につい<http://technet.microsoft.com/en-us/library/hh231721.aspx>ては、を参照してください。 SQL Server 2008 のフェールオーバークラスタリングについ<http://technet.microsoft.com/en-us/library/ms189134(v=sql.105).aspx>ては、を参照してください。

SQL Server をインストールする際は、SQL Server Management Studio をインストールしてデータベースとログ ファイルの場所を管理する必要があります。SQL Server Management Studio は、SQL Server のインストール時にオプション コンポーネントとしてインストールされます。

<div>


> [!IMPORTANT]  
> SQL Server ベースのサーバーにデータベースをインストールして展開するには、データベースファイルをインストールする SQL server ベースのサーバーの SQL Server sysadmin グループのメンバーである必要があります。 SQL Server sysadmin グループのメンバーでない場合は、データベースファイルが展開されるまで、グループに追加するように依頼する必要があります。 Sysadmin グループのメンバーになることができない場合は、SQL Server データベース管理者に、データベースを構成して展開するためのスクリプトを用意する必要があります。 手順を実行するために必要な適切なユーザー権限と権限の詳細については、「 <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Lync server 2013 の SQL Server の展開権限</A>」を参照してください。



</div>

<div>

## <a name="to-configure-sql-server-clustering"></a>SQL Server クラスタリングを構成するには

1.  SQL Server クラスタリングのインストールと構成を完了した後は、sql server の仮想クラスター名 (SQL Server クラスタリングのセットアップで構成されます) とインスタンスを使用して、トポロジビルダーで SQL Server ストアを定義します。SQL Server データベースの名前。 SQL Server ベースの1台のサーバーとは異なり、クラスター化された SQL Server ベースのサーバーには仮想ノードの完全修飾ドメイン名 (FQDN) を使用します。
    
    <div>
    

    > [!NOTE]  
    > 個々の Windows Server クラスターノードは、トポロジビルダー用に構成する必要はありません。 仮想 SQL Server クラスター名のみが使用されます。

    
    </div>

2.  トポロジビルダーを使用してデータベースを展開している場合は、SQL Server sysadmin グループのメンバーである必要があります。 SQL Server sysadmin グループのメンバーであるが、ドメインの権限がない場合 (たとえば、SQL Server データベース管理者の役割)、データベースを作成する権限はありますが、Lync Server で必要な情報を読み取ることはできません。 Lync Server の展開に必要なユーザー権限と権限の詳細については、「 [Lync server 2013 の SQL Server の展開権限](lync-server-2013-deployment-permissions-for-sql-server.md)」を参照してください。

3.  SQL Server Management Studio を使用して、データベースフォルダーとログファイルフォルダーの既定値が、SQL Server クラスターの共有ディスクに正しくマッピングされていることを確認します。 トポロジビルダーを使用してデータベースを作成する場合は、この手順を実行する必要があります。
    
    <div>
    

    > [!NOTE]  
    > SQL Server Management Studio をインストールしていない場合は、SQL Server のインストールを再実行して、既存の SQL Server 展開の追加機能として管理ツールを選択してインストールできます。

    
    </div>

4.  トポロジビルダーまたは Windows PowerShell コマンドレットを使用して、SQL Server ベースのサーバーのデータベースをインストールします。 トポロジビルダーを使用するには、次の手順を使用します。 Windows PowerShell コマンドレットを使用するには、「 [lync server 2013 の Lync Server 管理シェルを使用したデータベースのインストール](lync-server-2013-database-installation-using-lync-server-management-shell.md)」を参照してください。

</div>

<div>

## <a name="to-create-databases-using-topology-builder"></a>トポロジビルダーを使用してデータベースを作成するには

1.  トポロジビルダーを開始します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server Topology Builder**] の順にクリックします。
    
    <div>
    

    > [!WARNING]  
    > 次の手順では、トポロジビルダーでトポロジを定義して構成していることを前提としています。 トポロジの定義の詳細については、「<A href="lync-server-2013-defining-and-configuring-the-topology.md">Lync Server 2013 でトポロジを定義して構成する</A>」を参照してください。 トポロジビルダーを使用してトポロジを公開し、データベースを構成するには、適切なユーザー権限とグループメンバーシップを持つユーザーとしてログオンする必要があります。 必要な権限とグループメンバーシップの詳細については、「 <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Lync server 2013 の SQL Server の展開権限</A>」を参照してください。

    
    </div>

2.  トポロジビルダーでは、トポロジを公開するときに、[**データベースの作成**] ページで [**詳細設定**] をクリックします。

3.  **[データベースファイルの場所の選択**] ページには、データベースファイルが SQL Server クラスターにどのように展開されるかを決定する2つのオプションがあります。 次のいずれかを選択します。
    
      - **データベースファイルの場所を自動的に特定します。** この選択では、アルゴリズムを使って、SQL Server ベースのサーバーのドライブ構成に基づいて、データベースログとデータファイルの場所を特定します。 ファイルは、最適なパフォーマンスを実現するための手段として配布されます。
    
      - [既定の SQL Server インスタンスを使用する]。 このオプションを選択すると、SQL Server インスタンスの設定に従ってログとデータファイルがインストールされます。 Sql server にデータベースファイルを展開した後、SQL server データベース管理者は、特定の SQL Server 構成要件のパフォーマンスを最適化するために、ファイルを再配置することができます。

4.  トポロジの発行を完了し、操作中にエラーがないことを確認します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

