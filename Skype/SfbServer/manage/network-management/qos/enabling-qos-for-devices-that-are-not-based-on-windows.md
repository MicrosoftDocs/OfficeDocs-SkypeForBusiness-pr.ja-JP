---
title: Windows に基づかないデバイスの QoS の有効化
ms.reviewer: ''
ms:assetid: 26f793df-aef8-4028-9e3b-6c2c37ea61b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204750(v=OCS.15)
ms:contentKeyID: 48183661
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Windows 以外のオペレーティングシステムを使用している組織で使用されているデバイスの QoS を有効にする方法について説明します。
ms.openlocfilehash: 956fff0e7fc69b1950e35261c02f9f44977510ce
ms.sourcegitcommit: 100ba1409bf0af58e4430877c1d29622d793d23f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2019
ms.locfileid: "37341943"
---
# <a name="enabling-qos-in-skype-for-business-server-for-devices-that-are-not-based-on-windows"></a>Windows ベースではないデバイスのために Skype for Business Server で QoS を有効にする


Skype for Business Server をインストールすると、Windows 以外のオペレーティングシステムを使用しているすべてのデバイスで、QoS (Quality of Service) が有効になりません。 これを確認するには、Skype for Business ServerManagement Shell で次のコマンドを実行します。

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

EnableQoS プロパティが False に設定されている場合 (上記の出力の場合)、Windows 以外のオペレーティングシステムを使用するコンピューターやデバイスではサービスの品質が有効になっていないことを意味します。

グローバルスコープでサービスの品質を有効にするには、Skype for Business Server 管理シェルで次のコマンドを実行します。

    Set-CsMediaConfiguration -EnableQoS $True

上のコマンドはグローバルスコープで QoS を有効にします。ただし、メディア構成の設定はサイトのスコープにも適用できることに注意する必要があります。 サイトのサービス品質を有効にする必要がある場合は、Set-CsMediaConfiguration を呼び出すときに、構成設定の Id を含める必要があります。 たとえば、次のコマンドは、Redmond サイトの QoS を有効にします。

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True



> [!NOTE]  
> サイトスコープで QoS を有効にする必要がありますか? ケースバイケースです。 サイトの範囲に割り当てられている設定は、グローバルスコープに割り当てられている設定より優先されます。 グローバルスコープで QoS が有効になっているが、サイトのスコープ (Redmond サイト) で無効になっているとします。 その場合、Redmond サイトのサービスの品質は無効になります。これは、サイトの設定が優先されるためです。 Redmond サイトの QoS を有効にするには、そのサイトに適用されているメディア構成設定を使用する必要があります。


スコープに関係なく、すべてのメディア構成設定で QoS を同時に有効にするには、LSkype for Business Server 管理シェルで次のコマンドを実行します。

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

Windows 以外のオペレーティングシステムを使用しているデバイスでは、EnableQoS プロパティの値を False に設定することにより、QoS を無効にすることができます。 次に例を示します。

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

これにより、ネットワークの他の部分でサービスの品質を無効にしたまま、ネットワークの一部の部分 (レドモンドサイトなど) に QoS を実装することができます。

QoS を有効または無効にするには、Windows PowerShell を使用する必要があります。 これらのオプションは、Skype for Business Server コントロールパネルでは使用できません。

> [!NOTE]
> IOS バージョン6.17 以降の Skype for Business クライアントで、QoS がサポートされるようになりました。  この QoS 機能は、Skype for Business クライアントと、管理されたネットワーク上の内部の Skype for Business または Lync プールサーバーに直接登録される IP 電話デバイスにのみ適用されます。 QoS は、インターネット経由でルーティングされるトラフィックには適用されません。



