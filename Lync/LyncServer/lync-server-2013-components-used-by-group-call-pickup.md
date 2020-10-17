---
title: 'Lync Server 2013: グループ通話ピックアップで使用されるコンポーネント'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components used by Group Call Pickup
ms:assetid: 45db2f23-d486-4b20-a8cf-7b48a1f9fd3a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945625(v=OCS.15)
ms:contentKeyID: 51541470
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 062dc114534abb7d2a011c31b9747c2d6a0a45bb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502364"
---
# <a name="components-used-by-group-call-pickup-in-lync-server-2013"></a>Lync Server 2013 のグループ通話ピックアップで使用されるコンポーネント

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-01-30_

グループ通話ピックアップは、エンタープライズ Voip およびコールパークアプリケーションを展開するときに自動的に展開されます。 グループ通話ピックアップを有効にするには、通話ピックアップグループ番号として指定された別の番号の範囲を使用してコールパークオービットテーブルを構成し、ユーザーを割り当ててグループ通話ピックアップのユーザーを有効にします。 グループ通話ピックアップをサポートする Lync Server コンポーネントは次のとおりです。

  - **アプリケーションサービス**    Application service は、コールパークアプリケーションなどの統合コミュニケーションアプリケーションを展開、ホスト、および管理するためのプラットフォームを提供します。 アプリケーションサービスは、フロントエンドプール内のすべてのフロントエンドサーバーとすべての Standard Edition サーバーに自動的にインストールされます。

  - **コールパークアプリケーション**    コールパークアプリケーションは、アプリケーションサービスによってホストされている統合コミュニケーションアプリケーションの1つです。 グループ通話ピックアップは、コールパークアプリケーションに基づいています。

  - **Lync Server 管理シェル**    グループ通話ピックアップグループを管理するには、Lync Server 管理シェルを使用します。

  - **SEFAUtil リソースキットツール**    第2の拡張機能のアクティブ化ユーティリティ (SEFAUtil) を使用して、ユーザーを通話ピックアップグループに割り当て、ユーザーの通話ピックアップを有効または無効にします。

</div>

<span> </span>

</div>

</div>

</div>

