---
title: 'Lync Server 2013: 簡単な URL の編集または構成'
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
ms.openlocfilehash: 0fe6ae7197e2f47c590384547c34dd4b1db50950
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739537"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="edit-or-configure-simple-urls-in-lync-server-2013"></a><span data-ttu-id="2bef9-102">Lync Server 2013 での簡単な URL の編集または構成</span><span class="sxs-lookup"><span data-stu-id="2bef9-102">Edit or configure simple URLs in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2bef9-103">_**最終更新日:** 2014-02-04_</span><span class="sxs-lookup"><span data-stu-id="2bef9-103">_**Topic Last Modified:** 2014-02-04_</span></span>

<span data-ttu-id="2bef9-104">この手順では、ローカル管理者または特権ドメイングループのメンバーシップは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="2bef9-104">This procedure does not require membership in a local administrator or privileged domain group.</span></span> <span data-ttu-id="2bef9-105">コンピューターに標準ユーザーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2bef9-105">You should log on to a computer as a standard user.</span></span>

<span data-ttu-id="2bef9-106">Lync Server 2013 では、展開されている場合、フロントエンドサーバーまたはディレクター上のサービスに対して、内部および外部の通話を転送するために、シンプルな Url を使用します。</span><span class="sxs-lookup"><span data-stu-id="2bef9-106">Lync Server 2013 uses simple URLs to direct internal and external calls to services on the Front End Server or on the Director, if one has been deployed.</span></span> <span data-ttu-id="2bef9-107">単純な Url の詳細については、計画ドキュメントの「 [Lync Server 2013 での単純な url の計画](lync-server-2013-planning-for-simple-urls.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2bef9-107">For more information about simple URLs, see [Planning for simple URLs in Lync Server 2013](lync-server-2013-planning-for-simple-urls.md) in the Planning documentation.</span></span> <span data-ttu-id="2bef9-108">簡単な Url の書式は、いくつかのオプションから選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="2bef9-108">You can select the format for your simple URLs from several options.</span></span> <span data-ttu-id="2bef9-109">これらのオプションの詳細については、計画ドキュメントの「 [Lync Server 2013 での単純な url の DNS 要件](lync-server-2013-dns-requirements-for-simple-urls.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2bef9-109">For details about these options, see [DNS requirements for simple URLs in Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) in the Planning documentation.</span></span>

<span data-ttu-id="2bef9-110">既定では、単純な Url は次の形式で構成されます (例: ダイヤルイン simple URL) https://dialin.\<SIP 。ドメイン\></span><span class="sxs-lookup"><span data-stu-id="2bef9-110">By default, simple URLs will be configured in the form of (for example, the dial-in simple URL): https://dialin.\<SIP Domain\></span></span>

<div>

## <a name="to-configure-simple-urls"></a><span data-ttu-id="2bef9-111">単純な Url を構成するには</span><span class="sxs-lookup"><span data-stu-id="2bef9-111">To configure simple URLs</span></span>

1.  <span data-ttu-id="2bef9-112">[トポロジビルダー] で、[ **Lync Server** ] ノードを右クリックし、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2bef9-112">In Topology Builder, right-click the **Lync Server** node, and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="2bef9-113">[**簡易 URL**] ウィンドウで、編集する [**電話アクセスの URL:**] (Dial-in) または [**会議の URL:**] (Meet) のいずれかを選択し、[**URL の編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2bef9-113">In the **Simple URLs** pane, select either **Phone access URLs:** (Dial-in) or **Meeting URLs:** (Meet) to edit, and then click **Edit URL**.</span></span>

3.  <span data-ttu-id="2bef9-114">URL を目的の値に更新し、[**OK**] をクリックして編集した URL を保存します。</span><span class="sxs-lookup"><span data-stu-id="2bef9-114">Update the URL to the value you want, and then click **OK** to save the edited URL.</span></span> <span data-ttu-id="2bef9-115">次に示す例では、ダイヤルイン URL がにhttps://pool01.contoso.net/dialin変更されました。</span><span class="sxs-lookup"><span data-stu-id="2bef9-115">The example shown here has modified the Dial-in URL to https://pool01.contoso.net/dialin.</span></span>

4.  <span data-ttu-id="2bef9-116">必要に応じて、同じ手順を使用して会議 URL を編集します。</span><span class="sxs-lookup"><span data-stu-id="2bef9-116">Edit the Meet URL by using the same steps, if necessary.</span></span>

</div>

<div>

## <a name="to-define-the-optional-admin-simple-url"></a><span data-ttu-id="2bef9-117">オプションの管理用の簡易 URL を定義する</span><span class="sxs-lookup"><span data-stu-id="2bef9-117">To define the optional Admin simple URL</span></span>

1.  <span data-ttu-id="2bef9-118">[トポロジビルダー] で、[ **Lync Server** ] ノードを右クリックし、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2bef9-118">In Topology Builder, right-click the **Lync Server** node, and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="2bef9-119">[**管理アクセスの url** ] ボックスに、Lync Server 2013 コントロールパネルへの管理アクセスに使用する単純な url を入力し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2bef9-119">In the **Administrative access URL** box, enter the simple URL you want for administrative access to Lync Server 2013 Control Panel, and then click **OK**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="2bef9-120">管理 URL には、できる限りシンプルな URL を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2bef9-120">We recommend using the simplest possible URL for the Admin URL.</span></span> <span data-ttu-id="2bef9-121">最も簡単なオプションは<STRONG> https://adminです。</STRONG>&lt;ドメイン&gt;。</span><span class="sxs-lookup"><span data-stu-id="2bef9-121">The simplest option is <STRONG>https://admin.</STRONG>&lt;domain&gt;.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="2bef9-122">最初の展開後に簡易 URL を変更する場合、簡易 URL のドメイン ネーム システム (DNS) レコードと証明書に影響する変更について注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2bef9-122">If you change a simple URL after initial deployment, you must be aware of what changes impact your Domain Name System (DNS) records and certificates for simple URLs.</span></span> <span data-ttu-id="2bef9-123">変更が単純な URL のベースに影響する場合は、DNS レコードと証明書も変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2bef9-123">If the change impacts the base of a simple URL, then you must change the DNS records and certificates as well.</span></span> <span data-ttu-id="2bef9-124">たとえば、to https://lync.contoso.com/Meet https://meet.contoso.comから MEET.CONTOSO.COM へのベース URL の変更は、lync.contoso.com を参照するように DNS レコードと証明書を変更する必要があるためです。</span><span class="sxs-lookup"><span data-stu-id="2bef9-124">For example, changing from https://lync.contoso.com/Meet to https://meet.contoso.com changes the base URL from lync.contoso.com to meet.contoso.com, so you would need to change the DNS records and certificates to refer to meet.contoso.com.</span></span> <span data-ttu-id="2bef9-125">Simple URL をからhttps://lync.contoso.com/Meetにhttps://lync.contoso.com/Meetings変更した場合、lync.contoso.com のベース url は変わりません。そのため、DNS や証明書の変更は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="2bef9-125">If you changed the simple URL from https://lync.contoso.com/Meet to https://lync.contoso.com/Meetings, the base URL of lync.contoso.com stays the same, so no DNS or certificate changes are needed.</span></span> <span data-ttu-id="2bef9-126">ただし、単純な URL 名を変更した場合は必ず、各ダイレクタとフロントエンドサーバーで、 <STRONG>CsComputer</STRONG>コマンドレットを実行して変更を登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2bef9-126">Whenever you change a simple URL name, however, you must run the <STRONG>Enable-CsComputer</STRONG> cmdlet on each Director and Front End Server to register the change.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2bef9-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="2bef9-127">See Also</span></span>


[<span data-ttu-id="2bef9-128">Lync Server 2013 での簡単な URL の計画</span><span class="sxs-lookup"><span data-stu-id="2bef9-128">Planning for simple URLs in Lync Server 2013</span></span>](lync-server-2013-planning-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

