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


