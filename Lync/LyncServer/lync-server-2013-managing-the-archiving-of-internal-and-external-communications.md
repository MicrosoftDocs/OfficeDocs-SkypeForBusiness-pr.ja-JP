---
title: 内部通信と外部通信のアーカイブの管理
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing the Archiving of internal and external communications
ms:assetid: 6c2cf941-3204-4f1a-a7e0-416c828056d9
ms:mtpsurl: https://technet.microsoft.com/library/JJ204977(v=OCS.15)
ms:contentKeyID: 48184417
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 14df9a4472d920e5b583e4d2abe2deeb3fba0c98
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525034"
---
# <a name="managing-the-archiving-of-internal-and-external-communications-in-lync-server-2013"></a>Lync Server 2013 での内部および外部通信のアーカイブの管理

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-09_

Lync Server 2013 では、アーカイブポリシーを使用して、内部通信と外部通信のアーカイブを有効または無効にします。 Microsoft Exchange 統合を使用していない場合、または Exchange 2013 に所属していないユーザーがメールボックスを In-Place ホールドにしている場合。 これには、次のアーカイブ ポリシーが含まれます。

  - Lync Server 2013 を展開するときに既定で作成されるグローバルポリシー。

  - 特定のサイトまたはユーザーに対するアーカイブの実装方法を指定するために作成して使用できるオプションのサイトレベルおよびユーザーレベルのポリシー。

アーカイブ ポリシーは、最初はアーカイブの展開時にセットアップしますが、展開後に変更、追加、および削除できます。 Lync Server 2013 コントロールパネルでは、**アーカイブおよび監視**グループの [**アーカイブポリシー** ] ページを使用して、グローバルレベル、サイトレベル、およびユーザーレベルでポリシーを管理できます。 Lync Server ストレージと Exchange 2013 ストレージを統合すると、Exchange ユーザーポリシーは Lync Server 2013 アーカイブポリシーよりも優先されます。

ポリシーの階層など、ポリシーの実装方法の詳細については、「計画」、「展開」、または「操作」のドキュメントの「 [Lync Server 2013 でのアーカイブの仕組み](lync-server-2013-how-archiving-works.md) 」を参照してください。

<div>


> [!NOTE]
> アーカイブの実装を制御するには、重要モード、削除オプション、IM と会議のどちらをアーカイブするかなどのアーカイブ構成のオプションを指定する必要があります。 既定では、グローバル アーカイブ構成やサイトまたはプール アーカイブ構成で有効になっているオプションはありません。 アーカイブ ポリシーで内部通信または外部通信のアーカイブを有効にする前に、すべての該当するオプションをアーカイブ構成で指定する必要があります。 詳細については、「操作」のドキュメントの「 <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Lync Server 2013 での組織、サイト、およびプールのアーカイブ構成オプションの管理</A> 」を参照してください。<BR>展開に対して Microsoft Exchange 統合を有効にした場合は、exchange 2013 に所属しているユーザーに対してアーカイブを有効にするかどうかを制御し、メールボックスを In-Place ホールドにします。 詳細については、「展開」のドキュメントの「 <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies For Exchange server integration using The Lync server 2013</A> 」を参照してください。



</div>

<div>

## <a name="in-this-section"></a>このセクションの内容

  - [Lync Server 2013 のアーカイブポリシーを作成して、特定のサイトまたはユーザーの内部通信または外部通信のアーカイブを有効または無効にする](lync-server-2013-create-archiving-policy-sites-users.md)

  - [組織、サイト、ユーザーの内部通信または外部通信のアーカイブを有効または無効にするための Lync Server 2013 のアーカイブポリシーの変更](lync-server-2013-change-archiving-policy-org-sites-users.md)

  - [Lync Server 2013 でのユーザーへのアーカイブポリシーの適用](lync-server-2013-applying-an-archiving-policy-to-users.md)

  - [Exchange Server 統合を使用する場合の Lync Server 2013 でのアーカイブポリシーの設定](lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md)

  - [Lync Server 2013 でのアーカイブポリシーの削除](lync-server-2013-deleting-an-archiving-policy.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

