---
title: 'Lync Server 2013: 簡単な Url の編集または構成'
description: 'Lync Server 2013: 簡単な Url の編集または構成を行います。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Edit or configure simple URLs
ms:assetid: 0008aeea-4ae9-4e36-83cd-ef7ff7b6e128
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398063(v=OCS.15)
ms:contentKeyID: 48183216
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f9152a65083f71510f4cdb1189b3982afdd68b4c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551633"
---
# <a name="edit-or-configure-simple-urls-in-lync-server-2013"></a>Lync Server 2013 での簡易 Url の編集または構成

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-02-04_

この手順では、ローカル管理者または特権が割り当てられたドメイン グループのメンバーシップは必要ありません。標準ユーザーとしてコンピューターにログオンする必要があります。

Lync Server 2013 は、シンプルな Url を使用して、フロントエンドサーバーまたはディレクター (展開されている場合) のサービスへの内部および外部呼び出しを送信します。 簡易 Url の詳細については、「計画」のドキュメントの「 [planning for Simple urls In Lync Server 2013](lync-server-2013-planning-for-simple-urls.md) 」を参照してください。 簡単な Url の形式は、いくつかのオプションから選択できます。 これらのオプションの詳細については、「計画」のドキュメントの「 [Lync Server 2013 の簡易 url の DNS 要件](lync-server-2013-dns-requirements-for-simple-urls.md) 」を参照してください。

既定では、簡易 Url はの形式 (たとえば、ダイヤルインの簡易 URL) で構成され https://dialin ます。\<SIP Domain\>

<div>

## <a name="to-configure-simple-urls"></a>簡易 URL を構成するには

1.  トポロジビルダーで、[ **Lync Server** ] ノードを右クリックし、[ **プロパティの編集**] をクリックします。

2.  [ **簡易 url** ] ウィンドウで、[ **電話アクセスの url:** (ダイヤルイン)] または [ **ミーティングの Url:** (会議の url)] を選択して編集し、[ **URL の編集**] をクリックします。

3.  URL を目的の値に更新し、[**OK**] をクリックして編集した URL を保存します。 ここに示す例では、にダイヤルイン URL を変更しました https://pool01.contoso.net/dialin 。

4.  必要に応じて、同じ手順を使用して Meet URL を編集します。

</div>

<div>

## <a name="to-define-the-optional-admin-simple-url"></a>オプションの管理用の簡易 URL を定義するには

1.  トポロジビルダーで、[ **Lync Server** ] ノードを右クリックし、[ **プロパティの編集**] をクリックします。

2.  [ **管理アクセスの url** ] ボックスに、Lync Server 2013 コントロールパネルへの管理アクセスに使用する簡易 URL を入力し、[ **OK**] をクリックします。
    
    <div>
    

    > [!TIP]  
    > 管理 URL にできるだけ簡易 URL を使用することをお勧めします。 最も簡単なオプションは、 <STRONG> https://admin です。</STRONG> &lt;ドメイン &gt; 。

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > 最初の展開後に簡易 URL を変更する場合、簡易 URL のドメイン ネーム システム (DNS) レコードと証明書に影響する変更について注意する必要があります。 変更が簡易 URL の基本部分に影響する場合は、DNS レコードと証明書も変更する必要があります。 たとえば、からに変更すると https://lync.contoso.com/Meet https://meet.contoso.com ベース URL が lync.contoso.com から meet.contoso.com に変更されるため、meet.contoso.com を参照するように DNS レコードと証明書を変更する必要があります。 からに簡単な URL を変更した場合、 https://lync.contoso.com/Meet https://lync.contoso.com/Meetings lync.contoso.com のベース url は同じままになるため、DNS や証明書の変更は必要ありません。 ただし、簡単な URL 名を変更する場合は必ず、各ディレクターおよびフロントエンドサーバーで、 <STRONG>CsComputer</STRONG> コマンドレットを実行して変更を登録する必要があります。

    
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

