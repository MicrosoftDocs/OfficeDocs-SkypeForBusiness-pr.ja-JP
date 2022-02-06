---
title: Windows ベースではないデバイスの QoS の有効化
ms.reviewer: null
'ms:assetid': 26f793df-aef8-4028-9e3b-6c2c37ea61b9
'ms:mtpsurl': 'https://technet.microsoft.com/en-us/library/JJ204750(v=OCS.15)'
'ms:contentKeyID': 48183661
mtps_version: v=OCS.15
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
description: 組織で使用されているデバイスで QoS を有効にする方法について説明します。この方法では、他のオペレーティング システムを使用Windows。
---

# <a name="enabling-qos-in-skype-for-business-server-for-devices-that-are-not-based-on-windows"></a>デバイスに基づいてSkype for Business Serverデバイスの QoS を有効Windows


サービス をインストールSkype for Business Server、サービス品質 (QoS) は、ユーザー以外のオペレーティング システムを使用する組織内で使用されるデバイスに対して有効Windows。 これを確認するには、次のコマンドを ServerManagement シェルSkype for Business実行します。

**Get-CsMediaConfiguration**

メディア構成設定を変更していない場合は、次のような情報を取得する必要があります。

ID : グローバル<br/>
EnableQoS : False<br/>
EncryptionLevel : RequireEncryption<br/>
EnableSiren : False<br/>
MaxVideoRateAllowed : VGA600K<br/>
EnableG722StereoCodec : True<br/>
EnableH264Codec : True<br/>
EnableAdaptiveBandwidthEstimation : True<br/>

EnableQoS プロパティが False (前の出力と同様) に設定されている場合は、Windows 以外のオペレーティング システムを使用するコンピューターやデバイスでサービス品質が有効になっていないという意味です。

グローバル スコープでサービス品質を有効にするには、管理シェル内から次のコマンドSkype for Business Server実行します。

**Set-CsMediaConfiguration -EnableQoS $True**

前のコマンドは、グローバル スコープで QoS を有効にしています。ただし、メディア構成設定をサイト スコープにも適用できる点に注意することが重要です。 サイトのサービス品質を有効にする必要がある場合は、Set-CsMediaConfiguration を呼び出す際に構成設定の ID を含める必要があります。 たとえば、このコマンドは Redmond サイトの QoS を有効にしています。

**Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True**


> [!NOTE]
> QoS をサイト スコープで有効にする必要があるかどうかは、状況によって異なります。 サイト スコープに割り当てた設定は、グローバル スコープに割り当てた設定に優先します。 たとえば、QoS をグローバル スコープで有効にし、サイト スコープ (Redmond サイト) では無効にしているとします。 グローバル スコープで QoS が有効になっているが、サイト スコープで無効になっているとします (Redmond サイトの場合)。 その場合、サービス品質は Redmond サイトで無効になります。これは、サイト設定が優先されるためです。 Redmond サイトの QoS を有効にするには、そのサイトに適用されるメディア構成設定を使用して有効にする必要があります。


すべてのメディア構成設定 (スコープに関係なく) で QoS を同時に有効にする場合は、LSkype for Business Server 管理シェル内から次のコマンドを実行します。

**Get-CsMediaConfiguration |Set-CsMediaConfiguration -EnableQoS $True**

EnableQoS プロパティの値を False に設定すると、Windows以外のオペレーティング システムを使用するデバイスの QoS を無効にできます。 次に例を示します。

**Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False**

これにより、ネットワーク (Redmond サイトなど) の一部で QoS を実装しながら、ネットワークの他の部分では QoS を無効のままにすることができます。

QoS を有効または無効にできるのは、次のWindows PowerShell。 これらのオプションは、[コントロール パネル] Skype for Business Server使用できません。

> [!NOTE]
> Skype for Businessバージョン 6.17 以降のクライアントは QoS をサポートしています。  この QoS 機能は、Skype for Businessネットワーク上の内部クライアントまたは Lync プール サーバー Skype for Businessに直接登録されているクライアントおよび IP 電話デバイスにのみ適用されます。 QoS は、インターネットを通してルーティングされるトラフィックには適用されません。
