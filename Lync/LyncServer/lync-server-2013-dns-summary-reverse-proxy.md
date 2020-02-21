---
title: 'Lync Server 2013: DNS の概要-リバースプロキシ'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Reverse proxy
ms:assetid: 3073affa-4d92-4453-9974-3a82ca0c6445
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204781(v=OCS.15)
ms:contentKeyID: 48183755
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a5f79437c5253365e4333e7cd064883bba968a54
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213104"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-summary---reverse-proxy-in-lync-server-2013"></a>DNS の概要-Lync Server 2013 のリバースプロキシ

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-03-22_

リバース プロキシでは、2 つのネットワーク アダプターを次のように構成します。

<div>

## <a name="reverse-proxy-network-adapter-requirements"></a>リバース プロキシ ネットワーク アダプターの要件

  - **ネットワーク アダプター 1 (内部インターフェイス)** の例
    
    172.25.33.40 が割り当てられた内部インターフェイス。
    
    デフォルト ゲートウェイは定義されません。
    
    リバースプロキシの内部インターフェイスを含むネットワークから、Lync Server フロントエンドプールサーバー (たとえば、172.25.33.0 から 192.168.10.0) を含む任意のネットワークへのルートが存在することを確認します。

  - **ネットワーク アダプター 2 (外部インターフェイス)** の例
    
    このネットワーク アダプターには、1 つ以上のパブリック IP アドレスが割り当てられます。
    
    ゲートウェイは、境界の外側のルーターまたは統合ファイアウォールを指すように定義されます (シナリオ例では 10.45.16.1)。

### <a name="dns-records-required-for-reverse-proxy"></a>リバース プロキシで必要な DNS レコード

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>場所/種類/ポート</th>
<th>FQDN</th>
<th>IP アドレス</th>
<th>マッピング先/コメント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>外部 DNS/A</p></td>
<td><p>webext.contoso.com</p></td>
<td><p>外部に公開されたリソースに割り当てられたリスナー</p></td>
<td><p>内部展開からの外部 Web サービス。このリバース プロキシを使用し、外部 Web サービスを定義している任意の SIP ドメインの、すべてのプールと単一のサーバーについて、追加のレコードを定義および作成できます。</p></td>
</tr>
<tr class="even">
<td><p>外部 DNS/A</p></td>
<td><p>webdirext.contoso.com</p></td>
<td><p>外部に公開されたリソースに割り当てられたリスナー</p></td>
<td><p>展開内のディレクターまたはディレクタープール用の外部 web サービス。 別の SIP ドメインに関連付けることができる個別のディレクターとして、ディレクターをいくつか定義できます。</p>
<div>

> [!IMPORTANT]  
> ディレクターの DNS レコードを定義して、ディレクターを公開することは、フロントエンドプールまたはディレクターの決定にはなりません。 ディレクターを使用している場合は、ディレクターおよびフロントエンドプールの外部 web サービスの両方を定義して発行する必要があります。 トポロジで定義されている場合は、特定の種類のトラフィック (認証やその他の使用用) が最初にディレクターに送信されます。


</div></td>
</tr>
<tr class="odd">
<td><p>外部 DNS/A</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>外部に公開されたリソースに割り当てられたリスナー</p></td>
<td><p>外部に公開されるダイヤルイン会議</p></td>
</tr>
<tr class="even">
<td><p>外部 DNS/A</p></td>
<td><p>meet.contoso.com</p></td>
<td><p>外部に公開されたリソースに割り当てられたリスナー</p></td>
<td><p>外部に公開される会議</p></td>
</tr>
<tr class="odd">
<td><p>外部 DNS/A</p></td>
<td><p>officewebapps01.contoso.com</p></td>
<td><p>Office Web Apps サーバー用に割り当てられたリスナー</p></td>
<td><p>内部または境界に展開され、外部クライアントアクセス用に公開された Office Web Apps サーバー</p></td>
</tr>
<tr class="even">
<td><p>外部 DNS/A</p></td>
<td><p>lyncdiscover.contoso.com</p></td>
<td><p>外部に公開されたリソースに割り当てられたリスナー</p></td>
<td><p>Lync は外部公開自動検出の外部レコードを検出し、モビリティ、Microsoft Lync Web App、および scheduler Web アプリを含みます。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

