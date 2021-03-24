---
title: Skype for Business Server の個々の SIP トランクに関する情報を表示する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Skype for Business Server では、複数のトランクを 1 つの PSTN ゲートウェイに割り当てることができます。つまり、ゲートウェイとトランクは同じではなく、管理者は Get-CsTrunk コマンドレットを使用して個々の SIP トランクに関する情報を表示する必要があります。
ms.openlocfilehash: eebba2982a6f574ca2af99609f19ba5426139acb
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103003"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a><span data-ttu-id="33047-103">Skype for Business Server の個々の SIP トランクに関する情報を表示する</span><span class="sxs-lookup"><span data-stu-id="33047-103">View information about individual SIP trunks in Skype for Business Server</span></span>

<span data-ttu-id="33047-104">Skype for Business Server では、複数のトランクを 1 つの PSTN ゲートウェイに割り当てることができます。つまり、ゲートウェイとトランクは同じではなく、管理者は [Get-CsTrunk](/powershell/module/skype/Get-CsTrunk) コマンドレットを使用して個々の SIP トランクに関する情報を表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="33047-104">In Skype for Business Server, multiple trunks can be assigned to a single PSTN gateway; this means that gateways and trunks are not one and the same, and that administrators must use the [Get-CsTrunk](/powershell/module/skype/Get-CsTrunk) cmdlet to view information about an individual SIP trunk.</span></span>

<span data-ttu-id="33047-105">このGet-CsTrunkは、Skype for Business Server 管理シェルから、またはサーバーのリモート セッションから実行Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="33047-105">The Get-CsTrunk cmdlet can be run either from the  Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span>

<span data-ttu-id="33047-106">**すべての SIP トランクの情報を表示するには**</span><span class="sxs-lookup"><span data-stu-id="33047-106">**To view information for all your SIP trunks**</span></span>

<span data-ttu-id="33047-107">次のコマンドは、組織で使用中のすべての SIP トランクに関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="33047-107">The following command returns information about all the SIP trunks in use in your organization:</span></span>

`Get-CsTrunk`

<span data-ttu-id="33047-108">**特定の SIP トランクの情報を表示するには**</span><span class="sxs-lookup"><span data-stu-id="33047-108">**To view information for a specific SIP trunk**</span></span>

<span data-ttu-id="33047-109">このコマンドは、PstnGateway:192.168.0.240 という Identity を持つ SIP トランクに関する情報のみを返します。</span><span class="sxs-lookup"><span data-stu-id="33047-109">This command returns information only for the SIP trunk with the Identity PstnGateway:192.168.0.240:</span></span>

`Get-CsTrunk -Identity "PstnGateway:192.168.0.240"`

<span data-ttu-id="33047-110">**プールに割り当てられているすべての SIP トランクに関する情報の表示**</span><span class="sxs-lookup"><span data-stu-id="33047-110">**Viewing Information for All the SIP Trunks Assigned to a Pool**</span></span>

<span data-ttu-id="33047-111">この例では、プール atl-cs-001.litwareinc.com に割り当てられているすべての SIP トランクについて情報が返されます。</span><span class="sxs-lookup"><span data-stu-id="33047-111">In this example, information is returned for all the SIP trunks assigned to the pool atl-cs-001.litwareinc.com:</span></span>

`Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"`