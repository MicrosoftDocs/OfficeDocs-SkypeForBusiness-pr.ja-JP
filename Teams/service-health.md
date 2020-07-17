---
title: Microsoft Teams のサービス正常性を確認する
ms.reviewer: ''
author: LolaJacobsen
ms.author: lolaj
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
description: Teams サービスが正常であることと、Exchange、SharePoint、OneDrive for Business などの他の Microsoft 365 または Office 365 コンポーネントを確認することをお勧めします。
appliesto:
- Microsoft Teams
ms.openlocfilehash: c30a4da2a37f75540c2b81a1f0d37e2c1e348339
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085523"
---
<a name="verify-service-health-for-microsoft-teams"></a><span data-ttu-id="879af-103">Microsoft Teams のサービス正常性を確認する</span><span class="sxs-lookup"><span data-stu-id="879af-103">Verify service health for Microsoft Teams</span></span>
===========================================

<span data-ttu-id="879af-104">Microsoft Teams のサービス正常性は、Microsoft 365 管理センターに表示されます。</span><span class="sxs-lookup"><span data-stu-id="879af-104">Service health for Microsoft Teams is displayed on the Microsoft 365 admin center.</span></span> <span data-ttu-id="879af-105">問題のトラブルシューティングを行う前に、Teams サービスが正常に実行されていることを確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="879af-105">Before troubleshooting issues, it's a good practice to verify that the Teams service is healthy.</span></span> <span data-ttu-id="879af-106"><a href=" https://admin.microsoft.com/adminportal/home?ref=servicehealth" target="_blank">Teams サービス正常性</a>コンソールに移動して、サービス正常性を確認します。</span><span class="sxs-lookup"><span data-stu-id="879af-106">Go to the <a href=" https://admin.microsoft.com/adminportal/home?ref=servicehealth" target="_blank">Teams Service Health</a> console to review the service health.</span></span>

<span data-ttu-id="879af-107">また、microsoft Teams は、他の Microsoft 365 または Office 365 サービスの上に構築されているため、サービスの正常性を確認するときには、Exchange、SharePoint、OneDrive for Business の状態も確認する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="879af-107">Also, keep in mind that, Microsoft Teams is built on top of additional Microsoft 365 or Office 365 services, so when looking at Service Health, remember to also check the status of Exchange, SharePoint, and OneDrive for Business.</span></span> <span data-ttu-id="879af-108">その他のサービスのサービス正常性の問題により、チームが影響を受けることはありません (Exchange でのアドレス帳のダウンロードは利用できません)。ただし、Microsoft Teams への影響があるかどうかを判断するために、影響を受けるサービスのアドバイザリを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="879af-108">Service Health issues for these other services does not automatically mean that Teams is impacted (e.g. Address Book downloads in Exchange are unavailable), but that you should review the advisories for those affected services to determine if there is an impact to Microsoft Teams.</span></span>

![[サービス正常性] ページのスクリーンショット。](media/Verify_service_health_for_Microsoft_Teams_image1.png)

![Microsoft Teams サービスが正常であることを示すスクリーンショット。](media/Verify_service_health_for_Microsoft_Teams_image2.png)


## <a name="related-topics"></a><span data-ttu-id="879af-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="879af-111">Related topics</span></span>

[<span data-ttu-id="879af-112">チームのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="879af-112">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)