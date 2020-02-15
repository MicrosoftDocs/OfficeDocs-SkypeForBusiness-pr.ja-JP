---
title: サービスのセッションを禁止する
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Prevent sessions for services
ms:assetid: 4b541c72-cdc1-4f86-a5a8-c43c24f41d8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688049(v=OCS.15)
ms:contentKeyID: 49733642
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d936a063d5ce634a50b4ba4567f51473bf363612
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035853"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prevent-sessions-for-services"></a>サービスのセッションを禁止する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-04_

Microsoft Lync Server 2010 コントロールパネルを使用して、特定のコンピューターで実行されているすべての Lync Server 2010 サービスの新しいセッションを禁止したり、特定の Lync Server 2010 サービスの新しいセッションを禁止したりすることができます。

<div>

## <a name="to-prevent-new-sessions-for-all-lync-server-services-on-a-computer"></a>コンピューター上のすべての Lync Server サービスの新しいセッションを禁止するには

1.  RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウント、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、Lync Server 2013 を展開したネットワーク内の任意のコンピューターにログオンします。

2.  [Lync Server コントロール パネル] を開きます。

3.  左側のナビゲーション バーで [**トポロジ**] をクリックし、[**状態**] をクリックします。

4.  [**状態**] ページで、必要に応じてリストを並べ替えまたは検索し、新しいセッションを禁止するサービスを実行しているコンピューターを見つけてクリックします。

5.  [**アクション**] をクリックします。

6.  [**すべてのサービスの新しいセッションを禁止する] を**クリックします。

</div>

<div>

## <a name="to-prevent-new-sessions-for-a-specific-service"></a>特定のサービスの新しいセッションを禁止するには

1.  RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウント、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、Lync Server 2013 を展開したネットワーク内の任意のコンピューターにログオンします。

2.  [Lync Server コントロール パネル] を開きます。

3.  左側のナビゲーション バーで [**トポロジ**] をクリックし、[**状態**] をクリックします。

4.  [**状態**] ページで、必要に応じて一覧を並べ替えるかまたは検索して、開始または停止するサービスを実行しているコンピューターを確認してクリックします。

5.  [**プロパティ**] をクリックします。

6.  必要に応じてサービスの一覧を並べ替え、新しいセッションを禁止するサービスをクリックします。

7.  [**アクション**] をクリックします。

8.  [**サービスの新しいセッションを禁止する] を**クリックします。

9.  **[閉じる]** をクリックします。

</div>

</div>

<span> </span>

</div>

</div>

</div>

