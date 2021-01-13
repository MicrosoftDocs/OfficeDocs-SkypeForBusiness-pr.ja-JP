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
description: ネットワーク インターフェイス情報は、このコマンドレットと Windows PowerShell使用してGet-CsNetworkInterfaceできます。 このコマンドレットは、Skype for Business Server 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。
ms.openlocfilehash: 26876fe6f7d8ac6989c88e8247d28a72e78ff903
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815137"
---
# <a name="viewing-network-interface-information-in-skype-for-business-server"></a><span data-ttu-id="9fbe7-104">Skype for Business Server でのネットワーク インターフェイス情報の表示</span><span class="sxs-lookup"><span data-stu-id="9fbe7-104">Viewing network interface information in Skype for Business Server</span></span>

<span data-ttu-id="9fbe7-105">ネットワーク インターフェイス情報を表示するには、Windows PowerShell **Get-CsNetworkInterface コマンドレットを使用** します。</span><span class="sxs-lookup"><span data-stu-id="9fbe7-105">You can view network interface information by using Windows PowerShell and the **Get-CsNetworkInterface** cmdlet.</span></span> <span data-ttu-id="9fbe7-106">このコマンドレットは、Skype for Business Server 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="9fbe7-106">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-view-network-interface-information"></a><span data-ttu-id="9fbe7-107">ネットワーク インターフェイス情報を表示するには</span><span class="sxs-lookup"><span data-stu-id="9fbe7-107">To view network interface information</span></span>

  - <span data-ttu-id="9fbe7-108">ネットワーク インターフェイス情報を表示するには、Skype for Business Server 管理シェルで次のコマンドを入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="9fbe7-108">To view network interface information, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkInterface
    
    <span data-ttu-id="9fbe7-109">このコマンドは、各ネットワーク インターフェイスについて次のような情報を返します。</span><span class="sxs-lookup"><span data-stu-id="9fbe7-109">This command returns information similar to the following for each network interface:</span></span>
    
        Identity              : dc.vdomain.com/Primary/1
        ComputerFqdn          : dc.vdomain.com
        IPAddress             : 0.0.0.0
        IPv6Address           :
        Interface             : Primary
        InterfaceNumber       : 1
        ConfiguredFqdn        :
        ConfiguredIPAddress   :
        ConfiguredIPv6Address :
    
    <span data-ttu-id="9fbe7-110">詳細については、「 [Get-CsNetworkInterface](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterface)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9fbe7-110">For details, see [Get-CsNetworkInterface](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterface).</span></span>


