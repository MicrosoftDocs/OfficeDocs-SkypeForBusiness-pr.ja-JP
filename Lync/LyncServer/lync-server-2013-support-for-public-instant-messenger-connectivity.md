---
title: Lync Server 2013 パブリックインスタントメッセンジャー接続のサポート
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Support for public instant messenger connectivity
ms:assetid: 9c6eb500-647b-4ccd-a00e-2b8dd7c44a76
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn458579(v=OCS.15)
ms:contentKeyID: 59170234
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be14e3dedf39883a81a040ed31ae38d2966ab647
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208283"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="support-for-public-instant-messenger-connectivity-in-lync-server-2013"></a><span data-ttu-id="16658-102">Lync Server 2013 でのパブリックインスタントメッセンジャー接続のサポート</span><span class="sxs-lookup"><span data-stu-id="16658-102">Support for public instant messenger connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="16658-103">_**トピックの最終更新日:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="16658-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<div>

## <a name="support-for-public-instant-messenger-connectivity"></a><span data-ttu-id="16658-104">パブリックインスタントメッセンジャー接続のサポート</span><span class="sxs-lookup"><span data-stu-id="16658-104">Support for Public Instant Messenger Connectivity</span></span>

<span data-ttu-id="16658-105">この記事では、パブリック IM 接続 (PIC) のサポートに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="16658-105">This article provides information about support for Public IM Connectivity (PIC).</span></span> <span data-ttu-id="16658-106">PIC は Microsoft Lync の機能です。これにより、組織は lync ユーザーが特定のパブリックインスタントメッセージング (IM) サービスのユーザーと Lync クライアントおよび id を介して接続できるようになります。</span><span class="sxs-lookup"><span data-stu-id="16658-106">PIC is a feature of Microsoft Lync that allows organizations to enable their Lync users to connect with users of certain public instant messaging (IM) services through their Lync clients and identities.</span></span>

<span data-ttu-id="16658-107">エンドユーザーにとっては、顧客、パートナー、およびベンダーとの間で顧客、パートナー、およびベンダーと接続できるという利点があります。</span><span class="sxs-lookup"><span data-stu-id="16658-107">End-users benefit from being able to connect with customers, partners, and vendors on their terms.</span></span> <span data-ttu-id="16658-108">Lync の制御、コンプライアンス、およびアーカイブ機能を維持しながら、1つのリアルタイム通信クライアントをサポートすることでメリットを得られます。</span><span class="sxs-lookup"><span data-stu-id="16658-108">IT benefits from supporting a single real-time communications client while maintaining the control, compliance, and archiving features of Lync.</span></span> <span data-ttu-id="16658-109">Lync と Skype の接続は、2013年 5[月に公開](https://blogs.technet.com/b/lync/archive/2013/05/23/lync-skype-connectivity-available-today.aspx)されていますが、Lync/Office Communications SERVER (OCS)/Live communications SERVER (LCS) を最初に、MSN/Windows LIVE、AOL、および Yahoo に接続する PIC で確立したものに依存しています。</span><span class="sxs-lookup"><span data-stu-id="16658-109">Lync-Skype connectivity, [publicly available in May 2013](https://blogs.technet.com/b/lync/archive/2013/05/23/lync-skype-connectivity-available-today.aspx), relies on the legacy that Lync/Office Communications Server (OCS)/Live Communications Server (LCS) first established with PIC in connecting to MSN/Windows Live, AOL, and Yahoo.</span></span><span data-ttu-id="16658-110">Lync と Skype の接続の詳細については、「 [lync-skype の接続](https://office.microsoft.com/lync/lync-skype-connectivity-fx103789635.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="16658-110">  For more information on Lync-Skype connectivity, see the [Lync-Skype connectivity](https://office.microsoft.com/lync/lync-skype-connectivity-fx103789635.aspx).</span></span> <span data-ttu-id="16658-111">Windows Live、AOL、および Yahoo とのフェデレーションは、それぞれ有効期限までの経路上にあります。</span><span class="sxs-lookup"><span data-stu-id="16658-111">Federation with Windows Live, AOL, and Yahoo are each on a path towards end-of-life.</span></span><span data-ttu-id="16658-112">このページには、各サービスの状態が記載されています。</span><span class="sxs-lookup"><span data-stu-id="16658-112"> This page documents the status of each service.</span></span>

<span data-ttu-id="16658-113">PIC を使用するには、お客様がパブリック IM サービスプロバイダーごとにサービスをアクティブにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="16658-113">To use PIC, customers have been required to activate the service for each public IM service provider.</span></span> <span data-ttu-id="16658-114">これを行う方法の要件と詳細については、「IM サービスプロバイダー」および「お客様の基になるライセンスプログラム」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="16658-114">The requirements and details for how to do this are dependent upon the IM service provider and the customer's underlying licensing program.</span></span>

<div>

## <a name="windows-live-messenger"></a><span data-ttu-id="16658-115">Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="16658-115">Windows Live Messenger</span></span>

<span data-ttu-id="16658-116">Microsoft は、Windows Live Messenger と Skype を一緒にご提供しています。</span><span class="sxs-lookup"><span data-stu-id="16658-116">Microsoft brought Windows Live Messenger and Skype together.</span></span> <span data-ttu-id="16658-117">2013年4月に、メッセンジャーユーザーが Skype For-サインインに移行されました。</span><span class="sxs-lookup"><span data-stu-id="16658-117">In April 2013, Messenger users were migrated to Skype upon sign-in.</span></span> <span data-ttu-id="16658-118">メッセンジャーとのフェデレーションを利用している Lync のお客様は、Skype に更新された後であっても、引き続きメッセンジャーの連絡先と通信できるようになります。</span><span class="sxs-lookup"><span data-stu-id="16658-118">Lync customers who rely on federation with Messenger will continue to be able to communicate with their Messenger contacts, even after those contacts update to Skype.</span></span> <span data-ttu-id="16658-119">Lync 管理者または Lync エンドユーザーがサービスの連続性を維持するために必要なことはありません。また、Lync 内でのこの機能の管理は、Messenger との通信のために維持されています。</span><span class="sxs-lookup"><span data-stu-id="16658-119">There is nothing that Lync administrators or Lync end-users need to do to maintain continuity of service, and management of this capability within Lync remains the same as it has been for communications with Messenger.</span></span> 

<span data-ttu-id="16658-120">Messenger ユーザーが自分の Microsoft アカウント (Messenger に使用される同じ資格情報) を使用して Skype にサインインするときに、Lync の連絡先を含むすべてのメッセンジャー連絡先 (たとえば、Skype に依存している)。</span><span class="sxs-lookup"><span data-stu-id="16658-120">When Messenger users sign into Skype using their Microsoft accounts (i.e., the same credentials used for Messenger) all of their Messenger contacts - including federated Lync contacts - follow them into Skype.</span></span> <span data-ttu-id="16658-121">これらの連絡先については、Skype と Lync 間のプレゼンス情報の共有とインスタントメッセージングを利用できます。</span><span class="sxs-lookup"><span data-stu-id="16658-121">Presence sharing and instant messaging between Skype and Lync for these contacts is available.</span></span> 

<span data-ttu-id="16658-122">Lync-Skype 接続-Lync および Skype ユーザー間の連絡先追加、プレゼンス共有、インスタントメッセージング、および音声通話は、すべての Lync お客様が利用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="16658-122">Lync-Skype connectivity - contact adding, presence sharing, instant messaging, and audio calling between Lync and Skype users - is also now available to all Lync customers.</span></span>

</div>

<div>

## <a name="yahoo-and-aol-instant-messenger"></a><span data-ttu-id="16658-123">Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="16658-123">Yahoo\!</span></span> <span data-ttu-id="16658-124">および AOL インスタントメッセンジャー</span><span class="sxs-lookup"><span data-stu-id="16658-124">and AOL Instant Messenger</span></span>

<span data-ttu-id="16658-125">Yahoo とのフェデレーション\!</span><span class="sxs-lookup"><span data-stu-id="16658-125">Federation with Yahoo\!</span></span> <span data-ttu-id="16658-126">および AOL は、Lync (および Office Communications Server) のお客様のために、エンドツーライフのパスにあります。</span><span class="sxs-lookup"><span data-stu-id="16658-126">and AOL are both on a path toward end-of-life for customers of Lync (and Office Communications Server).</span></span> <span data-ttu-id="16658-127">これらの各サービスを提供する Microsoft の機能は、Yahoo からのサポートに応じて異なります。\!</span><span class="sxs-lookup"><span data-stu-id="16658-127">Microsoft’s ability to provide each of these services has been contingent upon support from Yahoo\!</span></span> <span data-ttu-id="16658-128">および AOL は、これらの基礎となる契約が下になります。</span><span class="sxs-lookup"><span data-stu-id="16658-128">and AOL, and the underlying agreements of these are winding down.</span></span> <span data-ttu-id="16658-129">両方の Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="16658-129">For both Yahoo\!</span></span> <span data-ttu-id="16658-130">AOL の場合、サービスは2014年6月に継続されます。</span><span class="sxs-lookup"><span data-stu-id="16658-130">and AOL, service will continue through June 2014.</span></span>

  - <span data-ttu-id="16658-131">**Yahoo** Service は2014年6月に継続され、お客様は引き続き Microsoft LYNC パブリック IM 接続ユーザーサブスクリプションライセンス ("PIC USL") を使用してライセンスを供与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="16658-131">**Yahoo** - Service will continue through June 2014, and customers continue to need to be licensed with the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”).</span></span><span data-ttu-id="16658-132">2012年9月1日時点で、PIC USL は、新規または契約の更新の購入に使用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="16658-132">  As of September 1st, 2012, the PIC USL, is no longer available for purchase for new or renewing agreements.</span></span><span data-ttu-id="16658-133">この日以前に購入したライセンスを持つお客様は、Yahoo とのフェデレーションを続行できます。\!</span><span class="sxs-lookup"><span data-stu-id="16658-133">  Customers with licenses purchased prior to this date will be able to continue to federate with Yahoo\!</span></span> <span data-ttu-id="16658-134">サービスの以前の終了日まで、またはそのライセンスの有効期限が切れるまで。</span><span class="sxs-lookup"><span data-stu-id="16658-134">until the earlier of the service shut down date or their license expiration.</span></span><span data-ttu-id="16658-135">「Lync チームブログ」の[アナウンス](https://blogs.technet.com/b/lync/archive/2012/11/26/lync-and-yahoo-federation-end-of-life.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="16658-135"> Read [the announcement](https://blogs.technet.com/b/lync/archive/2012/11/26/lync-and-yahoo-federation-end-of-life.aspx) on the Lync Team Blog.</span></span><span data-ttu-id="16658-136">2014年6月30日よりも後の契約で PIC ライセンスを持っているお客様は、2014年6月30日以降の期間における支払い額に比例してクレジットを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="16658-136"> Customers who have PIC licenses on agreements that extend past June 30, 2014 will receive a credit in proportion to the amount of the payments covering the time period following June 30, 2014.</span></span>

  - <span data-ttu-id="16658-137">**AOL** -2014 年6月30日に、LYNC の IM 接続 ("PIC") サービスは使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="16658-137">**AOL** - On June 30, 2014, Lync's IM connectivity ("PIC") service will no longer be available.</span></span><span data-ttu-id="16658-138">サービスの終了時に顧客の中断を制限するために、お客様の追加のドメインのプロビジョニングは廃止されました。</span><span class="sxs-lookup"><span data-stu-id="16658-138"> In order to limit customer disruption when the service ends, we have discontinued the provisioning of additional customer domains.</span></span> <span data-ttu-id="16658-139">2014年6月30日まで、お客様は、ターゲットとのフェデレーション通信を引き続きサポートするために何もする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="16658-139">Until June 30, 2014, customers do not need to do anything to continue to support federated communications with AIM.</span></span> <span data-ttu-id="16658-140">この日以降 (または、その間に追加のドメインをプロビジョニングしたいと考えているお客様の場合)、AOL から直接代替サービスを利用できます。</span><span class="sxs-lookup"><span data-stu-id="16658-140">Beyond this date (or for customers that would like to provision additional domains in the meantime), a substitute service is available directly from AOL.</span></span> <span data-ttu-id="16658-141">AOL の新しいサービスの詳細については、「   [AIM を使用して直接フェデレーションを確立](http://aimenterprise.aol.com/pic.php)する (AOL.com で新しいページを開く)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="16658-141">For more information on AOL's new service, see [Establishing Direct Federation with AIM](http://aimenterprise.aol.com/pic.php)  (opens new page on AOL.com).</span></span>  

</div>

<div>

## <a name="public-im-provider-summary"></a><span data-ttu-id="16658-142">パブリック IM プロバイダーの概要</span><span class="sxs-lookup"><span data-stu-id="16658-142">Public IM Provider Summary</span></span>

<span data-ttu-id="16658-143">次の表は、パブリック IM サービスプロバイダー、Lync とのフェデレーション機能、およびライセンス要件の概要を示しています。</span><span class="sxs-lookup"><span data-stu-id="16658-143">The following table provides a summary of the Public IM service providers, federation capabilities with Lync, and licensing requirements.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="16658-144">パブリック IM サービスプロバイダー</span><span class="sxs-lookup"><span data-stu-id="16658-144">Public IM Service Provider</span></span></th>
<th><span data-ttu-id="16658-145">フェデレーション機能</span><span class="sxs-lookup"><span data-stu-id="16658-145">Federated Capabilities</span></span></th>
<th><span data-ttu-id="16658-146">ライセンス要件</span><span class="sxs-lookup"><span data-stu-id="16658-146">Licensing Requirements</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="16658-147">Skype</span><span class="sxs-lookup"><span data-stu-id="16658-147">Skype</span></span></p></td>
<td><p><span data-ttu-id="16658-148">IM、プレゼンス、オーディオ</span><span class="sxs-lookup"><span data-stu-id="16658-148">IM, Presence, Audio</span></span></p></td>
<td><p><span data-ttu-id="16658-149">Lync Server クライアントアクセスライセンス、Lync Online プラン1/2/3</span><span class="sxs-lookup"><span data-stu-id="16658-149">Lync Server Client Access Licenses, Lync Online Plan 1/2/3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16658-150">Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="16658-150">Windows Live Messenger</span></span></p></td>
<td><p><span data-ttu-id="16658-151">IM、プレゼンス、音声ビデオ</span><span class="sxs-lookup"><span data-stu-id="16658-151">IM, Presence, Audio/Video</span></span></p></td>
<td><p><span data-ttu-id="16658-152">Lync Server クライアントアクセスライセンス (WLM が市場にある限り、サポートされています)</span><span class="sxs-lookup"><span data-stu-id="16658-152">Lync Server Client Access Licenses (supported as long as WLM is in market)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16658-153">AOL</span><span class="sxs-lookup"><span data-stu-id="16658-153">AOL</span></span></p></td>
<td><p><span data-ttu-id="16658-154">IM、プレゼンス</span><span class="sxs-lookup"><span data-stu-id="16658-154">IM, Presence</span></span></p></td>
<td><p><span data-ttu-id="16658-155">Lync Server クライアントアクセスライセンス。既存のお客様に対して、2014年6月にサポートされます。</span><span class="sxs-lookup"><span data-stu-id="16658-155">Lync Server Client Access Licenses; supported through June 2014 for existing customers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16658-156">Yahoo!</span><span class="sxs-lookup"><span data-stu-id="16658-156">Yahoo!</span></span></p></td>
<td><p><span data-ttu-id="16658-157">IM、プレゼンス</span><span class="sxs-lookup"><span data-stu-id="16658-157">IM, Presence</span></span></p></td>
<td><p><span data-ttu-id="16658-158">Lync Server クライアントアクセスライセンスに加えて、追加の Microsoft Lync パブリック IM 接続ユーザーサブスクリプションライセンス ("PIC USL") が必要です。</span><span class="sxs-lookup"><span data-stu-id="16658-158">Requires additional Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) in addition to Lync Server Client Access Licences.</span></span> <span data-ttu-id="16658-159">2012年9月の価格リストの時点で、PIC USL は購入できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="16658-159">As of the September 2012 Price List, the PIC USL is no longer available for purchase.</span></span> <span data-ttu-id="16658-160">アクティブなライセンスを持つお客様は、Yahoo! とのフェデレーションを続行できます。</span><span class="sxs-lookup"><span data-stu-id="16658-160">Customers with active licenses are able to continue to federate with Yahoo!</span></span> <span data-ttu-id="16658-161">2014年6月30日にサービスがシャットダウンされるまでメッセンジャー。</span><span class="sxs-lookup"><span data-stu-id="16658-161">Messenger until the service shut down date on June 30, 2014.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

