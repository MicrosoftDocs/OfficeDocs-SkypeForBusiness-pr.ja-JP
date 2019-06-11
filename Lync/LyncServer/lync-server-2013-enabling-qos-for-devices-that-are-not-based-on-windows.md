---
title: 'Lync Server 2013: Windows ベースではないデバイスの QoS を有効にする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: QoS for devices that are not based on Windows
ms:assetid: 26f793df-aef8-4028-9e3b-6c2c37ea61b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204750(v=OCS.15)
ms:contentKeyID: 48183661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d993a6905dfad9f5f2eda10a48553f2ae29b58ef
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833231"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-qos-in-lync-server-2013-for-devices-that-are-not-based-on-windows"></a>Windows ベースではないデバイスの Lync Server 2013 で QoS を有効にする

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-11-01_

Microsoft Lync Server 2013 をインストールすると、Windows 以外のオペレーティングシステムを使用しているすべてのデバイスで、サービスの品質 (QoS) が有効になりません。 これを確認するには、Lync Server 2013 管理シェルで次のコマンドを実行します。

    Get-CsMediaConfiguration

メディア構成の設定を変更していない場合は、次のような情報が表示されます。

    Identity                          : Global
    EnableQoS                         : False
    EncryptionLevel                   : RequireEncryption
    EnableSiren                       : False
    MaxVideoRateAllowed               : VGA600K
    EnableG722StereoCodec             : True
    EnableH264Codec                   : True
    EnableAdaptiveBandwidthEstimation : True

EnableQoS プロパティが False に設定されている場合 (上記の出力の場合)、Windows 以外のオペレーティングシステムを使用するコンピューターやデバイスではサービスの品質が有効になっていないことを意味します。 Lync Phone Edition デバイスでは、QoS は既定で有効になっています。ただし、Lync Phone Edition のサービス品質を無効にすることもできます。

グローバルスコープでサービスの品質を有効にするには、Lync Server 管理シェルで次のコマンドを実行します。

    Set-CsMediaConfiguration -EnableQoS $True

上のコマンドはグローバルスコープで QoS を有効にします。ただし、メディア構成の設定はサイトのスコープにも適用できることに注意する必要があります。 サイトのサービス品質を有効にする必要がある場合は、Set-CsMediaConfiguration を呼び出すときに構成設定の Id を含める必要があります。 たとえば、次のコマンドは、Redmond サイトの QoS を有効にします。

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True

<div>


> [!NOTE]  
> サイトスコープで QoS を有効にする必要がありますか? ケースバイケースです。 サイトの範囲に割り当てられている設定は、グローバルスコープに割り当てられている設定より優先されます。 グローバルスコープで QoS が有効になっているが、サイトのスコープ (Redmond サイト) で無効になっているとします。その場合、Redmond サイトのサービスの品質は無効になります。これは、サイトの設定が優先されるためです。 Redmond サイトの QoS を有効にするには、そのサイトに適用されているメディア構成設定を使用する必要があります。



</div>

スコープに関係なく、すべてのメディア構成の設定で QoS を同時に有効にする場合は、Lync Server 管理シェルで次のコマンドを実行します。

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

Windows 以外のオペレーティングシステムを使用しているデバイスでは、EnableQoS プロパティの値を False に設定することにより、QoS を無効にすることができます。 次に例を示します。

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

これにより、ネットワークの他の部分でサービスの品質を無効にしたまま、ネットワークの一部の部分 (レドモンドサイトなど) に QoS を実装することができます。

QoS を有効または無効にするには、Windows PowerShell を使用する必要があります。これらのオプションは、Lync Server のコントロールパネルでは利用できません。

</div>

<span> </span>

</div>

</div>

</div>

