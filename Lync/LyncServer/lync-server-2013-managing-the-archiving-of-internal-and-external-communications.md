---
title: 社内および社外の通信のアーカイブを管理する
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
ms.openlocfilehash: ff349fcb7b012ed2604c4e75fe0f4bdd5ed99fc6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757961"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-the-archiving-of-internal-and-external-communications-in-lync-server-2013"></a>Lync Server 2013 での内部および外部通信のアーカイブの管理

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-09_

Lync Server 2013 では、アーカイブポリシーを使って内部通信と外部通信のアーカイブを有効または無効にすることができます。 Microsoft Exchange 統合を使用していない場合、または Exchange 2013 を使っていないユーザーがメールボックスを配置している場合インプレースホールド。 これには、次のアーカイブポリシーが含まれます。

  - Lync Server 2013 を展開するときに既定で作成されるグローバルポリシー。

  - 特定のサイトまたはユーザーに対するアーカイブの実装方法を指定するために作成および使用できる、オプションのサイトレベルとユーザーレベルのポリシー。

アーカイブの展開時にアーカイブポリシーを最初に設定しましたが、展開後にポリシーの変更、追加、削除を行うことができます。 Lync Server 2013 コントロールパネルで、[**アーカイブと監視**] グループの [**アーカイブポリシー** ] ページを使用して、グローバルレベル、サイトレベル、ユーザーレベルでポリシーを管理できます。 Lync Server ストレージと Exchange 2013 ストレージを統合すると、Exchange ユーザーポリシーは Lync Server 2013 アーカイブポリシーよりも優先されます。

ポリシーの実装方法 (ポリシーの階層を含む) について詳しくは、「計画ドキュメント、展開ドキュメント、または運用ドキュメント」の「 [Lync Server 2013 でのアーカイブの動作](lync-server-2013-how-archiving-works.md)」をご覧ください。

<div>


> [!NOTE]
> アーカイブの実装を制御するには、IM または会議のアーカイブ、重要モードの使用、削除オプションなど、アーカイブ構成のオプションを指定する必要があります。 既定では、グローバルアーカイブ構成またはサイトまたはプールのアーカイブ構成では、どのオプションも有効になっていません。 アーカイブポリシーで、内部または外部通信のアーカイブを有効にする前に、アーカイブ構成ですべての適切なオプションを指定する必要があります。 詳細については、「 <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Lync Server 2013 でアーカイブ構成オプションを管理</A>する」を参照してください。この操作のドキュメントでは、組織、サイト、プールについて説明します。<BR>展開に対して Microsoft Exchange の統合を有効にすると、exchange 2013 を使っているユーザーに対してアーカイブが有効になっているかどうかを Exchange ポリシーで制御し、そのメールボックスをインプレースホールドに入れます。 詳細については、展開ドキュメントで<A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Exchange Server との統合を使用する場合の「Lync server 2013 でアーカイブするためのポリシーを設定する</A>」を参照してください。



</div>

<div>

## <a name="in-this-section"></a>このセクション中

  - [Lync Server 2013 でアーカイブポリシーを作成して、特定のサイトまたはユーザーの内部または外部の通信のアーカイブを有効または無効にする](lync-server-2013-create-archiving-policy-sites-users.md)

  - [Lync Server 2013 でアーカイブポリシーを変更して、組織、サイト、またはユーザーの内部または外部の通信のアーカイブを有効または無効にする](lync-server-2013-change-archiving-policy-org-sites-users.md)

  - [Lync Server 2013 のユーザーにアーカイブポリシーを適用する](lync-server-2013-applying-an-archiving-policy-to-users.md)

  - [Exchange Server との統合を使用するときに、Lync Server 2013 でアーカイブするためのポリシーを設定する](lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md)

  - [Lync Server 2013 でアーカイブポリシーを削除する](lync-server-2013-deleting-an-archiving-policy.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

