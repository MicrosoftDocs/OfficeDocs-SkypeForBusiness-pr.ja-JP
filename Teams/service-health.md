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
description: Teams サービスが正常であることと、Exchange、SharePoint、OneDrive for Business などの他の Microsoft 365 または Office 365 コンポーネントを確認することをお勧めします。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 600bf8802dfb76dc1e96534be0ee303354267661
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2020
ms.locfileid: "46581838"
---
<a name="verify-service-health-for-microsoft-teams"></a><span data-ttu-id="5e8c1-103">Microsoft Teams のサービス正常性を確認する</span><span class="sxs-lookup"><span data-stu-id="5e8c1-103">Verify service health for Microsoft Teams</span></span>
===========================================

<span data-ttu-id="5e8c1-104">Microsoft Teams のサービス正常性は、Microsoft 365 管理センターに表示されます。</span><span class="sxs-lookup"><span data-stu-id="5e8c1-104">Service health for Microsoft Teams is displayed on the Microsoft 365 admin center.</span></span> <span data-ttu-id="5e8c1-105">問題のトラブルシューティングを行う前に、Teams サービスが正常に実行されていることを確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5e8c1-105">Before troubleshooting issues, it's a good practice to verify that the Teams service is healthy.</span></span> <span data-ttu-id="5e8c1-106"><a href=" https://admin.microsoft.com/adminportal/home?ref=servicehealth" target="_blank">Teams サービス正常性</a>コンソールに移動して、サービス正常性を確認します。</span><span class="sxs-lookup"><span data-stu-id="5e8c1-106">Go to the <a href=" https://admin.microsoft.com/adminportal/home?ref=servicehealth" target="_blank">Teams Service Health</a> console to review the service health.</span></span>

<span data-ttu-id="5e8c1-107">また、microsoft Teams は、他の Microsoft 365 または Office 365 サービスの上に構築されているため、サービスの正常性を確認するときには、Exchange、SharePoint、OneDrive for Business の状態も確認する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="5e8c1-107">Also, keep in mind that, Microsoft Teams is built on top of additional Microsoft 365 or Office 365 services, so when looking at Service Health, remember to also check the status of Exchange, SharePoint, and OneDrive for Business.</span></span> <span data-ttu-id="5e8c1-108">その他のサービスのサービス正常性の問題により、チームが影響を受けることはありません (Exchange でのアドレス帳のダウンロードは利用できません)。ただし、Microsoft Teams への影響があるかどうかを判断するために、影響を受けるサービスのアドバイザリを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5e8c1-108">Service Health issues for these other services does not automatically mean that Teams is impacted (e.g. Address Book downloads in Exchange are unavailable), but that you should review the advisories for those affected services to determine if there is an impact to Microsoft Teams.</span></span>

![[サービス正常性] ページのスクリーンショット。](media/Verify_service_health_for_Microsoft_Teams_image1.png)

![Microsoft Teams サービスが正常であることを示すスクリーンショット。](media/Verify_service_health_for_Microsoft_Teams_image2.png)


## <a name="related-topics"></a><span data-ttu-id="5e8c1-111">関連トピック</span><span class="sxs-lookup"><span data-stu-id="5e8c1-111">Related topics</span></span>

[<span data-ttu-id="5e8c1-112">Teams のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="5e8c1-112">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)