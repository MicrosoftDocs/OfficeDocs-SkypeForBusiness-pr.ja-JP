---
title: Windows ベース以外のデバイスの QoS を有効にします。
ms:assetid: 26f793df-aef8-4028-9e3b-6c2c37ea61b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204750(v=OCS.15)
ms:contentKeyID: 48183661
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Windows 以外のオペレーティング システムを使用する組織で使用するデバイスの QoS を有効にする方法を説明します。
ms.openlocfilehash: 0dc870080b3cfcd5f73eaf6e45aee841b9c8b488
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222773"
---
# <a name="enabling-qos-in-skype-for-business-server-for-devices-that-are-not-based-on-windows"></a>ビジネス サーバーの Windows ベース以外のデバイスに Skype で QoS を有効にします。


ビジネス サーバーの Skype をインストールするとサービスの品質 (QoS) になって、組織で使用される Windows 以外のオペレーティング システムを使用するすべてのデバイスのです。 ビジネス ServerManagement シェルには、Skype 内で次のコマンドを実行することによってこれを確認することができます。

    Get-CsMediaConfiguration

メディア構成の設定を変更を加えていない場合を想定して、必要がある情報が返されます次のような。

    Identity                          : Global
    EnableQoS                         : False
    EncryptionLevel                   : RequireEncryption
    EnableSiren                       : False
    MaxVideoRateAllowed               : VGA600K
    EnableG722StereoCodec             : True
    EnableH264Codec                   : True
    EnableAdaptiveBandwidthEstimation : True

場合は、EnableQoS プロパティは、Windows 以外のオペレーティング システムを使用するコンピューターおよびデバイスの品質のサービスが無効になっていることを意味する (上記の出力) と同様に False に設定されます。

グローバル スコープでは、品質のサービスを有効にするには、ビジネス サーバー管理シェルには、Skype 内で次のコマンドを実行します。

    Set-CsMediaConfiguration -EnableQoS $True

上記のコマンドは、グローバル スコープで QoS を有効にただし、重要なメディアの構成設定はサイト スコープにも適用できます。 サイトの品質のサービスを有効にする場合は、セット CsMediaConfiguration を呼び出すときに構成設定の Id を含める必要があります。 たとえば、このコマンドは、レドモンド サイトの QoS を有効にします。

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True



> [!NOTE]  
> サイトのスコープで QoS を有効にする必要がありますか。 ケースバイケースです。 サイト スコープに割り当てられている設定は、グローバル スコープに割り当てられている設定よりも優先されます。 QoS をグローバル スコープで有効になっているが、(レドモンド サイトの) サイトのスコープで無効にします。 Redmond のサイトの品質のサービスは無効にする場合は、サイトの設定が優先するためです。 レドモンド サイトで QoS を有効にするのには、メディアの構成設定を使用してそのサイトに適用されるようにする必要があります。


(スコープ) に関係なくすべてのメディア構成設定の QoS を同時に有効にする場合は、ビジネス サーバー管理シェルの場合、LSkype 内からは、このコマンドを実行します。

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

Windows 以外のオペレーティング システムを使用して、EnableQoS プロパティの値を False に設定しているデバイスの QoS を無効にすることができます。 次に例を示します。

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

こうことによりでいくつかの部分 (たとえば、レドモンド サイト) で、ネットワークの QoS を実装するためにサービスの品質は、ネットワークのほかの部分を無効にしたまま。

QoS を有効になっているだけと Windows PowerShell を使用して無効にします。 これらのオプションは、ビジネス サーバーのコントロール パネルの Skype でご利用いただけません。


