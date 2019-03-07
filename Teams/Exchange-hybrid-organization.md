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
ms.openlocfilehash: e52c757b3e2456561d664b07667a5f08fd1c1617
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/07/2019
ms.locfileid: "30458933"
---
<a name="configure-an-exchange-hybrid-organization-for-use-with-microsoft-teams"></a><span data-ttu-id="08a42-103">Microsoft Teams で使用する Exchange ハイブリッド展開の組織を構成する</span><span class="sxs-lookup"><span data-stu-id="08a42-103">Configure an Exchange hybrid organization for use with Microsoft Teams</span></span>
======================================================================

<span data-ttu-id="08a42-p101">通常、Microsoft Teams で使用するために Exchange Online の機能を構成する必要はありません。ただし、Exchange ハイブリッドのシナリオでは、Exchange Server (オンプレミス) と Exchange Online 間でグループ メンバーシップを同期するために必要な手順を行う必要があります。この手順では、Azure AD Connect や様々な初期化スクリプトでグループの書き戻し機能を有効にします。「[オンプレミスの Exchange ハイブリッドを使用して Office 365 グループを構成する](https://go.microsoft.com/fwlink/?linkid=854389)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="08a42-p101">Generally, you should not have to configure any Exchange Online functionality for use with Microsoft Teams. However, for Exchange Hybrid scenarios, there are steps necessary to ensure Group memberships are synchronized between Exchange Server (on-premises) and Exchange Online. This involves enablement of Group Writeback functionality in Azure AD Connect along with various initialization scripts: [Configure Office 365 Groups with on-premises Exchange hybrid](https://go.microsoft.com/fwlink/?linkid=854389)</span></span>
