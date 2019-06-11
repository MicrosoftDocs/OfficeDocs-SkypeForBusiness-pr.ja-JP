---
title: 'Lync Server 2013: 証明書の概要 - リバース プロキシ'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate summary - Reverse proxy
ms:assetid: f2b9a53f-aead-413d-81e9-4a294a010fbb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205381(v=OCS.15)
ms:contentKeyID: 48185820
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b9a10259ac4a0beb6d79897b26bf446b109801a8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840642"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---reverse-proxy-in-lync-server-2013"></a>証明書の概要 - Lync Server 2013 リバース プロキシ

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-11-14_

リバースプロキシの証明書の要件は、エッジサーバーよりもずっと簡単です。 提供されたフローチャートは、必要な要件を示します。 この表に示すのは、microsoft が Edge Server のディスカッションでレビューしたシナリオに関連する、一般的な証明書のサブジェクト名とサブジェクトの別名を示しています。 エッジサーバーのシナリオについて詳しくは、「 [Lync server 2013 での外部ユーザーアクセスのシナリオ](lync-server-2013-scenarios-for-external-user-access.md)」をご覧ください。

**リバースプロキシ用の証明書フローチャート**

![エッジサーバーの証明書フローチャート](images/JJ205381.026045d7-1b4b-4651-b32f-2d43a7161198(OCS.15).jpg "エッジサーバーの証明書フローチャート")

### <a name="reverse-proxy-external-interface"></a>リバースプロキシ: 外部インターフェイス

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
<th>サブジェクト代替名 (SAN) の/Order</th>
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
<td><p>証明書は、公開 CA とサーバー EKU によって発行される必要があります。 サービスには、アドレス帳サービス、配布グループ展開会議用 Office Web Apps、Lync IP デバイス発行ルールが含まれます。 サブジェクトの代替名には以下が含まれます。</p>
<ul>
<li><p>フロントエンドサーバーまたはフロントエンドプール用の外部 Web サービス FQDN</p></li>
<li><p>ディレクターまたはディレクタープール用の外部 Web サービス FQDN</p></li>
<li><p>ダイヤルイン会議</p></li>
<li><p>オンライン会議の公開ルール</p></li>
<li><p>会議用の Office Web Apps</p></li>
<li><p>Lyncdiscover (自動検出)</p></li>
</ul>
<p>会議の開始とダイヤルインの両方のオプションワイルドカード</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

