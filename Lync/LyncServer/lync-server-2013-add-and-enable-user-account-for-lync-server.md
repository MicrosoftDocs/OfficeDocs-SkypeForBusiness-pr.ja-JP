---
title: 'Lync Server 2013: Lync Server のユーザーアカウントの追加と有効化'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add and enable user account for Lync Server
ms:assetid: 1edd1c1c-307d-450b-abea-33aaf56bdf13
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520961(v=OCS.15)
ms:contentKeyID: 48183578
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b0478bec0d78b56061cf68d9efabe5e78a60bad4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037839"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-and-enable-user-account-for-lync-server-2013"></a>Lync Server 2013 のユーザーアカウントを追加して有効にする

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-11-02_

Active Directory ユーザーとコンピューターでユーザーアカウントを有効にした後、lync server コントロールパネルを使用して、lync Server に Active Directory ユーザーを追加することにより、新しい Lync Server 2013 ユーザーアカウントを作成して有効にすることができます。

<div>

## <a name="to-add-and-enable-a-new-lync-server-user"></a>新しい Lync Server ユーザーを追加して有効にするには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで [**ユーザー**] をクリックします。

4.  [**ユーザーの有効化**] をクリックします。

5.  [**新規 Lync Server ユーザー**] ダイアログで [**追加**] をクリックします。

6.  [**ユーザーの検索**] ボックスに、名前、表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、電子メール アドレス、ユーザーのプリンシパル名 (UPN)、または対象の Active Directory ユーザー アカウントの電話番号の全体か最初の一部の文字列を入力して、[**検索**] をクリックします。

7.  表で、Lync Server に追加するアカウントを選択し、[ **OK]** をクリックします。

8.  ユーザーをプールに割り当て、詳細情報を指定し、ポリシーを対象のユーザーに割り当て、[**有効にする**] をクリックします。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 のユーザーアカウントを無効または再度有効にする](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  
[Lync Server 2013 からユーザーアカウントを削除する](lync-server-2013-remove-a-user-account-from-lync-server.md)  


[Lync Server 2013 のユーザーの有効化および無効化](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

