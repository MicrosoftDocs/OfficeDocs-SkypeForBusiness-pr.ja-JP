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
# <a name="viewing-network-interface-information-in-skype-for-business-server"></a>Skype for Business Server でのネットワークインターフェイス情報の表示

Windows PowerShell と**CsNetworkInterface**コマンドレットを使用して、ネットワークインターフェイス情報を表示できます。 このコマンドレットは、Skype for Business Server 管理シェルまたは Windows PowerShell のリモートセッションから実行できます。 

## <a name="to-view-network-interface-information"></a>ネットワークインターフェイス情報を表示するには

  - ネットワークインターフェイス情報を表示するには、Skype for Business Server 管理シェルで次のコマンドを入力し、enter キーを押します。
    
        Get-CsNetworkInterface
    
    このコマンドは、各ネットワークインターフェイスについて、次のような情報を返します。
    
        Identity              : dc.vdomain.com/Primary/1
        ComputerFqdn          : dc.vdomain.com
        IPAddress             : 0.0.0.0
        IPv6Address           :
        Interface             : Primary
        InterfaceNumber       : 1
        ConfiguredFqdn        :
        ConfiguredIPAddress   :
        ConfiguredIPv6Address :
    
    詳細については、「 [Get-CsNetworkInterface](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterface)」を参照してください。


