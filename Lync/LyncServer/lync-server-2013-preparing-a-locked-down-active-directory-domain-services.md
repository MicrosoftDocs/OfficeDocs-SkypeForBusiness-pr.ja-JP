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
# <a name="preparing-a-locked-down-active-directory-domain-services-in-lync-server-2013"></a><span data-ttu-id="c93be-102">Lync Server 2013 のロックダウンされた Active Directory ドメインサービスの準備</span><span class="sxs-lookup"><span data-stu-id="c93be-102">Preparing a locked-down Active Directory Domain Services in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c93be-103">_**トピックの最終更新日:** 2012-05-14_</span><span class="sxs-lookup"><span data-stu-id="c93be-103">_**Topic Last Modified:** 2012-05-14_</span></span>

<span data-ttu-id="c93be-104">組織は、セキュリティリスクを軽減するために Active Directory ドメインサービスをロックダウンすることがよくあります。</span><span class="sxs-lookup"><span data-stu-id="c93be-104">Organizations often lock down Active Directory Domain Services to help mitigate security risks.</span></span> <span data-ttu-id="c93be-105">ただし、ロックダウンされた Active Directory 環境では、Lync Server 2013 に必要なアクセス許可を制限することができます。</span><span class="sxs-lookup"><span data-stu-id="c93be-105">However, a locked-down Active Directory environment can limit the permissions that Lync Server 2013 requires.</span></span> <span data-ttu-id="c93be-106">Lync Server 2013 のロックダウンされた Active Directory 環境を適切に準備するには、追加の考慮事項と手順が必要です。</span><span class="sxs-lookup"><span data-stu-id="c93be-106">Properly preparing a locked-down Active Directory environment for Lync Server 2013 involves some additional considerations and steps.</span></span>

<span data-ttu-id="c93be-107">ロックダウンされた Active Directory 環境でアクセス許可が制限されるのは、一般に次の 2 つの場合です。</span><span class="sxs-lookup"><span data-stu-id="c93be-107">Two common ways in which permissions are limited in a locked-down Active Directory environment are as follows:</span></span>

  - <span data-ttu-id="c93be-108">認証済みユーザーのアクセス制御エントリ (ACE) がコンテナーから削除されている。</span><span class="sxs-lookup"><span data-stu-id="c93be-108">Authenticated user access control entries (ACEs) are removed from containers.</span></span>

  - <span data-ttu-id="c93be-109">ユーザー オブジェクト、連絡先オブジェクト、InetOrgPerson オブジェクト、またはコンピューター オブジェクトのコンテナーでアクセス許可の継承が無効になっている。</span><span class="sxs-lookup"><span data-stu-id="c93be-109">Permissions inheritance is disabled on containers of User, Contact, InetOrgPerson, or Computer objects.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c93be-110">このセクション中</span><span class="sxs-lookup"><span data-stu-id="c93be-110">In This Section</span></span>

  - [<span data-ttu-id="c93be-111">Lync Server 2013 で認証済みユーザーのアクセス許可が削除される</span><span class="sxs-lookup"><span data-stu-id="c93be-111">Authenticated user permissions are removed in Lync Server 2013</span></span>](lync-server-2013-authenticated-user-permissions-are-removed.md)

  - [<span data-ttu-id="c93be-112">Lync Server 2013 のコンピューター、ユーザー、または InetOrgPerson コンテナーでアクセス許可の継承が無効になっている</span><span class="sxs-lookup"><span data-stu-id="c93be-112">Permissions inheritance Is disabled on computers, users, or InetOrgPerson containers in Lync Server 2013</span></span>](lync-server-2013-permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

