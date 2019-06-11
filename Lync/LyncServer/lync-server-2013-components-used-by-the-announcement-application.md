---
title: 'Lync Server 2013: アナウンス アプリケーションで使用されるコンポーネント'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Components used by the Announcement application
ms:assetid: 7b1a0281-cf31-459d-a734-5f10a129089c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398608(v=OCS.15)
ms:contentKeyID: 48184595
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e8e4a0fdfe0dcdd69a3f371aed338caf7f73348
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840501"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-used-by-the-announcement-application-in-lync-server-2013"></a>Lync Server 2013 のアナウンス アプリケーションで使用されるコンポーネント

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-13_

Lync Server 2013 では、アナウンスメントアプリケーションは応答グループアプリケーションのコンポーネントです。 エンタープライズ Voip を展開すると、応答グループアプリケーションと共に、アナウンスメントアプリケーションが自動的にインストールされ、アクティブ化されます。 このセクションでは、アナウンスメントアプリケーションをサポートするコンポーネントについて説明します。

<div>

## <a name="announcement-application-components"></a>アナウンスメントアプリケーションのコンポーネント

以下の Lync Server コンポーネントは、アナウンスメントアプリケーションをサポートしています。

  - **アプリケーションサービス**   アプリケーションサービスは、ユニファイドコミュニケーションアプリケーションを展開、ホスティング、および管理するためのプラットフォームを提供します。 アプリケーションサービスは、フロントエンドプールのすべてのフロントエンドサーバーと、すべての Standard Edition サーバーに自動的にインストールされます。

  - **応答グループ**   アプリケーション応答グループアプリケーションは、アプリケーションサービスによってホストされるユニファイドコミュニケーションアプリケーションの1つです。 [割り当てられていない電話番号] の範囲がお知らせにルーティングするように構成されている場合は、電話番号への通話をルーティングするために応答グループアプリケーションが必要です。 (応答グループアプリケーションは、すべての範囲が Exchange ユニファイドメッセージング (UM) にルーティングするように構成されている場合は必須ではありません)。

  - ****   アナウンスメントにはオーディオファイルのオーディオファイルが使用されます。

  - **ファイルストア**   アナウンスメントアプリケーションは、ファイルストアを使ってオーディオファイルを保存します。

  - **Lync server コントロールパネル**   lync server コントロールパネルを使用して、割り当てられていない番号テーブルを構成することができます。

  - **Lync server 管理**   シェルコマンドレットを使用して、アナウンスメントの設定および未使用の番号テーブルを構成することができます。

</div>

</div>

<span> </span>

</div>

</div>

</div>

