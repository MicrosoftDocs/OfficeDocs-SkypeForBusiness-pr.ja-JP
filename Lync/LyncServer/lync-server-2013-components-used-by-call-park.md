---
title: 'Lync Server 2013: コール パークで使用されるコンポーネント'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components used by Call Park
ms:assetid: c7ffbee3-0ce1-48c0-bb56-af098b41d6d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398824(v=OCS.15)
ms:contentKeyID: 48185374
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ae458d7ef3245e366e4f2bdd61f192401909213b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757081"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-used-by-call-park-in-lync-server-2013"></a>Lync Server 2013 のコール パークで使用されるコンポーネント

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-13_

エンタープライズ Voip を展開すると、コールパークアプリケーションが自動的にインストールされます。 音声ポリシーを構成して、コールパークを有効にします。 次の Lync Server 2013 コンポーネントは、コールパークアプリケーションをサポートしています。

  - **アプリケーションサービス**   アプリケーションサービスは、コールパークアプリケーションなどのユニファイドコミュニケーションアプリケーションを展開、ホスティング、および管理するためのプラットフォームを提供します。 アプリケーションサービスは、フロントエンドプールのすべてのフロントエンドサーバーと、すべての Standard Edition サーバーに自動的にインストールされます。

  - **コールパーク**   アプリケーションは、アプリケーションサービスによってホストされるユニファイドコミュニケーションアプリケーションの1つです。 エンタープライズボイスの展開時に自動的に含まれます。 [パークパーク] を選び、通話を取得して、通話パークの orbits を管理します。

  - **音楽-保留-ファイル**   音楽が有効になっている場合は、通話の保留中に音楽ファイルが再生されます。 既定の音楽ファイルは、コールパークアプリケーションがインストールされているときに含まれます。

  - **ファイルストア**   コールパークアプリケーションは、カスタムオーディオファイルを保持するためにファイルストアを使用します。

  - **Lync server コントロールパネル**   lync server コントロールパネルを使用すると、通話パークの軌道の表を構成し、ユーザーに対してコールパークを有効にすることができます。

  - **Lync server 管理シェル**   すべてのコールパークアプリケーション構成は、lync Server 管理シェルコマンドレットを使用して実行できます。

</div>

<span> </span>

</div>

</div>

</div>

