---
title: 'Lync Server 2013: グループ通話のピックアップで使用されるコンポーネント'
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
ms.openlocfilehash: 7b9c810d5835d113a26bd3a15295f75a71552590
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757071"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-used-by-group-call-pickup-in-lync-server-2013"></a>Lync Server 2013 でグループ通話のピックアップによって使用されるコンポーネント

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-01-30_

グループ通話のピックアップは、エンタープライズボイスと Call パークアプリケーションを展開したときに自動的に展開されます。 グループ通話のピックアップを有効にするには、通話ピックアップグループ番号として指定された別の範囲の番号を使用して、ユーザーをピックアップグループに発信し、グループ通話のピックアップを許可するようにユーザーを割り当てることで、グループ通話のピックアップを有効にします。 グループ通話のピックアップは、次の Lync Server コンポーネントでサポートされています。

  - **アプリケーションサービス**   アプリケーションサービスは、コールパークアプリケーションなどのユニファイドコミュニケーションアプリケーションを展開、ホスティング、および管理するためのプラットフォームを提供します。 アプリケーションサービスは、フロントエンドプールのすべてのフロントエンドサーバーと、すべての Standard Edition サーバーに自動的にインストールされます。

  - **コールパーク**   アプリケーションは、アプリケーションサービスによってホストされるユニファイドコミュニケーションアプリケーションの1つです。 グループ通話のピックアップは、コールパークアプリケーションに基づいています。

  - **Lync server 管理**   シェル lync server 管理シェルを使ってグループ通話のピックアップグループを管理します。

  - **SEFAUtil リソースキットツール**   セカンダリ拡張機能のアクティブ化ユーティリティ (SEFAUtil) を使って、ユーザーを通話ピックアップグループに割り当て、ユーザーに対して通話集配を有効または無効にします。

</div>

<span> </span>

</div>

</div>

</div>

