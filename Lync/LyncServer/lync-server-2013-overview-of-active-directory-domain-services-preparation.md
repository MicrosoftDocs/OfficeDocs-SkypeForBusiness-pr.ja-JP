---
title: 'Lync Server 2013: Active Directory ドメイン サービスの準備の概要'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of Active Directory Domain Services preparation
ms:assetid: cdd2a652-6a0d-4728-9950-3fcaa7a80066
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398869(v=OCS.15)
ms:contentKeyID: 48185662
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26636846ce7b985a33af3175d51798c4c12c5ea7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825822"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-active-directory-domain-services-preparation-in-lync-server-2013"></a>Lync Server 2013 の Active Directory ドメイン サービスの準備の概要

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-29_

Lync Server 2013 の展開用に Active Directory ドメインサービスを準備するには、次の3つの手順を特定の順序で行う必要があります。

次の表では、Lync Server 用の AD DS を準備するために必要な手順について説明します。

### <a name="active-directory-preparation-steps"></a>Active Directory の準備手順

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>ステップ</th>
<th>説明</th>
<th>実行場所</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1.</p></td>
<td><p><a href="lync-server-2013-preparing-the-active-directory-schema.md">Lync Server 2013 での Active Directory スキーマの準備</a></p></td>
<td><p>Lync Server によって使用される新しいクラスと属性を追加して、Active Directory スキーマを拡張します。</p>
<p>Lync Server が展開されている展開で、フォレストごとに1回実行します。</p></td>
<td><p>Lync Server を展開する各フォレストのルートドメインのスキーママスターに対して。</p>
<div>

> [!NOTE]  
> スキーママスターに対してアクセス許可を持っているが、ルートドメインで Schema Admins グループのメンバーであり、かつスキーママスターの Enterprise Admins グループのメンバーである必要がある場合は、ルートドメインでこの手順を実行する必要はありません。 リソースフォレストのトポロジでは、この手順は、ユーザーのフォレスト内ではなく、リソースフォレストでのみ実行します。 中央フォレストトポロジでは、この手順は、ユーザーのフォレストではなく中央のフォレストでのみ実行します。


</div></td>
</tr>
<tr class="even">
<td><p>2.</p></td>
<td><p><a href="lync-server-2013-preparing-the-forest.md">Lync Server 2013 でのフォレストの準備</a></p></td>
<td><p>Lync Server で使用されるグローバル設定とユニバーサルグループを作成します。</p>
<p>Lync Server が展開されている展開で、フォレストごとに1回実行します。</p></td>
<td><p>Lync Server を展開する各フォレストのルートドメイン。 この手順を実行するには、Enterprise Admins グループのメンバーである必要があります。</p>
<div>

> [!NOTE]  
> リソースフォレストのトポロジでは、この手順は、ユーザーのフォレスト内ではなく、リソースフォレストでのみ実行します。 中央フォレストトポロジでは、この手順は、ユーザーのフォレストではなく中央のフォレストでのみ実行します。


</div></td>
</tr>
<tr class="odd">
<td><p>3.</p></td>
<td><p><a href="lync-server-2013-preparing-domains.md">Lync Server 2013 のドメインの準備</a></p></td>
<td><p>ユニバーサルグループのメンバーによって使用されるオブジェクトにアクセス許可を追加します。</p>
<p>ユーザードメインまたはサーバードメインごとに1回実行します。</p>
<div>

> [!NOTE]  
> Lync Server 2010 から Lync Server 2013 に移行している場合、展開ウィザードでは、ドメインの準備が既に完了していることが示される場合があります。 ドメインの準備をもう一度実行する必要はありません。 Lync Server 2010 から Lync Server 2013 へのアクセス許可が変更されていない。


</div></td>
<td><p>Lync Server を展開する各ドメインのメンバーサーバー上。 この手順を実行するには、Domain Admins グループのメンバーである必要があります。</p></td>
</tr>
</tbody>
</table>


<div id="sectionSection0" class="section">

Lync server 2010 などの lync Server 2013 では、Office Communications Server 2007 R2 の場合と同様に、AD DS ではなく、中央管理ストアに構成情報が保存されます。 ただし、次の情報は AD DS に保存されています。

  - **スキーマの拡張機能**:
    
      - ユーザー オブジェクトの拡張
    
      - 下位互換性を維持するための Office Communications Server 2007 R2 クラスの拡張機能

<!-- end list -->

  - **データ**(Lync Server 拡張スキーマと既存のスキーマクラスに保存されています):
    
      - ユーザー SIP の Uniform Resource Identifier (URI) とその他のユーザー設定
    
      - 返信グループ、会議アテンダントなどのアプリケーションの連絡先オブジェクト
    
      - 中央管理ストアへのポインター
    
      - Kerberos 認証アカウント (オプションのコンピューターオブジェクト)

Lync Server 2013 では、RTCUniversalServerAdmins ユニバーサルグループにセットアップアクセス許可を付与して、そのグループのメンバーがローカルサーバーに Lync Server 2013 をインストールしてライセンス認証を行うことができるように、セットアップと管理を委任します (サーバーを追加した後で、トポロジ、公開済み、有効)。 委任されたユーザーは、Lync Server 2013 をインストールしてアクティブ化するコンピューターのローカル管理者である必要がありますが、Domain Admins グループのメンバーである必要はありません。 また、特定の組織単位 (Ou) 内のオブジェクトに対するアクセス許可を付与して、フォレストの準備中に作成されたユニバーサルグループのメンバーが、Domain Admins グループのメンバーにならずにそれらのオブジェクトにアクセスできるようにすることもできます。

Lync Server 2013 の新しい展開の場合、グローバル設定は構成コンテナーに保存されている必要があります。 組織が以前のバージョンからアップグレードしていて、システムコンテナーでまだグローバル設定を使用している場合は、システムコンテナーは引き続きサポートされます。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での Active Directory スキーマの準備](lync-server-2013-preparing-the-active-directory-schema.md)  
[Lync Server 2013 が使用する Active Directory のスキーマ拡張、クラス、属性](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md)  


[Lync Server 2013 でのフォレストの準備](lync-server-2013-preparing-the-forest.md)  
[Lync Server 2013 のドメインの準備](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

