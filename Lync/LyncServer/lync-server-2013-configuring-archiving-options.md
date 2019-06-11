---
title: 'Lync Server 2013: アーカイブオプションを構成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Archiving options
ms:assetid: b2f7f74d-e1ad-494e-9d46-5eb0efe5fb29
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205182(v=OCS.15)
ms:contentKeyID: 48185158
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 98356b53940c6189abac5a4b554769093f84dd2a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840290"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-archiving-options-in-lync-server-2013"></a>Lync Server 2013 でアーカイブオプションを構成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-10_

Lync Server 2013 コントロールパネルで、アーカイブの実装方法を指定するには、アーカイブ構成を使います。 これには、次のアーカイブ構成が含まれます。

  - Lync Server 2013 を展開するときに既定で作成されるグローバル構成。

  - 作成および使用して、特定のサイトまたはプールに対するアーカイブの実装方法を指定することができる、オプションのサイトレベルとプールレベルの構成。

アーカイブの展開時にアーカイブ構成を最初に設定しましたが、展開後に構成の変更、追加、削除を行うことができます。 Lync Server 2013 コントロールパネルで、[**アーカイブと監視**] グループの [**アーカイブの構成**] ページを使用して、グローバルレベル、サイトレベル、プールレベルで構成を管理できます。 アーカイブ構成の実装方法について詳しくは、「指定できるオプションやアーカイブ構成の階層」を参照してください。「 [Lync Server 2013 でのアーカイブの動作](lync-server-2013-how-archiving-works.md)(計画ドキュメント、展開)」を参照してください。ドキュメント、または操作のドキュメント。 展開後に構成を管理する方法について詳しくは、「 [Lync Server 2013 でアーカイブ構成オプションを管理](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)する」を参照してください。この操作については、「運用ドキュメント」を参照してください。

<div>


> [!NOTE]  
> アーカイブを使用するには、内部通信のアーカイブを有効にするか、外部通信を有効にするか、または Lync Server 2013 を使用しているユーザーに対してアーカイブを有効にするかを指定するようにアーカイブポリシーを構成する必要があります。 既定では、内部または外部の通信でアーカイブは有効になっていません。 すべてのポリシーでアーカイブを有効にする前に、このセクションで説明するように、展開に適したアーカイブ構成を指定し、必要に応じて特定のサイトとプールを指定する必要があります。 アーカイブを有効にする方法の詳細については、展開ドキュメントの「 <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Lync Server 2013 でアーカイブポリシーを構成して割り当てる</A>」を参照してください。<BR>展開内のすべてのユーザーに対して Microsoft Exchange の統合を使用しない場合は、内部通信のアーカイブを有効にするか、外部通信を有効にするか、または両方を有効にするかを指定するようにアーカイブポリシーを構成する必要があります。 既定では、Lync Server 2013 アーカイブデータベースを使用しているときに、データをアーカイブするための内部通信または外部通信は、アーカイブが有効になっていません。 すべてのポリシーでアーカイブを有効にする前に、このセクションで説明するように、展開用に適切なアーカイブ構成を指定し、必要に応じて特定のサイトとプールを指定する必要があります。 Lync Server 2013 アーカイブデータベースで使用するためのアーカイブを有効にする方法について詳しくは、「展開ドキュメントの<A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Lync Server 2013 でのアーカイブポリシーの構成と割り当て</A>」をご覧ください。



</div>

<div>

## <a name="in-this-section"></a>このセクション中

  - [Lync Server 2013 のグローバルレベルでアーカイブオプションを構成する](lync-server-2013-configuring-archiving-options-at-the-global-level.md)

  - [Lync Server 2013 でサイトのアーカイブオプションを構成する](lync-server-2013-configuring-archiving-options-for-a-site.md)

  - [Lync Server 2013 でプールのアーカイブオプションを構成する](lync-server-2013-configuring-archiving-options-for-a-pool.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

