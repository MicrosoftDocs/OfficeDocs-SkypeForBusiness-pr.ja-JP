---
title: 'Lync Server 2013: 応答グループによって使用されるコンポーネント'
description: 'Lync Server 2013: 応答グループによって使用されるコンポーネント。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components used by Response Group
ms:assetid: 2b058785-47ca-43b7-b3de-6928a60dc685
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425768(v=OCS.15)
ms:contentKeyID: 48183693
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2a1e916d9e4bf986bf0337a6f1f1dd918ff2772e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571703"
---
# <a name="components-used-by-response-group-in-lync-server-2013"></a>Lync Server 2013 の応答グループによって使用されるコンポーネント

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-11_

応答グループアプリケーションは、エンタープライズ Voip の展開時に自動的に有効になります。 このセクションでは、応答グループアプリケーションをサポートするコンポーネントについて説明します。

<div>

## <a name="response-group-components"></a>応答グループコンポーネント

次の Microsoft Lync Server 2013 コンポーネントは、応答グループアプリケーションをサポートします。

  - **アプリケーションサービス**    Application service は、応答グループなどの統合コミュニケーションアプリケーションを展開、ホスト、および管理するためのプラットフォームを提供します。 アプリケーションサービスは、フロントエンドプール内のすべてのフロントエンドサーバーとすべての Standard Edition サーバーに自動的にインストールされます。

  - **応答グループアプリケーション**    応答グループアプリケーションは、アプリケーションサービスによってホストされている統合コミュニケーションアプリケーションの1つです。 応答グループを展開するときに自動的に含まれます。 応答グループアプリケーションは、エージェントのグループへの着信呼び出しをルーティングし、キューに入れます。

  - **言語パック**    音声合成と音声認識をサポートするには、言語パックが必要です。 これらの音声技術は、メッセージ (ウェルカムメッセージやその他の音声ガイダンス、音声応答 (IVR) の質問と回答など) を構成するときに使用されます。 既定では、Lync Server 2013 を展開すると、サポートされている26言語パックがインストールされます。

  - **オーディオファイル**    オーディオファイルは、メッセージおよび保留音に使用されます。

  - **ファイルストア**    応答グループは、ファイルストアを使用してオーディオファイルを格納します。 複数の応答グループプールで、同じインスタンスのファイルストアを使用できます。

  - **応答グループ構成ツール**    応答グループ構成ツールは、応答グループの作成と構成に使用される web ベースのツールです。 Web サービスをインストールするときに、応答グループ構成ツールが含まれています。

  - **Microsoft Lync Server 2013 コントロールパネル**    Lync Server コントロールパネルを使用して、応答グループのエージェントグループおよびキューをセットアップして構成できます。

  - **Lync Server 管理シェル**    すべての応答グループの設定は、Lync Server 管理シェルコマンドレットを使用して構成できます。

  - **Microsoft Lync 2013**    公式エージェント (グループへの通話を受け付ける前にグループにサインインする必要があるエージェント) は、Lync 2013 を使用して、グループにサインインし、グループからサインアウトします。 エージェントグループが正式なエージェントに対して構成されている場合、エージェントは Lync 2013 のメニュー項目をクリックして、Internet Explorer を開き、グループにサインインおよびサインアウトするための web ページコンソールを表示します。

  - **Web サービス**    Web サービスは、応答グループの構成ツール、エージェントのサインインとサインアウトコンソール、Lync Server コントロールパネル、および応答グループクライアント web サービスに必要です。

  - **応答グループクライアント Web サービス**    Response Group application はクライアント web サービスを提供します。このサービスは、サードパーティのアプリケーションで使用して、エージェント、エージェントグループのメンバーシップ、エージェントのサインイン状態、グループの呼び出しの状態、匿名呼び出しをサポートするグループに関する情報を取得することができます。 Lync 2013 および Lync 2010 アテンダントは応答グループクライアント Web サービスを使用して、エージェントが匿名呼び出しを行うために使用できる応答グループの一覧を取得します。 Web サービスをインストールすると、クライアント web サービスが含まれます。

</div>

</div>

<span> </span>

</div>

</div>

</div>

