---
title: 'Lync Server 2013: トポロジの公開'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publish the topology
ms:assetid: 3b5a744b-b3a8-4538-a55e-e2e4f72dff47
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425880(v=OCS.15)
ms:contentKeyID: 48183866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e94e47536c8af6ef8fd3c22dba245b03c961c575
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512364"
---
# <a name="publish-the-topology-in-lync-server-2013"></a>Lync Server 2013 でトポロジを公開する

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-10-01_

サーバーの役割を追加または削除する際に、トポロジを正常に公開したり、有効または無効にするには、RTCUniversalServerAdmins グループおよび Domain Admins グループのメンバーであるユーザーとしてログインしている必要があります。 適切な管理者権限とアクセス許可を委任することもできます。 詳細については、「 [Lync Server 2013 でのセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」を参照してください。 他の構成変更の場合は、RTCUniversalServerAdmins グループのメンバーシップのみが必要です。

トポロジビルダーでトポロジを定義した後で、トポロジを中央管理ストアに公開する必要があります。 中央管理ストアは、Lync Server 2013 展開の定義、設定、管理、管理、説明、および運用に必要なデータの堅牢で schematized ストレージを提供します。 また、構成の一貫性を確保するために、データを検証します。 この構成データに加えられたすべての変更は中央管理ストアで行われるため、"同期ができません" の問題が発生しなくなります。 このデータの読み取り専用のコピーは、エッジ サーバーを含めたトポロジ内のすべてのサーバーにレプリケートされます。

<div>


> [!NOTE]  
> 最初のトポロジを公開して中央管理サーバーを作成するには、SQL Server で最小 20 GB のディスクの空き領域が必要です。



</div>

<div>


> [!NOTE]  
> Enterprise Edition の場合のみ: トポロジを公開するには、SQL Server ベースのバック エンド サーバーがオンラインになっていて、所定のファイアウォール例外を使用してアクセスできる必要があります。 ファイアウォール例外の指定の詳細については、「 <A href="lync-server-2013-understanding-firewall-requirements-for-sql-server.md">Lync server 2013 を使用した SQL Server のファイアウォール要件につい</A>て」を参照してください。 SQL Server の構成の詳細については、「 <A href="lync-server-2013-configure-sql-server-for-lync-server.md">CONFIGURE Sql server For Lync Server 2013</A>」を参照してください。



</div>

<div>

## <a name="to-publish-a-topology"></a>トポロジを公開するには

1.  トポロジ ビルダーを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server トポロジ ビルダー**] の順にクリックします。

2.  ローカル ファイルからトポロジを選択して開きます。 トポロジを定義したコンピューターで作業している場合、ローカル ファイルは前の手順でトポロジを保存した場所です。 ローカル ファイルは、通常、トポロジを構成したユーザーのドキュメント フォルダーです。

3.  [ **Lync Server 2013** ] ノードを右クリックし、[ **トポロジの公開**] をクリックします。

4.  [**トポロジの公開**] ページで、[**次へ**] をクリックします。

5.  [**データベースの作成**] ページで、公開するデータベースを選択します。
    
    <div>
    

    > [!NOTE]  
    > データベースを作成するための適切な権限がない場合は、これらのデータベースの横のチェック ボックスをオフにしておけば、適切な権限を持つ他のユーザーが後でデータベースを作成できます。 詳細については、「 <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Lync server 2013 の SQL Server の展開権限</A>」を参照してください。

    
    </div>

6.  オプションで [**詳細設定**] をクリックします。 SQL Server の高度なデータファイル配置オプションを使用すると、次のオプションを選択できます。
    
      - [**データベース ファイルの場所を自動的に判断する**] – このオプションを選択すると、SQL Server ベースのサーバー上のディスク構成に基づいて、ログ ファイルとデータ ファイルを最適な場所に分散することで、最適な動作パフォーマンスが判断されます。
    
      - [**既定の SQL Server インスタンスを使用する**] – このオプションを選択すると、インスタンス設定により、ログ ファイルとデータ ファイルが SQL Server ベースのサーバーに配置されます。 このオプションでは、ログとデータの最適な場所を決定するのに、SQL Server ベースのサーバーの操作上の機能は使用されません。SQL Server の管理者が通常、SQL Server ベースのサーバーおよび組織の管理手順に適した場所にログ ファイルとデータ ファイルを移動します。
    
    [**OK**] をクリックして、[**次へ**] をクリックします。

7.  [ **中央管理サーバーの選択** ] ページで、フロントエンドプールを選択します。

8.  オプションで [**詳細設定**] をクリックします。 SQL Server の高度なデータファイル配置オプションを使用すると、次のオプションを選択できます。
    
      - [**データベース ファイルの場所を自動的に判断する**] – このオプションを選択すると、SQL Server ベースのサーバー上のディスク構成に基づいて、ログ ファイルとデータ ファイルを最適な場所に分散することで、最適な動作パフォーマンスが判断されます。
    
      - [**既定の SQL Server インスタンスを使用する**] – このオプションを選択すると、インスタンス設定により、ログ ファイルとデータ ファイルが SQL Server ベースのサーバーに配置されます。このオプションでは、ログとデータの最適な場所を決定するのに、SQL Server ベースのサーバーの操作上の機能は使用されません。SQL Server の管理者が通常、SQL Server ベースのサーバーおよび組織の管理手順に適した場所にログ ファイルとデータ ファイルを移動します。
    
    [**OK**] をクリックします。

9.  [**次へ**] をクリックして公開プロセスを完了します。

10. 公開プロセスが完了したら、[**完了**] をクリックします。
    
    トポロジが正常に公開されたら、トポロジで Lync Server 2013 を実行している各サーバーに中央管理ストアのローカルレプリカをインストールし始めることができます。 最初のフロントエンドプールから始めることをお勧めします。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 のフロントエンドサーバーおよびフロントエンドプールの設定](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

