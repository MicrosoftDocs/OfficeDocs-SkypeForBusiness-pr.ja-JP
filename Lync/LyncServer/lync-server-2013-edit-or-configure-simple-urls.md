---
title: 'Lync Server 2013: 簡単な URL の編集または構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Edit or configure simple URLs
ms:assetid: 0008aeea-4ae9-4e36-83cd-ef7ff7b6e128
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398063(v=OCS.15)
ms:contentKeyID: 48183216
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b1439ddb0dafc63b0e70439ee5231477fdbb6be
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833320"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="edit-or-configure-simple-urls-in-lync-server-2013"></a>Lync Server 2013 での簡単な URL の編集または構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-02-04_

この手順では、ローカル管理者または特権ドメイングループのメンバーシップは必要ありません。 コンピューターに標準ユーザーとしてログオンする必要があります。

Lync Server 2013 では、展開されている場合、フロントエンドサーバーまたはディレクター上のサービスに対して、内部および外部の通話を転送するために、シンプルな Url を使用します。 単純な Url の詳細については、計画ドキュメントの「 [Lync Server 2013 での単純な url の計画](lync-server-2013-planning-for-simple-urls.md)」を参照してください。 簡単な Url の書式は、いくつかのオプションから選ぶことができます。 これらのオプションの詳細については、計画ドキュメントの「 [Lync Server 2013 での単純な url の DNS 要件](lync-server-2013-dns-requirements-for-simple-urls.md)」を参照してください。

既定では、単純な Url は次の形式で構成されます (例: ダイヤルイン simple URL) https://dialin.\<SIP 。ドメイン\>

<div>

## <a name="to-configure-simple-urls"></a>単純な Url を構成するには

1.  [トポロジビルダー] で、[ **Lync Server** ] ノードを右クリックし、[**プロパティの編集**] をクリックします。

2.  [**簡易 URL**] ウィンドウで、編集する [**電話アクセスの URL:**] (Dial-in) または [**会議の URL:**] (Meet) のいずれかを選択し、[**URL の編集**] をクリックします。

3.  URL を目的の値に更新し、[**OK**] をクリックして編集した URL を保存します。 次に示す例では、ダイヤルイン URL がにhttps://pool01.contoso.net/dialin変更されました。

4.  必要に応じて、同じ手順を使用して会議 URL を編集します。

</div>

<div>

## <a name="to-define-the-optional-admin-simple-url"></a>オプションの管理用の簡易 URL を定義する

1.  [トポロジビルダー] で、[ **Lync Server** ] ノードを右クリックし、[**プロパティの編集**] をクリックします。

2.  [**管理アクセスの url** ] ボックスに、Lync Server 2013 コントロールパネルへの管理アクセスに使用する単純な url を入力し、[ **OK]** をクリックします。
    
    <div>
    

    > [!TIP]  
    > 管理 URL には、できる限りシンプルな URL を使用することをお勧めします。 最も簡単なオプションは<STRONG> https://adminです。</STRONG>&lt;ドメイン&gt;。

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > 最初の展開後に簡易 URL を変更する場合、簡易 URL のドメイン ネーム システム (DNS) レコードと証明書に影響する変更について注意する必要があります。 変更が単純な URL のベースに影響する場合は、DNS レコードと証明書も変更する必要があります。 たとえば、to https://lync.contoso.com/Meet https://meet.contoso.comから MEET.CONTOSO.COM へのベース URL の変更は、lync.contoso.com を参照するように DNS レコードと証明書を変更する必要があるためです。 Simple URL をからhttps://lync.contoso.com/Meetにhttps://lync.contoso.com/Meetings変更した場合、lync.contoso.com のベース url は変わりません。そのため、DNS や証明書の変更は必要ありません。 ただし、単純な URL 名を変更した場合は必ず、各ダイレクタとフロントエンドサーバーで、 <STRONG>CsComputer</STRONG>コマンドレットを実行して変更を登録する必要があります。

    
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

