---
title: 'Lync Server 2013: サポートされているハイブリッド構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported hybrid configurations
ms:assetid: 5d456d6c-ad71-420c-b6d8-4d9cd0324f86
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945633(v=OCS.15)
ms:contentKeyID: 51541482
ms.date: 05/10/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c757fc19bd82fbf1ae3096bb4a8ac8982f9035b6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142403"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="supported-lync-server-2013-hybrid-configurations"></a><span data-ttu-id="41e11-102">サポートされている Lync Server 2013 ハイブリッド構成</span><span class="sxs-lookup"><span data-stu-id="41e11-102">Supported Lync Server 2013 hybrid configurations</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="41e11-103">_**トピックの最終更新日:** 2016-05-10_</span><span class="sxs-lookup"><span data-stu-id="41e11-103">_**Topic Last Modified:** 2016-05-10_</span></span>

<span data-ttu-id="41e11-104">Lync Server 2013 の展開は、Microsoft Exchange Server 2010 と Microsoft Exchange Server 2013 および SharePoint Server (オンプレミスとオンラインの両方) との統合のために構成できます。</span><span class="sxs-lookup"><span data-stu-id="41e11-104">You can configure Lync Server 2013 deployments for integration with both Microsoft Exchange Server 2010 and Microsoft Exchange Server 2013 and SharePoint Server, both on-premises and online.</span></span> <span data-ttu-id="41e11-105">次の表に示す機能は、特に指定のない限り、すべてのクライアントでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="41e11-105">The features listed in the following table are supported with all clients unless otherwise specified.</span></span> <span data-ttu-id="41e11-106">クライアントサポートの詳細については、「 [client comparison tables For Lync Server 2013](lync-server-2013-desktop-client-comparison-tables.md) 」および「skype For business online クライアントでの skype for business online[の](https://go.microsoft.com/fwlink/p/?linkid=281902)クライアントの比較表」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="41e11-106">For more information about client support, see [Client comparison tables for Lync Server 2013](lync-server-2013-desktop-client-comparison-tables.md) and Skype for Business Online client comparison tables at [Clients for Skype for Business Online](https://go.microsoft.com/fwlink/p/?linkid=281902).</span></span>

<div>

## <a name="integration-with-exchange-server"></a><span data-ttu-id="41e11-107">Exchange Server との統合</span><span class="sxs-lookup"><span data-stu-id="41e11-107">Integration with Exchange Server</span></span>

<span data-ttu-id="41e11-108">次の表に、Microsoft Exchange Server と統合した場合にハイブリッド展開でサポートされる機能を示します。</span><span class="sxs-lookup"><span data-stu-id="41e11-108">The following table lists the features supported in a hybrid deployment when integrated with Microsoft Exchange Server.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="41e11-109">オンプレミスの Exchange</span><span class="sxs-lookup"><span data-stu-id="41e11-109">Exchange on-premises</span></span></th>
<th><span data-ttu-id="41e11-110">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="41e11-110">Exchange Online</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="41e11-111"><strong>Lync Server 2013 オンプレミス</strong></span><span class="sxs-lookup"><span data-stu-id="41e11-111"><strong>Lync Server 2013 on-premises</strong></span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="41e11-112">Outlook での IM/プレゼンス</span><span class="sxs-lookup"><span data-stu-id="41e11-112">IM/Presence in Outlook</span></span></p>
<p><span data-ttu-id="41e11-113">詳細については、「 <a href="lync-server-2013-im-and-presence.md">Lync Server 2013 の IM とプレゼンス</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="41e11-113">For more information, see <a href="lync-server-2013-im-and-presence.md">IM and presence in Lync Server 2013</a></span></span></p></li>
<li><p><span data-ttu-id="41e11-114">Outlook を使用してオンライン会議のスケジュールを設定して参加する</span><span class="sxs-lookup"><span data-stu-id="41e11-114">Schedule and join online meetings through Outlook</span></span></p>
<p><span data-ttu-id="41e11-115">詳細については、「 <a href="lync-server-2013-integrating-with-microsoft-exchange-server-2013.md">Microsoft Lync Server 2013 と Microsoft Exchange Server 2013 の統合</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="41e11-115">For more information, see <a href="lync-server-2013-integrating-with-microsoft-exchange-server-2013.md">Integrating Microsoft Lync Server 2013 and Microsoft Exchange Server 2013</a></span></span></p></li>
<li><p><span data-ttu-id="41e11-116">Outlook Web App での IM/プレゼンス</span><span class="sxs-lookup"><span data-stu-id="41e11-116">IM/Presence in Outlook Web App</span></span></p>
<p><span data-ttu-id="41e11-117">詳細については、「 <a href="lync-server-2013-configuring-lync-server-in-a-cross-premises-environment.md">Microsoft Lync Server 2013 をクロスプレミス環境で構成する</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="41e11-117">For more information, see <a href="lync-server-2013-configuring-lync-server-in-a-cross-premises-environment.md">Configuring Microsoft Lync Server 2013 in a cross-premises environment</a></span></span></p></li>
<li><p><span data-ttu-id="41e11-118">Outlook Web App を使用したオンライン会議のスケジュールと参加</span><span class="sxs-lookup"><span data-stu-id="41e11-118">Schedule and join online meetings through Outlook Web App</span></span></p></li>
<li><p><span data-ttu-id="41e11-119">モバイルクライアントでの IM/プレゼンス</span><span class="sxs-lookup"><span data-stu-id="41e11-119">IM/Presence in Mobile Clients</span></span></p></li>
<li><p><span data-ttu-id="41e11-120">モバイルクライアントでのオンライン会議への参加</span><span class="sxs-lookup"><span data-stu-id="41e11-120">Join online meetings in Mobile clients</span></span></p>
<p><span data-ttu-id="41e11-121">詳細については、「 <a href="lync-server-2013-deploying-mobility.md">Lync Server でのモビリティの展開 2013</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="41e11-121">For more information, see <a href="lync-server-2013-deploying-mobility.md">Deploying mobility in Lync Server 2013</a></span></span></p></li>
<li><p><span data-ttu-id="41e11-122">Outlook 予定表の空き時間情報に基づく状態の公開</span><span class="sxs-lookup"><span data-stu-id="41e11-122">Publish status based on Outlook calendar free/busy information</span></span></p></li>
<li><p><span data-ttu-id="41e11-123">連絡先リスト (統合連絡先ストア経由)</span><span class="sxs-lookup"><span data-stu-id="41e11-123">Contact List (via Unified Contact Store)</span></span></p>
<p><span data-ttu-id="41e11-124">詳細については、「 <a href="lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md">Microsoft Lync Server 2013 を構成して統合連絡先ストアを使用する</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="41e11-124">For more information, see <a href="lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md">Configuring Microsoft Lync Server 2013 to use the unified contact store</a></span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="41e11-125">Exchange 2013 が必要です。</span><span class="sxs-lookup"><span data-stu-id="41e11-125">Requires Exchange 2013.</span></span><BR><span data-ttu-id="41e11-126">Lync 2013 デスクトップクライアントが必要です。</span><span class="sxs-lookup"><span data-stu-id="41e11-126">A Lync 2013 desktop client is required.</span></span>


</div></li>
<li><p><span data-ttu-id="41e11-127">Lync 2013 クライアントおよび Lync Web App の、高解像度の連絡先写真。</span><span class="sxs-lookup"><span data-stu-id="41e11-127">High-resolution Contact Photo in Lync 2013 client and Lync Web App.</span></span></p>
<p><span data-ttu-id="41e11-128">詳細については、「 <a href="lync-server-2013-configuring-the-use-of-high-resolution-photos.md">Microsoft Lync Server 2013 で高解像度写真の使用を構成する</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="41e11-128">For more information, see <a href="lync-server-2013-configuring-the-use-of-high-resolution-photos.md">Configuring the use of high-resolution photos in Microsoft Lync Server 2013</a></span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="41e11-129">Exchange 2013 が必要です。</span><span class="sxs-lookup"><span data-stu-id="41e11-129">Requires Exchange 2013.</span></span>


</div></li>
<li><p><span data-ttu-id="41e11-130">会議の委任</span><span class="sxs-lookup"><span data-stu-id="41e11-130">Meeting delegation</span></span></p>
<p><span data-ttu-id="41e11-131">両方のユーザーが同じフォレストでオンラインになっている場合、または両方のユーザーがオンプレミスに所属している場合にのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="41e11-131">Supported only when both users are homed online in the same forest, or both are homed on-premises.</span></span></p></li>
<li><p><span data-ttu-id="41e11-132">不在着信した会話の履歴と通話ログはユーザーの exchange メールボックスに書き込まれる</span><span class="sxs-lookup"><span data-stu-id="41e11-132">Missed Conversations history and Call Logs are written to user’s exchange mailbox</span></span></p></li>
<li><p><span data-ttu-id="41e11-133">Exchange のアーカイブコンテンツ (IM および会議)</span><span class="sxs-lookup"><span data-stu-id="41e11-133">Archiving Content (IM and Meeting) in Exchange</span></span></p>
<p><span data-ttu-id="41e11-134">詳細については、「 <a href="lync-server-2013-deployment-checklist-for-archiving.md">Lync Server 2013 のアーカイブの展開チェックリスト</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="41e11-134">For more information, see <a href="lync-server-2013-deployment-checklist-for-archiving.md">Deployment checklist for Archiving in Lync Server 2013</a></span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="41e11-135">Exchange 2013 が必要です。</span><span class="sxs-lookup"><span data-stu-id="41e11-135">Requires Exchange 2013.</span></span>


</div></li>
<li><p><span data-ttu-id="41e11-136">アーカイブされたコンテンツの検索</span><span class="sxs-lookup"><span data-stu-id="41e11-136">Search archived content</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="41e11-137">Exchange 2013 が必要です。</span><span class="sxs-lookup"><span data-stu-id="41e11-137">Requires Exchange 2013.</span></span>


</div></li>
<li><p><span data-ttu-id="41e11-138">ボイス メール</span><span class="sxs-lookup"><span data-stu-id="41e11-138">Voice mail</span></span></p>
<p><span data-ttu-id="41e11-139">詳細については、「<a href="lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md">オンプレミスの EXCHANGE UM を展開して Lync Server 2013 ボイスメールを提供する</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="41e11-139">For more information, see <a href="lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md">Deploying on-premises Exchange UM to provide Lync Server 2013 voice mail</a></span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="41e11-140">Outlook での IM/プレゼンス</span><span class="sxs-lookup"><span data-stu-id="41e11-140">IM/Presence in Outlook</span></span></p>
<p><span data-ttu-id="41e11-141">詳細については、「<a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">オンプレミスの Lync Server 2013 と Exchange Online との統合の構成</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="41e11-141">For more information, see <a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">Configuring on-premises Lync Server 2013 integration with Exchange Online</a></span></span></p></li>
<li><p><span data-ttu-id="41e11-142">Outlook を使用してオンライン会議のスケジュールを設定して参加する</span><span class="sxs-lookup"><span data-stu-id="41e11-142">Schedule and join online meeting through Outlook</span></span></p></li>
<li><p><span data-ttu-id="41e11-143">OWA での IM/プレゼンス</span><span class="sxs-lookup"><span data-stu-id="41e11-143">IM/Presence in OWA</span></span></p>
<p><span data-ttu-id="41e11-144">詳細については、「<a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">オンプレミスの Lync Server 2013 と Exchange Online との統合の構成</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="41e11-144">For more information, see <a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">Configuring on-premises Lync Server 2013 integration with Exchange Online</a></span></span></p></li>
<li><p><span data-ttu-id="41e11-145">Outlook Web App からのオンライン会議のスケジュールと参加</span><span class="sxs-lookup"><span data-stu-id="41e11-145">Schedule and join online meeting from Outlook Web App</span></span></p>
<p><span data-ttu-id="41e11-146">詳細については、「<a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">オンプレミスの Lync Server 2013 と Exchange Online との統合の構成</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="41e11-146">For more information, see <a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">Configuring on-premises Lync Server 2013 integration with Exchange Online</a></span></span></p></li>
<li><p><span data-ttu-id="41e11-147">モバイルクライアントでの IM/プレゼンス</span><span class="sxs-lookup"><span data-stu-id="41e11-147">IM/Presence in Mobile Clients</span></span></p></li>
<li><p><span data-ttu-id="41e11-148">モバイルクライアントでのオンライン会議への参加</span><span class="sxs-lookup"><span data-stu-id="41e11-148">Join online meeting in Mobile clients</span></span></p></li>
<li><p><span data-ttu-id="41e11-149">Outlook 予定表の空き時間情報に基づく状態の公開</span><span class="sxs-lookup"><span data-stu-id="41e11-149">Publish status based on Outlook calendar free/busy information</span></span></p></li>
<li><p><span data-ttu-id="41e11-150">連絡先リスト (統合連絡先ストア経由)。</span><span class="sxs-lookup"><span data-stu-id="41e11-150">Contact List (via Unified Contact Store).</span></span> <span data-ttu-id="41e11-151">詳細については、「 <a href="lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md">Microsoft Lync Server 2013 を構成して統合連絡先ストアを使用する</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="41e11-151">For more information, see <a href="lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md">Configuring Microsoft Lync Server 2013 to use the unified contact store</a></span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="41e11-152">Lync Server 2013 のみ。</span><span class="sxs-lookup"><span data-stu-id="41e11-152">Lync Server 2013 only.</span></span> <span data-ttu-id="41e11-153">Lync 2013 デスクトップクライアントが必要です。</span><span class="sxs-lookup"><span data-stu-id="41e11-153">A Lync 2013 desktop client is required.</span></span>


</div></li>
<li><p><span data-ttu-id="41e11-154">Lync 2013 クライアントおよび Lync Web App の、高解像度の連絡先写真。</span><span class="sxs-lookup"><span data-stu-id="41e11-154">High-resolution Contact Photo in Lync 2013 client and Lync Web App.</span></span></p>
<p><span data-ttu-id="41e11-155">詳細については、「 <a href="lync-server-2013-configuring-the-use-of-high-resolution-photos.md">Microsoft Lync Server 2013 で高解像度写真の使用を構成する</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="41e11-155">For more information, see <a href="lync-server-2013-configuring-the-use-of-high-resolution-photos.md">Configuring the use of high-resolution photos in Microsoft Lync Server 2013</a>.</span></span></p></li>
<li><p><span data-ttu-id="41e11-156">会議の委任</span><span class="sxs-lookup"><span data-stu-id="41e11-156">Meeting delegation</span></span></p>
<p><span data-ttu-id="41e11-157">両方のユーザーが同じフォレストでオンラインになっている場合、または両方のユーザーがオンプレミスに所属している場合にのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="41e11-157">Supported only when both users are homed online in the same forest, or both are homed on-premises.</span></span></p></li>
<li><p><span data-ttu-id="41e11-158">不在着信した会話の履歴と通話ログはユーザーの exchange メールボックスに書き込まれる</span><span class="sxs-lookup"><span data-stu-id="41e11-158">Missed Conversations history and Call Logs are written to user’s exchange mailbox</span></span></p></li>
<li><p><span data-ttu-id="41e11-159">Exchange のアーカイブコンテンツ (IM および会議)。</span><span class="sxs-lookup"><span data-stu-id="41e11-159">Archiving Content (IM and Meeting) in Exchange.</span></span></p>
<p><span data-ttu-id="41e11-160">詳細については、「 <a href="lync-server-2013-deployment-checklist-for-archiving.md">Lync Server 2013 のアーカイブの展開チェックリスト</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="41e11-160">For more information, see <a href="lync-server-2013-deployment-checklist-for-archiving.md">Deployment checklist for Archiving in Lync Server 2013</a></span></span></p></li>
<li><p><span data-ttu-id="41e11-161">アーカイブされたコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="41e11-161">Search archived content.</span></span> <span data-ttu-id="41e11-162">詳細については、「 <a href="https://go.microsoft.com/fwlink/p/?linkid=285448">Configure Exchange For SharePoint EDiscovery Center</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="41e11-162">For more information, see at <a href="https://go.microsoft.com/fwlink/p/?linkid=285448">Configure Exchange for SharePoint eDiscovery Center</a></span></span></p></li>
<li><p><span data-ttu-id="41e11-163">ボイスメール</span><span class="sxs-lookup"><span data-stu-id="41e11-163">Voice mail.</span></span> <span data-ttu-id="41e11-164">詳細については、「 <a href="lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md">Lync Server 2013 ユーザーのボイスメールをホストされている EXCHANGE UM で提供</a>する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="41e11-164">For more information, see <a href="lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md">Providing Lync Server 2013 users voice mail on hosted Exchange UM</a></span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41e11-165"><strong>Lync Online</strong></span><span class="sxs-lookup"><span data-stu-id="41e11-165"><strong>Lync Online</strong></span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="41e11-166">Outlook での IM とプレゼンス</span><span class="sxs-lookup"><span data-stu-id="41e11-166">IM and Presence in Outlook</span></span></p></li>
<li><p><span data-ttu-id="41e11-167">Outlook を使用してオンライン会議のスケジュールを設定して参加する</span><span class="sxs-lookup"><span data-stu-id="41e11-167">Schedule and join online meetings through Outlook</span></span></p></li>
<li><p><span data-ttu-id="41e11-168">モバイルクライアントでの IM/プレゼンス</span><span class="sxs-lookup"><span data-stu-id="41e11-168">IM/Presence in Mobile clients</span></span></p></li>
<li><p><span data-ttu-id="41e11-169">不在着信した会話の履歴と通話ログはユーザーの exchange メールボックスに書き込まれる</span><span class="sxs-lookup"><span data-stu-id="41e11-169">Missed Conversations history and Call Logs are written to user’s exchange mailbox</span></span></p></li>
<li><p><span data-ttu-id="41e11-170">Lync 2013 クライアントの高解像度の連絡先写真。</span><span class="sxs-lookup"><span data-stu-id="41e11-170">High-resolution Contact Photo in Lync 2013 client.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="41e11-171">Microsoft Exchange Server 2013 が必要です。</span><span class="sxs-lookup"><span data-stu-id="41e11-171">Requires Microsoft Exchange Server 2013.</span></span> <span data-ttu-id="41e11-172">これは、ユーザーが Skype for Business Online に所属している場合、Lync Web App ではサポートされません。</span><span class="sxs-lookup"><span data-stu-id="41e11-172">This is not supported in Lync Web App when users are homed on Skype for Business Online.</span></span>


</div></li>
<li><p><span data-ttu-id="41e11-173">モバイルクライアントでのオンライン会議への参加</span><span class="sxs-lookup"><span data-stu-id="41e11-173">Join online meeting in Mobile clients</span></span></p></li>
<li><p><span data-ttu-id="41e11-174">Outlook 予定表の空き時間情報に基づく状態の公開</span><span class="sxs-lookup"><span data-stu-id="41e11-174">Publish status based on Outlook calendar free/busy information</span></span></p></li>
<li><p><span data-ttu-id="41e11-175">会議の委任</span><span class="sxs-lookup"><span data-stu-id="41e11-175">Meeting delegation</span></span></p>
<p><span data-ttu-id="41e11-176">両方のユーザーが同じフォレストでオンラインになっている場合、または両方のユーザーがオンプレミスに所属している場合にのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="41e11-176">Supported only when both users are homed online in the same forest, or both are homed on-premises.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="41e11-177">Outlook での IM/プレゼンス</span><span class="sxs-lookup"><span data-stu-id="41e11-177">IM/Presence in Outlook</span></span></p></li>
<li><p><span data-ttu-id="41e11-178">Outlook を使用してオンライン会議のスケジュールを設定して参加する</span><span class="sxs-lookup"><span data-stu-id="41e11-178">Schedule and join online meetings through Outlook</span></span></p></li>
<li><p><span data-ttu-id="41e11-179">Outlook Web App での IM/プレゼンス</span><span class="sxs-lookup"><span data-stu-id="41e11-179">IM/Presence in Outlook Web App</span></span></p></li>
<li><p><span data-ttu-id="41e11-180">Outlook Web App からのオンライン会議のスケジュールと参加</span><span class="sxs-lookup"><span data-stu-id="41e11-180">Schedule and join online meeting from Outlook Web App</span></span></p></li>
<li><p><span data-ttu-id="41e11-181">モバイルクライアントでの IM/プレゼンス</span><span class="sxs-lookup"><span data-stu-id="41e11-181">IM/Presence in Mobile Clients</span></span></p></li>
<li><p><span data-ttu-id="41e11-182">モバイルクライアントでのオンライン会議への参加</span><span class="sxs-lookup"><span data-stu-id="41e11-182">Join online meeting in Mobile clients</span></span></p></li>
<li><p><span data-ttu-id="41e11-183">Outlook 予定表の空き時間情報に基づく状態の公開</span><span class="sxs-lookup"><span data-stu-id="41e11-183">Publish status based on Outlook calendar free/busy information</span></span></p></li>
<li><p><span data-ttu-id="41e11-184">不在着信した会話の履歴と通話ログはユーザーの exchange メールボックスに書き込まれる</span><span class="sxs-lookup"><span data-stu-id="41e11-184">Missed Conversations history and Call Logs are written to user’s exchange mailbox</span></span></p></li>
<li><p><span data-ttu-id="41e11-185">連絡先リスト (統合連絡先ストア経由)</span><span class="sxs-lookup"><span data-stu-id="41e11-185">Contact List (via Unified Contact Store)</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="41e11-186">Lync Server 2013 クライアントが必要</span><span class="sxs-lookup"><span data-stu-id="41e11-186">Lync Server 2013 client Required</span></span>


</div></li>
<li><p><span data-ttu-id="41e11-187">Lync 2013 クライアントおよび Lync Web App の高解像度の連絡先写真</span><span class="sxs-lookup"><span data-stu-id="41e11-187">High-resolution Contact Photo in Lync 2013 client and Lync Web App</span></span></p></li>
<li><p><span data-ttu-id="41e11-188">会議の委任</span><span class="sxs-lookup"><span data-stu-id="41e11-188">Meeting delegation</span></span></p>
<p><span data-ttu-id="41e11-189">両方のユーザーが同じフォレストでオンラインになっている場合、または両方のユーザーがオンプレミスに所属している場合にのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="41e11-189">Supported only when both users are homed online in the same forest, or both are homed on-premises.</span></span></p></li>
<li><p><span data-ttu-id="41e11-190">Exchange のアーカイブコンテンツ (IM および会議)</span><span class="sxs-lookup"><span data-stu-id="41e11-190">Archiving Content (IM and Meeting) in Exchange</span></span></p></li>
<li><p><span data-ttu-id="41e11-191">アーカイブされたコンテンツの検索</span><span class="sxs-lookup"><span data-stu-id="41e11-191">Search archived content</span></span></p></li>
<li><p><span data-ttu-id="41e11-192">ボイスメール</span><span class="sxs-lookup"><span data-stu-id="41e11-192">Voicemail</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="integration-with-sharepoint"></a><span data-ttu-id="41e11-193">SharePoint との統合</span><span class="sxs-lookup"><span data-stu-id="41e11-193">Integration with SharePoint</span></span>

<span data-ttu-id="41e11-194">次の表に、SharePoint と統合した場合に Lync Server 2013 ハイブリッド展開でサポートされる機能を示します。</span><span class="sxs-lookup"><span data-stu-id="41e11-194">The following table lists the features supported in a Lync Server 2013 hybrid deployment when integrated with SharePoint.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="41e11-195">SharePoint 社内展開</span><span class="sxs-lookup"><span data-stu-id="41e11-195">SharePoint on-premises</span></span></th>
<th><span data-ttu-id="41e11-196">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="41e11-196">SharePoint Online</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="41e11-197"><strong>Lync Server 2013 オンプレミス</strong></span><span class="sxs-lookup"><span data-stu-id="41e11-197"><strong>Lync Server 2013 on-premises</strong></span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="41e11-198">スキル検索</span><span class="sxs-lookup"><span data-stu-id="41e11-198">Skills search</span></span></p></li>
<li><p><span data-ttu-id="41e11-199">SharePoint でのプレゼンス</span><span class="sxs-lookup"><span data-stu-id="41e11-199">Presence in SharePoint</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="41e11-200">SharePoint でのプレゼンス</span><span class="sxs-lookup"><span data-stu-id="41e11-200">Presence in SharePoint</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41e11-201"><strong>Lync Online</strong></span><span class="sxs-lookup"><span data-stu-id="41e11-201"><strong>Lync Online</strong></span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="41e11-202">SharePoint でのプレゼンス</span><span class="sxs-lookup"><span data-stu-id="41e11-202">Presence in SharePoint</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="41e11-203">SharePoint でのプレゼンス</span><span class="sxs-lookup"><span data-stu-id="41e11-203">Presence in SharePoint</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

