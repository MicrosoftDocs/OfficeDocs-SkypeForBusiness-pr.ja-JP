---
title: エッジ インストール用のトポロジをエクスポートして外部メディアにコピーする
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Export your topology and copy it to external media for edge installation
ms:assetid: def9f416-c519-4a72-b242-7d3057d9c1fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398983(v=OCS.15)
ms:contentKeyID: 48185615
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8eb8f20e7af8cbfd772226917b027a33a688a4a5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756211"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="export-your-lync-server-2013-topology-and-copy-it-to-external-media-for-edge-installation"></a>エッジ インストール用の Lync Server 2013 のトポロジをエクスポートして外部メディアにコピーする

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-08_

トポロジを公開した後、Lync Server 展開ウィザードでは、サーバー上で展開プロセスを開始するために、中央管理ストアのデータにアクセスする必要があります。 内部ネットワークでは、データはサーバーから直接利用できますが、内部ドメインにないエッジサーバーはデータにアクセスすることはできません。 エッジサーバーの展開用にトポロジ構成データを利用できるようにするには、Lync Server の Dep を実行する前に、トポロジデータをファイルにエクスポートして、外部メディア (USB ドライブや、エッジサーバーから入手できるネットワーク共有など) にコピーする必要があります。エッジサーバー上の loyment ウィザード。 展開するエッジサーバーでトポロジ構成データを利用できるようにするには、次の手順に従います。

<div>


> [!NOTE]
> エッジサーバーに Lync Server 2013 をインストールした後は、内部ネットワークの管理ツールを使用してエッジサーバーを管理します。これにより、展開のエッジサーバーに構成が自動的にレプリケートされます。 唯一の例外として、証明書の割り当てとインストール、サービスの停止と開始はどちらもエッジサーバーで実行する必要があります。



</div>

<div>

## <a name="to-make-your-topology-data-available-on-an-edge-server-by-using-lync-server-management-shell"></a>Lync Server 管理シェルを使用して、トポロジデータをエッジサーバーで利用できるようにするには

1.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

2.  Lync Server 管理シェルで、次のコマンドレットを実行します。
    
        Export-CsConfiguration -FileName <ConfigurationFilePath.zip>

3.  エクスポートしたファイルを外部メディア (たとえば、展開中にエッジサーバーから利用可能な USB ドライブやネットワーク共有など) にコピーします。

</div>

</div>

<span> </span>

</div>

</div>

</div>

