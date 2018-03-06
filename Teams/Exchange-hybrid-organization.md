---
title: "Microsoft Teams で使用する Exchange ハイブリッド展開の組織を構成する"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: crowe
description: "Microsoft Teams で使用する Exchange ハイブリッド展開の組織を構成する方法について説明します。"
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: d92a0434200c6ee0ee52830272a55741fa572a4e
ms.sourcegitcommit: 85105cb4e42ae8eb6e7e76eaf6d4dd5b9568cf41
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2018
---
<a name="configure-an-exchange-hybrid-organization-for-use-with-microsoft-teams"></a><span data-ttu-id="20c33-103">Microsoft Teams で使用する Exchange ハイブリッド展開の組織を構成する</span><span class="sxs-lookup"><span data-stu-id="20c33-103">Configure an Exchange hybrid organization for use with Microsoft Teams</span></span>
======================================================================

<span data-ttu-id="20c33-p101">通常、Microsoft Teams で使用するために Exchange Online の機能を構成する必要はありません。ただし、Exchange ハイブリッドのシナリオでは、Exchange Server (オンプレミス) と Exchange Online 間でグループ メンバーシップを同期するために必要な手順を行う必要があります。この手順では、Azure AD Connect や様々な初期化スクリプトでグループの書き戻し機能を有効にします。「[オンプレミスの Exchange ハイブリッドを使用して Office 365 グループを構成する](https://go.microsoft.com/fwlink/?linkid=854389)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="20c33-p101">Generally, you should not have to configure any Exchange Online functionality for use with Microsoft Teams. However, for Exchange Hybrid scenarios, there are steps necessary to ensure Group memberships are synchronized between Exchange Server (on-premises) and Exchange Online. This involves enablement of Group Writeback functionality in Azure AD Connect along with various initialization scripts: [Configure Office 365 Groups with on-premises Exchange hybrid](https://go.microsoft.com/fwlink/?linkid=854389)</span></span>
