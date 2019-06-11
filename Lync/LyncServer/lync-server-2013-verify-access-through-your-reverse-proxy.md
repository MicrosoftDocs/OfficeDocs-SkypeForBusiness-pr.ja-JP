---
title: 'Lync Server 2013: リバース プロキシ経由のアクセスを確認する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Verify access through your reverse proxy
ms:assetid: 3076a786-e022-4d41-91ec-1bf252b2a468
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429697(v=OCS.15)
ms:contentKeyID: 48183753
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e35e3908f66952b0e631484efa590bcd76fc0456
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848248"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-access-through-your-reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="5415f-102">Lync Server 2013 でリバース プロキシ経由のアクセスを確認する</span><span class="sxs-lookup"><span data-stu-id="5415f-102">Verify access through your reverse proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5415f-103">_**最終更新日:** 2013-03-29_</span><span class="sxs-lookup"><span data-stu-id="5415f-103">_**Topic Last Modified:** 2013-03-29_</span></span>

<span data-ttu-id="5415f-104">リバースプロキシ上の情報にユーザーがアクセスできることを確認するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="5415f-104">Use the following procedure to verify that your users can access information on the reverse proxy.</span></span> <span data-ttu-id="5415f-105">Access が正常に動作するためには、ファイアウォールの構成とドメインネームシステム (DNS) の構成を完了する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="5415f-105">You might need to complete the firewall configuration and Domain Name System (DNS) configuration before access will work correctly.</span></span>

<div>

## <a name="to-verify-that-you-can-access-the-website-through-the-internet"></a><span data-ttu-id="5415f-106">インターネット経由で web サイトにアクセスできることを確認するには</span><span class="sxs-lookup"><span data-stu-id="5415f-106">To verify that you can access the website through the Internet</span></span>

  - <span data-ttu-id="5415f-107">Web ブラウザーを開き、クライアントがアドレス帳ファイルと会議の web サイトにアクセスするために使用する**アドレス**バーに、次のように url を入力します。</span><span class="sxs-lookup"><span data-stu-id="5415f-107">Open a web browser, type the URLs in the **Address** bar that clients use to access the Address Book files and the website for conferencing as follows:</span></span>
    
      - <span data-ttu-id="5415f-108">アドレス帳サーバーの場合、次のような URL を入力**https://externalwebfarmFQDN/abs**します。ここで、externalwebfarmFQDN は、アドレス帳サービスをホストする外部 web サービスの外部 FQDN です。</span><span class="sxs-lookup"><span data-stu-id="5415f-108">For Address Book Server, type a URL similar to the following: **https://externalwebfarmFQDN/abs** where externalwebfarmFQDN is the external FQDN of the external web services that hosts Address Book services.</span></span> <span data-ttu-id="5415f-109">アドレス帳サーバーフォルダーのディレクトリセキュリティが既定で Windows 認証に構成されているため、ユーザーは HTTP チャレンジを受け取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="5415f-109">The user should receive an HTTP challenge, because directory security on the Address Book Server folder is configured to Windows authentication by default.</span></span>
    
      - <span data-ttu-id="5415f-110">[会議] には、次のような URL **https://externalwebfarmFQDN/meet**を入力します。ここで、externalwebfarmFQDN は会議コンテンツをホストする web ファームの外部 FQDN です。</span><span class="sxs-lookup"><span data-stu-id="5415f-110">For conferencing, type a URL similar to the following: **https://externalwebfarmFQDN/meet** where externalwebfarmFQDN is the external FQDN of the web farm that hosts meeting content.</span></span> <span data-ttu-id="5415f-111">この URL には、会議のトラブルシューティングページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5415f-111">This URL should display the troubleshooting page for conferencing.</span></span> <span data-ttu-id="5415f-112">または、会議の簡単な URL が正しく機能することを確認します。</span><span class="sxs-lookup"><span data-stu-id="5415f-112">Alternatively, confirm that your Simple URL for conferencing functions correctly.</span></span> <span data-ttu-id="5415f-113">会議参加の単純な URL の例を次に示します。https://meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5415f-113">An example Simple URL for the conference join might be https://meet.contoso.com</span></span>
    
      - <span data-ttu-id="5415f-114">配布グループの展開については、次のような**https://externalwebfarmFQDN/GroupExpansion/service.svc**URL を入力してください。</span><span class="sxs-lookup"><span data-stu-id="5415f-114">For distribution group expansion, type a URL similar to the following: **https://externalwebfarmFQDN/GroupExpansion/service.svc**.</span></span> <span data-ttu-id="5415f-115">配布グループ展開サービスのディレクトリセキュリティが既定で Windows 認証に構成されているため、ユーザーは HTTP チャレンジを受け取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="5415f-115">The user should receive an HTTP challenge, because directory security on the distribution group expansion service is configured to Windows authentication by default.</span></span>
    
      - <span data-ttu-id="5415f-116">[ダイヤルイン] には、次**https://externalwebfarmFQDN/dialin**のような単純な URL を入力します。ここで、externalwebfarmFQDN は、ダイヤルイン会議のダイヤルインページをホストする web ファームの外部 FQDN です。</span><span class="sxs-lookup"><span data-stu-id="5415f-116">For dial-in, type the simple URL similar to the following **https://externalwebfarmFQDN/dialin** where externalwebfarmFQDN is the external FQDN of the web farm that hosts the dial-in page for dial-in conferencing.</span></span> <span data-ttu-id="5415f-117">ユーザーは、ダイヤルインページに転送される必要があります。</span><span class="sxs-lookup"><span data-stu-id="5415f-117">The user should be directed to the dial-in page.</span></span> <span data-ttu-id="5415f-118">または、Simple URL のダイヤルイン機能が正しく動作することを確認します。</span><span class="sxs-lookup"><span data-stu-id="5415f-118">Alternatively, confirm that your Simple URL dial-in functions correctly.</span></span> <span data-ttu-id="5415f-119">ダイヤルインの単純な URL の例を次に示します。https://dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5415f-119">An example Simple URL for dial-in might be https://dialin.contoso.com</span></span>
    
      - <span data-ttu-id="5415f-120">自動検出 URL が機能していることをhttps://lyncdiscover確認するには、「」と入力します。</span><span class="sxs-lookup"><span data-stu-id="5415f-120">To confirm that the autodiscover URL is working, type https://lyncdiscover.</span></span> <span data-ttu-id="5415f-121">Externaldomaqdn。</span><span class="sxs-lookup"><span data-stu-id="5415f-121">externaldomainFQDN.</span></span> <span data-ttu-id="5415f-122">ブラウザーでファイルを開くように求められます。</span><span class="sxs-lookup"><span data-stu-id="5415f-122">The browser should prompt you to open a file.</span></span> <span data-ttu-id="5415f-123">[メモ帳] を選択して開きます。</span><span class="sxs-lookup"><span data-stu-id="5415f-123">Select Notepad to open it.</span></span> <span data-ttu-id="5415f-124">一般的な応答は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="5415f-124">A typical response would be similar to:</span></span>
        
            {"AccessLocation":"External","Root":{"Links":[{"href":"https:\/\/extweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/domain","token":"Domain"},
            {"href":"https:\/\/extweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/user","token":"User"},
            {"href":"https:\/\/lyncweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/oauth\/user","token":"OAuth"}]}}

</div>

</div>

<span> </span>

</div>

</div>

</div>

