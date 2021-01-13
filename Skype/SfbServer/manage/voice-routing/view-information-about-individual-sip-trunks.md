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
ms.openlocfilehash: b49846ed7244dec2f51f51f262becc440662026c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826177"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a><span data-ttu-id="a083c-103">Skype for Business Server の個々の SIP トランクに関する情報を表示する</span><span class="sxs-lookup"><span data-stu-id="a083c-103">View information about individual SIP trunks in Skype for Business Server</span></span>

<span data-ttu-id="a083c-104">Skype for Business Server では、1 つの PSTN ゲートウェイに複数のトランクを割り当てることができます。つまり、ゲートウェイとトランクは同じではなく、管理者は [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk) コマンドレットを使用して個々の SIP トランクに関する情報を表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a083c-104">In Skype for Business Server, multiple trunks can be assigned to a single PSTN gateway; this means that gateways and trunks are not one and the same, and that administrators must use the [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk) cmdlet to view information about an individual SIP trunk.</span></span>

<span data-ttu-id="a083c-105">このGet-CsTrunkは、Skype for Business Server 管理シェルから、または Skype for Business Server 管理シェルのリモート セッションから実行Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="a083c-105">The Get-CsTrunk cmdlet can be run either from the  Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span>

<span data-ttu-id="a083c-106">**すべての SIP トランクの情報を表示するには**</span><span class="sxs-lookup"><span data-stu-id="a083c-106">**To view information for all your SIP trunks**</span></span>

<span data-ttu-id="a083c-107">次のコマンドは、組織で使用中のすべての SIP トランクに関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="a083c-107">The following command returns information about all the SIP trunks in use in your organization:</span></span>

`Get-CsTrunk`

<span data-ttu-id="a083c-108">**特定の SIP トランクの情報を表示するには**</span><span class="sxs-lookup"><span data-stu-id="a083c-108">**To view information for a specific SIP trunk**</span></span>

<span data-ttu-id="a083c-109">このコマンドは、PstnGateway:192.168.0.240 という Identity を持つ SIP トランクに関する情報のみを返します。</span><span class="sxs-lookup"><span data-stu-id="a083c-109">This command returns information only for the SIP trunk with the Identity PstnGateway:192.168.0.240:</span></span>

`Get-CsTrunk -Identity "PstnGateway:192.168.0.240"`

<span data-ttu-id="a083c-110">**プールに割り当てられているすべての SIP トランクに関する情報の表示**</span><span class="sxs-lookup"><span data-stu-id="a083c-110">**Viewing Information for All the SIP Trunks Assigned to a Pool**</span></span>

<span data-ttu-id="a083c-111">この例では、プール atl-cs-001.litwareinc.com に割り当てられているすべての SIP トランクについて情報が返されます。</span><span class="sxs-lookup"><span data-stu-id="a083c-111">In this example, information is returned for all the SIP trunks assigned to the pool atl-cs-001.litwareinc.com:</span></span>

`Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"`
