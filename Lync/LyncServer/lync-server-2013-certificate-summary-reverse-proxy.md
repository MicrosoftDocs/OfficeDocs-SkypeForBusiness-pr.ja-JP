---
title: 'Lync Server 2013: 証明書の概要-リバースプロキシ'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Reverse proxy
ms:assetid: f2b9a53f-aead-413d-81e9-4a294a010fbb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205381(v=OCS.15)
ms:contentKeyID: 48185820
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e5691b20031d9998877a64f34f6578b654494a99
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151167"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-summary---reverse-proxy-in-lync-server-2013"></a>証明書の概要-Lync Server 2013 のリバースプロキシ

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-11-14_

リバースプロキシの証明書要件は、エッジサーバーよりもはるかに簡単です。 提供されているフローチャートは必要な要件を示します。 付属の表では、エッジサーバーのディスカッションで確認されたシナリオに関して、一般的な証明書のサブジェクト名とサブジェクトの別名を示しています。 エッジサーバーのシナリオの詳細については、「 [Lync server 2013 の外部ユーザーアクセスのシナリオ](lync-server-2013-scenarios-for-external-user-access.md)」を参照してください。

**リバース プロキシの証明書のフロー チャート**

![エッジ サーバーの証明書のフロー チャート](images/JJ205381.026045d7-1b4b-4651-b32f-2d43a7161198(OCS.15).jpg "エッジ サーバーの証明書のフロー チャート")

### <a name="reverse-proxy-external-interface"></a>リバース プロキシ: 外部インターフェイス

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
<th>サブジェクトの別名 (SAN)/順序</th>
<th>コメント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>リバース プロキシ</p></td>
<td><p>webext.contoso.com</p></td>
<td><p>webext.contoso.com</p>
<p>webdirext.contoso.com</p>
<p>dialin.contoso.com</p>
<p>meet.contoso.com</p>
<p>officewebapps01.contoso.com</p>
<p>lyncdiscover.contoso.com</p>
<p>(省略可能):* contoso.com</p></td>
<td><p>証明書は公的 CA によって発行され、サーバー EKU を含んでいる必要があります。 サービスには、アドレス帳サービス、会議用の Office Web Apps、および Lync IP デバイス公開ルールが含まれます。 サブジェクトの別名には、次のものがあります。</p>
<ul>
<li><p>フロントエンドサーバーまたはフロントエンドプールの外部 Web サービス FQDN</p></li>
<li><p>ディレクターまたはディレクタープール用の外部 Web サービス FQDN</p></li>
<li><p>ダイヤルイン会議</p></li>
<li><p>オンライン会議の公開ルール</p></li>
<li><p>会議用の Office Web Apps</p></li>
<li><p>Lyncdiscover (自動検出)</p></li>
</ul>
<p>オプションのワイルドカードは meet と dialin SAN の両方を置き換えます</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

