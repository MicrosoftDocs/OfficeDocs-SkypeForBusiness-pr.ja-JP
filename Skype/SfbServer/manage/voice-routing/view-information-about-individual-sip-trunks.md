---
title: Skype for Business Server での個々の SIP トランクに関する情報の表示
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Skype for Business Server では、複数のトランクを1つの PSTN ゲートウェイに割り当てることができます。これは、ゲートウェイとトランクが1つだけではなく、管理者は、個々の SIP トランクに関する情報を表示するために、Get-help コマンドレットを使用する必要があることを意味します。
ms.openlocfilehash: c5288e676f546e07504f4d8609fcea63913b6457
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048180"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a><span data-ttu-id="e2710-103">Skype for Business Server での個々の SIP トランクに関する情報の表示</span><span class="sxs-lookup"><span data-stu-id="e2710-103">View information about individual SIP trunks in Skype for Business Server</span></span>

<span data-ttu-id="e2710-104">Skype for Business Server では、複数のトランクを1つの PSTN ゲートウェイに割り当てることができます。これは、ゲートウェイとトランクが同一ではなく、管理者が個々の SIP トランクに関する情報を表示するには、[コマンドレット](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk)を使用する必要があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="e2710-104">In Skype for Business Server, multiple trunks can be assigned to a single PSTN gateway; this means that gateways and trunks are not one and the same, and that administrators must use the [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk) cmdlet to view information about an individual SIP trunk.</span></span>

<span data-ttu-id="e2710-105">Get-help コマンドレットは、Skype for Business Server 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="e2710-105">The Get-CsTrunk cmdlet can be run either from the  Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span>

<span data-ttu-id="e2710-106">**すべての SIP トランクに関する情報を表示するには**</span><span class="sxs-lookup"><span data-stu-id="e2710-106">**To view information for all your SIP trunks**</span></span>

<span data-ttu-id="e2710-107">次のコマンドは、組織で使用中のすべての SIP トランクに関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="e2710-107">The following command returns information about all the SIP trunks in use in your organization:</span></span>

`Get-CsTrunk`

<span data-ttu-id="e2710-108">**特定の SIP トランクに関する情報を表示するには**</span><span class="sxs-lookup"><span data-stu-id="e2710-108">**To view information for a specific SIP trunk**</span></span>

<span data-ttu-id="e2710-109">このコマンドは、PstnGateway:192.168.0.240 という Identity を持つ SIP トランクに関する情報のみを返します。</span><span class="sxs-lookup"><span data-stu-id="e2710-109">This command returns information only for the SIP trunk with the Identity PstnGateway:192.168.0.240:</span></span>

`Get-CsTrunk -Identity "PstnGateway:192.168.0.240"`

<span data-ttu-id="e2710-110">**プールに割り当てられているすべての SIP トランクに関する情報の表示**</span><span class="sxs-lookup"><span data-stu-id="e2710-110">**Viewing Information for All the SIP Trunks Assigned to a Pool**</span></span>

<span data-ttu-id="e2710-111">この例では、プール atl-cs-001.litwareinc.com に割り当てられているすべての SIP トランクについて情報が返されます。</span><span class="sxs-lookup"><span data-stu-id="e2710-111">In this example, information is returned for all the SIP trunks assigned to the pool atl-cs-001.litwareinc.com:</span></span>

`Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"`
