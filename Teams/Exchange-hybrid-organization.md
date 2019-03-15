---
title: Microsoft Teams で使用する Exchange ハイブリッド展開の組織を構成する
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: crowe
description: Microsoft Teams で使用する Exchange ハイブリッド展開の組織を構成する方法について説明します。
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d4dfc6b476498fef4484718a90f9c242a565cd64
ms.sourcegitcommit: bc2b227b4ac0a9521993f808a1361b4f9bc7faad
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "30568561"
---
<a name="configure-an-exchange-hybrid-organization-for-use-with-microsoft-teams"></a><span data-ttu-id="c31be-103">Microsoft Teams で使用する Exchange ハイブリッド展開の組織を構成する</span><span class="sxs-lookup"><span data-stu-id="c31be-103">Configure an Exchange hybrid organization for use with Microsoft Teams</span></span>
======================================================================

<span data-ttu-id="c31be-p101">一般に、マイクロソフトのチームで使用するための Exchange Online の機能を構成する必要はありません。ただし、Exchange ハイブリッド シナリオでは、手順があるグループのメンバーシップは、Exchange Server (設置型) および Exchange Online の間で同期することを確認するために必要です。Azure AD 接続すると、さまざまな初期化スクリプトでは、グループの書き戻し機能の有効化は、この: [Office 365 グループの構成で、オンプレミス Exchange ハイブリッド](https://go.microsoft.com/fwlink/?linkid=854389)。</span><span class="sxs-lookup"><span data-stu-id="c31be-p101">Generally, you should not have to configure any Exchange Online functionality for use with Microsoft Teams. However, for Exchange Hybrid scenarios, there are steps necessary to ensure Group memberships are synchronized between Exchange Server (on-premises) and Exchange Online. This involves enablement of Group Writeback functionality in Azure AD Connect along with various initialization scripts: [Configure Office 365 Groups with on-premises Exchange hybrid](https://go.microsoft.com/fwlink/?linkid=854389).</span></span>
