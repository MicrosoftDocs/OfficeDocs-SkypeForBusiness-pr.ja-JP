---
title: ビジネス サーバーの Skype での個々 の SIP トランクに関する情報を表示
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ビジネス サーバーの Skype で複数トランクを 1 つの PSTN ゲートウェイを割り当てることができます。つまり、ゲートウェイおよびトランクは、特定の 1 つだけ、管理者は個々 の SIP トランクに関する情報を表示するのには、Get CsTrunk コマンドレットを使用する必要があります。
ms.openlocfilehash: bf9229dba17b7b2e49eb9a05d9469f42c0b9b998
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930821"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a><span data-ttu-id="efc04-103">ビジネス サーバーの Skype での個々 の SIP トランクに関する情報を表示</span><span class="sxs-lookup"><span data-stu-id="efc04-103">View information about individual SIP trunks in Skype for Business Server</span></span>

<span data-ttu-id="efc04-104">ビジネス サーバーの Skype で複数トランクを 1 つの PSTN ゲートウェイを割り当てることができます。つまり、ゲートウェイまたはトランクは、1 つだけ、ではないことと、管理者が個々 の SIP トランクに関する情報を表示するのには[Get CsTrunk](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunk)コマンドレットを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="efc04-104">In Skype for Business Server, multiple trunks can be assigned to a single PSTN gateway; this means that gateways and trunks are not one and the same, and that administrators must use the [Get-CsTrunk](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunk) cmdlet to view information about an individual SIP trunk.</span></span>

<span data-ttu-id="efc04-105">ビジネス サーバー管理シェルの Skype とは Windows PowerShell のリモート セッションからは、Get CsTrunk コマンドレットを実行できます。</span><span class="sxs-lookup"><span data-stu-id="efc04-105">The Get-CsTrunk cmdlet can be run either from the  Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span>

<span data-ttu-id="efc04-106">**すべての SIP トランクに関する情報の表示**</span><span class="sxs-lookup"><span data-stu-id="efc04-106">**To view information for all your SIP trunks**</span></span>

<span data-ttu-id="efc04-107">次のコマンドは、組織で使用中のすべての SIP トランクに関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="efc04-107">The following command returns information about all the SIP trunks in use in your organization:</span></span>

`Get-CsTrunk`

<span data-ttu-id="efc04-108">**特定の SIP トランクに関する情報の表示**</span><span class="sxs-lookup"><span data-stu-id="efc04-108">**To view information for a specific SIP trunk**</span></span>

<span data-ttu-id="efc04-109">このコマンドは、PstnGateway:192.168.0.240 という Identity を持つ SIP トランクに関する情報のみを返します。</span><span class="sxs-lookup"><span data-stu-id="efc04-109">This command returns information only for the SIP trunk with the Identity PstnGateway:192.168.0.240:</span></span>

`Get-CsTrunk -Identity "PstnGateway:192.168.0.240"`

<span data-ttu-id="efc04-110">**プールに割り当てられているすべての SIP トランクに関する情報を表示します。**</span><span class="sxs-lookup"><span data-stu-id="efc04-110">**Viewing Information for All the SIP Trunks Assigned to a Pool**</span></span>

<span data-ttu-id="efc04-111">この例では、プール atl-cs-001.litwareinc.com に割り当てられているすべての SIP トランクについて情報が返されます。</span><span class="sxs-lookup"><span data-stu-id="efc04-111">In this example, information is returned for all the SIP trunks assigned to the pool atl-cs-001.litwareinc.com:</span></span>

`Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"`
