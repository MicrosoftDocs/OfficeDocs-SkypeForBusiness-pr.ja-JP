---
title: 'Lync Server 2013: ユーザーの E9-1-1 を有効にする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enabling users for E9-1-1
ms:assetid: 3cc64f5b-492e-4c47-9713-3c376f2aad02
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425892(v=OCS.15)
ms:contentKeyID: 48183884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d62d811d78695cbc04fa8def76da1843beddb586
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833223"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-users-for-e9-1-1-in-lync-server-2013"></a>Lync Server 2013 でのユーザーの E9-1 の有効化

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-06-06_

顧客の登録中に、Lync Server は場所ポリシーを使って、エンタープライズボイス対応ユーザーの E9 プロパティを構成します。 このポリシーには、E9-1-1 の実装方法を定義する設定が含まれます。 たとえば、場所情報のポリシーには、緊急ダイヤルの文字列などの情報が含まれています。また、位置情報サービスで自動的に場所を指定しない場合は、その場所を手動で入力する必要があります。 位置情報ポリシーの完全な定義については、「 [Lync Server 2013 の位置情報ポリシーを定義](lync-server-2013-defining-the-location-policy.md)する」を参照してください。

Lync Server は、サブネットに基づいてクライアントまたはグローバル、サイトごと、またはユーザーごとのポリシーに基づいてユーザーに位置情報ポリシーを割り当てることができます。 ユーザーを有効にする方法を決定するには、まず、次の情報を確認する必要があります。

  - **すべてのユーザーを有効にするか、またはエンタープライズの特定の地理的領域にサポートを限定するか。**  
    グローバルな場所ポリシーを使用することで、エンタープライズ内のすべてのユーザーに場所を割り当てることができます。 ただし、Lync Server ネットワークサイトに位置情報ポリシーを割り当て、サブネットをサイトに追加することによって、E9 のサポートをエンタープライズ内の選択した場所に制限し、サイトごとに E9 ルーティング動作を指定できます。

<!-- end list -->

  - **ユーザー ポリシーを使用して個々のユーザーを有効にするか。**  
    E9-1-1 サポートをカスタマイズする必要がある場合は、場所ポリシーを特定のユーザーまたは共通領域電話の連絡先オブジェクトに直接割り当てることができます。

<!-- end list -->

  - **クライアントがネットワーク外を移動している場合、または定義されていないサブネットから接続されている場合、そのクライアントでも E9-1-1 を有効にするか。**  
    ユーザーにグローバル、サイト、またはユーザーごとの場所のポリシーが割り当てられている場合、クライアントが定義されたサブネット内に存在しない場合、または場所情報サービスによって場所が見つからない場合は、クライアントに場所を手動で入力する必要があります。 詳細については、「 [Lync Server 2013 で場所を手動で取得するためのユーザーエクスペリエンスの定義](lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md)」を参照してください。

</div>

<span> </span>

</div>

</div>

</div>

