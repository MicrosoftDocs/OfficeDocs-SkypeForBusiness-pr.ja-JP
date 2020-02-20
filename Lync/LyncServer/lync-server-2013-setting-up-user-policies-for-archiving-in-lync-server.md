---
title: 'Lync Server 2013: Lync Server でのアーカイブ用のユーザーポリシーのセットアップ'
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
ms.openlocfilehash: 78a30684619a67fc1e48f3692a2bc40ccae55b14
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142783"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-user-policies-for-archiving-in-lync-server-2013"></a>Lync Server 2013 でのアーカイブ用のユーザーポリシーのセットアップ

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-10_

Lync Server 2013 に所属する特定のユーザーに対してアーカイブを有効または無効にするには、1つ以上のユーザーポリシーを作成して構成し、特定のユーザーまたはユーザーグループに適切なポリシーを適用する必要があります。 ユーザーポリシーは、サイトポリシーとグローバルポリシーより優先されますが、Lync Server 2013 に所属するユーザーのみが対象となります。

ユーザーは常に Lync Server に所属しています。 Microsoft Exchange 統合が有効になっている場合は、メールボックスが Microsoft Exchange Server 2013 にあるユーザーは、Lync Server でのアーカイブポリシーを管理する必要はありません。 アーカイブを使用するこれらのユーザーは、Exchange のインプレース保持によって管理されます。

グローバルポリシー、サイトポリシー、およびユーザーポリシーの階層を含むアーカイブポリシーのしくみの詳細については、「計画」、「展開」、または「操作」のドキュメントの「 [Lync Server 2013 でのアーカイブの仕組み](lync-server-2013-how-archiving-works.md)」を参照してください。

<div>


> [!NOTE]  
> 展開に対して Microsoft Exchange 統合を有効にした場合、exchange 2013 に所属しているユーザーに対してアーカイブを有効にするかどうかは、Exchange のインプレース保持ポリシーによって制御されます。 これらのユーザーのアーカイブでは、ユーザーのメールボックスがインプレース保持の状態になっている必要があります。 詳細については、「展開」のドキュメントの「 <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies For Exchange server integration using The Lync server 2013</A> 」を参照してください。<BR>アーカイブを有効にするには、その前にアーカイブ構成で適切なオプションをすべて指定する必要があります。 詳細については、「展開」のドキュメントの「 <A href="lync-server-2013-configuring-archiving-options.md">Lync Server 2013 のアーカイブオプションの構成</A>」を参照してください。



</div>

<div>

## <a name="in-this-section"></a>このセクションの内容

  - [Lync Server 2013 でのアーカイブ用のユーザーポリシーの作成と構成](lync-server-2013-creating-and-configuring-user-policies-for-archiving-in-lync-server.md)

  - [Lync server 2013 のユーザーへの Lync Server アーカイブポリシーの適用](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

