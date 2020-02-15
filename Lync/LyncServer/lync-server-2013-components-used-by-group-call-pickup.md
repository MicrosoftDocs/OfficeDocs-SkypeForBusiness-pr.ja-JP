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
ms.openlocfilehash: a05bf0b6a55eb3d8d3d322061947ac43f6295c63
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007927"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-used-by-group-call-pickup-in-lync-server-2013"></a>Lync Server 2013 のグループ通話ピックアップで使用されるコンポーネント

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-01-30_

グループ通話ピックアップは、エンタープライズ Voip およびコールパークアプリケーションを展開するときに自動的に展開されます。 グループ通話ピックアップを有効にするには、通話ピックアップグループ番号として指定された別の番号の範囲を使用してコールパークオービットテーブルを構成し、ユーザーを割り当ててグループ通話ピックアップのユーザーを有効にします。 グループ通話ピックアップをサポートする Lync Server コンポーネントは次のとおりです。

  - **Application service**   アプリケーションサービスは、コールパークアプリケーションなどの統合コミュニケーションアプリケーションを展開、ホスト、および管理するためのプラットフォームを提供します。 アプリケーションサービスは、フロントエンドプール内のすべてのフロントエンドサーバーとすべての Standard Edition サーバーに自動的にインストールされます。

  - **コールパークアプリケーション**   コールパークアプリケーションは、アプリケーションサービスによってホストされている統合コミュニケーションアプリケーションの1つです。 グループ通話ピックアップは、コールパークアプリケーションに基づいています。

  - **Lync server 管理シェル**   lync server 管理シェルを使用して、グループ通話ピックアップグループを管理します。

  - **SEFAUtil resource kit tool**   セカンダリ拡張機能のアクティブ化ユーティリティ (SEFAUtil) を使用して、ユーザーを通話ピックアップグループに割り当て、ユーザーの通話ピックアップを有効または無効にします。

</div>

<span> </span>

</div>

</div>

</div>

