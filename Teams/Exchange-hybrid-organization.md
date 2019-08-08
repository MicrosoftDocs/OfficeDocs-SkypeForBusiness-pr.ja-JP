---
title: Microsoft Teams で使用する Exchange ハイブリッド展開の組織を構成する
author: dstrome
ms.author: dstrome
manager: serdars
ms.date: 09/25/2017
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: dstrome
description: Microsoft Teams で使用する Exchange ハイブリッド展開の組織を構成する方法について説明します。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 68b2fee13668db8ba3986302d58bc16b0fa89080
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36235204"
---
<a name="configure-an-exchange-hybrid-organization-for-use-with-microsoft-teams"></a><span data-ttu-id="74e5e-103">Microsoft Teams で使用する Exchange ハイブリッド展開の組織を構成する</span><span class="sxs-lookup"><span data-stu-id="74e5e-103">Configure an Exchange hybrid organization for use with Microsoft Teams</span></span>
======================================================================

<span data-ttu-id="74e5e-104">通常、Microsoft Teams で使用するために Exchange Online 機能を構成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="74e5e-104">Generally, you should not have to configure any Exchange Online functionality for use with Microsoft Teams.</span></span> <span data-ttu-id="74e5e-105">ただし、Exchange ハイブリッドシナリオの場合、グループメンバーシップが Exchange Server (オンプレミス) と Exchange Online の間で同期されるようにするために、以下の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="74e5e-105">However, for Exchange Hybrid scenarios, there are steps necessary to ensure Group memberships are synchronized between Exchange Server (on-premises) and Exchange Online.</span></span> <span data-ttu-id="74e5e-106">これには、Azure AD Connect のグループ書き戻し機能と、さまざまな初期化スクリプトが含まれます。[オンプレミスの Exchange ハイブリッドを使用して Office 365 グループを構成](https://go.microsoft.com/fwlink/?linkid=854389)します。</span><span class="sxs-lookup"><span data-stu-id="74e5e-106">This involves enablement of Group Writeback functionality in Azure AD Connect along with various initialization scripts: [Configure Office 365 Groups with on-premises Exchange hybrid](https://go.microsoft.com/fwlink/?linkid=854389).</span></span>
