---
title: 'Lync Server 2013: Lync Server でアーカイブ用のユーザーポリシーを設定する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up user policies for Archiving in Lync Server
ms:assetid: 22d6cc76-6b5c-4a8c-bb8a-7996450ec085
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204742(v=OCS.15)
ms:contentKeyID: 48183626
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fa8f377c2a78275419c7d4906a51a9550864b8ba
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764533"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-user-policies-for-archiving-in-lync-server-2013"></a>Lync Server 2013 でアーカイブ用のユーザーポリシーを設定する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-10_

Lync Server 2013 上にある特定のユーザーに対してアーカイブを有効または無効にするには、1つ以上のユーザーポリシーを作成して構成し、適切なポリシーを特定のユーザーまたはユーザーグループに適用する必要があります。 ユーザーポリシーは、サイトとグローバルポリシーを上書きします。ただし、Lync Server 2013 に所属しているユーザーのみです。

ユーザーは常に Lync Server に置かれています。 Microsoft Exchange の統合が有効になっている場合、メールボックスが Microsoft Exchange Server 2013 にあるユーザーは、Lync Server で管理されているアーカイブポリシーを持っている必要はありません。 アーカイブを使用するユーザーは、インプレースホールドで管理されます。

グローバル、サイト、ユーザーのポリシーの階層など、アーカイブポリシーの動作について詳しくは、「計画ドキュメント、展開ドキュメント、または操作のドキュメント」の「 [Lync Server 2013 でのアーカイブの動作](lync-server-2013-how-archiving-works.md)」をご覧ください。

<div>


> [!NOTE]  
> 展開で Microsoft Exchange の統合を有効にしている場合、exchange 2013 を使っているユーザーに対してアーカイブが有効になっているかどうかは、インプレースホールドポリシーによって制御されます。 これらのユーザーのアーカイブでは、メールボックスがインプレース保持されるようにする必要があります。 詳細については、展開ドキュメントで<A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Exchange Server との統合を使用する場合の「Lync server 2013 でアーカイブするためのポリシーを設定する</A>」を参照してください。<BR>アーカイブを有効にする前に、アーカイブ構成ですべての適切なオプションを指定する必要があります。 詳細については、展開ドキュメントの「 <A href="lync-server-2013-configuring-archiving-options.md">Lync Server 2013 でアーカイブオプションを構成する</A>」を参照してください。



</div>

<div>

## <a name="in-this-section"></a>このセクション中

  - [Lync Server 2013 でアーカイブ用のユーザーポリシーを作成および構成する](lync-server-2013-creating-and-configuring-user-policies-for-archiving-in-lync-server.md)

  - [Lync server 2013 でユーザーに Lync Server のアーカイブポリシーを適用する](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

