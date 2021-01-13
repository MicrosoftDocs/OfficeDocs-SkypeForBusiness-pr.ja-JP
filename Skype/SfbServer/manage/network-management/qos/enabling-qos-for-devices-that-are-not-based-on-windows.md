---
title: Windows ベースではないデバイスの QoS の有効化
ms.reviewer: ''
ms:assetid: 26f793df-aef8-4028-9e3b-6c2c37ea61b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204750(v=OCS.15)
ms:contentKeyID: 48183661
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Windows 以外のオペレーティング システムを使用する組織で使用されているデバイスで QoS を有効にする方法について説明します。
ms.openlocfilehash: c22f9c98c796ee11d06e3d58a02a36befef4539e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814177"
---
# <a name="enabling-qos-in-skype-for-business-server-for-devices-that-are-not-based-on-windows"></a>Windows ベースではないデバイスに対する Skype for Business Server での QoS の有効化


Skype for Business Server をインストールすると、Windows 以外のオペレーティング システムを使用する組織で使用されているデバイスでは、サービスの品質 (QoS) が有効になりません。 これを確認するには、Skype for Business ServerManagement シェル内から次のコマンドを実行します。

    Get-CsMediaConfiguration

メディア構成設定を変更していない場合は、次のような情報を取得する必要があります。

    Identity                          : Global
    EnableQoS                         : False
    EncryptionLevel                   : RequireEncryption
    EnableSiren                       : False
    MaxVideoRateAllowed               : VGA600K
    EnableG722StereoCodec             : True
    EnableH264Codec                   : True
    EnableAdaptiveBandwidthEstimation : True

EnableQoS プロパティが False (前の出力と同様) に設定されている場合、Windows 以外のオペレーティング システムを使用するコンピューターおよびデバイスではサービスの品質が有効になっていません。

グローバル スコープでサービスの品質を有効にするには、Skype for Business Server 管理シェル内から次のコマンドを実行します。

    Set-CsMediaConfiguration -EnableQoS $True

上のコマンドは、グローバル スコープで QoS を有効にしています。ただし、メディア構成設定はサイト スコープにも適用できる点に注意することが重要です。 サイトのサービス品質を有効にする必要がある場合は、Set-CsMediaConfiguration を呼び出す際に構成設定の ID を含める必要があります。 たとえば、次のコマンドを実行すると、Redmond サイトの QoS が有効にされます。

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True



> [!NOTE]  
> QoS をサイト スコープで有効にする必要があるかどうかは、状況によって異なります。 サイト スコープに割り当てた設定は、グローバル スコープに割り当てた設定に優先します。 たとえば、QoS をグローバル スコープで有効にし、サイト スコープ (Redmond サイト) では無効にしているとします。 QoS がグローバル スコープで有効になっているが、サイト スコープで無効になっているとします (Redmond サイトの場合)。 その場合、Redmond サイトではサービスの品質が無効になります。これは、サイト設定が優先されるためです。 Redmond サイトで QoS を有効にするには、そのサイトに適用されるメディア構成設定を使用して有効にする必要があります。


すべてのメディア構成設定 (スコープに関係なく) で QoS を同時に有効にする場合は、LSkype for Business Server 管理シェル内から次のコマンドを実行します。

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

EnableQoS プロパティの値を False に設定することで、Windows 以外のオペレーティング システムを使用するデバイスの QoS を無効にできます。 次に例を示します。

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

これにより、ネットワーク (Redmond サイトなど) の一部で QoS を実装しながら、ネットワークの他の部分では QoS を無効のままにすることができます。

QoS を有効または無効にできるのは、次のWindows PowerShell。 これらのオプションは、Skype for Business Server コントロール パネルでは使用できません。

> [!NOTE]
> iOS Version 6.17 以降の Skype for Business クライアントは、QoS をサポートします。  この QoS 機能は、管理対象ネットワーク上の内部 Skype for Business または Lync プール サーバーに直接登録されている Skype for Business クライアントおよび IP 電話デバイスにのみ適用されます。 QoS は、インターネット上でルーティングされるトラフィックには適用されません。



