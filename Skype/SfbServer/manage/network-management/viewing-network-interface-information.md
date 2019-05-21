---
title: ネットワークインターフェイス情報の表示
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Windows PowerShell と CsNetworkInterface コマンドレットを使用して、ネットワークインターフェイス情報を表示できます。 このコマンドレットは、Skype for Business Server 管理シェルまたは Windows PowerShell のリモートセッションから実行できます。
ms.openlocfilehash: ac0df8450b938a377e1325f9c3179b4650b31bdf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279390"
---
# <a name="viewing-network-interface-information-in-skype-for-business-server"></a><span data-ttu-id="a85d0-104">Skype for Business Server でのネットワークインターフェイス情報の表示</span><span class="sxs-lookup"><span data-stu-id="a85d0-104">Viewing network interface information in Skype for Business Server</span></span>

<span data-ttu-id="a85d0-105">Windows PowerShell と**CsNetworkInterface**コマンドレットを使用して、ネットワークインターフェイス情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="a85d0-105">You can view network interface information by using Windows PowerShell and the **Get-CsNetworkInterface** cmdlet.</span></span> <span data-ttu-id="a85d0-106">このコマンドレットは、Skype for Business Server 管理シェルまたは Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="a85d0-106">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-view-network-interface-information"></a><span data-ttu-id="a85d0-107">ネットワークインターフェイス情報を表示するには</span><span class="sxs-lookup"><span data-stu-id="a85d0-107">To view network interface information</span></span>

  - <span data-ttu-id="a85d0-108">ネットワークインターフェイス情報を表示するには、Skype for Business Server 管理シェルで次のコマンドを入力し、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="a85d0-108">To view network interface information, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkInterface
    
    <span data-ttu-id="a85d0-109">このコマンドは、各ネットワークインターフェイスについて、次のような情報を返します。</span><span class="sxs-lookup"><span data-stu-id="a85d0-109">This command returns information similar to the following for each network interface:</span></span>
    
        Identity              : dc.vdomain.com/Primary/1
        ComputerFqdn          : dc.vdomain.com
        IPAddress             : 0.0.0.0
        IPv6Address           :
        Interface             : Primary
        InterfaceNumber       : 1
        ConfiguredFqdn        :
        ConfiguredIPAddress   :
        ConfiguredIPv6Address :
    
    <span data-ttu-id="a85d0-110">詳細については、「 [Get-CsNetworkInterface](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterface)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a85d0-110">For details, see [Get-CsNetworkInterface](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterface).</span></span>


