---
title: 'Lync Server 2013: ユーザーのアーカイブポリシーの設定'
description: 'Lync Server 2013: ユーザーのアーカイブポリシーのセットアップ。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up Archiving policies for users
ms:assetid: 1bbb45df-0590-4c66-9d65-d25526f57790
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204722(v=OCS.15)
ms:contentKeyID: 48183549
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c18a15c1a0611f49a6fd9a4983f3ce87104332e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559523"
---
# <a name="setting-up-archiving-policies-for-users-in-lync-server-2013"></a>Lync Server 2013 でユーザーのアーカイブポリシーをセットアップする

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-09_

ユーザーのアーカイブ ポリシーを作成および構成し、そのポリシーを特定のユーザーまたはユーザー グループに適用することで、特定のユーザーに対してアーカイブを有効または無効にできます。 ユーザー ポリシーは、グローバル ポリシーやサイト ポリシーより優先されます。 アーカイブポリシーは、Microsoft Exchange 統合を使用していない場合、または Microsoft Exchange 統合を使用しているが、Exchange 2013 を使用しておらず、メールボックスを In-Place 保持に配置するユーザーがいる場合にのみ適用されます。

グローバルポリシー、サイトポリシー、およびユーザーポリシーの階層を含むアーカイブポリシーのしくみの詳細については、「 [Lync Server 2013](lync-server-2013-how-archiving-works.md) の計画に関するドキュメント、展開に関するドキュメント、または操作のドキュメントでのアーカイブの仕組み」を参照してください。

<div>


> [!NOTE]  
> 展開に対して Microsoft Exchange 統合を有効にした場合は、exchange 2013 に所属しているユーザーに対してアーカイブを有効にし、メールボックスを In-Place ホールドにするかどうかを Exchange In-Place 保持ポリシーで制御します。 詳細については、「展開」のドキュメントの「 <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies For Exchange server integration using The Lync server 2013</A> 」を参照してください。<BR>アーカイブ ポリシーで内部または外部の通信のアーカイブを有効にする前に、アーカイブ構成のすべてのオプションを適切に指定してください。 詳細については、「展開」のドキュメントの「 <A href="lync-server-2013-configuring-archiving-options.md">Lync Server 2013 のアーカイブオプションの構成</A> 」を参照してください。



</div>

<div>

## <a name="in-this-section"></a>このセクションの内容

  - [Lync Server 2013 でのアーカイブ用のユーザーポリシーのセットアップ](lync-server-2013-setting-up-user-policies-for-archiving-in-lync-server.md)

  - [Exchange Server 統合を使用する場合の Lync Server 2013 でのアーカイブポリシーの設定](lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

