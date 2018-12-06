---
title: Lync Server 2013 の Active Directory のサポート
TOCTitle: Active Directory のサポート
ms:assetid: 28ed9ac4-586d-4803-ad45-99c4fa793f54
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg425756(v=OCS.15)
ms:contentKeyID: 48271628
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での Active Directory のサポート

 

_**トピックの最終更新日:** 2016-12-08_

Lync Server 2013 でサポートされる Active Directory ドメイン サービス 内部設置型トポロジは次のとおりです。

  - 単一のドメインを含む単一のフォレスト

  - 単一のツリーと複数のドメインを含む単一のフォレスト

  - 複数のツリーと不整合の名前空間を含む単一のフォレスト

  - 中央フォレスト トポロジの複数のフォレスト

  - リソース フォレスト トポロジの複数のフォレスト

> [!NOTE]
> Lync Server 2013 では、単一ラベルのドメインはサポートされません。たとえば、<strong>contoso.local</strong> という名前のルート ドメインを持つフォレストはサポートされますが、<strong>local</strong> という名前の単一ラベルのルート ドメインはサポートされません。詳細については、Microsoft サポート技術情報の記事 300684「単一ラベル DNS 名を使用して Active Directory のドメインを構成する」(<a href="http://go.microsoft.com/fwlink/?linkid=143752%26clcid=0x411" class="uri">http://go.microsoft.com/fwlink/?linkid=143752&amp;clcid=0x411</a>) を参照してください。


> [!NOTE]
> Lync Server 2013 では、ドメインの名前変更はサポートしていません。Lync Server が展開されるドメインの名前を変更する必要がある場合は、最初に Lync Server をアンインストールし、ドメインの名前を変更してから、Lync Server を再インストールする必要があります。


内部設置型展開でサポートされるトポロジと要件の詳細については、「計画」のドキュメントの「[Lync Server 2013 の Active Directory ドメイン サービスの要件、サポート、およびトポロジ](lync-server-2013-active-directory-domain-services-requirements-support-and-topologies.md)」を参照してください。

