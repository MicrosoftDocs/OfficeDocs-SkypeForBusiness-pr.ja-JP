---
title: Exchange ハイブリッド組織を構成する
author: dstrome
ms.author: dstrome
manager: serdars
ms.date: 09/25/2017
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: dstrome
description: グループメンバーシップを同期するために Microsoft Teams で使用する Exchange ハイブリッド組織を構成する方法について説明します。
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1061ce633dcd1db8f956a37143850deed9855e56
ms.sourcegitcommit: ab094058e3ffa974527fce8a331dad609ac19609
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/04/2020
ms.locfileid: "46551963"
---
<a name="configure-an-exchange-hybrid-organization-for-use-with-microsoft-teams"></a><span data-ttu-id="79993-103">Microsoft Teams で使用する Exchange ハイブリッド展開の組織を構成する</span><span class="sxs-lookup"><span data-stu-id="79993-103">Configure an Exchange hybrid organization for use with Microsoft Teams</span></span>
======================================================================

<span data-ttu-id="79993-104">通常、Microsoft Teams で使用するために Exchange Online 機能を構成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="79993-104">Generally, you should not have to configure any Exchange Online functionality for use with Microsoft Teams.</span></span> <span data-ttu-id="79993-105">ただし、Exchange ハイブリッドシナリオの場合、グループメンバーシップが Exchange Server (オンプレミス) と Exchange Online の間で同期されるようにするために、以下の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="79993-105">However, for Exchange Hybrid scenarios, there are steps necessary to ensure Group memberships are synchronized between Exchange Server (on-premises) and Exchange Online.</span></span> <span data-ttu-id="79993-106">これには、Azure AD Connect のグループ書き戻し機能と、さまざまな初期化スクリプトが含まれます。[オンプレミスの Exchange ハイブリッドを使用して Microsoft 365 グループを構成](https://docs.microsoft.com/exchange/hybrid-deployment/set-up-microsoft-365-groups)します。</span><span class="sxs-lookup"><span data-stu-id="79993-106">This involves enablement of Group Writeback functionality in Azure AD Connect along with various initialization scripts: [Configure Microsoft 365 Groups with on-premises Exchange hybrid](https://docs.microsoft.com/exchange/hybrid-deployment/set-up-microsoft-365-groups).</span></span>
