---
title: Skype 会議アプリの最小ネットワーク要件
ms.author: v-cichur
author: cichur
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
description: '概要: Microsoft 365 または Office 365 を使用しない組織、および Microsoft 365 がホストする組織がホストする会議にアクセスする必要がある組織向け情報。'
ms.openlocfilehash: d5e6b838ceddb4ea1195694eb0ad11a1d029a1bb
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816307"
---
# <a name="skype-meetings-app-minimum-network-requirements"></a><span data-ttu-id="02e0f-103">Skype 会議アプリの最小ネットワーク要件</span><span class="sxs-lookup"><span data-stu-id="02e0f-103">Skype Meetings App minimum network requirements</span></span>
 
<span data-ttu-id="02e0f-104">**概要:**  Microsoft 365 または Office 365 を使用しない組織、および Microsoft 365 がホストする組織がホストする会議にアクセスする必要がある組織向け情報。</span><span class="sxs-lookup"><span data-stu-id="02e0f-104">**Summary:**  Information for organizations who don't use Microsoft 365 or Office 365 and need to access meetings hosted by organizations that do.</span></span> <span data-ttu-id="02e0f-105">この記事は、これらのアプリのユーザー向けではありません。</span><span class="sxs-lookup"><span data-stu-id="02e0f-105">This article is not intended for the users of these apps.</span></span>
  
<span data-ttu-id="02e0f-106">ユーザーが Skype for Business Online でホストされている会議に Skype 会議アプリを使用して参加するには、Microsoft 365 または Office 365 を使用しない組織のネットワーク管理者が、以下に説明する FQDN、IPS、およびポートを許可するか、利用できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="02e0f-106">To allow users to use Skype Meetings App to  attend meetings hosted in Skype for Business Online, network administrators of organizations who don't use Microsoft 365 or Office 365 should allow or otherwise make available the FQDNs, IPs, and ports mentioned below.</span></span>

## <a name="requirements-for-skype-meetings-app-connectivity"></a><span data-ttu-id="02e0f-107">Skype 会議アプリの接続の要件</span><span class="sxs-lookup"><span data-stu-id="02e0f-107">Requirements for Skype Meetings App connectivity</span></span>

<span data-ttu-id="02e0f-108">ここに示す情報は [、Office 365](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)URL と IP アドレス範囲のサブセットであり、より深く提供され、常に最新の情報になります。</span><span class="sxs-lookup"><span data-stu-id="02e0f-108">The information listed here is a subset of [Office 365 URLs and IP address ranges](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US), which provides more depth and will always be the most up to date.</span></span>
                    
 
|<span data-ttu-id="02e0f-109">アプリ</span><span class="sxs-lookup"><span data-stu-id="02e0f-109">App</span></span> |<span data-ttu-id="02e0f-110">宛先 FQDN</span><span class="sxs-lookup"><span data-stu-id="02e0f-110">Destination FQDNs</span></span>  |<span data-ttu-id="02e0f-111">IP アドレス</span><span class="sxs-lookup"><span data-stu-id="02e0f-111">IP Addresses</span></span>  |<span data-ttu-id="02e0f-112">ポート</span><span class="sxs-lookup"><span data-stu-id="02e0f-112">Ports</span></span>  |
|---|---------|---------|---------|
|<span data-ttu-id="02e0f-113">**Skype 会議アプリ**</span><span class="sxs-lookup"><span data-stu-id="02e0f-113">**Skype Meetings App**</span></span> | <span data-ttu-id="02e0f-114">\*.lync.com</span><span class="sxs-lookup"><span data-stu-id="02e0f-114">\*.lync.com</span></span> <br/><span data-ttu-id="02e0f-115">\*.infra.lync.com</span><span class="sxs-lookup"><span data-stu-id="02e0f-115">\*.infra.lync.com</span></span><br/><span data-ttu-id="02e0f-116">\*.pipe.aria.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="02e0f-116">\*.pipe.aria.microsoft.com</span></span><br/><span data-ttu-id="02e0f-117">\*.sfbassets.com</span><span class="sxs-lookup"><span data-stu-id="02e0f-117">\*.sfbassets.com</span></span><br/><span data-ttu-id="02e0f-118">\*.msecnd.net</span><span class="sxs-lookup"><span data-stu-id="02e0f-118">\*.msecnd.net</span></span><br/><span data-ttu-id="02e0f-119">\*broadcast <span></span> .officeapps.live.com</span><span class="sxs-lookup"><span data-stu-id="02e0f-119">\*broadcast<span></span>.officeapps.live.com</span></span> <br/><span data-ttu-id="02e0f-120">\*powerpoint <span></span> .officeapps.live.com</span><span class="sxs-lookup"><span data-stu-id="02e0f-120">\*powerpoint<span></span>.officeapps.live.com</span></span> <br/><span data-ttu-id="02e0f-121">\*.office.live.com</span><span class="sxs-lookup"><span data-stu-id="02e0f-121">\*.office.live.com</span></span><br/><span data-ttu-id="02e0f-122">\*.cdn.office.net</span><span class="sxs-lookup"><span data-stu-id="02e0f-122">\*.cdn.office.net</span></span><br/><span data-ttu-id="02e0f-123">\*.s-microsoft.com</span><span class="sxs-lookup"><span data-stu-id="02e0f-123">\*.s-microsoft.com</span></span><br/>        |   <span data-ttu-id="02e0f-124">これらの IP アドレスは頻繁に更新されます。</span><span class="sxs-lookup"><span data-stu-id="02e0f-124">These IP addresses are frequently updated.</span></span>  <span data-ttu-id="02e0f-125">Skype [for Business の IP 範囲と](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) IP 範囲Office [参照](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)</span><span class="sxs-lookup"><span data-stu-id="02e0f-125">See [Skype for Business IP ranges](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) as well as [Office IP Ranges](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)</span></span>         |<span data-ttu-id="02e0f-126">TCP: 80 &amp; 443</span><span class="sxs-lookup"><span data-stu-id="02e0f-126">TCP: 80 &amp; 443</span></span><br/><span data-ttu-id="02e0f-127">UDP: 3478-3481</span><span class="sxs-lookup"><span data-stu-id="02e0f-127">UDP: 3478-3481</span></span><br/>
|<span data-ttu-id="02e0f-128">**Teams**</span><span class="sxs-lookup"><span data-stu-id="02e0f-128">**Teams**</span></span>    | <span data-ttu-id="02e0f-129">\*<span></span>.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="02e0f-129">\*<span></span>.microsoft.com</span></span> <br/><span data-ttu-id="02e0f-130">\*<span></span>.skype.com</span><span class="sxs-lookup"><span data-stu-id="02e0f-130">\*<span></span>.skype.com</span></span> | <span data-ttu-id="02e0f-131">これらの IP アドレスは頻繁に更新されます。</span><span class="sxs-lookup"><span data-stu-id="02e0f-131">These IP addresses are frequently updated.</span></span>  <span data-ttu-id="02e0f-132">Skype [for Business の IP 範囲と](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) IP 範囲Office [参照](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)</span><span class="sxs-lookup"><span data-stu-id="02e0f-132">See [Skype for Business IP ranges](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) as well as [Office IP Ranges](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)</span></span>      |<span data-ttu-id="02e0f-133">TCP: 443</span><span class="sxs-lookup"><span data-stu-id="02e0f-133">TCP:  443</span></span> <br/> <span data-ttu-id="02e0f-134">UDP: 3478-3481</span><span class="sxs-lookup"><span data-stu-id="02e0f-134">UDP: 3478-3481</span></span>

## <a name="see-also"></a><span data-ttu-id="02e0f-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="02e0f-135">See also</span></span>
<span data-ttu-id="02e0f-136"><a name="BKMK_Conferencing"> </a></span><span class="sxs-lookup"><span data-stu-id="02e0f-136"><a name="BKMK_Conferencing"> </a></span></span>

[<span data-ttu-id="02e0f-137">会議クライアント用の計画 (Web アプリおよび会議アプリ)</span><span class="sxs-lookup"><span data-stu-id="02e0f-137">Plan for Meetings clients (Web App and Meetings App)</span></span>](meetings-clients.md)

[<span data-ttu-id="02e0f-138">Skype for Business Server で Web ダウンロード可能なクライアントを展開する</span><span class="sxs-lookup"><span data-stu-id="02e0f-138">Deploy Web downloadable clients in Skype for Business Server</span></span>](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[<span data-ttu-id="02e0f-139">Skype 会議アプリでサポートされるプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="02e0f-139">Supported platforms for Skype Meetings App</span></span>](https://support.office.com/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
