---
title: 'Lync Server 2013: Lync server 2013 Standard Edition を既存の Lync Server 2013 エンタープライズに展開する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Lync Server 2013 Standard Edition into an existing Lync Server 2013 Enterprise
ms:assetid: 05ea128d-6c94-49b3-b28b-477367196425
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398112(v=OCS.15)
ms:contentKeyID: 48183297
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 733dcadc52550c665cc74407a81cddbfbd5ea640
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195370"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-lync-server-2013-standard-edition-into-an-existing-lync-server-2013-enterprise"></a>既存の Lync Server 2013 Enterprise への Lync Server 2013 Standard Edition の展開

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-01_

Standard Edition サーバーを既存の Enterprise Edition の展開に展開することは、追加のサーバーの役割の展開に似ています。 Standard Edition サーバーは別のサイトに展開される可能性があります。これにより、そのサイトのユーザーは、ワイドエリアネットワーク (WAN) を介してフロントエンドプールではなく、Standard Edition サーバーに所属することができます。 サイトに新しいサイトとサーバーをインストールする手順は、「 [Lync Server 2013](lync-server-2013-deploying-lync-server.md)ドキュメントの展開」の他のセクションで既に定義されています。

<div id="sectionSection0" class="section">

**新しいサイトを定義するには**

1.  トポロジ ビルダーを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server トポロジ ビルダー**] の順にクリックします。

2.  コンソールツリーで、[ **Lync Server 2013**] を右クリックし、[**新しいセントラルサイト**] をクリックします。

3.  [**サイトの識別**] ページでサイトに名前を付け、オプションで説明を入力します。

4.  サイト トポロジの残りを定義する手順を実行します。 詳細については、「 [Lync Server 2013 でのトポロジの定義と構成](lync-server-2013-defining-and-configuring-the-topology.md)」を参照してください。

5.  更新したトポロジを公開します。 詳細については、「 [Lync Server 2013 でトポロジを公開する](lync-server-2013-publish-the-topology.md)」を参照してください。

6.  Standard Edition サーバーをセットアップしてインストールします。
    
    <div>
    

    > [!Caution]  
    > Standard Edition サーバーのみを使用して環境を展開した場合は、[<STRONG>最初の Standard edition サーバーの準備</STRONG>] リンクを使用して、新しい standard edition サーバーに初期データベースファイルをインストールすることによって、Lync Server 展開ウィザードからセットアッププロセスを開始します。 Standard Edition サーバーを既存の Lync Server 2013 展開にインストールする場合は、このプロセスを実行<STRONG>しないでください</STRONG>。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

