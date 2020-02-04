---
title: 移行後の簡易 URL の変更
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Change simple URLs after migration
ms:assetid: addb0dc8-8324-42b1-9a00-f4bd14fdf5c0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721844(v=OCS.15)
ms:contentKeyID: 49733777
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a24eda274734e0c5a27fab30640a363de6653514
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726727"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="change-simple-urls-after-migration"></a>移行後の簡易 URL の変更

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-22_

Lync Server は、次の3つの簡単な Url をサポートします。

  - **会議**は、サイトまたは組織内のすべての会議のベース URL として使用されます。 [会議への参加] の [シンプル URL] を使用すると、会議に参加するためのリンクを簡単に理解して、簡単に連絡して配布することができます。

  - [**ダイヤル**イン] は、ダイヤルイン会議の設定の web ページにアクセスできるようにします。 ダイヤルインの簡易 URL は、会議にダイヤルインするユーザーが必要な電話番号と PIN 情報にアクセスできるように、すべての会議出席依頼に含まれています。

  - **管理者**が Lync Server コントロールパネルにすばやくアクセスできるようにします。 管理者の簡易 URL は、組織の内部にあります。

Lync Server 2013 に移行した後は、変更によって単純な Url の DNS レコードと証明書にどのような影響があるかを把握しておく必要があります。 従来の Lync Server 2010 ディレクターがトポロジで引き続き使用されている場合は、単純な Url への変更は必要ありません。 移行後に Lync Server 2010 ディレクターがトポロジから削除された場合は、Lync Server 2013 プールの1つをポイントするように、単純な URL の DNS レコードを更新する必要があります。 ただし、単純な URL 名を変更する場合は必ず、各ディレクターとフロントエンドサーバーで [ユーザーの有効化] を実行して、変更を登録する必要があります。

<div>

## <a name="changing-simple-urls-after-migration"></a>移行後に単純な Url を変更する

**[シンプルの概要 URL を更新するには、**

1.  [トポロジビルダー] で、トップノードの**Lync サーバー**を右クリックし、[**プロパティの編集**] をクリックします。

2.  左側のウィンドウで [**単純な url** ] を選び、[会議 url] を選び**ます。** [会議 url] を選び、[ **url の編集**] をクリックします。

3.  URL を目的の値に更新し、[**OK**] をクリックして編集した URL を保存します。

**管理者の簡易 URL を更新するには**

1.  [トポロジビルダー] で、トップノードの**Lync サーバー**を右クリックし、[**プロパティの編集**] をクリックします。

2.  左側のウィンドウで [**単純な url** ] を選び、[**管理アクセス URL** ] ボックスに、Lync Server 2013 コントロールパネルへの管理アクセスに使用する単純な url を入力して、[ **OK]** をクリックします。
    
    <div>
    

    > [!TIP]  
    > 管理 URL には、できる限りシンプルな URL を使用することをお勧めします。 最も簡単なオプションは<STRONG> https://adminです。</STRONG>&lt;ドメイン&gt;。

    
    </div>

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での簡単な URL の計画](lync-server-2013-planning-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

