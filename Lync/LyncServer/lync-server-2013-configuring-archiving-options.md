---
title: 'Lync Server 2013: アーカイブオプションの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Archiving options
ms:assetid: b2f7f74d-e1ad-494e-9d46-5eb0efe5fb29
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205182(v=OCS.15)
ms:contentKeyID: 48185158
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 873b7775c889f5d866e21f04c1f154a3158ea99d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147010"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-archiving-options-in-lync-server-2013"></a>Lync Server 2013 でのアーカイブオプションの構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-10_

Lync Server 2013 コントロールパネルでは、アーカイブ構成を使用してアーカイブの実装方法を指定します。 これには、次のアーカイブ構成が含まれます。

  - Lync Server 2013 を展開するときに既定で作成されるグローバル構成。

  - 特定のサイトまたはプールに対するアーカイブの実装方法を指定するために作成して使用できる、オプションのサイトレベルおよびプールレベルのポリシー。

アーカイブ構成は、最初はアーカイブの展開時に設定しますが、展開後に変更、追加、および削除できます。 Lync Server 2013 コントロールパネルでは、**アーカイブおよび監視**グループの [**アーカイブ構成**] ページを使用して、グローバルレベル、サイトレベル、およびプールレベルで構成を管理できます。 指定できるオプションやアーカイブ構成の階層など、アーカイブ構成の実装方法の詳細については、「計画」のドキュメント、「展開」、または「操作」のドキュメントの「 [Lync Server 2013 でのアーカイブの仕組み](lync-server-2013-how-archiving-works.md)」を参照してください。 展開後に構成を管理する方法の詳細については、「操作」のドキュメントの「 [Lync Server 2013 での組織、サイト、およびプールのアーカイブ構成オプションの管理](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)」を参照してください。

<div>


> [!NOTE]  
> アーカイブを使用するには、アーカイブポリシーを構成して、内部通信、外部通信、または Lync Server 2013 に所属するユーザーの両方に対してアーカイブを有効にするかどうかを指定する必要があります。 既定では、アーカイブは内部通信および外部通信のどちらに対しても有効になっていません。 ポリシーでアーカイブを有効にする前に、このセクションの説明に従って、展開に対して、また必要に応じて特定のサイトやプールに対して、適切なアーカイブ構成を指定する必要があります。 アーカイブを有効にする方法の詳細については、「展開」のドキュメントの「 <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Lync Server 2013 でのアーカイブポリシーの構成と割り当て</A>」を参照してください。<BR>展開内のすべてのユーザーに対して Microsoft Exchange 統合を使用しない場合、アーカイブポリシーを構成して、内部通信、外部通信、またはその両方のアーカイブを有効にするかどうかを指定する必要があります。 既定では、Lync Server 2013 アーカイブデータベースを使用するときに、データのアーカイブの内部通信または外部通信のどちらかのアーカイブが有効になっていません。 ポリシーでアーカイブを有効にする前に、このセクションの説明に従って、展開および必要に応じて特定のサイトやプールに対して適切なアーカイブ構成を指定する必要があります。 Lync Server 2013 アーカイブデータベースで使用するアーカイブを有効にする方法の詳細については、「展開」のドキュメントの「 <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Lync server 2013 でのアーカイブポリシーの構成と割り当て</A>」を参照してください。



</div>

<div>

## <a name="in-this-section"></a>このセクションの内容

  - [Lync Server 2013 のグローバルレベルでのアーカイブオプションの構成](lync-server-2013-configuring-archiving-options-at-the-global-level.md)

  - [Lync Server 2013 でのサイトのアーカイブオプションの構成](lync-server-2013-configuring-archiving-options-for-a-site.md)

  - [Lync Server 2013 でのプールのアーカイブオプションの構成](lync-server-2013-configuring-archiving-options-for-a-pool.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

