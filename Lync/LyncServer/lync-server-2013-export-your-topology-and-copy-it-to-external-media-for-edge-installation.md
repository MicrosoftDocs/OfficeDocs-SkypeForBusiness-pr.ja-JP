---
title: エッジインストール用のトポロジをエクスポートして外部メディアにコピーする
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
ms.openlocfilehash: 784ed29372b137d5d3f58d749a3660d11cbb55d5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134613"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="export-your-lync-server-2013-topology-and-copy-it-to-external-media-for-edge-installation"></a>エッジインストールのために Lync Server 2013 トポロジをエクスポートして外部メディアにコピーする

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-08_

トポロジを公開した後、Lync Server 展開ウィザードは、サーバー上で展開プロセスを開始するために、中央管理ストアのデータにアクセスする必要があります。 内部ネットワークでは、データはサーバーから直接使用できますが、内部ドメインにないエッジサーバーはデータにアクセスできません。 トポロジ構成データをエッジサーバーの展開に使用できるようにするには、Lync Server の Dep を実行する前に、トポロジデータをファイルにエクスポートして外部メディア (たとえば、エッジサーバーから使用できる USB ドライブやネットワーク共有) にコピーする必要があります。エッジサーバー上の loyment ウィザード。 展開するエッジサーバーでトポロジ構成データを使用できるようにするには、次の手順を使用します。

<div>


> [!NOTE]
> エッジサーバーに Lync Server 2013 をインストールした後、内部ネットワークの管理ツールを使用してエッジサーバーを管理します。これにより、展開内の任意のエッジサーバーに構成が自動的にレプリケートされます。 唯一の例外は、証明書を割り当ててインストールし、サービスを停止および開始することです。どちらもエッジサーバーで実行する必要があります。



</div>

<div>

## <a name="to-make-your-topology-data-available-on-an-edge-server-by-using-lync-server-management-shell"></a>Lync Server 管理シェルを使用して、エッジサーバーでトポロジデータを使用できるようにするには

1.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

2.  Lync Server 管理シェルで、次のコマンドレットを実行します。
    
        Export-CsConfiguration -FileName <ConfigurationFilePath.zip>

3.  エクスポートされたファイルを外部メディア (たとえば、展開中にエッジサーバーから使用できる USB ドライブやネットワーク共有) にコピーします。

</div>

</div>

<span> </span>

</div>

</div>

</div>

