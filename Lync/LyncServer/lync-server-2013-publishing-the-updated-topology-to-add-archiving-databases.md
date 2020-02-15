---
title: 'Lync Server 2013: 更新されたトポロジを公開してアーカイブデータベースを追加する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publishing the updated topology to add Archiving databases
ms:assetid: 454c68df-2ef5-4b5f-a44c-4eee02635d45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204860(v=OCS.15)
ms:contentKeyID: 48184034
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 543ee664aeb8f2d8688fd35f7591726c9c0c7392
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045960"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publishing-the-updated-topology-to-add-archiving-databases-in-lync-server-2013"></a>更新されたトポロジを公開して Lync Server 2013 にアーカイブデータベースを追加する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-01_

トポロジビルダーでトポロジを更新した後は、アーカイブを構成して使用する前に、トポロジを中央管理ストアに公開する必要があります。 このデータの読み取り専用コピーはトポロジ内のすべてのサーバーにレプリケートされ、すべてのサーバーは、トポロジおよび他の構成の変更と同期された状態で維持されます。

<div>

## <a name="to-publish-your-updated-topology"></a>更新したトポロジを公開するには

1.  Lync Server 2013 を実行しているコンピューター、または Lync Server 管理ツールがインストールされているコンピューターで、ローカルユーザーグループのメンバーであるアカウント (または同等のユーザー権限を持つアカウント) を使用してログオンします。
    
    <div>
    

    > [!NOTE]  
    > トポロジを定義するには、ローカルユーザーグループのメンバーであるアカウントを使用しますが、トポロジを公開するには、サーバーをトポロジに追加する必要があります。 <STRONG>Domain Admins</STRONG>グループおよび<STRONG>RTCUniversalServerAdmins</STRONG>グループのメンバーであり、かつ、Lync server 2013 ファイルストアに使用しているファイル共有のフルコントロールのアクセス許可 (つまり、読み取り、書き込み、および変更) を持つアカウントを使用する必要があります (つまり、トポロジビルダーが必要な随意アクセス制御リスト (dacl) を構成できるようにする必要があります。、またはそれと同等の権限を持つアカウント。

    
    </div>

2.  トポロジビルダーを使用して、前のセクションで作成したトポロジを開きます。

3.  コンソールツリーで、[ **Lync Server 2013**] を右クリックし、[**トポロジの公開**] をクリックします。

4.  [**トポロジの公開**] ページで、[**次へ**] をクリックします。

5.  [**データベースの作成**] ページで、データベースが選択されていることを確認して、[**次へ**] をクリックします。
    
    <div>
    

    > [!NOTE]  
    > データベースを作成するための適切なアクセス許可を持っていない場合、ここでのデータベースの選択を取り消して、適切なアクセス許可を持つ別のユーザーがデータベースを作成できます。 必要な管理者権限とアクセス許可の詳細については、「展開」のドキュメントの「 <A href="lync-server-2013-deployment-permissions-for-sql-server.md">deployment permissions For Lync server 2013</A> 」を参照してください。<BR>トポロジビルダーを使用してインストールできるのは、専用の SQL Server サーバー上のデータベースだけです。 他のサーバーコンポーネントと併置されている SQL Server サーバー上のデータベースは、そのコンピューターでローカルセットアップを実行してインストールする必要があります。

    
    </div>

6.  [**公開ウィザードの完了**] ページで、トポロジが正常に公開されたことを確認し、[**完了**] をクリックします。
    
    <div>
    

    > [!IMPORTANT]  
    > トポロジを公開した後、コンテンツをアーカイブする前に、アーカイブのオプションおよびポリシーを構成する必要があります。 詳細については、「展開」のドキュメントの「 <A href="lync-server-2013-configuring-support-for-archiving.md">Lync Server 2013 でのアーカイブのサポートの構成</A>」を参照してください。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

