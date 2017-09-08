---
title: "Microsoft Teams で使用する Exchange ハイブリッド展開の組織を構成する | Microsoft サポート"
author: LolaJacobsen
ms.author: lolaj
manager: serdar
ms.date: 08/10/2017
ms.topic: overview
ms.prod: teams
description: "Microsoft Teams で使用する Exchange ハイブリッド展開の組織を構成する方法について説明します。"
ms.openlocfilehash: 0089de5dde421b4e4e1687defbf6addf4c9b93e0
ms.sourcegitcommit: 3b9b3f07f4f67cd5f43da68f48d62222d7e49167
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2017
---
<a name="configure-an-exchange-hybrid-organization-for-use-with-microsoft-teams"></a><span data-ttu-id="d49ef-103">Microsoft Teams で使用する Exchange ハイブリッド展開の組織を構成する</span><span class="sxs-lookup"><span data-stu-id="d49ef-103">Configure an Exchange hybrid organization for use with Microsoft Teams</span></span>
======================================================================

<span data-ttu-id="d49ef-p101">通常、Microsoft Teams で使用するために Exchange Online の機能を構成する必要はありません。ただし、Exchange ハイブリッドのシナリオでは、Exchange Server (オンプレミス) と Exchange Online 間でグループ メンバーシップを同期するために必要な手順を行う必要があります。この手順では、Azure AD Connect や様々な初期化スクリプトでグループの書き戻し機能を有効にします。「[オンプレミスの Exchange ハイブリッドを使用して Office 365 グループを構成する](https://go.microsoft.com/fwlink/?linkid=854389)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d49ef-p101">Generally, you should not have to configure any Exchange Online functionality for use with Microsoft Teams. However, for Exchange Hybrid scenarios, there are steps necessary to ensure Group memberships are synchronized between Exchange Server (on-premises) and Exchange Online. This involves enablement of Group Writeback functionality in Azure AD Connect along with various initialization scripts: [Configure Office 365 Groups with on-premises Exchange hybrid](https://go.microsoft.com/fwlink/?linkid=854389)</span></span>
