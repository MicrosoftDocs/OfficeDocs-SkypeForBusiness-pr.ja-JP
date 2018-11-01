---
title: Windows に基づかないデバイスの QoS の有効化
TOCTitle: Windows に基づかないデバイスの QoS の有効化
ms:assetid: 26f793df-aef8-4028-9e3b-6c2c37ea61b9
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ204750(v=OCS.15)
ms:contentKeyID: 48271593
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Windows に基づかないデバイスの QoS の有効化

 

_**トピックの最終更新日:** 2012-11-01_

Microsoft Lync Server 2013 をインストールしたときに、組織で使用しているデバイスのうち Windows 以外のオペレーティング システムを使用するデバイスでは、サービスの品質 (QoS) が有効になりません。このことは Lync Server 2013 管理シェル内から次のコマンドを実行して確認できます。

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

EnableQoS プロパティが (前の出力のように) False に設定されている場合、Windows 以外のオペレーティング システムを使用するコンピューターとデバイスではサービスの品質が有効になっていません。Lync Phone Edition デバイスでは、QoS が既定で有効になります。ただし、Lync Phone Edition でサービスの品質を無効にすることもできます。

サービスの品質をグローバル スコープで有効にするには、Lync Server 管理シェル内から次のコマンドを実行します。

    Set-CsMediaConfiguration -EnableQoS $True

このコマンドを実行すると QoS がグローバル スコープで有効になります。ただし、メディア構成設定はサイト スコープにも適用できるという点に注意してください。サービスの品質を特定のサイトで有効にする必要がある場合は、Set-CsMediaConfiguration を呼び出すときに構成設定の Identity を指定します。たとえば、次のコマンドは Redmond サイトで QoS を有効にします。

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True

> [!NOTE]
> QoS をサイト スコープで有効にする必要があるかどうかは、状況によって異なります。サイト スコープに割り当てた設定は、グローバル スコープに割り当てた設定に優先します。たとえば、QoS をグローバル スコープで有効にし、サイト スコープ (Redmond サイト) では無効にしているとします。この場合、Redmond サイトではサービスの品質が無効になります。サイトの設定が優先するからです。Redmond サイトで QoS を有効にするには、サイトに適用されるメディア構成設定を使用して有効にする必要があります。


すべてのメディア構成設定で (スコープにかかわらず) QoS を同時に有効にする場合は、Lync Server 管理シェル内から次のコマンドを実行します。

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

Windows 以外のオペレーティング システムを使用するデバイスで QoS を無効にするには、EnableQoS プロパティの値を False に設定します。次に例を示します。

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

これにより、ネットワーク (Redmond サイトなど) の一部で QoS を実装しながら、ネットワークの他の部分では QoS を無効のままにすることができます。

QoS を有効または無効にするには Lync Server 管理シェルを使用する必要があります。Lync Server コントロール パネルには、これらのオプションはありません。

