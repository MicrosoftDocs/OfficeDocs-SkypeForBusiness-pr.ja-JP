---
title: 'Lync Server 2013: Lync Server ユーザーの検索'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Search for Lync Server users
ms:assetid: 3b9f6f55-d7a9-46ae-8e10-f221ba0d3bb5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429701(v=OCS.15)
ms:contentKeyID: 48183871
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b690b0880e1da838b3b8f15392e64c4f4c650c10
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510494"
---
# <a name="search-for-lync-server-users-in-lync-server-2013"></a>Lync server 2013 での Lync Server ユーザーの検索

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-05-14_

検索クエリの結果を使用して、Lync Server 2013 のユーザーを構成できます。 ユーザーは、表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、または回線 URI (Uniform Resource Identifier) で検索できます。

ユーザーの検索には、Lync Server コントロール パネルまたは Active Directory ユーザーおよびコンピューター スナップインを使用できます。 次の手順では、Lync Server コントロールパネルを使用してユーザーを検索する方法について説明します。

<div>


> [!NOTE]  
> 中央フォレストトポロジを使用している環境では、ユーザーの電子メールアドレスでユーザーを検索すると、検索結果が正確でないことがあります。 代わりに、SIP アドレスプレフィックスを指定してユーザーを検索できます。たとえば、sip: name、検索フィルターを追加して、電子メールアドレスの一部を含む SIP アドレスを選択するか、または <STRONG>Get-help user</STRONG> コマンドレットを使用します。



</div>

<div>

## <a name="to-search-for-one-or-more-users"></a>1 つ以上のユーザーを検索するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで [**ユーザー**] をクリックします。

4.  [**ユーザーの検索**] ボックスに、検索対象のユーザー アカウントの表示名、名、姓、SAM のアカウント名、SIP アドレス、または回線 URI の全体か最初の一部の文字列を入力して、[**検索**] をクリックします。

5.  (オプション) 結果を絞り込むための追加の検索条件を次のように指定します。
    
    1.  画面の右上隅、[**検索結果**] の上にある展開の矢印ボタンをクリックして、[**フィルターの追加** をクリックします。
    
    2.  ユーザーのプロパティを入力するか、ドロップダウン リストの矢印をクリックして選択し、ユーザーのプロパティを指定します。
    
    3.  [**次の値に等しい**] リストで、[**次の値に等しい**] または [**次の値に等しくない**] をクリックします。
    
    4.  テキスト ボックスで、検索結果のフィルターに使う検索条件を入力して、[**検索**] をクリックします。

6.  [**検索結果**] に検索結果が表示されます。 リストのユーザーの一部または全部を選択して、選択したユーザーに対して構成タスクを実行できます。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 に対して有効になっているユーザーアカウントに関する情報の表示](lync-server-2013-viewing-information-about-user-accounts-enabled-for-lync-server.md)  
[Lync Server 2013 のユーザーの有効化および無効化](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

