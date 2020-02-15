---
title: Lync Server 2013 Active Directory のサポート
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Active Directory support
ms:assetid: 28ed9ac4-586d-4803-ad45-99c4fa793f54
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425756(v=OCS.15)
ms:contentKeyID: 48183679
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b3ded5de5500778559efe632c5272db50b0eadbd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034117"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="active-directory-support-in-lync-server-2013"></a>Lync Server 2013 での Active Directory のサポート

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-12-04_

Lync Server 2013 でサポートされている Active Directory ドメインサービスのオンプレミストポロジは次のとおりです。

  - 単一のドメインを含む単一のフォレスト

  - 単一のツリーと複数のドメインを含む単一のフォレスト

  - 複数のツリーと不整合の名前空間を含む単一のフォレスト

  - 中央フォレスト トポロジの複数のフォレスト

  - リソース フォレスト トポロジの複数のフォレスト

<div>


> [!NOTE]  
> Lync Server 2013 では、単一ラベルドメインはサポートされていません。 たとえば、 <STRONG>contoso</STRONG>という名前のルートドメインを持つフォレストはサポートされていますが、 <STRONG>local</STRONG>という名前の単一ラベルルートドメインはサポートされていません。 詳細については、「Microsoft サポート技術情報の記事300684」を参照してください<A href="http://go.microsoft.com/fwlink/p/?linkid=143752">http://go.microsoft.com/fwlink/p/?linkId=143752</A>。単一ラベル DNS 名のドメインに対する Windows の構成については、「」を参照してください。



</div>

<div>


> [!NOTE]  
> Lync Server 2013 では、ドメイン名の変更はサポートされていません。 Lync Server が展開されているドメインの名前を変更する必要がある場合は、まず Lync Server をアンインストールしてから、ドメインの名前を変更してから Lync Server を再インストールする必要があります。



</div>

オンプレミス展開でサポートされるトポロジと要件の詳細については、「計画」のドキュメントの「 [Active Directory ドメインサービスの要件、サポート、および Lync Server 2013 のトポロジ](lync-server-2013-active-directory-domain-services-requirements-support-and-topologies.md)」を参照してください。

</div>

<span> </span>

</div>

</div>

</div>

