---
title: 'Lync Server 2013: DNS の概要 - リバース プロキシ'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS summary - Reverse proxy
ms:assetid: 3073affa-4d92-4453-9974-3a82ca0c6445
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204781(v=OCS.15)
ms:contentKeyID: 48183755
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47606fe71b271e01cc7fbefbcf319a2efe93f478
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833348"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---reverse-proxy-in-lync-server-2013"></a>DNS の概要 - Lync Server 2013 でのリバース プロキシ

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-03-22_

リバースプロキシでは、次のように2つのネットワークアダプターを構成します。

<div>

## <a name="reverse-proxy-network-adapter-requirements"></a>リバースプロキシネットワークアダプターの要件

  - **ネットワークアダプター 1 (内部インターフェイス)** の例
    
    172.25.33.40 が割り当てられている内部インターフェイス。
    
    既定のゲートウェイは定義されていません。
    
    Lync Server フロントエンドプールサーバーが含まれているネットワーク (172.25.33.0 から192.168.10.0 など) に、リバースプロキシの内部インターフェイスが含まれているネットワークからのルートがあることを確認します。

  - **ネットワークアダプター 2 (外部インターフェイス)** の例
    
    このネットワークアダプターには、少なくとも1つのパブリック IP アドレスが割り当てられています。
    
    ゲートウェイは、外部境界のルーターまたは統合ファイアウォールを指すように定義されています。 (シナリオの例の 10.45.16.1)

### <a name="dns-records-required-for-reverse-proxy"></a>リバースプロキシに必要な DNS レコード

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
<th>マップ先/コメント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>外部 DNS/A</p></td>
<td><p>webext.contoso.com</p></td>
<td><p>外部公開リソースの割り当て済みのリスナー</p></td>
<td><p>内部展開からの外部 web サービス。 このリバースプロキシを使用し、外部 web サービスが定義されているすべての SIP ドメイン用のすべてのプールおよび単一サーバー用に、追加のレコードを定義して作成することができます。</p></td>
</tr>
<tr class="even">
<td><p>外部 DNS/A</p></td>
<td><p>webdirext.contoso.com</p></td>
<td><p>外部公開リソースの割り当て済みのリスナー</p></td>
<td><p>展開内のディレクターまたはディレクタープール用の外部 web サービス。 複数のダイレクタを定義できます。これらは、他の SIP ドメインと関連付けられる場合があります。</p>
<div>

> [!IMPORTANT]  
> ディレクターの DNS レコードの定義と、フロントエンドプールまたはディレクターの決定にはなりません。 ディレクターを使用している場合は、監督とフロントエンドプールの両方の外部 web サービスを定義して公開する必要があります。 トポロジで定義されている場合、まず、特定のトラフィックの種類 (認証やその他の使用用) がディレクターに送信されます。


</div></td>
</tr>
<tr class="odd">
<td><p>外部 DNS/A</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>外部公開リソースの割り当て済みのリスナー</p></td>
<td><p>外部で公開されたダイヤルイン会議</p></td>
</tr>
<tr class="even">
<td><p>外部 DNS/A</p></td>
<td><p>meet.contoso.com</p></td>
<td><p>外部公開リソースの割り当て済みのリスナー</p></td>
<td><p>外部で公開された会議</p></td>
</tr>
<tr class="odd">
<td><p>外部 DNS/A</p></td>
<td><p>officewebapps01.contoso.com</p></td>
<td><p>Office Web Apps サーバーの割り当て済みのリスナー</p></td>
<td><p>Office Web Apps サーバーが内部または境界内に展開され、外部クライアントアクセス用に公開されている</p></td>
</tr>
<tr class="even">
<td><p>外部 DNS/A</p></td>
<td><p>lyncdiscover.contoso.com</p></td>
<td><p>外部公開リソースの割り当て済みのリスナー</p></td>
<td><p>Lync で外部公開の自動検出の外部レコードが検出されました。モビリティ、Microsoft Lync Web App、scheduler Web アプリが含まれています。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

