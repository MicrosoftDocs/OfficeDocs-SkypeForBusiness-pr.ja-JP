---
title: "Microsoft Teams で使用する Exchange ハイブリッド展開の組織を構成する"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Microsoft Teams で使用する Exchange ハイブリッド展開の組織を構成する方法について説明します。"
MS.collection: Strat_MT_TeamsAdmin
ms.openlocfilehash: 95b891394584d457f16a25b86d24614883443f9f
ms.sourcegitcommit: 3faedb6057da8650b06b05f9c9bdd941d5ade175
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/20/2017
---
<a name="configure-an-exchange-hybrid-organization-for-use-with-microsoft-teams"></a><span data-ttu-id="9f6aa-103">Microsoft Teams で使用する Exchange ハイブリッド展開の組織を構成する</span><span class="sxs-lookup"><span data-stu-id="9f6aa-103">Configure an Exchange hybrid organization for use with Microsoft Teams</span></span>
======================================================================

<span data-ttu-id="9f6aa-p101">通常、Microsoft Teams で使用するために Exchange Online の機能を構成する必要はありません。ただし、Exchange ハイブリッドのシナリオでは、Exchange Server (オンプレミス) と Exchange Online 間でグループ メンバーシップを同期するために必要な手順を行う必要があります。この手順では、Azure AD Connect や様々な初期化スクリプトでグループの書き戻し機能を有効にします。「[オンプレミスの Exchange ハイブリッドを使用して Office 365 グループを構成する](https://go.microsoft.com/fwlink/?linkid=854389)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9f6aa-p101">Generally, you should not have to configure any Exchange Online functionality for use with Microsoft Teams. However, for Exchange Hybrid scenarios, there are steps necessary to ensure Group memberships are synchronized between Exchange Server (on-premises) and Exchange Online. This involves enablement of Group Writeback functionality in Azure AD Connect along with various initialization scripts: [Configure Office 365 Groups with on-premises Exchange hybrid](https://go.microsoft.com/fwlink/?linkid=854389)</span></span>
