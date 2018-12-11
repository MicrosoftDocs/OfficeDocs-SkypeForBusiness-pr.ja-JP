---
title: ネットワーク インターフェイス情報を表示します。
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Windows PowerShell と Get CsNetworkInterface コマンドレットを使用して、ネットワーク インターフェイスの情報を表示できます。 ビジネス サーバー管理シェルの Skype とは Windows PowerShell のリモート セッションからは、このコマンドレットを実行することができます。
ms.openlocfilehash: b3f1217c53176ae2a67ba81893864e1fb3a4e384
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222766"
---
# <a name="viewing-network-interface-information-in-skype-for-business-server"></a>Skype のビジネス サーバーのネットワーク インターフェイス情報を表示します。

Windows PowerShell と**Get CsNetworkInterface**コマンドレットを使用して、ネットワーク インターフェイスの情報を表示できます。 ビジネス サーバー管理シェルの Skype とは Windows PowerShell のリモート セッションからは、このコマンドレットを実行することができます。 

## <a name="to-view-network-interface-information"></a>ネットワーク インターフェイス情報を表示するのには

  - ネットワーク インターフェイス情報を表示するのには、Skype のビジネス サーバー管理シェルには、次のコマンドを入力し、し、ENTER キーを押します。
    
        Get-CsNetworkInterface
    
    このコマンドは、各ネットワーク インターフェイスは、次のような情報を返します。
    
        Identity              : dc.vdomain.com/Primary/1
        ComputerFqdn          : dc.vdomain.com
        IPAddress             : 0.0.0.0
        IPv6Address           :
        Interface             : Primary
        InterfaceNumber       : 1
        ConfiguredFqdn        :
        ConfiguredIPAddress   :
        ConfiguredIPv6Address :
    
    詳細については、 [Get CsNetworkInterface](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterface)を参照してください。


