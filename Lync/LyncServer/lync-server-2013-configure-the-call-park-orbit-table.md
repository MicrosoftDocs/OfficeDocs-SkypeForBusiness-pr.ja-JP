---
title: 'Lync Server 2013: コールパークオービットテーブルの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure the Call Park orbit table
ms:assetid: e5cc0c19-7b2c-48e7-a21d-cfb23c842f0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399020(v=OCS.15)
ms:contentKeyID: 48185666
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e0f4de5568dc8d265acd412999aafc814c68dbc9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520364"
---
# <a name="configure-the-call-park-orbit-table-in-lync-server-2013"></a>Lync Server 2013 でコールパークオービットテーブルを構成する

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-10_

コールパークは、オービットを使用してパーキング呼び出しを行います。 ユーザーが通話をパークおよび取得できるようにするには、コールパークオービットテーブルを構成する必要があります。 組織がパーキング呼び出しに対して予約する内線番号の範囲 (オービット) を指定し、各範囲のルーティングを定義する必要があります。その範囲には、各範囲で処理するコールパークプールを指定します。 オービット範囲を定義するときには、1つのオービットが短時間で再利用されないように、また、ユーザーまたはその他のサービスで使用できる拡張機能の数を制限するために、多くのオービットを使用するのではなく、十分なオービットを使用することを目標にします。 コールパークアプリケーションが展開されている Lync Server プールごとに、複数のコールパークオービット範囲を作成できます。 各コールパークオービット範囲には、グローバルに一意の名前と、固有の拡張子のセットを含める必要があります。

<div>


> [!IMPORTANT]  
> 一般的にオービット範囲には 100 未満のオービットが含まれます。 1 つの範囲の上限は 10,000 オービットです。1 つのプールに含まれるオービットの数は 50,000 未満です。 範囲が小さすぎると、オービットが再び使用されるまでの時間が短くなります。



</div>

オービット範囲には、仮想内線番号ブロック (ユーザーまたは電話機が割り当てられていない内線番号) を使用します。

<div>


> [!NOTE]  
> コールパークオービットテーブルでは、Direct 内ダイヤル (DID) 番号をオービット番号として割り当てることはサポートされていません。



</div>

<div>

## <a name="in-this-section"></a>このセクションの内容

[Lync Server 2013 でのコールパークオービット範囲の作成または変更](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

