---
title: 'Lync Server 2013: 更新されたトポロジを発行してアーカイブデータベースを追加する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Publishing the updated topology to add Archiving databases
ms:assetid: 454c68df-2ef5-4b5f-a44c-4eee02635d45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204860(v=OCS.15)
ms:contentKeyID: 48184034
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7f39e5f35dbd088543456f09ddd49f6aa2f9325c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823694"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publishing-the-updated-topology-to-add-archiving-databases-in-lync-server-2013"></a>更新されたトポロジを発行して、Lync Server 2013 でアーカイブデータベースを追加する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-01_

トポロジビルダーでトポロジを更新した後は、アーカイブを構成して使用する前に、トポロジを中央管理ストアに発行する必要があります。 このデータの読み取り専用コピーはトポロジ内のすべてのサーバーにレプリケートされ、すべてのサーバーは、トポロジおよび他の構成の変更と同期された状態で維持されます。

<div>

## <a name="to-publish-your-updated-topology"></a>更新されたトポロジを公開するには

1.  Lync Server 2013 を実行しているコンピューター、または Lync Server 管理ツールがインストールされているコンピューターで、ローカルユーザーグループのメンバーであるアカウント (または同等のユーザー権限を持つアカウント) を使用してログオンします。
    
    <div>
    

    > [!NOTE]  
    > トポロジを定義するには、ローカルユーザーグループのメンバーであるアカウントを使用します。ただし、トポロジにサーバーを追加するために必要なトポロジを公開するには、 <STRONG>Domain Admins</STRONG>グループと RTCUniversalServer のメンバーであるアカウントを使用する必要があります。 <STRONG>管理者</STRONG>グループ、および Lync Server 2013 ファイルストアで使用しているファイル共有に対するフルコントロールのアクセス許可 (つまり、読み取り、書き込み、変更) が含まれている (つまり、トポロジビルダーが必要な随意アクセス制御リスト (dacl) を構成できるようにするためです。または、同等の権限を持つアカウント。

    
    </div>

2.  トポロジービルダーを使用して、前のセクションで作成したトポロジを開きます。

3.  コンソールツリーで、[ **Lync Server 2013**] を右クリックし、[**トポロジの公開**] をクリックします。

4.  [**トポロジの公開**] ページで、[**次へ**] をクリックします。

5.  [**データベースの作成**] ページで、データベースが選択されていることを確認し、[**次へ**] をクリックします。
    
    <div>
    

    > [!NOTE]  
    > データベースを作成するための適切なアクセス許可を持っていない場合、ここでのデータベースの選択を取り消して、適切なアクセス許可を持つ別のユーザーがデータベースを作成できます。 必要な管理者権限と権限の詳細については、展開ドキュメントの「 <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Lync server 2013 の SQL server の展開権限</A>」を参照してください。<BR>トポロジビルダーを使用すると、専用の SQL Server サーバー上のデータベースのみをインストールできます。 他のサーバーコンポーネントと連携している SQL Server サーバー上のデータベースは、そのコンピューターのローカルセットアップを実行してインストールする必要があります。

    
    </div>

6.  [**公開ウィザードの完了**] ページで、トポロジが正常に公開されたことを確認し、[**完了**] をクリックします。
    
    <div>
    

    > [!IMPORTANT]  
    > トポロジを公開した後、コンテンツをアーカイブする前に、アーカイブのオプションおよびポリシーを構成する必要があります。 詳細については、「展開ドキュメントの「 <A href="lync-server-2013-configuring-support-for-archiving.md">Lync Server 2013 でアーカイブのサポートを構成する</A>」を参照してください。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

