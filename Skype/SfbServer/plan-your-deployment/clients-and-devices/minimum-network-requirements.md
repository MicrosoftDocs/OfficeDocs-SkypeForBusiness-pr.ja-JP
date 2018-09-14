---
title: Skype 会議アプリの最小ネットワーク要件
ms.author: jambirk
author: jambirk
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 6/4/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d9666787-e72b-41e1-ba37-aec5fb849a10
description: '組織で Office 365 を使用しないしを行っている組織でホストされている会議にアクセスする必要があります: の概要情報です。'
ms.openlocfilehash: 00862a4acecb8a5e6555f44d9416a2efa5834e61
ms.sourcegitcommit: b265545216ff36772d5dc2df381a9046bc71098e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/13/2018
ms.locfileid: "23965906"
---
# <a name="skype-meetings-app-minimum-network-requirements"></a><span data-ttu-id="edfde-103">Skype 会議アプリの最小ネットワーク要件</span><span class="sxs-lookup"><span data-stu-id="edfde-103">Skype Meetings App minimum network requirements</span></span>
 
<span data-ttu-id="edfde-104">**の概要:** 組織 Office 365 を使用しないを行っている組織でホストされている会議にアクセスする必要があるユーザーの情報です。</span><span class="sxs-lookup"><span data-stu-id="edfde-104">**Summary:**  Information for organizations who don't use Office 365 and need to access meetings hosted by organizations that do.</span></span> <span data-ttu-id="edfde-105">この記事はこれらのアプリのユーザー向けのものではありません。</span><span class="sxs-lookup"><span data-stu-id="edfde-105">This article is not intended for the users of these apps.</span></span>
  
<span data-ttu-id="edfde-106">Skype 会議アプリケーションを使用して、オンライン ビジネスの Skype でホストされている会議に参加できるように、組織のネットワーク管理者が Office 365 を使用しないユーザーには、ホワイト リストや、Fqdn、ip アドレス、およびポートは、以下に説明を使用することが必要があります。</span><span class="sxs-lookup"><span data-stu-id="edfde-106">To allow users to use Skype Meetings App to  attend meetings hosted in Skype for Business Online, network administrators of organizations who don't use Office 365 should whitelist or otherwise make available the FQDNs, IPs, and ports mentioned below.</span></span>

## <a name="requirements-for-skype-meetings-app-connectivity"></a><span data-ttu-id="edfde-107">Skype 会議アプリの接続の要件</span><span class="sxs-lookup"><span data-stu-id="edfde-107">Requirements for Skype Meetings App connectivity</span></span>

<span data-ttu-id="edfde-108">ここで記載されている情報は、 [Office 365 の Url と IP アドレスの範囲](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)詳細を提供しは必ず、最新のサブセットです。</span><span class="sxs-lookup"><span data-stu-id="edfde-108">The information listed here is a subset of [Office 365 URLs and IP address ranges](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US), which provides more depth and will always be the most up to date.</span></span>
                    
 
|<span data-ttu-id="edfde-109">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="edfde-109">App</span></span> |<span data-ttu-id="edfde-110">宛先の FQDN</span><span class="sxs-lookup"><span data-stu-id="edfde-110">Destination FQDNs</span></span>  |<span data-ttu-id="edfde-111">IP アドレス</span><span class="sxs-lookup"><span data-stu-id="edfde-111">IP Addresses</span></span>  |<span data-ttu-id="edfde-112">ポート</span><span class="sxs-lookup"><span data-stu-id="edfde-112">Ports</span></span>  |
|---|---------|---------|---------|
|<span data-ttu-id="edfde-113">**Skype 会議アプリ**</span><span class="sxs-lookup"><span data-stu-id="edfde-113">**Skype Meetings App**</span></span> | <span data-ttu-id="edfde-114">\*。 lync.com</span><span class="sxs-lookup"><span data-stu-id="edfde-114">\*.lync.com</span></span> <br/><span data-ttu-id="edfde-115">\*。 infra.lync.com</span><span class="sxs-lookup"><span data-stu-id="edfde-115">\*.infra.lync.com</span></span><br/><span data-ttu-id="edfde-116">\*。 pipe.aria.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="edfde-116">\*.pipe.aria.microsoft.com</span></span><br/><span data-ttu-id="edfde-117">\*。 sfbassets.com</span><span class="sxs-lookup"><span data-stu-id="edfde-117">\*.sfbassets.com</span></span><br/><span data-ttu-id="edfde-118">\*。 msecnd.net</span><span class="sxs-lookup"><span data-stu-id="edfde-118">\*.msecnd.net</span></span><br/><span data-ttu-id="edfde-119">\*ブロードキャスト<span></span>です officeapps.live.com。</span><span class="sxs-lookup"><span data-stu-id="edfde-119">\*broadcast<span></span>.officeapps.live.com</span></span> <br/><span data-ttu-id="edfde-120">\*powerpoint<span></span>です officeapps.live.com。</span><span class="sxs-lookup"><span data-stu-id="edfde-120">\*powerpoint<span></span>.officeapps.live.com</span></span> <br/><span data-ttu-id="edfde-121">\*。 office.live.com</span><span class="sxs-lookup"><span data-stu-id="edfde-121">\*.office.live.com</span></span><br/><span data-ttu-id="edfde-122">\*。 cdn.office.net</span><span class="sxs-lookup"><span data-stu-id="edfde-122">\*.cdn.office.net</span></span><br/><span data-ttu-id="edfde-123">microsoft.com の \*.s</span><span class="sxs-lookup"><span data-stu-id="edfde-123">\*.s-microsoft.com</span></span><br/>        |   <span data-ttu-id="edfde-124">これらの IP アドレスは頻繁に更新されます。</span><span class="sxs-lookup"><span data-stu-id="edfde-124">These IP addresses are frequently updated.</span></span>  <span data-ttu-id="edfde-125">[ビジネス IP の範囲の Skype](https://support.office.com/en-us/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip)と[Office オンラインの IP 範囲](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="edfde-125">See [Skype for Business IP ranges](https://support.office.com/en-us/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) as well as [Office Online IP Ranges](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)</span></span>         |<span data-ttu-id="edfde-126">TCP: 80 &amp; 443</span><span class="sxs-lookup"><span data-stu-id="edfde-126">TCP: 80 &amp; 443</span></span><br/><span data-ttu-id="edfde-127">UDP: 3478 ～ 3481</span><span class="sxs-lookup"><span data-stu-id="edfde-127">UDP: 3478-3481</span></span><br/>
|<span data-ttu-id="edfde-128">**Teams**</span><span class="sxs-lookup"><span data-stu-id="edfde-128">**Teams**</span></span>    | <span data-ttu-id="edfde-129">\*<span></span>。 microsoft.com</span><span class="sxs-lookup"><span data-stu-id="edfde-129">\*<span></span>.microsoft.com</span></span> <br/><span data-ttu-id="edfde-130">\*<span></span>。 skype.com</span><span class="sxs-lookup"><span data-stu-id="edfde-130">\*<span></span>.skype.com</span></span> | <span data-ttu-id="edfde-131">これらの IP アドレスは頻繁に更新されます。</span><span class="sxs-lookup"><span data-stu-id="edfde-131">These IP addresses are frequently updated.</span></span>  <span data-ttu-id="edfde-132">[ビジネス IP の範囲の Skype](https://support.office.com/en-us/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip)と[Office オンラインの IP 範囲](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="edfde-132">See [Skype for Business IP ranges](https://support.office.com/en-us/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) as well as [Office Online IP Ranges](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)</span></span>      |<span data-ttu-id="edfde-133">TCP: 443</span><span class="sxs-lookup"><span data-stu-id="edfde-133">TCP:  443</span></span> <br/> <span data-ttu-id="edfde-134">UDP: 3478 ～ 3481</span><span class="sxs-lookup"><span data-stu-id="edfde-134">UDP: 3478-3481</span></span>

## <a name="see-also"></a><span data-ttu-id="edfde-135">この手順は役に立ちましたか? 役に立った場合は、この記事の下でお知らせください。役に立たなかった場合は、わかりにくかった部分をお知らせください。いただいたフィードバックを元に手順を再確認します。</span><span class="sxs-lookup"><span data-stu-id="edfde-135">See also</span></span>
<span data-ttu-id="edfde-136"><a name="BKMK_Conferencing"> </a></span><span class="sxs-lookup"><span data-stu-id="edfde-136"></span></span>

[<span data-ttu-id="edfde-137">会議クライアント用の計画 (Web アプリおよび会議アプリ)</span><span class="sxs-lookup"><span data-stu-id="edfde-137">Plan for Meetings clients (Web App and Meetings App)</span></span>](meetings-clients.md)

[<span data-ttu-id="edfde-138">Skype のダウンロード可能なクライアントの Web をビジネスのサーバーの展開します。</span><span class="sxs-lookup"><span data-stu-id="edfde-138">Deploy Web downloadable clients in Skype for Business Server</span></span>](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[<span data-ttu-id="edfde-139">Skype 会議アプリケーションでサポートされるプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="edfde-139">Supported platforms for Skype Meetings App</span></span>](https://support.office.com/en-US/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)