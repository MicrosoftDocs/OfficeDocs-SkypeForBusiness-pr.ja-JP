---
title: 'Lync Server 2013: トポロジを公開する場合の要件'
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
ms.openlocfilehash: 0f1422df35ebbe9f368dc8aa3d121caf740e7033
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723787"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="requirements-to-publish-a-topology-in-lync-server-2013"></a>Lync Server 2013 でトポロジを公開する場合の要件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-21_

このトピックでは、トポロジビルダーを使用するか、または Lync Server 2013 Management Shell コマンドラインインターフェイスを使用しているかにかかわらず、トポロジの発行に固有のインフラストラクチャとソフトウェアの要件について説明します。 これらの要件は、すべての Lync Server 2013 管理ツールに適用されるオペレーティングシステム、ソフトウェア、アクセス許可の一般的な要件に加えています。 トポロジを公開する前に、管理ツールの要件をすべて満たしていることを確認してください。

  - Active Directory ドメインサービスの準備手順が既に完了していることを確認して、管理ツールの使用を有効にするには、作成中の Lync Server 2013 展開の同じドメインまたはフォレストに参加しているコンピューターでトポロジビルダーを実行する必要があります。このコンピューターでトポロジを正常に公開します。

  - トポロジで定義されたコンピューターは、エッジサーバーと AD DS を除き、ドメインに参加する必要があります。 ただし、トポロジを公開するときに、コンピューターはオンラインである必要はありません。

  - プールのファイル共有を作成し、リモートユーザーが使用できるようにする必要があります。

  - Enterprise Edition のフロントエンドプールを公開するには、SQL Server ベースのバックエンドサーバーを、リモートユーザーが利用できるようにするために、適切なファイアウォールルールを使用してサーバーを展開しているドメインに参加している必要があります。 ファイアウォールの例外の指定の詳細については、「 [Lync server 2013 での SQL Server のファイアウォール要件につい](lync-server-2013-understanding-firewall-requirements-for-sql-server.md)て」を参照してください。 SQL Server の構成の詳細については、「 [Lync server 2013 用に Sql server を構成する](lync-server-2013-configure-sql-server-for-lync-server.md)」を参照してください。
    
    <div>
    

    > [!NOTE]  
    > Standard Edition サーバーには、公開された構成を受け入れる、併置されたデータベースがあります。 まず、Lync Server 展開ウィザードで [<STRONG>最初の Standard Edition server</STRONG>セットアップ] タスクを実行する必要があります。

    
    </div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でトポロジを公開する](lync-server-2013-publish-the-topology.md)  
[Lync Server 2013 でのセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)  


[Lync Server 2013 の管理ツールのソフトウェア要件](lync-server-2013-administrative-tools-software-requirements.md)  
[Lync Server 2013 でのサーバーおよびツールのオペレーティング システムのサポート](lync-server-2013-server-and-tools-operating-system-support.md)  


[Lync Server 2013 のセットアップと管理に必要な管理者権限およびアクセス許可](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

