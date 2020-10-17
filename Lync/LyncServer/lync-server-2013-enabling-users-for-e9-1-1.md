---
title: 'Lync Server 2013: E9-1-1 でのユーザーの有効化'
description: 'Lync Server 2013: E9-1-1 に対してユーザーを有効にします。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling users for E9-1-1
ms:assetid: 3cc64f5b-492e-4c47-9713-3c376f2aad02
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425892(v=OCS.15)
ms:contentKeyID: 48183884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ba29406dc0d7a1140c83a1a9d271afca5d6b0c7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546443"
---
# <a name="enabling-users-for-e9-1-1-in-lync-server-2013"></a>Lync Server 2013 での E9-1-1 のユーザーの有効化

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-06-06_

クライアントの登録時に、Lync Server は場所のポリシーを使用して、エンタープライズ Voip が有効なユーザーの E9-1-1 プロパティを構成します。 このポリシーには、E9-1-1 の実装方法を定義する設定が含まれます。 たとえば、場所のポリシーには緊急ダイヤル文字列などの情報が含まれており、場所情報サービスが自動的に所在地情報を提供しない場合は、ユーザーが場所を手動で入力する必要があるかどうか。 場所ポリシーの完全な定義については、「 [Lync Server 2013 の場所のポリシーの定義](lync-server-2013-defining-the-location-policy.md)」を参照してください。

Lync Server は、サブネットに基づいて、またはグローバル、サイトごと、またはユーザーごとのポリシーに基づいて、場所ポリシーをクライアントに割り当てることができます。 ユーザーを有効にする方法を決定するには、まず、次の情報を確認する必要があります。

  - **すべてのユーザーを有効にするか、またはエンタープライズの特定の地理的領域にサポートを限定するか。**  
    グローバルな場所ポリシーを使用することで、エンタープライズ内のすべてのユーザーに場所を割り当てることができます。 ただし、場所のポリシーを Lync Server ネットワークサイトに割り当ててからサブネットをサイトに追加することによって、E9-1-1 のサポートをエンタープライズ内の選択された場所に制限し、E9-1-1 のルーティング動作をサイトごとに指定することができます。

<!-- end list -->

  - **ユーザー ポリシーを使用して個々のユーザーを有効にするか。**  
    E9-1-1 サポートをカスタマイズする必要がある場合は、場所ポリシーを特定のユーザーまたは共通領域電話の連絡先オブジェクトに直接割り当てることができます。

<!-- end list -->

  - **クライアントがネットワーク外を移動している場合、または定義されていないサブネットから接続されている場合、そのクライアントでも E9-1-1 を有効にするか。**  
    ユーザーがグローバル、サイト、またはユーザー単位の場所のポリシーを割り当てられている場合は、クライアントが定義されたサブネット内に存在しないか、場所情報サービスによって場所が見つからない場合は、クライアントに場所を手動で入力する必要があります。 詳細については、「 [Lync Server 2013 で手動で場所を取得するためのユーザーの作業を定義](lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md)する」を参照してください。

</div>

<span> </span>

</div>

</div>

</div>

