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
ms.openlocfilehash: 0d8cfb5b446456d99750529d883172ed3cb56e3e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726557"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-and-assigning-archiving-policies-in-lync-server-2013"></a>Lync Server 2013 でアーカイブポリシーを構成して割り当てる

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-01_

Lync server 2013 では、ポリシーを使って、内部通信のアーカイブを有効または無効にすることができます。また、Lync Server 2013 を使用しているユーザー向けの外部通信を有効または無効にします。 これには、次のアーカイブポリシーが含まれます。

  - Lync Server 2013 を展開するときに既定で作成されるグローバルポリシー。

  - 特定のサイトまたはユーザーに対するアーカイブの実装方法を指定するために作成および使用できる、オプションのサイトレベルとユーザーレベルのポリシー。

アーカイブの展開時にアーカイブポリシーを最初に設定しましたが、展開後にポリシーの変更、追加、削除を行うことができます。 Lync Server 2013 コントロールパネルで、[**アーカイブと監視**] グループの [**アーカイブポリシー** ] ページを使用して、グローバルレベル、サイトレベル、ユーザーレベルでポリシーを管理できます。

<div>


> [!NOTE]  
> アーカイブの実装を制御するには、IM または会議のアーカイブ、重要モードの使用、削除オプションなど、アーカイブ構成のオプションを指定する必要があります。 既定では、グローバルアーカイブ構成またはサイトまたはプールのアーカイブ構成では、どのオプションも有効になっていません。 アーカイブポリシーで、内部または外部通信のアーカイブを有効にする前に、アーカイブ構成ですべての適切なオプションを指定する必要があります。 詳細については、「 <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Lync Server 2013 でアーカイブ構成オプションを管理</A>する」を参照してください。この操作のドキュメントでは、組織、サイト、プールについて説明します。<BR>Lync Server ストレージを Exchange 2013 ストレージと統合する場合、Exchange ユーザーのポリシーは、Lync Server 2013 アーカイブポリシーよりも優先されますが、Exchange 2013 を使用しているユーザーに対して、メールボックスがインプレースホールドに組み込まれています。



</div>

ポリシーの実装方法 (ポリシーの階層を含む) について詳しくは、「計画ドキュメント、展開ドキュメント、または運用ドキュメント」の「 [Lync Server 2013 でのアーカイブの動作](lync-server-2013-how-archiving-works.md)」をご覧ください。 展開後にポリシーを管理する方法について詳しくは、「運用ドキュメントの「 [Lync Server 2013 での社内および社外の通信のアーカイブを管理](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)する」をご覧ください。

<div>

## <a name="in-this-section"></a>このセクション中

  - [Lync Server 2013 でアーカイブ用のグローバルポリシーを構成する](lync-server-2013-configuring-the-global-policy-for-archiving.md)

  - [Lync Server 2013 でアーカイブ用のサイトポリシーを設定する](lync-server-2013-setting-up-site-policies-for-archiving.md)

  - [Lync Server 2013 でユーザーのアーカイブポリシーを設定する](lync-server-2013-setting-up-archiving-policies-for-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

