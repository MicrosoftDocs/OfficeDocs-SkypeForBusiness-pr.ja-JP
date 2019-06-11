---
title: 'Lync Server 2013: 会議の出席依頼を設定する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring the meeting invitation
ms:assetid: 7faa4797-0344-418b-9fa3-59dfb9c2baf7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398638(v=OCS.15)
ms:contentKeyID: 48184641
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 014a42597e3df416d9e502eaaa90e2f1e71e35ec
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840177"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-meeting-invitation-in-lync-server-2013"></a><span data-ttu-id="83a7a-102">Lync Server 2013 で会議出席依頼を設定する</span><span class="sxs-lookup"><span data-stu-id="83a7a-102">Configuring the meeting invitation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="83a7a-103">_**最終更新日:** 2013-07-16_</span><span class="sxs-lookup"><span data-stu-id="83a7a-103">_**Topic Last Modified:** 2013-07-16_</span></span>

<span data-ttu-id="83a7a-104">Lync 2013 用のオンライン会議アドインで送信された会議出席依頼をカスタマイズするには、会議出席依頼の本文に次のオプションの項目を含めます。</span><span class="sxs-lookup"><span data-stu-id="83a7a-104">You can customize meeting invitations sent by the Online Meeting Add-in for Lync 2013 by including the following optional items in the body of the meeting invitation:</span></span>

  - <span data-ttu-id="83a7a-105">**組織のロゴ**[ロゴの URL] オプションを使用して、組織のロゴを会議出席依頼に追加します。</span><span class="sxs-lookup"><span data-stu-id="83a7a-105">**Your organization’s logo** Add your organization’s logo to meeting invitations by using the Logo URL option.</span></span> <span data-ttu-id="83a7a-106">会議の出席依頼が組織外のユーザーに送信される場合、画像は公開されている URL である必要があります。</span><span class="sxs-lookup"><span data-stu-id="83a7a-106">If meeting invitations will be sent to people external to your organization, the image should be located at a publicly available URL.</span></span> <span data-ttu-id="83a7a-107">サポートされている画像形式は、GIF と JPG です。</span><span class="sxs-lookup"><span data-stu-id="83a7a-107">The supported image formats are GIF and JPG.</span></span> <span data-ttu-id="83a7a-108">Lync Server 2013 には、画像のサイズ制限のない URL が保存されていますが、最適な結果を得るには、画像の最大サイズは、高さ30ピクセル、幅188ピクセルです。</span><span class="sxs-lookup"><span data-stu-id="83a7a-108">Although Lync Server 2013 stores the URL with no size restrictions on the image, for best results, the maximum size of the image should be 30 pixels high by 188 pixels wide.</span></span>

  - <span data-ttu-id="83a7a-109">**カスタムヘルプまたはサポートリンク**組織のヘルプまたはサポートチームの web サイトの URL を追加します。</span><span class="sxs-lookup"><span data-stu-id="83a7a-109">**A Custom Help or Support Link** Add a URL for your organization’s help or support team website.</span></span> <span data-ttu-id="83a7a-110">会議の出席依頼が組織外のユーザーに送信される場合、URL は公開されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="83a7a-110">If meeting invitations will be sent to people external to your organization, the URL should be publicly available.</span></span> <span data-ttu-id="83a7a-111">URL の最大長は 1 KB です。</span><span class="sxs-lookup"><span data-stu-id="83a7a-111">The maximum URL length is 1 KB.</span></span>

  - <span data-ttu-id="83a7a-112">**法的免責事項のテキスト**すべての会議出席依頼に表示される法的テキストまたは免責事項の URL を追加します。</span><span class="sxs-lookup"><span data-stu-id="83a7a-112">**Legal disclaimer text** Add a URL for legal text or a disclaimer that will be displayed in all meeting invitations.</span></span> <span data-ttu-id="83a7a-113">会議の出席依頼が組織外のユーザーに送信される場合、URL は公開されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="83a7a-113">If meeting invitations will be sent to people external to your organization, the URL should be publicly available.</span></span> <span data-ttu-id="83a7a-114">URL の最大長は 1 KB です。</span><span class="sxs-lookup"><span data-stu-id="83a7a-114">The maximum URL length is 1 KB.</span></span>

  - <span data-ttu-id="83a7a-115">**ユーザー設定のフッターテキスト**招待状にカスタムフッターとして表示されるテキストを追加します。</span><span class="sxs-lookup"><span data-stu-id="83a7a-115">**Custom footer text** Add text that will be rendered as a custom footer in the invitation.</span></span> <span data-ttu-id="83a7a-116">追加できるテキストの最大文字数は 2 KB です。</span><span class="sxs-lookup"><span data-stu-id="83a7a-116">The maximum length of text that can be added is 2 KB.</span></span>

<span data-ttu-id="83a7a-117">Lync Server コントロールパネルまたは Lync Server 管理シェルを使用して、これらのオプションを構成できます。</span><span class="sxs-lookup"><span data-stu-id="83a7a-117">You can configure these options by using either Lync Server Control Panel or Lync Server Management Shell.</span></span>

<div>


<span data-ttu-id="83a7a-118">**Lync Server コントロールパネルを使用して会議出席依頼をカスタマイズするには**</span><span class="sxs-lookup"><span data-stu-id="83a7a-118">**To Customize the Meeting Invitation by using Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="83a7a-119">RTCUniversalServerAdmins グループのメンバーであるか (または同等のユーザー権限を持っている)、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザーアカウントで、Lync Server 2013 を展開したネットワーク上のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="83a7a-119">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="83a7a-120">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="83a7a-120">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="83a7a-121">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="83a7a-121">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="83a7a-122">左側のナビゲーションバーで、[**会議**] をクリックし、[**会議の設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="83a7a-122">In the left navigation bar, click **Conferencing** and then click **Meeting Configuration**.</span></span>

4.  <span data-ttu-id="83a7a-123">[**会議の構成**] ページで、[**新規作成**] をクリックし、次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="83a7a-123">On the **Meeting Configuration** page, click **New**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="83a7a-p106">サイト レベルのポリシーを作成するには、[**サイト構成**] をクリックします。[**サイトの選択**] 検索フィールドに、会議参加設定を定義するサイトの名前の全体または一部を入力します。サイトの結果一覧で対象のサイトをクリックして、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="83a7a-p106">To create a site-level policy, click **Site configuration**. In the **Select a Site** search field, type all or part of the name of the site for which you want to define meeting join settings. In the resulting list of sites, click the site you want, and then click **OK**.</span></span>
    
      - <span data-ttu-id="83a7a-p107">プール レベルのポリシーを作成するには、[**プール構成**] をクリックします。[**サービスの選択**] 検索フィールドに、会議参加設定を定義するプール サービスの名前の全体または一部を入力します。サービスの結果一覧で、対象のプールをクリックして [**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="83a7a-p107">To create a pool-level policy, click **Pool configuration**. In the **Select a Service** search field, type all or part of the name of the pool service for which you want to define meeting join settings. In the resulting list of services, click the pool you want, and then click **OK**.</span></span>

5.  <span data-ttu-id="83a7a-130">次のいずれかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="83a7a-130">Do any of the following:</span></span>
    
      - <span data-ttu-id="83a7a-131">[**ロゴの url** ] フィールドに、組織のロゴ画像の URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="83a7a-131">In the **Logo URL** field, type the URL for your organization’s logo image.</span></span>
    
      - <span data-ttu-id="83a7a-132">[**ヘルプ URL** ] フィールドに、組織のヘルプまたはサポートサイトの url を入力します。</span><span class="sxs-lookup"><span data-stu-id="83a7a-132">In the **Help URL** field, type the URL to your organization’s help or support site.</span></span>
    
      - <span data-ttu-id="83a7a-133">[**法的テキスト**] フィールドに、会議出席依頼に含める法的なテキストまたは免責事項の URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="83a7a-133">In the **Legal text** field, type the URL to the legal text or disclaimer that you want to include in meeting invitations.</span></span>
    
      - <span data-ttu-id="83a7a-134">[**ユーザー設定のフッターテキスト**] フィールドに、「フッターテキスト」と入力します (最大 2 KB)。</span><span class="sxs-lookup"><span data-stu-id="83a7a-134">In the **Custom footer text** field, type footer text, up to 2 KB.</span></span>

<span data-ttu-id="83a7a-135">**Lync Server 管理シェルを使用して会議出席依頼をカスタマイズするには**</span><span class="sxs-lookup"><span data-stu-id="83a7a-135">**To Customize the Meeting Invitation by using Lync Server Management Shell**</span></span>

1.  <span data-ttu-id="83a7a-136">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="83a7a-136">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="83a7a-137">**新しい csmeeting 構成**を実行するか、または**セットアップ**して、会議出席依頼のオプションを作成または構成します。</span><span class="sxs-lookup"><span data-stu-id="83a7a-137">Run the **New-CsMeetingConfiguration** or **Set-CsMeetingConfiguration** cmdlet to create or configure the meeting invitation options.</span></span> <span data-ttu-id="83a7a-138">たとえば、以下を実行します。</span><span class="sxs-lookup"><span data-stu-id="83a7a-138">For example, run:</span></span>
    
        New-CsMeetingConfiguration -Identity site:Redmond -LogoURL "http://www.contoso.com/logo/contosobanner.gif" -HelpURL "http://www.contoso.com/support" -LegalURL "http://www.contoso.com/disclaimer" -CustomFooterText "Communications may be monitored or recorded."

</div>

</div>

<span> </span>

</div>

</div>

</div>

