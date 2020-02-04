---
title: 'Lync Server 2013: Lync Server で有効になっているユーザーアカウント'
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
ms.openlocfilehash: 613d6350fcb405b1ae8beef78c3ee8c8a64a084c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744657"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-accounts-enabled-for-lync-server-2013"></a>Lync Server 2013 で有効になっているユーザーアカウント

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-04-18_

このセクションのトピックでは、Lync Server 2013 コントロールパネルを使用して実行できるユーザー設定を構成するための手順について説明します。

<div>


> [!IMPORTANT]  
> Lync Server コントロールパネルを使用して、Active Directory Domain Admins グループのメンバーであるユーザーを管理することはできません。 ドメイン管理者のユーザーの場合は、Lync Server コントロールパネルのみを使って読み取り専用の検索操作を実行できます。 ドメイン管理者のユーザーに対して書き込み操作を実行するには (たとえば、Lync Server コントロールパネルの有効化または無効化、プールまたはポリシーの割り当ての変更、テレフォニーの設定、SIP アドレス)、ドメイン管理者ユーザーとしてログオンしている場合は、Windows PowerShell コマンドレットを使用する必要があります。 Windows PowerShell コマンドレットを使用してユーザーを管理する方法の詳細については、「 <A href="lync-server-2013-lync-server-management-shell.md">Lync Server 2013 管理シェル</A>」を参照してください。



</div>

ユーザーを検索する、またはユーザーの検索結果をフィルター処理する必要がある Lync Server 2013 管理タスクを実行すると、一部のユーザープロパティが Active Directory ドメインサービスの属性として存在しますが、グローバルカタログにはレプリケートされません。Microsoft Exchange Server が展開されるまで。 Microsoft Exchange は、Lync Server ではなく、インストール時にグローバルカタログへの次の属性をマークします。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>ユーザー情報</th>
<th>住所と電話番号</th>
<th>組織</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ネーム</p></td>
<td><p>住所</p>
<p>国または地域</p>
<p>ページャー</p>
<p>/Fax</p>
<p>モバイル</p></td>
<td><p>タイトル</p>
<p>貴社</p>
<p>各部</p>
<p>Office</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a>このセクション中

  - [Lync Server 2013 で有効になっているユーザーアカウントに関する情報の表示](lync-server-2013-viewing-information-about-user-accounts-enabled-for-lync-server.md)

  - [Lync Server 2013 のユーザーを有効または無効にする](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)

  - [Lync Server 2013 でのユーザーのエンタープライズボイスの管理](lync-server-2013-managing-enterprise-voice-for-users.md)

  - [Lync Server 2013 でユーザーアカウントのプロパティを変更する](lync-server-2013-modifying-user-account-properties.md)

  - [Lync Server 2013 での組織の外部アクセス ポリシーの管理](lync-server-2013-manage-external-access-policy-for-your-organization.md)

  - [Lync Server 2013 でのユーザーごとのポリシーの割り当て](lync-server-2013-assigning-per-user-policies.md)

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 のユーザー管理コマンドレット](lync-server-2013-user-management-cmdlets.md)  


[Lync Server 2013 のユーザー管理](lync-server-2013-managing-users-in-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

