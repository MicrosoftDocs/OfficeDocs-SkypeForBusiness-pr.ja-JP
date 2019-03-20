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
description: '概要: Office 365 を使用している組織が開催する会議に、Office 365 を使用していない組織がアクセスすることが必要な場合に役立つ情報です。'
ms.openlocfilehash: 00862a4acecb8a5e6555f44d9416a2efa5834e61
ms.sourcegitcommit: b265545216ff36772d5dc2df381a9046bc71098e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/13/2018
ms.locfileid: "23965906"
---
# <a name="skype-meetings-app-minimum-network-requirements"></a><span data-ttu-id="525ef-103">Skype 会議アプリの最小ネットワーク要件</span><span class="sxs-lookup"><span data-stu-id="525ef-103">Skype Meetings App minimum network requirements</span></span>
 
<span data-ttu-id="525ef-104">**概要:** Office 365 を使用している組織が開催する会議に、Office 365 を使用していない組織がアクセスすることが必要な場合に役立つ情報です。</span><span class="sxs-lookup"><span data-stu-id="525ef-104">Summary: Information for organizations who don't use nm-office-365-short and need to access meetings hosted by organizations that do.</span></span> <span data-ttu-id="525ef-105">この記事はこれらのアプリのユーザーを対象にしていません。</span><span class="sxs-lookup"><span data-stu-id="525ef-105">This article is not intended for the users of these apps.</span></span>
  
<span data-ttu-id="525ef-106">ユーザーが Skype for Business Online で開催された会議に Skype 会議アプリを使用して出席できるようにするには、Office 365 を使用していないネットワーク管理者が、下記の FQDN、IP、およびポートをホワイトリストに記載するか、そうでない場合はそれらを利用できる状態にします。</span><span class="sxs-lookup"><span data-stu-id="525ef-106">To allow users to use skype16_MeetingsApp to  attend meetings hosted in skype16_online, network administrators of organizations who don't use nm-office-365-short should whitelist or otherwise make available the FQDNs, IPs, and ports mentioned below.</span></span>

## <a name="requirements-for-skype-meetings-app-connectivity"></a><span data-ttu-id="525ef-107">Skype 会議アプリの接続の要件</span><span class="sxs-lookup"><span data-stu-id="525ef-107">Requirements for Skype Meetings App connectivity</span></span>

<span data-ttu-id="525ef-108">「[Office 365 の URL と IP アドレスの範囲](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)」には、常に最新の情報が詳細に記載されていますが、ここで示されている情報はその一部です。</span><span class="sxs-lookup"><span data-stu-id="525ef-108">The information listed here is a subset of [Office 365 URLs and IP address rangeshttps://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US), which provides more depth and will always be the most up to date.</span></span>
                    
 
|<span data-ttu-id="525ef-109">アプリ</span><span class="sxs-lookup"><span data-stu-id="525ef-109">App preferences</span></span> |<span data-ttu-id="525ef-110">宛先の FQDN</span><span class="sxs-lookup"><span data-stu-id="525ef-110">Destination FQDNs</span></span>  |<span data-ttu-id="525ef-111">IP アドレス</span><span class="sxs-lookup"><span data-stu-id="525ef-111">IP Addresses</span></span>  |<span data-ttu-id="525ef-112">ポート</span><span class="sxs-lookup"><span data-stu-id="525ef-112">Ports</span></span>  |
|---|---------|---------|---------|
|<span data-ttu-id="525ef-113">**Skype 会議アプリ**</span><span class="sxs-lookup"><span data-stu-id="525ef-113">**Skype Meetings App**</span></span> | <span data-ttu-id="525ef-114">\*.lync.com</span><span class="sxs-lookup"><span data-stu-id="525ef-114">\*\*.lync.com</span></span> <br/><span data-ttu-id="525ef-115">\*.infra.lync.com</span><span class="sxs-lookup"><span data-stu-id="525ef-115">\*\*.infra.lync.com</span></span><br/><span data-ttu-id="525ef-116">\*.pipe.aria.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="525ef-116">\*\*.pipe.aria.microsoft.com</span></span><br/><span data-ttu-id="525ef-117">\*.sfbassets.com</span><span class="sxs-lookup"><span data-stu-id="525ef-117">\*\*.sfbassets.com</span></span><br/><span data-ttu-id="525ef-118">\*.msecnd.net</span><span class="sxs-lookup"><span data-stu-id="525ef-118">\*\*.msecnd.net</span></span><br/><span data-ttu-id="525ef-119">\*broadcast<span></span>.officeapps.live.com</span><span class="sxs-lookup"><span data-stu-id="525ef-119">\*broadcast.officeapps.live.com
</span></span> <br/><span data-ttu-id="525ef-120">\*powerpoint<span></span>.officeapps.live.com</span><span class="sxs-lookup"><span data-stu-id="525ef-120">\*powerpoint.officeapps.live.com
</span></span> <br/><span data-ttu-id="525ef-121">\*.office.live.com</span><span class="sxs-lookup"><span data-stu-id="525ef-121">\*\*.office.live.com</span></span><br/><span data-ttu-id="525ef-122">\*.cdn.office.net</span><span class="sxs-lookup"><span data-stu-id="525ef-122">\*\*.cdn.office.net</span></span><br/><span data-ttu-id="525ef-123">\*.s-microsoft.com</span><span class="sxs-lookup"><span data-stu-id="525ef-123">\*.s-microsoft.com</span></span><br/>        |   <span data-ttu-id="525ef-124">これらの IP アドレスは頻繁に更新されます。</span><span class="sxs-lookup"><span data-stu-id="525ef-124">These IP addresses are frequently updated.</span></span>  <span data-ttu-id="525ef-125">「[Skype for Business の IP 範囲](https://support.office.com/en-us/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip)」および「[Office Online の IP 範囲](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)」をご覧ください</span><span class="sxs-lookup"><span data-stu-id="525ef-125">See [Skype for Business IP ranges](https://support.office.com/en-us/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) as well as [Office Online IP Ranges](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)</span></span>         |<span data-ttu-id="525ef-126">TCP: 80、443</span><span class="sxs-lookup"><span data-stu-id="525ef-126">TCP: 80 & 443</span></span><br/><span data-ttu-id="525ef-127">UDP: 3478 ～ 3481</span><span class="sxs-lookup"><span data-stu-id="525ef-127">UDP: 3478-3481</span></span><br/>
|<span data-ttu-id="525ef-128">**Teams**</span><span class="sxs-lookup"><span data-stu-id="525ef-128">**Teams**</span></span>    | <span data-ttu-id="525ef-129">\*<span></span>.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="525ef-129">\*.microsoft.com 
</span></span> <br/><span data-ttu-id="525ef-130">\*<span></span>.skype.com</span><span class="sxs-lookup"><span data-stu-id="525ef-130">\*.skype.com</span></span> | <span data-ttu-id="525ef-131">これらの IP アドレスは頻繁に更新されます。</span><span class="sxs-lookup"><span data-stu-id="525ef-131">These IP addresses are frequently updated.</span></span>  <span data-ttu-id="525ef-132">「[Skype for Business の IP 範囲](https://support.office.com/en-us/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip)」および「[Office Online の IP 範囲](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)」をご覧ください</span><span class="sxs-lookup"><span data-stu-id="525ef-132">See [Skype for Business IP ranges](https://support.office.com/en-us/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) as well as [Office Online IP Ranges](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)</span></span>      |<span data-ttu-id="525ef-133">TCP: 443</span><span class="sxs-lookup"><span data-stu-id="525ef-133">TCP:  443</span></span> <br/> <span data-ttu-id="525ef-134">UDP: 3478 ～ 3481</span><span class="sxs-lookup"><span data-stu-id="525ef-134">UDP: 3478-3481</span></span>

## <a name="see-also"></a><span data-ttu-id="525ef-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="525ef-135">See also</span></span>
<span data-ttu-id="525ef-136"><a name="BKMK_Conferencing"> </a></span><span class="sxs-lookup"><span data-stu-id="525ef-136"></span></span>

[<span data-ttu-id="525ef-137">会議クライアント用の計画 (Web アプリおよび会議アプリ)</span><span class="sxs-lookup"><span data-stu-id="525ef-137">Plan for Meetings clients (Web App and Meetings App)</span></span>](meetings-clients.md)

[<span data-ttu-id="525ef-138">Skype for Business Server で Web ダウンロード可能なクライアントを展開する</span><span class="sxs-lookup"><span data-stu-id="525ef-138">Deploy Web downloadable clients in Skype for Business Server 2015</span></span>](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

<span data-ttu-id="525ef-139">
  [Skype 会議アプリでサポートされるプラットフォーム](https://support.office.com/en-US/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)</span><span class="sxs-lookup"><span data-stu-id="525ef-139">[Supported platforms for Skype Meetings App](https://support.office.com/en-US/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)</span></span>