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
description: Teams サービスや Exchange、SharePoint、OneDrive for Business といったその他の Office 365 コンポーネントが正常であることを確認することをお勧めします。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 219c484b4bf8eff35d78966820a3002e55aecbb7
ms.sourcegitcommit: 5d64e30a1984a4b1d9ff36e2e1721cb4bbf9e450
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "42706577"
---
<a name="verify-service-health-for-microsoft-teams"></a><span data-ttu-id="fb16a-103">Microsoft Teams のサービス正常性を確認する</span><span class="sxs-lookup"><span data-stu-id="fb16a-103">Verify service health for Microsoft Teams</span></span>
===========================================

<span data-ttu-id="fb16a-104">Microsoft Teams のサービス正常性は、Microsoft 365 管理センターに表示されます。</span><span class="sxs-lookup"><span data-stu-id="fb16a-104">Service health for Microsoft Teams is displayed on the Microsoft 365 admin center.</span></span> <span data-ttu-id="fb16a-105">問題のトラブルシューティングを行う前に、Teams サービスが正常に実行されていることを確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="fb16a-105">Before troubleshooting issues, it's a good practice to verify that the Teams service is healthy.</span></span>

<span data-ttu-id="fb16a-p102">さらに、Microsoft Teams は追加の Office 365 サービスの上に構築されるため、サービス正常性を確認する場合は、Exchange、SharePoint、OneDrive for Business の状態も検証する必要があります。これらのサービスのサービス正常性の問題 (Exchange でのアドレス帳のダウンロードが利用できないなどの問題) は必然的に Teams に影響を与えるものではありませんが、影響を受けるサービスに関する注意事項を確認して、Microsoft Teams に対する影響があるかどうかを判断する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb16a-p102">Also, keep in mind that, Microsoft Teams is built on top of additional Office 365 services, so when looking at Service Health, remember to also check the status of Exchange, SharePoint, and OneDrive for Business. Service Health issues for these other services does not automatically mean that Teams is impacted (e.g. Address Book downloads in Exchange are unavailable), but that you should review the advisories for those affected services to determine if there is an impact to Microsoft Teams.</span></span>

![[サービス正常性] ページのスクリーンショット。](media/Verify_service_health_for_Microsoft_Teams_image1.png)

![Microsoft Teams サービスが正常であることを示すスクリーンショット。](media/Verify_service_health_for_Microsoft_Teams_image2.png)
