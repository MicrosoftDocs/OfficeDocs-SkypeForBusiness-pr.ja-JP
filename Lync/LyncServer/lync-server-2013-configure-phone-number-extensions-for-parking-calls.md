---
title: 'Lync Server 2013: パーキング呼び出しの電話番号内線を構成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure phone number extensions for parking calls
ms:assetid: fbf97624-9587-42a6-b276-1b69c574a74d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182611(v=OCS.15)
ms:contentKeyID: 48185980
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 97a8871454ed95b955558c441d567f68dd0974bd
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520434"
---
# <a name="configure-phone-number-extensions-for-parking-calls-in-lync-server-2013"></a>Lync Server 2013 でのパーキング呼び出しの内線電話番号の構成

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-10_

コールパークアプリケーションは、コールパークオービットテーブルの内線番号を使用して通話をパークします。 保留呼び出しに対して組織で予約されている内線番号の範囲を使用して、コールパークオービットテーブルを構成する必要があります。 これらの内線番号は仮想の内線番号 (つまり、ユーザーや電話が割り当てられていない内線番号) にする必要あがります。 コールパークアプリケーションが展開および構成されている各 Lync Server プールは、1つ以上のオービット範囲を持つことができます。 オービット範囲は、Lync Server の展開間でグローバルに一意である必要があります。

<div>


> [!IMPORTANT]  
> コールパークを使用する前に、音声ポリシーの [ <STRONG>コールパークを有効</STRONG> にする] チェックボックスをオンにする必要があります。 既定では、このオプションはオフになっています。



</div>

<div>

## <a name="in-this-section"></a>このセクションの内容

  - [Lync Server 2013 でのコールパークオービット範囲の作成または変更](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)

  - [Lync Server 2013 でのコールパークオービット範囲の削除](lync-server-2013-delete-a-call-park-orbit-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

