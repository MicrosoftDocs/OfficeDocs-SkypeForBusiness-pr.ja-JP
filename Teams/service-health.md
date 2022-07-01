---
title: Microsoft Teams のサービス正常性を確認する
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
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
description: Teams サービスが正常であり、Exchange、SharePoint、OneDrive for Businessなどの他の Microsoft 365 またはOffice 365 コンポーネントも正常であることを確認することをお勧めします。
appliesto:
- Microsoft Teams
ms.openlocfilehash: a3f410a24d77a0ab18d94679896bae96b1fecdd8
ms.sourcegitcommit: 472e46b6eb907f41920516616683a61f0fc6f741
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/30/2022
ms.locfileid: "66563795"
---
# <a name="verify-service-health-for-microsoft-teams"></a>Microsoft Teams のサービス正常性を確認する

Microsoft Teams のサービス正常性は、Microsoft 365 管理センターに表示されます。 問題のトラブルシューティングを行う前に、Teams サービスが正常であることを確認することをお勧めします。 <a href=" https://admin.microsoft.com/adminportal/home?ref=servicehealth" target="_blank">Teams Service Health</a> コンソールに移動して、サービスの正常性を確認します。

また、Microsoft Teams は他の Microsoft 365 またはOffice 365 サービスの上に構築されているため、Service Health を確認するときは、Exchange、SharePoint、OneDrive for Businessの状態も必ず確認してください。 これらの他のサービスの Service Health の問題は、自動的に Teams が影響を受けるという意味ではありませんが (たとえば、Exchange でのアドレス帳のダウンロードは利用できません)、影響を受けるサービスのアドバイザリを確認して、Microsoft Teams に影響があるかどうかを判断する必要があります。

![[サービス正常性] ページのスクリーンショット。](media/Verify_service_health_for_Microsoft_Teams_image1.png)

![Microsoft Teams サービスが正常であることを示すスクリーンショット。](media/Verify_service_health_for_Microsoft_Teams_image2.png)


## <a name="related-topics"></a>関連項目

[Teams のトラブルシューティング](/MicrosoftTeams/troubleshoot/teams)
