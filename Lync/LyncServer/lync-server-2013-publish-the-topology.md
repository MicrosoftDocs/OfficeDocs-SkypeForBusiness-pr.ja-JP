---
title: 'Lync Server 2013: トポロジを公開する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Publish the topology
ms:assetid: 3b5a744b-b3a8-4538-a55e-e2e4f72dff47
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425880(v=OCS.15)
ms:contentKeyID: 48183866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fee3b14776c6cdf6ddd52ada724d3d4a6d6a245a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823967"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publish-the-topology-in-lync-server-2013"></a>Lync Server 2013 でトポロジを公開する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-10-01_

トポロジを正常に発行、有効化、または無効にするには、RTCUniversalServerAdmins および Domain Admins グループのメンバーであるユーザーとしてログインしている必要があります。 適切な管理者権限と権限を委任することもできます。 詳細については、「 [Lync Server 2013 でセットアップのアクセス許可を委任](lync-server-2013-delegate-setup-permissions.md)する」を参照してください。 その他の構成変更については、RTCUniversalServerAdmins グループのメンバーシップのみが必要です。

トポロジビルダーでトポロジを定義したら、トポロジを中央管理ストアに発行する必要があります。 中央管理ストアでは、Lync Server 2013 の展開を定義、セットアップ、管理、管理、説明、操作するために必要なデータの堅牢で schematized なストレージを提供します。 また、構成の一貫性を確保するために、データを検証します。 構成データへの変更はすべて中央管理ストアでなされるので、"非同期" の問題を回避できます。 データの読み取り専用コピーは、エッジサーバーを含むトポロジ内のすべてのサーバーにレプリケートされます。

<div>


> [!NOTE]  
> 最初のトポロジを正常に発行し、中央管理サーバーを作成するには、SQL Server の最低 20 GB の空き領域が必要です。



</div>

<div>


> [!NOTE]  
> Enterprise Edition のみ: トポロジを公開するには、SQL Server ベースのバックエンドサーバーがオンラインであり、ファイアウォール例外が発生してアクセスできる必要があります。 ファイアウォールの例外の指定の詳細については、「 <A href="lync-server-2013-understanding-firewall-requirements-for-sql-server.md">Lync server 2013 での SQL Server のファイアウォール要件につい</A>て」を参照してください。 SQL Server の構成の詳細については、「 <A href="lync-server-2013-configure-sql-server-for-lync-server.md">Lync server 2013 用に Sql server を構成する</A>」を参照してください。



</div>

<div>

## <a name="to-publish-a-topology"></a>トポロジを公開するには

1.  トポロジビルダーを開始します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server Topology Builder**] の順にクリックします。

2.  ローカルファイルからトポロジを開く場合に選択します。 トポロジを定義したコンピューターを使用している場合、これは前の手順で保存した場所になります。 通常、これはトポロジを構成したユーザーの [ドキュメント] フォルダーになります。

3.  [ **Lync Server 2013** ] ノードを右クリックし、[**トポロジの公開**] をクリックします。

4.  [**トポロジの公開**] ページで、[**次へ**] をクリックします。

5.  [**データベースの作成**] ページで、発行するデータベースを選択します。
    
    <div>
    

    > [!NOTE]  
    > データベースを作成するための適切な権限がない場合は、これらのデータベースの横のチェック ボックスをオフにしておけば、適切な権限を持つ他のユーザーが後でデータベースを作成できます。 詳細については、「 <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Lync server 2013 の SQL Server の展開権限</A>」を参照してください。

    
    </div>

6.  オプションで [**詳細設定**] をクリックします。 SQL Server のデータファイルの詳細な配置オプションを使用して、次のオプションを選ぶことができます。
    
      - [**データベースファイルの場所を自動的に特定**する]: このオプションは、ログとデータファイルを最適な場所に配布することにより、SQL server ベースのサーバーのディスク構成に基づいて最適な運用パフォーマンスを決定します。
    
      - [**既定の SQL Server インスタンスを使用する**] - このオプションを選択した場合は、インスタンス設定により、ログ ファイルとデータ ファイルが SQL Server ベースのサーバーに配置されます。このオプションでは、ログとデータの最適な場所を決定するのに、SQL Server ベースのサーバーの操作上の機能は使用されません。SQL Server の管理者が通常、SQL Server ベースのサーバーおよび組織の管理手順に適した場所にログ ファイルとデータ ファイルを移動します。
    
    [**OK**] をクリックして、[**次へ**] をクリックします。

7.  [**サーバーの選択]** ページで、フロントエンドプールを選択します。

8.  オプションで [**詳細設定**] をクリックします。 SQL Server のデータファイルの詳細な配置オプションを使用すると、次のオプションを選ぶことができます。
    
      - [**データベースファイルの場所を自動的に特定**する]: このオプションは、ログとデータファイルを最適な場所に配布することにより、SQL server ベースのサーバーのディスク構成に基づいて最適な運用パフォーマンスを決定します。
    
      - [**既定の SQL Server インスタンスを使用する**] - このオプションを選択した場合は、インスタンス設定により、ログ ファイルとデータ ファイルが SQL Server ベースのサーバーに配置されます。このオプションでは、ログとデータの最適な場所を決定するのに、SQL Server ベースのサーバーの操作上の機能は使用されません。SQL Server の管理者が通常、SQL Server ベースのサーバーおよび組織の管理手順に適した場所にログ ファイルとデータ ファイルを移動します。
    
    [**OK**] をクリックします。

9.  [**次へ**] をクリックして公開プロセスを完了します。

10. 発行プロセスが完了したら、[**完了**] をクリックします。
    
    トポロジが正常に公開された場合は、トポロジで Lync Server 2013 を実行している各サーバーに、中央管理ストアのローカルレプリカをインストールし始めることができます。 最初のフロントエンド プールから開始することをお勧めします。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でのフロント エンド サーバーおよびフロント エンド プールの設定](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

