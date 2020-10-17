---
title: 'Lync Server 2013: リバースプロキシ経由のアクセスを確認する'
description: 'Lync Server 2013: リバースプロキシ経由のアクセスを確認します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify access through your reverse proxy
ms:assetid: 3076a786-e022-4d41-91ec-1bf252b2a468
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429697(v=OCS.15)
ms:contentKeyID: 48183753
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 593aac5574f0dcf683351f12a6392f6116480ac5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547123"
---
# <a name="verify-access-through-your-reverse-proxy-in-lync-server-2013"></a>Lync Server 2013 でリバースプロキシ経由のアクセスを確認する

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-03-29_

以下の手順に従って、ユーザーがリバース プロキシ上の情報にアクセスできることを確認します。 正しくアクセスできるようにするには、ファイアウォール構成とドメイン ネーム システム (DNS) 構成を完了する必要がある場合があります。

<div>

## <a name="to-verify-that-you-can-access-the-website-through-the-internet"></a>インターネット経由で Web サイトにアクセスできることを確認するには

  - Web ブラウザーを開き、アドレス帳ファイルや会議用の Web サイトにアクセスする際にクライアントが使用する URL を [**アドレス**] バーに入力します。以下に例を示します。
    
      - アドレス帳サーバーの場合は、次のような URL を入力します。ここで、 **https://externalwebfarmFQDN/abs** externalwebfarmFQDN は、アドレス帳サービスをホストする外部 web サービスの外部 FQDN です。 アドレス帳サーバーフォルダーのディレクトリセキュリティが既定で Windows 認証に構成されているため、ユーザーは HTTP チャレンジを受信する必要があります。
    
      - 会議の場合は、次のような URL を入力します。ここで、 **https://externalwebfarmFQDN/meet** externalwebfarmFQDN は、会議コンテンツをホストする web ファームの外部 FQDN です。 この URL には、会議のトラブルシューティングのページが表示されます。 または、会議用の簡易 URL が正常に動作することを確認します。 会議参加の簡単な URL の例を次に示します。 https://meet.contoso.com
    
      - 配布グループの展開の場合は、次のような URL を入力 **https://externalwebfarmFQDN/GroupExpansion/service.svc** します。 配布グループ拡張サービスのディレクトリセキュリティが既定で Windows 認証に構成されているため、ユーザーは HTTP チャレンジを受信する必要があります。
    
      - ダイヤルインの場合、次のような簡単な URL を入力し **https://externalwebfarmFQDN/dialin** ます。ここで、externalwebfarmFQDN は、ダイヤルイン会議のダイヤルインページをホストする web ファームの外部 FQDN です。 ユーザーはダイヤルインのページに進みます。 または、簡易 URL でのダイヤルインが正常に動作することを確認します。 ダイヤルインの簡単な URL の例は、次のようになります。 https://dialin.contoso.com
    
      - 自動検出 URL が機能していることを確認するには、「」と入力 https://lyncdiscover します。 externaldomainFQDN。 ブラウザーからファイルを開くように求めるメッセージが表示されます。 [メモ帳] を選択して開きます。 通常の応答は次のようになります。
        
            {"AccessLocation":"External","Root":{"Links":[{"href":"https:\/\/extweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/domain","token":"Domain"},
            {"href":"https:\/\/extweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/user","token":"User"},
            {"href":"https:\/\/lyncweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/oauth\/user","token":"OAuth"}]}}

</div>

</div>

<span> </span>

</div>

</div>

</div>

