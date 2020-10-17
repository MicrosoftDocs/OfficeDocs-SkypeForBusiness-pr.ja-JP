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
# <a name="verify-access-through-your-reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="6d8d2-103">Lync Server 2013 でリバースプロキシ経由のアクセスを確認する</span><span class="sxs-lookup"><span data-stu-id="6d8d2-103">Verify access through your reverse proxy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6d8d2-104">_**トピックの最終更新日:** 2013-03-29_</span><span class="sxs-lookup"><span data-stu-id="6d8d2-104">_**Topic Last Modified:** 2013-03-29_</span></span>

<span data-ttu-id="6d8d2-p101">以下の手順に従って、ユーザーがリバース プロキシ上の情報にアクセスできることを確認します。 正しくアクセスできるようにするには、ファイアウォール構成とドメイン ネーム システム (DNS) 構成を完了する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="6d8d2-p101">Use the following procedure to verify that your users can access information on the reverse proxy. You might need to complete the firewall configuration and Domain Name System (DNS) configuration before access will work correctly.</span></span>

<div>

## <a name="to-verify-that-you-can-access-the-website-through-the-internet"></a><span data-ttu-id="6d8d2-107">インターネット経由で Web サイトにアクセスできることを確認するには</span><span class="sxs-lookup"><span data-stu-id="6d8d2-107">To verify that you can access the website through the Internet</span></span>

  - <span data-ttu-id="6d8d2-108">Web ブラウザーを開き、アドレス帳ファイルや会議用の Web サイトにアクセスする際にクライアントが使用する URL を [**アドレス**] バーに入力します。以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="6d8d2-108">Open a web browser, type the URLs in the **Address** bar that clients use to access the Address Book files and the website for conferencing as follows:</span></span>
    
      - <span data-ttu-id="6d8d2-109">アドレス帳サーバーの場合は、次のような URL を入力します。ここで、 **https://externalwebfarmFQDN/abs** externalwebfarmFQDN は、アドレス帳サービスをホストする外部 web サービスの外部 FQDN です。</span><span class="sxs-lookup"><span data-stu-id="6d8d2-109">For Address Book Server, type a URL similar to the following: **https://externalwebfarmFQDN/abs** where externalwebfarmFQDN is the external FQDN of the external web services that hosts Address Book services.</span></span> <span data-ttu-id="6d8d2-110">アドレス帳サーバーフォルダーのディレクトリセキュリティが既定で Windows 認証に構成されているため、ユーザーは HTTP チャレンジを受信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d8d2-110">The user should receive an HTTP challenge, because directory security on the Address Book Server folder is configured to Windows authentication by default.</span></span>
    
      - <span data-ttu-id="6d8d2-111">会議の場合は、次のような URL を入力します。ここで、 **https://externalwebfarmFQDN/meet** externalwebfarmFQDN は、会議コンテンツをホストする web ファームの外部 FQDN です。</span><span class="sxs-lookup"><span data-stu-id="6d8d2-111">For conferencing, type a URL similar to the following: **https://externalwebfarmFQDN/meet** where externalwebfarmFQDN is the external FQDN of the web farm that hosts meeting content.</span></span> <span data-ttu-id="6d8d2-112">この URL には、会議のトラブルシューティングのページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6d8d2-112">This URL should display the troubleshooting page for conferencing.</span></span> <span data-ttu-id="6d8d2-113">または、会議用の簡易 URL が正常に動作することを確認します。</span><span class="sxs-lookup"><span data-stu-id="6d8d2-113">Alternatively, confirm that your Simple URL for conferencing functions correctly.</span></span> <span data-ttu-id="6d8d2-114">会議参加の簡単な URL の例を次に示します。 https://meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="6d8d2-114">An example Simple URL for the conference join might be https://meet.contoso.com</span></span>
    
      - <span data-ttu-id="6d8d2-115">配布グループの展開の場合は、次のような URL を入力 **https://externalwebfarmFQDN/GroupExpansion/service.svc** します。</span><span class="sxs-lookup"><span data-stu-id="6d8d2-115">For distribution group expansion, type a URL similar to the following: **https://externalwebfarmFQDN/GroupExpansion/service.svc**.</span></span> <span data-ttu-id="6d8d2-116">配布グループ拡張サービスのディレクトリセキュリティが既定で Windows 認証に構成されているため、ユーザーは HTTP チャレンジを受信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d8d2-116">The user should receive an HTTP challenge, because directory security on the distribution group expansion service is configured to Windows authentication by default.</span></span>
    
      - <span data-ttu-id="6d8d2-117">ダイヤルインの場合、次のような簡単な URL を入力し **https://externalwebfarmFQDN/dialin** ます。ここで、externalwebfarmFQDN は、ダイヤルイン会議のダイヤルインページをホストする web ファームの外部 FQDN です。</span><span class="sxs-lookup"><span data-stu-id="6d8d2-117">For dial-in, type the simple URL similar to the following **https://externalwebfarmFQDN/dialin** where externalwebfarmFQDN is the external FQDN of the web farm that hosts the dial-in page for dial-in conferencing.</span></span> <span data-ttu-id="6d8d2-118">ユーザーはダイヤルインのページに進みます。</span><span class="sxs-lookup"><span data-stu-id="6d8d2-118">The user should be directed to the dial-in page.</span></span> <span data-ttu-id="6d8d2-119">または、簡易 URL でのダイヤルインが正常に動作することを確認します。</span><span class="sxs-lookup"><span data-stu-id="6d8d2-119">Alternatively, confirm that your Simple URL dial-in functions correctly.</span></span> <span data-ttu-id="6d8d2-120">ダイヤルインの簡単な URL の例は、次のようになります。 https://dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="6d8d2-120">An example Simple URL for dial-in might be https://dialin.contoso.com</span></span>
    
      - <span data-ttu-id="6d8d2-121">自動検出 URL が機能していることを確認するには、「」と入力 https://lyncdiscover します。</span><span class="sxs-lookup"><span data-stu-id="6d8d2-121">To confirm that the autodiscover URL is working, type https://lyncdiscover.</span></span> <span data-ttu-id="6d8d2-122">externaldomainFQDN。</span><span class="sxs-lookup"><span data-stu-id="6d8d2-122">externaldomainFQDN.</span></span> <span data-ttu-id="6d8d2-123">ブラウザーからファイルを開くように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6d8d2-123">The browser should prompt you to open a file.</span></span> <span data-ttu-id="6d8d2-124">[メモ帳] を選択して開きます。</span><span class="sxs-lookup"><span data-stu-id="6d8d2-124">Select Notepad to open it.</span></span> <span data-ttu-id="6d8d2-125">通常の応答は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="6d8d2-125">A typical response would be similar to:</span></span>
        
            {"AccessLocation":"External","Root":{"Links":[{"href":"https:\/\/extweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/domain","token":"Domain"},
            {"href":"https:\/\/extweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/user","token":"User"},
            {"href":"https:\/\/lyncweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/oauth\/user","token":"OAuth"}]}}

</div>

</div>

<span> </span>

</div>

</div>

</div>

