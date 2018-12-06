---
title: ネットワーク インターフェイス情報の表示
TOCTitle: ネットワーク インターフェイス情報の表示
ms:assetid: e7dbb1ec-62b3-48be-a419-c493df5740e6
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ721916(v=OCS.15)
ms:contentKeyID: 49887189
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# ネットワーク インターフェイス情報の表示

 

_**トピックの最終更新日:** 2013-02-23_

## Lync Server 管理シェル コマンドレットを使用してネットワーク インターフェイス情報を表示する

Lync Server 管理シェルおよび **Get-CsNetworkInterface** コマンドレットを使用してネットワーク インターフェイス情報を表示できます。このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモート セッションから実行できます。リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 ([http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)) を参照してください。

## ネットワーク インターフェイス情報を表示するには

  - ネットワーク インターフェイス情報を表示するには、Lync Server 管理シェルに次のコマンドを入力し、Enter キーを押します。
    
        Get-CsNetworkInterface
    
    このコマンドは、各ネットワーク インターフェイスについて次のような情報を返します。
    
        Identity              : dc.vdomain.com/Primary/1
        ComputerFqdn          : dc.vdomain.com
        IPAddress             : 0.0.0.0
        IPv6Address           :
        Interface             : Primary
        InterfaceNumber       : 1
        ConfiguredFqdn        :
        ConfiguredIPAddress   :
        ConfiguredIPv6Address :

詳細については、「 [Get-CsNetworkInterface](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkInterface)」を参照してください。

