---
title: 'Lync Server 2013: Lync Server に対して有効になっているユーザーアカウント'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User accounts enabled for Lync Server 2013
ms:assetid: 8021087e-5084-4a39-9fef-ab9376c6d371
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182543(v=OCS.15)
ms:contentKeyID: 48184651
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c7133ee4f1753d5178bd1ac41e3483dfe61a9e1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530274"
---
# <a name="user-accounts-enabled-for-lync-server-2013"></a>Lync Server 2013 に対して有効になっているユーザーアカウント

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-04-18_

このセクションのトピックでは、Lync Server 2013 コントロールパネルを使用して実行できるユーザー設定を構成するための手順を順を追って説明します。

<div>


> [!IMPORTANT]  
> Lync Server コントロールパネルを使用して、Active Directory Domain Admins グループのメンバーであるユーザーを管理することはできません。 ドメイン管理者ユーザーの場合、Lync Server コントロールパネルのみを使用して読み取り専用の検索操作を実行できます。 ドメイン管理者のユーザーに対して書き込み操作を実行する (たとえば、Lync Server コントロールパネルの有効化または無効化、プールまたはポリシーの割り当ての変更、テレフォニー設定、SIP アドレス) については、ドメイン管理者ユーザーとしてログオンしているときに Windows PowerShell コマンドレットを使用する必要があります。 Windows PowerShell コマンドレットを使用してユーザーを管理する方法の詳細については、「 <A href="lync-server-2013-lync-server-management-shell.md">Lync Server 2013 Management Shell</A>」を参照してください。



</div>

ユーザーを検索したり、ユーザーの検索結果にフィルターを適用したりすることが必要な Lync Server 2013 管理タスクを実行すると、Active Directory ドメインサービスに属性として存在するが、Microsoft Exchange Server が展開されるまでグローバルカタログにレプリケートされないユーザープロパティがいくつかあります。 Lync Server ではなく、Microsoft Exchange は、次の属性がインストールされているグローバルカタログへのレプリケーションをマークします。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>ユーザー情報:</th>
<th>住所と電話番号:</th>
<th>組織</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Initials</p></td>
<td><p>番地</p>
<p>国/地域</p>
<p>Pager</p>
<p>FAX</p>
<p>Mobile</p></td>
<td><p>Title</p>
<p>Company</p>
<p>部署</p>
<p>事業所</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a>このセクションの内容

  - [Lync Server 2013 に対して有効になっているユーザーアカウントに関する情報の表示](lync-server-2013-viewing-information-about-user-accounts-enabled-for-lync-server.md)

  - [Lync Server 2013 のユーザーの有効化および無効化](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)

  - [Lync Server 2013 でのユーザーのエンタープライズ Voip の管理](lync-server-2013-managing-enterprise-voice-for-users.md)

  - [Lync Server 2013 でユーザーアカウントのプロパティを変更する](lync-server-2013-modifying-user-account-properties.md)

  - [Lync Server 2013 での外部アクセスポリシーの管理](lync-server-2013-manage-external-access-policy-for-your-organization.md)

  - [Lync Server 2013 でのユーザー単位のポリシーの割り当て](lync-server-2013-assigning-per-user-policies.md)

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でのユーザー管理のコマンドレット](lync-server-2013-user-management-cmdlets.md)  


[Lync Server 2013 でのユーザーの管理](lync-server-2013-managing-users-in-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

