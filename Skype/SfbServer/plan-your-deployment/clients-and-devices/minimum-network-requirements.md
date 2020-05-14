---
title: Skype 会議アプリの最小ネットワーク要件
ms.author: v-lanac
author: lanachin
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 6/4/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d9666787-e72b-41e1-ba37-aec5fb849a10
description: '概要: Microsoft 365 または Office 365 を使用しておらず、組織によってホストされている会議にアクセスする必要がある組織に関する情報。'
ms.openlocfilehash: 656f8fa52f4a1080cca0b8464becf77c8c2a0ef0
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "44219727"
---
# <a name="skype-meetings-app-minimum-network-requirements"></a><span data-ttu-id="56428-103">Skype 会議アプリの最小ネットワーク要件</span><span class="sxs-lookup"><span data-stu-id="56428-103">Skype Meetings App minimum network requirements</span></span>
 
<span data-ttu-id="56428-104">**概要:** Microsoft 365 または Office 365 を使用しておらず、組織によってホストされている会議にアクセスする必要がある組織の情報。</span><span class="sxs-lookup"><span data-stu-id="56428-104">**Summary:**  Information for organizations who don't use Microsoft 365 or Office 365 and need to access meetings hosted by organizations that do.</span></span> <span data-ttu-id="56428-105">この記事は、これらのアプリのユーザーを対象としたものではありません。</span><span class="sxs-lookup"><span data-stu-id="56428-105">This article is not intended for the users of these apps.</span></span>
  
<span data-ttu-id="56428-106">ユーザーが skype for Business Online でホストされている会議に参加するために Skype 会議アプリを使用できるようにするには、Microsoft 365 または Office 365 を使用していない組織のネットワーク管理者は、以下に記載されている Fqdn、Ip、およびポートをホワイトリストするか、それ以外の方法で使用できます。</span><span class="sxs-lookup"><span data-stu-id="56428-106">To allow users to use Skype Meetings App to  attend meetings hosted in Skype for Business Online, network administrators of organizations who don't use Microsoft 365 or Office 365 should whitelist or otherwise make available the FQDNs, IPs, and ports mentioned below.</span></span>

## <a name="requirements-for-skype-meetings-app-connectivity"></a><span data-ttu-id="56428-107">Skype 会議アプリの接続の要件</span><span class="sxs-lookup"><span data-stu-id="56428-107">Requirements for Skype Meetings App connectivity</span></span>

<span data-ttu-id="56428-108">ここに記載されている情報は、 [Office 365 の url と IP アドレスの範囲](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)の一部であり、より詳細で、常に最新の状態になります。</span><span class="sxs-lookup"><span data-stu-id="56428-108">The information listed here is a subset of [Office 365 URLs and IP address ranges](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US), which provides more depth and will always be the most up to date.</span></span>
                    
 
|<span data-ttu-id="56428-109">アプリ</span><span class="sxs-lookup"><span data-stu-id="56428-109">App</span></span> |<span data-ttu-id="56428-110">宛先の Fqdn</span><span class="sxs-lookup"><span data-stu-id="56428-110">Destination FQDNs</span></span>  |<span data-ttu-id="56428-111">IP アドレス</span><span class="sxs-lookup"><span data-stu-id="56428-111">IP Addresses</span></span>  |<span data-ttu-id="56428-112">ポート</span><span class="sxs-lookup"><span data-stu-id="56428-112">Ports</span></span>  |
|---|---------|---------|---------|
|<span data-ttu-id="56428-113">**Skype 会議アプリ**</span><span class="sxs-lookup"><span data-stu-id="56428-113">**Skype Meetings App**</span></span> | <span data-ttu-id="56428-114">\*. lync.com</span><span class="sxs-lookup"><span data-stu-id="56428-114">\*.lync.com</span></span> <br/><span data-ttu-id="56428-115">\*. infra.lync.com</span><span class="sxs-lookup"><span data-stu-id="56428-115">\*.infra.lync.com</span></span><br/><span data-ttu-id="56428-116">\*. pipe.aria.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="56428-116">\*.pipe.aria.microsoft.com</span></span><br/><span data-ttu-id="56428-117">\*. sfbassets.com</span><span class="sxs-lookup"><span data-stu-id="56428-117">\*.sfbassets.com</span></span><br/><span data-ttu-id="56428-118">\*. msecnd.net</span><span class="sxs-lookup"><span data-stu-id="56428-118">\*.msecnd.net</span></span><br/><span data-ttu-id="56428-119">\*<span></span>officeapps.live.com</span><span class="sxs-lookup"><span data-stu-id="56428-119">\*broadcast<span></span>.officeapps.live.com</span></span> <br/><span data-ttu-id="56428-120">\*<span></span>officeapps.live.com</span><span class="sxs-lookup"><span data-stu-id="56428-120">\*powerpoint<span></span>.officeapps.live.com</span></span> <br/><span data-ttu-id="56428-121">\*. office.live.com</span><span class="sxs-lookup"><span data-stu-id="56428-121">\*.office.live.com</span></span><br/><span data-ttu-id="56428-122">\*. cdn.office.net</span><span class="sxs-lookup"><span data-stu-id="56428-122">\*.cdn.office.net</span></span><br/><span data-ttu-id="56428-123">\*. s-microsoft.com</span><span class="sxs-lookup"><span data-stu-id="56428-123">\*.s-microsoft.com</span></span><br/>        |   <span data-ttu-id="56428-124">これらの IP アドレスは頻繁に更新されます。</span><span class="sxs-lookup"><span data-stu-id="56428-124">These IP addresses are frequently updated.</span></span>  <span data-ttu-id="56428-125">「 [Skype For business の ip 範囲](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip)」および「 [Office の ip 範囲](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="56428-125">See [Skype for Business IP ranges](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) as well as [Office IP Ranges](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)</span></span>         |<span data-ttu-id="56428-126">TCP:80 &amp; 443</span><span class="sxs-lookup"><span data-stu-id="56428-126">TCP: 80 &amp; 443</span></span><br/><span data-ttu-id="56428-127">UDP: 3478-3481</span><span class="sxs-lookup"><span data-stu-id="56428-127">UDP: 3478-3481</span></span><br/>
|<span data-ttu-id="56428-128">**Teams**</span><span class="sxs-lookup"><span data-stu-id="56428-128">**Teams**</span></span>    | <span data-ttu-id="56428-129">\*<span></span>. microsoft.com</span><span class="sxs-lookup"><span data-stu-id="56428-129">\*<span></span>.microsoft.com</span></span> <br/><span data-ttu-id="56428-130">\*<span></span>. skype.com</span><span class="sxs-lookup"><span data-stu-id="56428-130">\*<span></span>.skype.com</span></span> | <span data-ttu-id="56428-131">これらの IP アドレスは頻繁に更新されます。</span><span class="sxs-lookup"><span data-stu-id="56428-131">These IP addresses are frequently updated.</span></span>  <span data-ttu-id="56428-132">「 [Skype For business の ip 範囲](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip)」および「 [Office の ip 範囲](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="56428-132">See [Skype for Business IP ranges](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) as well as [Office IP Ranges](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)</span></span>      |<span data-ttu-id="56428-133">TCP: 443</span><span class="sxs-lookup"><span data-stu-id="56428-133">TCP:  443</span></span> <br/> <span data-ttu-id="56428-134">UDP: 3478-3481</span><span class="sxs-lookup"><span data-stu-id="56428-134">UDP: 3478-3481</span></span>

## <a name="see-also"></a><span data-ttu-id="56428-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="56428-135">See also</span></span>
<span data-ttu-id="56428-136"><a name="BKMK_Conferencing"> </a></span><span class="sxs-lookup"><span data-stu-id="56428-136"><a name="BKMK_Conferencing"> </a></span></span>

[<span data-ttu-id="56428-137">会議クライアントを計画する (Web アプリと会議アプリ)</span><span class="sxs-lookup"><span data-stu-id="56428-137">Plan for Meetings clients (Web App and Meetings App)</span></span>](meetings-clients.md)

[<span data-ttu-id="56428-138">Skype for Business Server で Web ダウンロード可能なクライアントを展開する</span><span class="sxs-lookup"><span data-stu-id="56428-138">Deploy Web downloadable clients in Skype for Business Server</span></span>](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[<span data-ttu-id="56428-139">Skype 会議アプリでサポートされているプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="56428-139">Supported platforms for Skype Meetings App</span></span>](https://support.office.com/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
