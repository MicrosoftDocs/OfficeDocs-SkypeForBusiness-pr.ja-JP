---
title: "Microsoft Teams で使用する Exchange ハイブリッド展開の組織を構成する | Microsoft サポート"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Microsoft Teams で使用する Exchange ハイブリッド展開の組織を構成する方法について説明します。"
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 9a046dd3eb2c36e84da913c2aad8b5606f019b04
ms.sourcegitcommit: 2e557e90b4e30fe99ff9df3897b8e54f38ea2f2e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2017
---
<a name="configure-an-exchange-hybrid-organization-for-use-with-microsoft-teams"></a><span data-ttu-id="181fb-103">Microsoft Teams で使用する Exchange ハイブリッド展開の組織を構成する</span><span class="sxs-lookup"><span data-stu-id="181fb-103">Configure an Exchange hybrid organization for use with Microsoft Teams</span></span>
======================================================================

<span data-ttu-id="181fb-p101">通常、Microsoft Teams で使用するために Exchange Online の機能を構成する必要はありません。ただし、Exchange ハイブリッドのシナリオでは、Exchange Server (オンプレミス) と Exchange Online 間でグループ メンバーシップを同期するために必要な手順を行う必要があります。この手順では、Azure AD Connect や様々な初期化スクリプトでグループの書き戻し機能を有効にします。「[オンプレミスの Exchange ハイブリッドを使用して Office 365 グループを構成する](https://go.microsoft.com/fwlink/?linkid=854389)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="181fb-p101">Generally, you should not have to configure any Exchange Online functionality for use with Microsoft Teams. However, for Exchange Hybrid scenarios, there are steps necessary to ensure Group memberships are synchronized between Exchange Server (on-premises) and Exchange Online. This involves enablement of Group Writeback functionality in Azure AD Connect along with various initialization scripts: [Configure Office 365 Groups with on-premises Exchange hybrid](https://go.microsoft.com/fwlink/?linkid=854389)</span></span>
