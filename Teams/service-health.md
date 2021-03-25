---
title: Microsoft Teams のサービス正常性を確認する
ms.reviewer: ''
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
f1.keywords:
- NOCSH
description: Teams サービスと、Exchange、SharePoint、OneDrive for Business などの他の Microsoft 365 または Office 365 コンポーネントが正常に機能する場合は、確認を行うのが良い方法です。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 53184bbdc25cc96e667cd8c0ddff9eae5bfdfe8c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51107513"
---
<a name="verify-service-health-for-microsoft-teams"></a><span data-ttu-id="6979c-103">Microsoft Teams のサービス正常性を確認する</span><span class="sxs-lookup"><span data-stu-id="6979c-103">Verify service health for Microsoft Teams</span></span>
===========================================

<span data-ttu-id="6979c-104">Microsoft Teams のサービス正常性は、Microsoft 365 管理センターに表示されます。</span><span class="sxs-lookup"><span data-stu-id="6979c-104">Service health for Microsoft Teams is displayed on the Microsoft 365 admin center.</span></span> <span data-ttu-id="6979c-105">問題のトラブルシューティングを行う前に、Teams サービスが正常に機能しているのを確認することをお使いください。</span><span class="sxs-lookup"><span data-stu-id="6979c-105">Before troubleshooting issues, it's a good practice to verify that the Teams service is healthy.</span></span> <span data-ttu-id="6979c-106">Teams サービス正常性コンソール <a href=" https://admin.microsoft.com/adminportal/home?ref=servicehealth" target="_blank">に移動して</a> 、サービスの正常性を確認します。</span><span class="sxs-lookup"><span data-stu-id="6979c-106">Go to the <a href=" https://admin.microsoft.com/adminportal/home?ref=servicehealth" target="_blank">Teams Service Health</a> console to review the service health.</span></span>

<span data-ttu-id="6979c-107">また、Microsoft Teams は追加の Microsoft 365 または Office 365 サービスの上に構築されている点に注意してください。サービス正常性を確認する場合は、Exchange、SharePoint、OneDrive for Business の状態も忘確認してください。</span><span class="sxs-lookup"><span data-stu-id="6979c-107">Also, keep in mind that, Microsoft Teams is built on top of additional Microsoft 365 or Office 365 services, so when looking at Service Health, remember to also check the status of Exchange, SharePoint, and OneDrive for Business.</span></span> <span data-ttu-id="6979c-108">これらの他のサービスのサービス正常性の問題は、Teams が自動的に影響を受けるという意味ではありません (Exchange でのアドレス帳のダウンロードは利用できません)。ただし、影響を受けるサービスの勧告を確認して、Microsoft Teams に影響を与えるかどうかを判断する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6979c-108">Service Health issues for these other services does not automatically mean that Teams is impacted (e.g. Address Book downloads in Exchange are unavailable), but that you should review the advisories for those affected services to determine if there is an impact to Microsoft Teams.</span></span>

![[サービス正常性] ページのスクリーンショット。](media/Verify_service_health_for_Microsoft_Teams_image1.png)

![Microsoft Teams サービスが正常であることを示すスクリーンショット。](media/Verify_service_health_for_Microsoft_Teams_image2.png)


## <a name="related-topics"></a><span data-ttu-id="6979c-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="6979c-111">Related topics</span></span>

[<span data-ttu-id="6979c-112">Teams のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="6979c-112">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)