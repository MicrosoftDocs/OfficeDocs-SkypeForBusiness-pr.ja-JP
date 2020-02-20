---
title: 'Lync Server 2013: アーカイブポリシーの構成と割り当て'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring and assigning Archiving policies
ms:assetid: acd18ea8-c7f1-4178-871a-cd3b75bdaa8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205175(v=OCS.15)
ms:contentKeyID: 48185121
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7db876d03f7322fae5f3a55f88708fe4165a20ba
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150946"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-and-assigning-archiving-policies-in-lync-server-2013"></a>Lync Server 2013 でのアーカイブポリシーの構成と割り当て

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-01_

Lync Server 2013 では、ポリシーを使用して、Lync Server 2013 に所属しているユーザーの内部通信と外部通信のアーカイブを有効または無効にします。 これには、次のアーカイブ ポリシーが含まれます。

  - Lync Server 2013 を展開するときに既定で作成されるグローバルポリシー。

  - 特定のサイトまたはユーザーに対するアーカイブの実装方法を指定するために作成して使用できるオプションのサイトレベルおよびユーザーレベルのポリシー。

アーカイブ ポリシーは、最初はアーカイブの展開時にセットアップしますが、展開後に変更、追加、および削除できます。 Lync Server 2013 コントロールパネルでは、**アーカイブおよび監視**グループの [**アーカイブポリシー** ] ページを使用して、グローバルレベル、サイトレベル、およびユーザーレベルでポリシーを管理できます。

<div>


> [!NOTE]  
> アーカイブの実装を制御するには、重要モード、削除オプション、IM と会議のどちらをアーカイブするかなどのアーカイブ構成のオプションを指定する必要があります。 既定では、グローバル アーカイブ構成やサイトまたはプール アーカイブ構成で有効になっているオプションはありません。 アーカイブ ポリシーで内部通信または外部通信のアーカイブを有効にする前に、すべての該当するオプションをアーカイブ構成で指定する必要があります。 詳細については、「操作」のドキュメントの「 <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Lync Server 2013 での組織、サイト、およびプールのアーカイブ構成オプションの管理</A>」を参照してください。<BR>Lync Server ストレージを Exchange 2013 ストレージと統合する場合、Exchange ユーザーポリシーは Lync Server 2013 アーカイブポリシーよりも優先されますが、メールボックスをインプレース保持に配置している Exchange 2013 に所属しているユーザーに対してのみ有効になります。



</div>

ポリシーの階層など、ポリシーの実装方法の詳細については、「計画」、「展開」、または「操作」のドキュメントの「 [Lync Server 2013 でのアーカイブの仕組み](lync-server-2013-how-archiving-works.md)」を参照してください。 展開後にポリシーを管理する方法の詳細については、「操作」のドキュメントの「 [Lync Server 2013 での内部および外部通信のアーカイブの管理](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)」を参照してください。

<div>

## <a name="in-this-section"></a>このセクションの内容

  - [Lync Server 2013 でのアーカイブ用のグローバルポリシーの構成](lync-server-2013-configuring-the-global-policy-for-archiving.md)

  - [Lync Server 2013 でのアーカイブ用のサイトポリシーのセットアップ](lync-server-2013-setting-up-site-policies-for-archiving.md)

  - [Lync Server 2013 でユーザーのアーカイブポリシーをセットアップする](lync-server-2013-setting-up-archiving-policies-for-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

