---
title: 'Lync Server 2013: トポロジ ビルダーでのトポロジの定義と構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Define and configure a topology in Topology Builder
ms:assetid: 99231ff5-1c21-432b-ad65-8675fcd484f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398788(v=OCS.15)
ms:contentKeyID: 48184953
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ee952eef30fc50f30448c98956899c3a1a06dc2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833708"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-and-configure-a-topology-in-topology-builder-for-lync-server-2013"></a>Lync Server 2013 のトポロジ ビルダーでのトポロジの定義と構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-21_

トポロジビルダーを実行して新しいトポロジを定義したり、既存のトポロジを変更したりするには、ローカル管理者または特権ドメイングループのメンバーシップは必要ありません。 トポロジビルダーは、構成要件に基づいて、Enterprise Edition フロントエンドプールまたは標準エディションのトポロジを定義するために必要な手順を実行します。

サーバーに Lync Server 2013 をインストールするには、トポロジビルダーを使用してトポロジを完了して公開する必要があります。 次の手順では、新しいトポロジを定義するために必要な手順について説明します。

<div>

## <a name="to-define-a-topology"></a>トポロジを定義するには

1.  トポロジビルダーを開始します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server Topology Builder**] の順にクリックします。

2.  [トポロジビルダー] で [**新しいトポロジ**] を選びます。 トポロジを保存する場所とファイル名を入力するように求められます。 トポロジファイルにわかりやすい名前を付け、tbxml の既定の拡張子をそのまま使用します。 **[OK]** をクリックします。

3.  新しいトポロジ XML ファイルを保存する場所に移動し、ファイルの名前を入力して、[**保存**] をクリックします。

4.  [**プライマリドメインの定義**] ページで、組織のプライマリ SIP ドメインの名前を入力し、[**次へ**] をクリックします。

5.  [**追加でサポートされるドメインの指定**] ページで、必要に応じて追加ドメインの名前を入力し、[**次へ**] をクリックします。

6.  [**最初のサイトの定義**] ページで、最初のサイトの名前と説明を入力し、[**次へ**] をクリックします。

7.  [**サイトの詳細の指定**] ページで、サイトの場所情報を入力し、[**次へ**] をクリックします。

8.  [**新しいトポロジの定義が完了しました**] ページで、[**このウィザードを閉じるときに新しいフロントエンドウィザードを開く**] チェックボックスがオンになっていることを確認し、[**完了**] をクリックします。

トポロジを定義して保存したら、新しいフロントエンドウィザードを使って、サイトのフロントエンドプールまたは Standard Edition サーバーを定義します。 詳細について[は、「Lync server 2013 でフロントエンドプールまたは Standard Edition サーバーを定義して構成](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md)する」を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

