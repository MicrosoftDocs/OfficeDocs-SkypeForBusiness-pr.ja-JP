---
title: 'Lync Server 2013: リバースプロキシ経由のアクセスを確認する'
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
ms.openlocfilehash: 8f7d061daedcdfabf4636c78a3a6a8bbe601903a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211803"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-access-through-your-reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="38fbc-102">Lync Server 2013 でリバースプロキシ経由のアクセスを確認する</span><span class="sxs-lookup"><span data-stu-id="38fbc-102">Verify access through your reverse proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="38fbc-103">_**トピックの最終更新日:** 2013-03-29_</span><span class="sxs-lookup"><span data-stu-id="38fbc-103">_**Topic Last Modified:** 2013-03-29_</span></span>

<span data-ttu-id="38fbc-p101">以下の手順に従って、ユーザーがリバース プロキシ上の情報にアクセスできることを確認します。 正しくアクセスできるようにするには、ファイアウォール構成とドメイン ネーム システム (DNS) 構成を完了する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="38fbc-p101">Use the following procedure to verify that your users can access information on the reverse proxy. You might need to complete the firewall configuration and Domain Name System (DNS) configuration before access will work correctly.</span></span>

<div>

## <a name="to-verify-that-you-can-access-the-website-through-the-internet"></a><span data-ttu-id="38fbc-106">インターネット経由で Web サイトにアクセスできることを確認するには</span><span class="sxs-lookup"><span data-stu-id="38fbc-106">To verify that you can access the website through the Internet</span></span>

  - <span data-ttu-id="38fbc-107">Web ブラウザーを開き、アドレス帳ファイルや会議用の Web サイトにアクセスする際にクライアントが使用する URL を [**アドレス**] バーに入力します。以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="38fbc-107">Open a web browser, type the URLs in the **Address** bar that clients use to access the Address Book files and the website for conferencing as follows:</span></span>
    
      - <span data-ttu-id="38fbc-108">アドレス帳サーバーの場合は、次のような URL を**https://externalwebfarmFQDN/abs**入力します。ここで、externalwebfarmFQDN は、アドレス帳サービスをホストする外部 web サービスの外部 FQDN です。</span><span class="sxs-lookup"><span data-stu-id="38fbc-108">For Address Book Server, type a URL similar to the following: **https://externalwebfarmFQDN/abs** where externalwebfarmFQDN is the external FQDN of the external web services that hosts Address Book services.</span></span> <span data-ttu-id="38fbc-109">アドレス帳サーバーフォルダーのディレクトリセキュリティが既定で Windows 認証に構成されているため、ユーザーは HTTP チャレンジを受信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="38fbc-109">The user should receive an HTTP challenge, because directory security on the Address Book Server folder is configured to Windows authentication by default.</span></span>
    
      - <span data-ttu-id="38fbc-110">会議の場合は、次のような URL を**https://externalwebfarmFQDN/meet**入力します。ここで、externalwebfarmFQDN は、会議コンテンツをホストする web ファームの外部 FQDN です。</span><span class="sxs-lookup"><span data-stu-id="38fbc-110">For conferencing, type a URL similar to the following: **https://externalwebfarmFQDN/meet** where externalwebfarmFQDN is the external FQDN of the web farm that hosts meeting content.</span></span> <span data-ttu-id="38fbc-111">この URL には、会議のトラブルシューティングのページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="38fbc-111">This URL should display the troubleshooting page for conferencing.</span></span> <span data-ttu-id="38fbc-112">または、会議用の簡易 URL が正常に動作することを確認します。</span><span class="sxs-lookup"><span data-stu-id="38fbc-112">Alternatively, confirm that your Simple URL for conferencing functions correctly.</span></span> <span data-ttu-id="38fbc-113">会議参加の簡単な URL の例を次に示します。https://meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="38fbc-113">An example Simple URL for the conference join might be https://meet.contoso.com</span></span>
    
      - <span data-ttu-id="38fbc-114">配布グループの展開の場合は、次のような URL **https://externalwebfarmFQDN/GroupExpansion/service.svc**を入力します。</span><span class="sxs-lookup"><span data-stu-id="38fbc-114">For distribution group expansion, type a URL similar to the following: **https://externalwebfarmFQDN/GroupExpansion/service.svc**.</span></span> <span data-ttu-id="38fbc-115">配布グループ拡張サービスのディレクトリセキュリティが既定で Windows 認証に構成されているため、ユーザーは HTTP チャレンジを受信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="38fbc-115">The user should receive an HTTP challenge, because directory security on the distribution group expansion service is configured to Windows authentication by default.</span></span>
    
      - <span data-ttu-id="38fbc-116">ダイヤルインの場合、次**https://externalwebfarmFQDN/dialin**のような簡単な URL を入力します。ここで、externalwebfarmFQDN は、ダイヤルイン会議のダイヤルインページをホストする web ファームの外部 FQDN です。</span><span class="sxs-lookup"><span data-stu-id="38fbc-116">For dial-in, type the simple URL similar to the following **https://externalwebfarmFQDN/dialin** where externalwebfarmFQDN is the external FQDN of the web farm that hosts the dial-in page for dial-in conferencing.</span></span> <span data-ttu-id="38fbc-117">ユーザーはダイヤルインのページに進みます。</span><span class="sxs-lookup"><span data-stu-id="38fbc-117">The user should be directed to the dial-in page.</span></span> <span data-ttu-id="38fbc-118">または、簡易 URL でのダイヤルインが正常に動作することを確認します。</span><span class="sxs-lookup"><span data-stu-id="38fbc-118">Alternatively, confirm that your Simple URL dial-in functions correctly.</span></span> <span data-ttu-id="38fbc-119">ダイヤルインの簡単な URL の例は、次のようになります。https://dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="38fbc-119">An example Simple URL for dial-in might be https://dialin.contoso.com</span></span>
    
      - <span data-ttu-id="38fbc-120">自動検出 URL が機能していることをhttps://lyncdiscover確認するには、「」と入力します。</span><span class="sxs-lookup"><span data-stu-id="38fbc-120">To confirm that the autodiscover URL is working, type https://lyncdiscover.</span></span> <span data-ttu-id="38fbc-121">externaldomainFQDN。</span><span class="sxs-lookup"><span data-stu-id="38fbc-121">externaldomainFQDN.</span></span> <span data-ttu-id="38fbc-122">ブラウザーからファイルを開くように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="38fbc-122">The browser should prompt you to open a file.</span></span> <span data-ttu-id="38fbc-123">[メモ帳] を選択して開きます。</span><span class="sxs-lookup"><span data-stu-id="38fbc-123">Select Notepad to open it.</span></span> <span data-ttu-id="38fbc-124">通常の応答は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="38fbc-124">A typical response would be similar to:</span></span>
        
            {"AccessLocation":"External","Root":{"Links":[{"href":"https:\/\/extweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/domain","token":"Domain"},
            {"href":"https:\/\/extweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/user","token":"User"},
            {"href":"https:\/\/lyncweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/oauth\/user","token":"OAuth"}]}}

</div>

</div>

<span> </span>

</div>

</div>

</div>

