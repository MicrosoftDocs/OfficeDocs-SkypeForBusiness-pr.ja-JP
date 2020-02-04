---
title: 'Lync Server 2013: 既存の Lync Server 2013 Enterprise への Lync Server 2013 Standard Edition の展開'
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
ms.openlocfilehash: 6467ae9eb3c4d5159181a2d022c060b0b9f1fec9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758021"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-lync-server-2013-standard-edition-into-an-existing-lync-server-2013-enterprise"></a>既存の Lync Server 2013 Enterprise への Lync Server 2013 Standard Edition の展開

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-01_

Standard Edition server を既存の Enterprise Edition の展開に展開することは、追加のサーバーロールの展開に似ています。 Standard Edition サーバーは、別のサイトに展開されることがあります。これにより、そのサイトのユーザーは、ワイドエリアネットワーク (WAN) 上のフロントエンドプールではなく、Standard Edition server をホームとして使用することができます。 このサイトに新しいサイトとサーバーをインストールする手順は、「[展開する Lync Server 2013](lync-server-2013-deploying-lync-server.md)ドキュメント」の他のセクションで既に定義されています。

<div id="sectionSection0" class="section">

**新しいサイトを定義するには**

1.  トポロジビルダーを開始します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server Topology Builder**] の順にクリックします。

2.  コンソールツリーで、[ **Lync Server 2013**] を右クリックし、[**新しいセントラルサイト**] をクリックします。

3.  [**サイトの識別**] ページで、サイトに名前を付け、必要に応じて説明を入力します。

4.  残りのサイトトポロジを定義する手順に従います。 詳細については、「 [Lync Server 2013 でトポロジを定義して構成する](lync-server-2013-defining-and-configuring-the-topology.md)」を参照してください。

5.  更新されたトポロジを公開します。 詳細については、「 [Lync Server 2013 でトポロジを発行する](lync-server-2013-publish-the-topology.md)」を参照してください。

6.  Standard Edition サーバーのセットアップとインストールを行います。
    
    <div>
    

    > [!Caution]  
    > Standard Edition サーバーのみを使用して環境を展開した場合、初期のデータベースファイルを新しい Standard Edition サーバーにインストールするには<STRONG>、Lync</STRONG> Server の展開ウィザードのセットアッププロセスを開始します。 既存の Lync Server 2013 展開に Standard Edition サーバーをインストールする場合は、そのプロセスに従わ<STRONG>ないでください</STRONG>。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

