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
ms.localizationpriority: medium
description: ネットワーク インターフェイスの情報を表示するには、Windows PowerShellコマンドレットをGet-CsNetworkInterfaceします。 このコマンドレットは、Skype for Business Server 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。
ms.openlocfilehash: 56d6abcd804a5dd525bdc1d9f7b3e5df74f756b0
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/30/2021
ms.locfileid: "60015361"
---
# <a name="viewing-network-interface-information-in-skype-for-business-server"></a>ネットワーク インターフェイスの情報を表示Skype for Business Server

ネットワーク インターフェイスの情報を表示するには、Windows PowerShell **Get-CsNetworkInterface コマンドレットを使用** します。 このコマンドレットは、Skype for Business Server 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。

## <a name="to-view-network-interface-information"></a>ネットワーク インターフェイス情報を表示するには

ネットワーク インターフェイス情報を表示するには、次のコマンドを [管理シェル] Skype for Business Server入力し、Enter キーを押します。
    
`Get-CsNetworkInterface`

このコマンドは、各ネットワーク インターフェイスについて次のような情報を返します。

```console    
Identity              : dc.vdomain.com/Primary/1
ComputerFqdn          : dc.vdomain.com
IPAddress             : 0.0.0.0
IPv6Address           :
Interface             : Primary
InterfaceNumber       : 1
ConfiguredFqdn        :
ConfiguredIPAddress   :
ConfiguredIPv6Address :
```

詳細については、「 [Get-CsNetworkInterface](/powershell/module/skype/Get-CsNetworkInterface)」を参照してください。
