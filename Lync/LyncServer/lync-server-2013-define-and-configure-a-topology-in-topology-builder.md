---
title: 'Lync Server 2013: トポロジビルダーでのトポロジの定義と構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define and configure a topology in Topology Builder
ms:assetid: 99231ff5-1c21-432b-ad65-8675fcd484f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398788(v=OCS.15)
ms:contentKeyID: 48184953
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0aa4a2c12771adf41972fc0c69222935d6935570
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504604"
---
# <a name="define-and-configure-a-topology-in-topology-builder-for-lync-server-2013"></a>Lync Server 2013 のトポロジビルダーでのトポロジの定義と構成

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-21_

トポロジビルダーを実行して新しいトポロジを定義したり、既存のトポロジを変更したりするには、ローカル管理者または特権ドメイングループのメンバーである必要はありません。 トポロジビルダーは、構成要件に基づいて、Enterprise Edition フロントエンドプールまたは Standard Edition のトポロジを定義するために必要な手順を説明します。

サーバーに Lync Server 2013 をインストールするには、トポロジビルダーを使用してトポロジを完成させ、公開する必要があります。 次の手順には、新しいトポロジを定義するために必要な手順も含まれています。

<div>

## <a name="to-define-a-topology"></a>トポロジを定義するには

1.  トポロジ ビルダーを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server トポロジ ビルダー**] の順にクリックします。

2.  [トポロジビルダー] で、[ **新しいトポロジ**] を選択します。 トポロジを保存する場所とファイル名を指定するように求められます。 トポロジ ファイルにわかりやすい名前を付け、既定の拡張子 .tbxml をそのまま使用します。 [**OK**] をクリックします。

3.  新しいトポロジ XML ファイルを保存する場所に移動してファイル名を入力し、[**保存**] をクリックします。

4.  [**プライマリ ドメインの定義**] ページで、組織のプライマリ SIP ドメイン名を入力し、[**次へ**] をクリックします。

5.  [**追加でサポートされるドメインの指定**] ページで、追加のドメイン名を入力し (存在する場合)、[**次へ**] をクリックします。

6.  [**最初のサイトの定義**] ページで、最初のサイトの名前と説明を入力し、[**次へ**] をクリックします。

7.  [**サイト詳細の指定**] ページで、サイトの場所情報を入力し、[**次へ**] をクリックします。

8.  [ **新しいトポロジが正常に定義されました** ] ページで、[ **このウィザードを閉じるときに新しいフロントエンドウィザードを開く** ] チェックボックスがオンになっていることを確認し、[ **完了**] をクリックします。

トポロジを定義して保存した後、新しいフロントエンドウィザードを使用して、サイトのフロントエンドプールまたは Standard Edition サーバーを定義します。 詳細については、「 [Lync server 2013 でのフロントエンドプールまたは Standard Edition サーバーの定義と構成](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md)」を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

