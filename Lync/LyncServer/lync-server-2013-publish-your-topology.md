---
title: 'Lync Server 2013: トポロジの公開'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publish your topology
ms:assetid: bfed3829-7a54-4b5c-a7cb-28871acd35e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412935(v=OCS.15)
ms:contentKeyID: 48185287
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4a741fe97faebe40841c4b0173820c2fc90d5b87
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183390"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="publish-your-topology-in-lync-server-2013"></a>Lync Server 2013 でのトポロジの公開

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-08_

トポロジビルダーを使用してトポロジを構築するたびに、トポロジを中央管理ストア内のデータベースに公開して、データを使用して Lync Server 2013 を展開できるようにする必要があります。 次の手順を使用してトポロジを公開してください。

<div>

## <a name="to-publish-the-topology"></a>トポロジを公開するには

1.  トポロジ ビルダーを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server トポロジ ビルダー**] の順にクリックします。

2.  トポロジビルダーのコンソールツリーで、[ **Lync 2013**] を右クリックし、[**トポロジの公開**] をクリックします。

3.  ウィザードの [**ようこそ**] ページで、[**次へ**] をクリックします。

4.  [**トポロジ ビルダーで検出した CMS ストア**] ページで、[**次へ**] をクリックします。

5.  [**他のデータベースの作成**] ページで、[**次へ**] をクリックします。

6.  状態に、データベースが正常に作成されたことが示されたら、次の操作を行います。
    
      - ログを表示するには、**[ログの表示]** をクリックします。
    
      - ウィザードを閉じるには、**[完了]** をクリックします。
        
        <div>
        

        > [!IMPORTANT]  
        > エッジサーバーまたはエッジプールの新規インストールの場合は、既存のフロントエンドサーバー、フロントエンドプール、または Standard Edition サーバーから、エッジサーバーの構成をエクスポートする必要があります。 構成をエクスポートするには、「 <A href="lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md">Lync Server 2013 トポロジをエクスポートし、それを外部メディアにコピーする (エッジインストール用</A>)」を参照してください。 構成ファイルは、Lync Server 展開ウィザードを使用して、エッジサーバーのセットアップと展開の段階で、外部メディアまたはネットワーク共有からインポートします。<BR>エッジサーバーが稼働しており、ローカルの構成管理ストアデータベースが内部展開でレプリケートされると、以降の Lync Server 2013 構成の更新プログラムが公開されて、エッジサーバーにレプリケートされます。

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

