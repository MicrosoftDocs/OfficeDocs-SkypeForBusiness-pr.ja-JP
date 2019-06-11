---
title: 'Lync Server 2013: Lync Server ユーザーを検索する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Search for Lync Server users
ms:assetid: 3b9f6f55-d7a9-46ae-8e10-f221ba0d3bb5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429701(v=OCS.15)
ms:contentKeyID: 48183871
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 068fe07bf14894d22f929291514854360d6d0465
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34821895"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="search-for-lync-server-users-in-lync-server-2013"></a>Lync server 2013 で Lync Server ユーザーを検索する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-05-14_

検索クエリの結果を使用して、Lync Server 2013 のユーザーを構成することができます。 ユーザーは、表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、または回線 URI (Uniform Resource Identifier) で検索できます。

Lync Server コントロールパネル、または Active Directory ユーザーとコンピュータースナップインを使用して、ユーザーを検索できます。 次の手順では、Lync Server コントロールパネルを使用してユーザーを検索する方法について説明します。

<div>


> [!NOTE]  
> 中央フォレストトポロジを持つ環境では、ユーザーのメールアドレスでユーザーを検索すると、検索結果が正確でない場合があります。 代わりに、SIP アドレスプレフィックスを指定してユーザーを検索することもできます。たとえば、sip: name、検索フィルターを追加して、メールアドレスの一部を含む SIP アドレスを選ぶか、または、<STRONG>ユーザー</STRONG>コマンドレットを使用します。



</div>

<div>

## <a name="to-search-for-one-or-more-users"></a>1人以上のユーザーを検索するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーション バーで [**ユーザー**] をクリックします。

4.  [**ユーザーの検索**] ボックスに、検索するユーザーアカウントの表示名、姓、名、SAM アカウント名、SIP アドレス、またはライン URI のすべてまたは最初の部分を入力して、[**検索**] をクリックします。

5.  (オプション) 結果を絞り込むための追加の検索条件を次のように指定します。
    
    1.  **検索結果**の上にある画面の右上隅にある展開矢印ボタンをクリックし、[**フィルターの追加**] をクリックします。
    
    2.  [ユーザー] プロパティを入力するか、ドロップダウンリストの矢印をクリックして、ユーザープロパティを選択します。
    
    3.  [指定の**値**に等しい] **** または [ **** 指定の値に等しい] をクリックします。
    
    4.  検索結果をフィルター処理するために使用する検索条件をテキストボックスに入力し、[**検索**] をクリックします。

6.  検索結果が [**検索結果**] の下に表示されます。 リスト内の任意またはすべてのユーザーを選択し、選択したユーザーに対して構成タスクを実行することができます。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 で有効になっているユーザーアカウントに関する情報の表示](lync-server-2013-viewing-information-about-user-accounts-enabled-for-lync-server.md)  
[Lync Server 2013 のユーザーを有効または無効にする](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

