---
title: 'Lync Server 2013: アナウンスメントアプリケーションで使用されるコンポーネント'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components used by the Announcement application
ms:assetid: 7b1a0281-cf31-459d-a734-5f10a129089c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398608(v=OCS.15)
ms:contentKeyID: 48184595
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 84fb2d57e03965acff9d647854b86d7a5a528246
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517714"
---
# <a name="components-used-by-the-announcement-application-in-lync-server-2013"></a>Lync Server 2013 のアナウンスアプリケーションで使用されるコンポーネント

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-13_

Lync Server 2013 では、アナウンスメントアプリケーションは応答グループアプリケーションのコンポーネントです。 エンタープライズ Voip を展開すると、アナウンスアプリケーションが自動的にインストールされ、応答グループアプリケーションと共にアクティブ化されます。 このセクションでは、アナウンスメントアプリケーションをサポートするコンポーネントについて説明します。

<div>

## <a name="announcement-application-components"></a>アナウンス アプリケーションのコンポーネント

アナウンスメントアプリケーションは、次の Lync Server コンポーネントでサポートされています。

  - **アプリケーションサービス**    アプリケーションサービスは、統合コミュニケーションアプリケーションを展開、ホスト、および管理するためのプラットフォームを提供します。 アプリケーションサービスは、フロントエンドプール内のすべてのフロントエンドサーバーとすべての Standard Edition サーバーに自動的にインストールされます。

  - **応答グループアプリケーション**    応答グループアプリケーションは、アプリケーションサービスによってホストされている統合コミュニケーションアプリケーションの1つです。 割り当てられていない電話番号の範囲をアナウンスにルーティングするように構成すると、その電話番号に発信された通話をルーティングするために、応答グループアプリケーションが必要になります。 (Exchange ユニファイドメッセージング (UM) にルーティングするようにすべての範囲が構成されている場合、応答グループアプリケーションは必要ありません)。

  - **オーディオファイル**    音声ファイルはアナウンスに使用されます。

  - **ファイルストア**    アナウンスメントアプリケーションは、ファイルストアを使用してオーディオファイルを保存します。

  - **Lync Server コントロールパネル**    Lync Server コントロールパネルを使用して、割り当てられていない番号の表を構成できます。

  - **Lync Server 管理シェル**    Lync Server 管理シェルコマンドレットを使用すると、アナウンスの設定と割り当てられていない番号の表を構成できます。

</div>

</div>

<span> </span>

</div>

</div>

</div>

