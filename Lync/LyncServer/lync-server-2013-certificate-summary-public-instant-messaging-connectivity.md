---
title: 'Lync Server 2013: 証明書の概要-パブリックインスタントメッセージングの接続'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate summary - Public instant messaging connectivity
ms:assetid: 2b3687ee-50c2-4c1c-880e-8dcf8bd4f309
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618370(v=OCS.15)
ms:contentKeyID: 49105657
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31988207403ef1ccb5ea366da6e1ec6b3d448b4e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840639"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---public-instant-messaging-connectivity-in-lync-server-2013"></a>証明書の概要-Lync Server 2013 でのパブリックインスタントメッセージング接続

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-19_

パブリックインスタントメッセージング接続用の証明書を構成するには、まず、America Online (AOL) には固有のものが必要であることを除き、他の SIP フェデレーションタイプまたは標準エッジサーバーの証明書には何も違いがないことに注意してください。証明書の構成。 America Online では、通常のサーバー拡張キー使用法 (EKU) に加えて、証明書または証明書 (Edge プールの場合) がクライアント EKU も含まれている必要があります。 クライアント EKU は証明書に追加されたものであり、エッジサーバーに割り当てられている外部公開証明書の一部です。

<div>

## <a name="certificate-summary--public-instant-messaging-connectivity"></a>証明書の概要–パブリックインスタントメッセージング接続


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>コンポーネント</th>
<th>サブジェクト名</th>
<th>サブジェクト代替名 (SAN)/Order</th>
<th>コメント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>外部/アクセスエッジ</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>sip.contoso.com</p>
<p>webcon.contoso.com</p>
<p>sip.fabrikam.com</p></td>
<td><p>証明書はパブリック CA からである必要があります。また、AOL とのパブリック IM 接続を展開する場合は、サーバーの EKU とクライアントの EKU を持っている必要があります。 証明書は、次のための外部エッジサーバーインターフェイスに割り当てられます。</p>
<ul>
<li><p>アクセス エッジ サービス</p></li>
<li><p>Web 会議エッジ サービス</p></li>
<li><p>音声ビデオ エッジ サービス</p></li>
</ul>
<p>San は、トポロジビルダーの定義に基づいて、自動的に証明書に追加されることに注意してください。 必要に応じて、必要に応じて SAN エントリを追加します。これには、サポートが必要な追加の SIP ドメインや他のエントリも含まれます。 サブジェクト名は SAN でレプリケートされ、正しい操作のために存在している必要があります。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 の外部ユーザー アクセスのシナリオ](lync-server-2013-scenarios-for-external-user-access.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

