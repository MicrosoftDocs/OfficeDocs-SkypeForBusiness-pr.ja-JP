---
title: 'Lync Server 2013: Active Directory ドメインサービスの準備の概要'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Active Directory Domain Services preparation
ms:assetid: cdd2a652-6a0d-4728-9950-3fcaa7a80066
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398869(v=OCS.15)
ms:contentKeyID: 48185662
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3085caf0b118b20bf52a4ff82a14b399d1ee6594
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036345"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-active-directory-domain-services-preparation-in-lync-server-2013"></a>Lync Server 2013 での Active Directory ドメインサービスの準備の概要

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-29_

Lync Server 2013 の展開用に Active Directory ドメインサービスを準備するには、特定の順序で3つの手順を実行する必要があります。

次の表では、Lync Server 用の AD DS を準備するために必要な手順について説明します。

### <a name="active-directory-preparation-steps"></a>Active Directory の準備のステップ

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
<th>手順</th>
<th>説明</th>
<th>実行場所</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1.</p></td>
<td><p><a href="lync-server-2013-preparing-the-active-directory-schema.md">Lync Server 2013 での Active Directory スキーマの準備</a></p></td>
<td><p>Lync Server で使用される新しいクラスと属性を追加して、Active Directory スキーマを拡張します。</p>
<p>Lync Server が展開されている展開内の各フォレストに対して1回実行します。</p></td>
<td><p>Lync Server を展開する各フォレストのルートドメインのスキーママスターに対して。</p>
<div>

> [!NOTE]  
> スキーマ マスターでのアクセス許可を持っている場合は、ルート ドメインでこのステップを実行する必要はありませんが、そのルート ドメインの Schema Admins グループのメンバーに、またスキーマ マスターでの Enterprise Admins グループのメンバーになっている必要があります。リソース フォレスト トポロジでは、ユーザー フォレストではなく、リソース フォレストのみでこのステップを実行します。中央フォレスト トポロジでは、ユーザー フォレストではなく、中央フォレストのみでこのステップを実行します。


</div></td>
</tr>
<tr class="even">
<td><p>2.</p></td>
<td><p><a href="lync-server-2013-preparing-the-forest.md">Lync Server 2013 のフォレストの準備</a></p></td>
<td><p>Lync Server で使用されるグローバル設定とユニバーサルグループを作成します。</p>
<p>Lync Server が展開されている展開内の各フォレストに対して1回実行します。</p></td>
<td><p>Lync Server を展開する各フォレストのルートドメイン。 このステップを実行するには、Enterprise Admins グループのメンバーになっている必要があります。</p>
<div>

> [!NOTE]  
> リソース フォレスト トポロジでは、ユーザー フォレストではなく、リソース フォレストのみでこのステップを実行します。中央フォレスト トポロジでは、ユーザー フォレストではなく、中央フォレストのみでこのステップを実行します。


</div></td>
</tr>
<tr class="odd">
<td><p>3.</p></td>
<td><p><a href="lync-server-2013-preparing-domains.md">Lync Server 2013 のドメインの準備</a></p></td>
<td><p>ユニバーサル グループのメンバーが使用するオブジェクトに対するアクセス許可を追加する。</p>
<p>ユーザー ドメインまたはサーバー ドメインあたり 1 回実行する。</p>
<div>

> [!NOTE]  
> Lync Server 2010 から Lync Server 2013 に移行する場合、展開ウィザードはドメインの準備が既に完了していることを示している場合があります。 ドメインの準備を再度実行する必要はありません。 アクセス許可が Lync Server 2010 から Lync Server 2013 に変更されていません。


</div></td>
<td><p>Lync Server が展開される各ドメインのメンバーサーバー上。 このステップを実行するには、Domain Admins グループのメンバーになっている必要があります。</p></td>
</tr>
</tbody>
</table>


<div id="sectionSection0" class="section">

Lync server 2013 (Lync Server 2010 など) は、Office Communications Server 2007 R2 の場合と同様に、AD DS ではなく中央管理ストアに構成情報の大部分を格納します。 ただし、次の情報は AD DS に格納されています。

  - **スキーマ拡張**:
    
      - ユーザー オブジェクトの拡張
    
      - 下位互換性を維持するための Office Communications Server 2007 R2 クラスの拡張機能

<!-- end list -->

  - **データ**(Lync Server 拡張スキーマおよび既存のスキーマクラスに格納されている):
    
      - ユーザーの SIP URI (Uniform Resource Identifier) と他のユーザー設定
    
      - リソース グループ、会議アテンダントなどのアプリケーションの連絡先オブジェクト
    
      - 中央管理ストアへのポインター
    
      - Kerberos 認証のアカウント (オプションのコンピューター オブジェクト)

Lync Server 2013 では、RTCUniversalServerAdmins ユニバーサルグループに対してセットアップのアクセス許可を付与することにより、セットアップと管理を委任します。これにより、そのグループのメンバーは、ローカルサーバーに Lync Server 2013 をインストールしてアクティブ化することができます (サーバーがローカルサーバーに追加されている場合)。トポロジ、公開済み、および有効)。 委任されたユーザーは、Lync Server 2013 をインストールしてアクティブ化するコンピューターのローカル管理者である必要がありますが、Domain Admins グループのメンバーである必要はありません。 また、フォレストの準備中に作成したユニバーサル グループのメンバーが Domain Admins グループのメンバーでなくてもそれらのオブジェクトにアクセスできるよう、指定された組織単位 (OU) 内のオブジェクトに対するアクセス許可を与えることもできます。

Lync Server 2013 の新しい展開では、グローバル設定を構成コンテナーに格納する必要があります。 以前のバージョンからアップグレードしていて、システムコンテナーにグローバル設定がある場合でも、システムコンテナーは引き続きサポートされます。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での Active Directory スキーマの準備](lync-server-2013-preparing-the-active-directory-schema.md)  
[Lync Server 2013 で使用される Active Directory スキーマの拡張、クラス、属性](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md)  


[Lync Server 2013 のフォレストの準備](lync-server-2013-preparing-the-forest.md)  
[Lync Server 2013 のドメインの準備](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

