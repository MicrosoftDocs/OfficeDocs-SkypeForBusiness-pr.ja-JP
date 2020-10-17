---
title: 'Lync Server 2013: ロックダウンされた Active Directory ドメインサービスの準備'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing a locked-down Active Directory Domain Services
ms:assetid: 68bde963-3fa3-4102-88d6-ac931c1dd2d7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398492(v=OCS.15)
ms:contentKeyID: 48184377
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1b3e1eb33568bbc0e1742e31638a20879e4fffdd
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513364"
---
# <a name="preparing-a-locked-down-active-directory-domain-services-in-lync-server-2013"></a>Lync Server 2013 のロックダウンされた Active Directory ドメインサービスの準備

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-05-14_

組織は、セキュリティリスクを軽減するために Active Directory ドメインサービスをロックダウンすることがよくあります。 ただし、ロックダウンされた Active Directory 環境では、Lync Server 2013 に必要なアクセス許可を制限することができます。 Lync Server 2013 のロックダウンされた Active Directory 環境を適切に準備するには、追加の考慮事項と手順が必要です。

ロックダウンされた Active Directory 環境でアクセス許可が制限されるのは、一般に次の 2 つの場合です。

  - 認証済みユーザーのアクセス制御エントリ (ACE) がコンテナーから削除されている。

  - ユーザー オブジェクト、連絡先オブジェクト、InetOrgPerson オブジェクト、またはコンピューター オブジェクトのコンテナーでアクセス許可の継承が無効になっている。

<div>

## <a name="in-this-section"></a>このセクション中

  - [Lync Server 2013 で認証済みユーザーのアクセス許可が削除される](lync-server-2013-authenticated-user-permissions-are-removed.md)

  - [Lync Server 2013 のコンピューター、ユーザー、または InetOrgPerson コンテナーでアクセス許可の継承が無効になっている](lync-server-2013-permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

