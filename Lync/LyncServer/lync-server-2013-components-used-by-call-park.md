---
title: 'Lync Server 2013: コールパークで使用されるコンポーネント'
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
ms.openlocfilehash: 21335597f0910e18a5afe36898c7d0eff6c1a338
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502394"
---
# <a name="components-used-by-call-park-in-lync-server-2013"></a>Lync Server 2013 のコールパークで使用されるコンポーネント

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-13_

コールパークアプリケーションは、エンタープライズ Voip を展開するときに自動的にインストールされます。 通話パークを有効にするには、音声ポリシーを構成します。 次の Lync Server 2013 コンポーネントは、コールパークアプリケーションをサポートします。

  - **アプリケーションサービス**    Application service は、コールパークアプリケーションなどの統合コミュニケーションアプリケーションを展開、ホスト、および管理するためのプラットフォームを提供します。 アプリケーションサービスは、フロントエンドプール内のすべてのフロントエンドサーバーとすべての Standard Edition サーバーに自動的にインストールされます。

  - **コールパークアプリケーション**    コールパークアプリケーションは、アプリケーションサービスによってホストされている統合コミュニケーションアプリケーションの1つです。 エンタープライズ VoIP を展開するときに自動的に組み込まれます。 コールパークパーク、通話を取得し、コールパークオービットを管理します。

  - **音楽-保留音-ファイル**    [音楽] が有効になっている場合は、通話が保留されている間、音楽ファイルが再生されます。 コールパークアプリケーションがインストールされている場合は、既定の音楽ファイルが含まれています。

  - **ファイルストア**    コールパークアプリケーションは、ファイルストアを使用してカスタムオーディオファイルを保持します。

  - **Lync Server コントロールパネル**    Lync Server コントロールパネルを使用して、コールパークオービットテーブルを構成し、ユーザーのコールパークを有効にすることができます。

  - **Lync Server 管理シェル**    すべてのコールパークアプリケーションの構成は、Lync Server 管理シェルコマンドレットを使用して実行できます。

</div>

<span> </span>

</div>

</div>

</div>

