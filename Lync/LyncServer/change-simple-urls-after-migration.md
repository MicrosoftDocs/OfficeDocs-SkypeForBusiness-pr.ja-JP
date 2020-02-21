---
title: 移行後に簡単な Url を変更する
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
ms.openlocfilehash: def26afe2bae21a7a3b6d0ffae4b358c76296e6d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181030"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="change-simple-urls-after-migration"></a>移行後に簡単な Url を変更する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-22_

Lync Server は、次の3つの簡単な Url をサポートします。

  - **Meet**は、サイトまたは組織内のすべての電話会議のベース URL として使用されます。 簡単な会議 URL を使用すると、会議に参加するためのリンクが覚えやすくなり、通知も配布も簡単になります。

  - **ダイヤル**インは、ダイヤルイン会議設定 web ページへのアクセスを有効にします。 ダイヤルインの簡易 URL は、すべての会議出席依頼に含まれているため、会議にダイヤルインするユーザーは必要な電話番号と PIN 情報にアクセスできます。

  - **管理者**は、Lync Server コントロールパネルにすばやくアクセスできます。 簡単な管理 URL は、組織内部の URL です。

Lync Server 2013 に移行した後、変更によって簡単な Url の DNS レコードと証明書に与える影響に注意する必要があります。 従来の Lync Server 2010 ディレクターがトポロジで使用されている場合は、簡易 Url を変更する必要はありません。 移行後に Lync Server 2010 ディレクターがトポロジから削除された場合は、簡単な URL の DNS レコードを更新して、Lync Server 2013 プールの1つをポイントする必要があります。 ただし、簡易 URL 名を変更する場合は必ず、各ディレクターおよびフロントエンド サーバーで Enable-CsComputer を実行して変更を登録する必要があります。

<div>

## <a name="changing-simple-urls-after-migration"></a>移行後の簡易 Url の変更

**簡単な会議 URL を更新するには**

1.  トポロジビルダーで、最上位ノードの [ **Lync Server**] を右クリックし、[**プロパティの編集**] をクリックします。

2.  左側のウィンドウで [**簡易 url** ] を選択し、[**会議の url:** ] の下の [url の**編集**] をクリックします。

3.  URL を目的の値に更新し、[**OK**] をクリックして編集した URL を保存します。

**管理者の簡易 URL を更新するには**

1.  トポロジビルダーで、最上位ノードの [ **Lync Server**] を右クリックし、[**プロパティの編集**] をクリックします。

2.  [**簡易 url**の選択] 左側のウィンドウで、[**管理アクセス url** ] ボックスに、Lync Server 2013 コントロールパネルへの管理アクセスに使用する簡易 url を入力し、[ **OK**] をクリックします。
    
    <div>
    

    > [!TIP]  
    > 管理 URL にできるだけ簡易 URL を使用することをお勧めします。 最も簡単なオプションは<STRONG> https://admin、です。</STRONG>&lt;ドメイン&gt;。

    
    </div>

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での簡単な Url の計画](lync-server-2013-planning-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

