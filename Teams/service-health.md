---
title: "Microsoft Teams のサービス正常性を確認する"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Teams サービスや Exchange、SharePoint、OneDrive for Business といったその他の Office 365 コンポーネントが正常であることを確認することをお勧めします。"
appliesto:
- Microsoft Teams
ms.openlocfilehash: b6f3fb65770f86447a1463ec3ac054d22ffcbf6f
ms.sourcegitcommit: 85105cb4e42ae8eb6e7e76eaf6d4dd5b9568cf41
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2018
---
<a name="verify-service-health-for-microsoft-teams"></a><span data-ttu-id="40f27-103">Microsoft Teams のサービス正常性を確認する</span><span class="sxs-lookup"><span data-stu-id="40f27-103">Verify service health for Microsoft Teams</span></span>
===========================================

<span data-ttu-id="40f27-p101">Microsoft Teams のサービス正常性は Office 365 管理ポータルのメイン ページに表示されます。問題を解決する際には、まず最初に Teams サービスが正常であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="40f27-p101">Service health for Microsoft Teams is displayed on the Office 365 Admin portal main page. Before troubleshooting issues, it's a good practice to verify that the Teams service is healthy.</span></span>

<span data-ttu-id="40f27-p102">さらに、Microsoft Teams は追加の Office 365 サービスの上に構築されるため、サービス正常性を確認する場合は、Exchange、SharePoint、OneDrive for Business の状態も検証する必要があります。これらのサービスのサービス正常性の問題 (Exchange でのアドレス帳のダウンロードが利用できないなどの問題) は必然的に Teams に影響を与えるものではありませんが、影響を受けるサービスに関する注意事項を確認して、Microsoft Teams に対する影響があるかどうかを判断する必要があります。</span><span class="sxs-lookup"><span data-stu-id="40f27-p102">Also, keep in mind that, Microsoft Teams is built on top of additional Office 365 services, so when looking at Service Health, remember to also check the status of Exchange, SharePoint, and OneDrive for Business. Service Health issues for these other services does not automatically mean that Teams is impacted (e.g. Address Book downloads in Exchange are unavailable), but that you should review the advisories for those affected services to determine if there is an impact to Microsoft Teams.</span></span>

![[サービス正常性] ページのスクリーンショット。](media/Verify_service_health_for_Microsoft_Teams_image1.png)

![Microsoft Teams サービスが正常であることを示すスクリーンショット。](media/Verify_service_health_for_Microsoft_Teams_image2.png)
