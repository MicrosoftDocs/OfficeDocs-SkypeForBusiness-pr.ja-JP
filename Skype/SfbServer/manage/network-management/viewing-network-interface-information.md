---
title: ネットワーク インターフェイス情報を表示します。
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Windows PowerShell と Get CsNetworkInterface コマンドレットを使用して、ネットワーク インターフェイスの情報を表示できます。 ビジネス サーバー管理シェルの Skype とは Windows PowerShell のリモート セッションからは、このコマンドレットを実行することができます。
ms.openlocfilehash: df4424e33cb42f3c1b2311cc822c762a2c4878f1
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30888030"
---
# <a name="viewing-network-interface-information-in-skype-for-business-server"></a><span data-ttu-id="64f45-104">Skype のビジネス サーバーのネットワーク インターフェイス情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="64f45-104">Viewing network interface information in Skype for Business Server</span></span>

<span data-ttu-id="64f45-105">Windows PowerShell と**Get CsNetworkInterface**コマンドレットを使用して、ネットワーク インターフェイスの情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="64f45-105">You can view network interface information by using Windows PowerShell and the **Get-CsNetworkInterface** cmdlet.</span></span> <span data-ttu-id="64f45-106">ビジネス サーバー管理シェルの Skype とは Windows PowerShell のリモート セッションからは、このコマンドレットを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="64f45-106">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-view-network-interface-information"></a><span data-ttu-id="64f45-107">ネットワーク インターフェイス情報を表示するのには</span><span class="sxs-lookup"><span data-stu-id="64f45-107">To view network interface information</span></span>

  - <span data-ttu-id="64f45-108">ネットワーク インターフェイス情報を表示するのには、Skype のビジネス サーバー管理シェルには、次のコマンドを入力し、し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="64f45-108">To view network interface information, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkInterface
    
    <span data-ttu-id="64f45-109">このコマンドは、各ネットワーク インターフェイスは、次のような情報を返します。</span><span class="sxs-lookup"><span data-stu-id="64f45-109">This command returns information similar to the following for each network interface:</span></span>
    
        Identity              : dc.vdomain.com/Primary/1
        ComputerFqdn          : dc.vdomain.com
        IPAddress             : 0.0.0.0
        IPv6Address           :
        Interface             : Primary
        InterfaceNumber       : 1
        ConfiguredFqdn        :
        ConfiguredIPAddress   :
        ConfiguredIPv6Address :
    
    <span data-ttu-id="64f45-110">詳細については、 [Get CsNetworkInterface](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterface)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="64f45-110">For details, see [Get-CsNetworkInterface](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterface).</span></span>


