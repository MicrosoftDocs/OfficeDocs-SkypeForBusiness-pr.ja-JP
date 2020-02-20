---
title: 'Lync Server 2013: Windows に基づかないデバイスの QoS の有効化'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: QoS for devices that are not based on Windows
ms:assetid: 26f793df-aef8-4028-9e3b-6c2c37ea61b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204750(v=OCS.15)
ms:contentKeyID: 48183661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ad830b2cf15e3f34c443feaa5ea21e19279804cb
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146360"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enabling-qos-in-lync-server-2013-for-devices-that-are-not-based-on-windows"></a>Windows に基づかないデバイスに対して Lync Server 2013 で QoS を有効にする

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-11-01_

Microsoft Lync Server 2013 をインストールする場合、Windows 以外のオペレーティングシステムを使用する組織で使用されているデバイスでは、サービスの品質 (QoS) は有効になりません。 これを確認するには、Lync Server 2013 管理シェルで次のコマンドを実行します。

    Get-CsMediaConfiguration

メディア構成設定に何も変更を加えていなければ、次のような情報が表示されます。

    Identity                          : Global
    EnableQoS                         : False
    EncryptionLevel                   : RequireEncryption
    EnableSiren                       : False
    MaxVideoRateAllowed               : VGA600K
    EnableG722StereoCodec             : True
    EnableH264Codec                   : True
    EnableAdaptiveBandwidthEstimation : True

EnableQoS プロパティが False (前の出力のように) に設定されている場合は、Windows 以外のオペレーティングシステムを使用するコンピューターとデバイスでサービスの品質が有効になっていないことを意味します。 Lync Phone Edition デバイスでは、既定で QoS が有効になっています。ただし、Lync Phone Edition のサービスの品質を無効にすることができます。

グローバルスコープでサービスの品質を有効にするには、Lync Server 管理シェルで次のコマンドを実行します。

    Set-CsMediaConfiguration -EnableQoS $True

このコマンドを実行すると QoS がグローバル スコープで有効になります。ただし、メディア構成設定はサイト スコープにも適用できるという点に注意してください。サービスの品質を特定のサイトで有効にする必要がある場合は、Set-CsMediaConfiguration を呼び出すときに構成設定の Identity を指定します。たとえば、次のコマンドは Redmond サイトで QoS を有効にします。

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True

<div>


> [!NOTE]  
> QoS をサイト スコープで有効にする必要があるかどうかは、状況によって異なります。サイト スコープに割り当てた設定は、グローバル スコープに割り当てた設定に優先します。たとえば、QoS をグローバル スコープで有効にし、サイト スコープ (Redmond サイト) では無効にしているとします。この場合、Redmond サイトではサービスの品質が無効になります。サイトの設定が優先するからです。Redmond サイトで QoS を有効にするには、サイトに適用されるメディア構成設定を使用して有効にする必要があります。



</div>

すべてのメディア構成設定 (スコープに関係なく) に対して QoS を同時に有効にする場合は、Lync Server 管理シェルから次のコマンドを実行します。

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

Windows 以外のオペレーティングシステムを使用しているデバイスでは、EnableQoS プロパティの値を False に設定することで QoS を無効にすることができます。 次に例を示します。

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

これにより、ネットワーク (Redmond サイトなど) の一部で QoS を実装しながら、ネットワークの他の部分では QoS を無効のままにすることができます。

QoS は、Windows PowerShell を使用して有効または無効にすることができます。これらのオプションは、Lync Server コントロールパネルでは使用できません。

</div>

<span> </span>

</div>

</div>

</div>

