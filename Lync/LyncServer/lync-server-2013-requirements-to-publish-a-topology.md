---
title: 'Lync Server 2013: トポロジを公開するための要件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Requirements to publish a topology
ms:assetid: 841cdf5d-d884-414d-ab50-3bb681b622ed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195733(v=OCS.15)
ms:contentKeyID: 48184688
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf8c36fee84880e5236c5048da35dca38a476eab
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182990"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="requirements-to-publish-a-topology-in-lync-server-2013"></a>Lync Server 2013 でトポロジを公開するための要件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-21_

このトピックでは、トポロジビルダーまたは Lync Server 2013 管理シェルコマンドラインインターフェイスを使用しているかどうかにかかわらず、トポロジの公開に固有のインフラストラクチャおよびソフトウェア要件について説明します。 これらの要件は、すべての Lync Server 2013 管理ツールに適用される一般的なオペレーティングシステム、ソフトウェア、およびアクセス許可の要件に加えてあります。 トポロジを公開する前に、すべての管理ツールの要件を満たしていることを確認してください。

  - Active Directory ドメインサービスの準備手順が既に完了しているために、作成する Lync Server 2013 の展開の同じドメインまたはフォレストに参加しているコンピューターでトポロジビルダーを実行して、管理ツールを使用できるようにする必要があります。そのコンピューターでトポロジが正常に公開されます。

  - トポロジに定義されているコンピューターは、ドメイン (エッジ サーバーを除く)、および AD DS に参加する必要があります。ただし、トポロジを公開するときにコンピューターがオンラインである必要はありません。

  - プールのファイル共有を作成し、リモート ユーザーが使用できるようにする必要があります。

  - Enterprise Edition フロントエンドプールを公開するには、SQL Server ベースのバックエンドサーバーが、サーバーを展開するドメインに参加しており、リモートユーザーが使用できるようにするための適切なファイアウォールルールで構成されている必要があります。 ファイアウォール例外の指定の詳細については、「 [Lync server 2013 を使用した SQL Server のファイアウォール要件につい](lync-server-2013-understanding-firewall-requirements-for-sql-server.md)て」を参照してください。 SQL Server の構成の詳細については、「 [CONFIGURE Sql server For Lync Server 2013](lync-server-2013-configure-sql-server-for-lync-server.md)」を参照してください。
    
    <div>
    

    > [!NOTE]  
    > Standard Edition サーバーには、公開された構成を受け付ける、併置されたデータベースがあります。 最初に、Lync Server 展開ウィザードで [<STRONG>最初の Standard Edition サーバーの準備</STRONG>] セットアップタスクを実行する必要があります。

    
    </div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でトポロジを公開する](lync-server-2013-publish-the-topology.md)  
[Lync Server 2013 でのセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)  


[Lync Server 2013 の管理ツールソフトウェア要件](lync-server-2013-administrative-tools-software-requirements.md)  
[Lync Server 2013 でのサーバーおよびツールのオペレーティングシステムのサポート](lync-server-2013-server-and-tools-operating-system-support.md)  


[Lync Server 2013 のセットアップと管理に必要な管理者権限およびアクセス許可](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

