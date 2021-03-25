---
title: ネットワーク インターフェイス情報の表示
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
description: ネットワーク インターフェイスの情報を表示するには、Windows PowerShellコマンドレットをGet-CsNetworkInterfaceします。 このコマンドレットは、Skype for Business Server 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。
ms.openlocfilehash: 0e72b2550413004038b110292b693dda25affaf8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122421"
---
# <a name="viewing-network-interface-information-in-skype-for-business-server"></a><span data-ttu-id="591c5-104">Skype for Business Server でのネットワーク インターフェイス情報の表示</span><span class="sxs-lookup"><span data-stu-id="591c5-104">Viewing network interface information in Skype for Business Server</span></span>

<span data-ttu-id="591c5-105">ネットワーク インターフェイスの情報を表示するには、Windows PowerShell **Get-CsNetworkInterface コマンドレットを使用** します。</span><span class="sxs-lookup"><span data-stu-id="591c5-105">You can view network interface information by using Windows PowerShell and the **Get-CsNetworkInterface** cmdlet.</span></span> <span data-ttu-id="591c5-106">このコマンドレットは、Skype for Business Server 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="591c5-106">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-view-network-interface-information"></a><span data-ttu-id="591c5-107">ネットワーク インターフェイス情報を表示するには</span><span class="sxs-lookup"><span data-stu-id="591c5-107">To view network interface information</span></span>

  - <span data-ttu-id="591c5-108">ネットワーク インターフェイス情報を表示するには、Skype for Business Server 管理シェルに次のコマンドを入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="591c5-108">To view network interface information, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkInterface
    
    <span data-ttu-id="591c5-109">このコマンドは、各ネットワーク インターフェイスについて次のような情報を返します。</span><span class="sxs-lookup"><span data-stu-id="591c5-109">This command returns information similar to the following for each network interface:</span></span>
    
        Identity              : dc.vdomain.com/Primary/1
        ComputerFqdn          : dc.vdomain.com
        IPAddress             : 0.0.0.0
        IPv6Address           :
        Interface             : Primary
        InterfaceNumber       : 1
        ConfiguredFqdn        :
        ConfiguredIPAddress   :
        ConfiguredIPv6Address :
    
    <span data-ttu-id="591c5-110">詳細については、「 [Get-CsNetworkInterface](/powershell/module/skype/Get-CsNetworkInterface)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="591c5-110">For details, see [Get-CsNetworkInterface](/powershell/module/skype/Get-CsNetworkInterface).</span></span>