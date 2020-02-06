---
title: ネットワークインターフェイス情報の表示
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
description: Windows PowerShell と CsNetworkInterface コマンドレットを使用して、ネットワークインターフェイス情報を表示できます。 このコマンドレットは、Skype for Business Server 管理シェルまたは Windows PowerShell のリモートセッションから実行できます。
ms.openlocfilehash: d4443f7ec10a0f56cc82ab495d88518f3f3aa17d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817353"
---
# <a name="viewing-network-interface-information-in-skype-for-business-server"></a><span data-ttu-id="7c0df-104">Skype for Business Server でのネットワークインターフェイス情報の表示</span><span class="sxs-lookup"><span data-stu-id="7c0df-104">Viewing network interface information in Skype for Business Server</span></span>

<span data-ttu-id="7c0df-105">Windows PowerShell と**CsNetworkInterface**コマンドレットを使用して、ネットワークインターフェイス情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="7c0df-105">You can view network interface information by using Windows PowerShell and the **Get-CsNetworkInterface** cmdlet.</span></span> <span data-ttu-id="7c0df-106">このコマンドレットは、Skype for Business Server 管理シェルまたは Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="7c0df-106">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-view-network-interface-information"></a><span data-ttu-id="7c0df-107">ネットワークインターフェイス情報を表示するには</span><span class="sxs-lookup"><span data-stu-id="7c0df-107">To view network interface information</span></span>

  - <span data-ttu-id="7c0df-108">ネットワークインターフェイス情報を表示するには、Skype for Business Server 管理シェルで次のコマンドを入力し、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="7c0df-108">To view network interface information, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkInterface
    
    <span data-ttu-id="7c0df-109">このコマンドは、各ネットワークインターフェイスについて、次のような情報を返します。</span><span class="sxs-lookup"><span data-stu-id="7c0df-109">This command returns information similar to the following for each network interface:</span></span>
    
        Identity              : dc.vdomain.com/Primary/1
        ComputerFqdn          : dc.vdomain.com
        IPAddress             : 0.0.0.0
        IPv6Address           :
        Interface             : Primary
        InterfaceNumber       : 1
        ConfiguredFqdn        :
        ConfiguredIPAddress   :
        ConfiguredIPv6Address :
    
    <span data-ttu-id="7c0df-110">詳細については、「 [Get-CsNetworkInterface](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterface)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7c0df-110">For details, see [Get-CsNetworkInterface](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterface).</span></span>


