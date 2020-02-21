---
title: 'Lync Server 2013: バックアップサービスの構成と監視'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring and monitoring the Backup Service
ms:assetid: c608280e-a7d1-4ae0-a75c-da6b524752fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205252(v=OCS.15)
ms:contentKeyID: 48185365
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a14e7a451b6d28df2663498e64cf2fb85c818352
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207563"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-and-monitoring-the-backup-service-in-lync-server-2013"></a>Lync Server 2013 でのバックアップサービスの構成と監視

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-11-01_

次の Lync Server 管理シェルコマンドを使用して、バックアップサービスの構成と監視を行うことができます。

<div>


> [!NOTE]  
> RTCUniversalServerAdmins グループは、既定で<STRONG>get-csbackupservicestatus</STRONG>を実行するためのアクセス許可を持つ唯一のグループです。 このコマンドレットを使用するには、このグループのメンバーとしてログオンします。 または、 <STRONG>get-csbackupserviceconfiguration</STRONG>コマンドレットを使用して、このコマンドへのアクセスを他のグループ (たとえば、csadministrator) に付与することもできます。



</div>

<div>

## <a name="to-see-the-backup-service-configuration"></a>バックアップサービスの構成を表示するには

次のコマンドレットを実行します。

    Get-CsBackupServiceConfiguration

SyncInterval の既定値は2分です。

</div>

<div>

## <a name="to-set-the-backup-service-sync-interval"></a>バックアップサービスの同期間隔を設定するには

次のコマンドレットを実行します。

    Set-CsBackupServiceConfiguration -SyncInterval interval

たとえば、次のように指定すると間隔が3分に設定されます。

    Set-CsBackupServiceConfiguration -SyncInterval 00:03:00

<div>


> [!IMPORTANT]  
> バックアップサービスの既定の同期間隔を変更するには、このコマンドレットを使用できますが、同期間隔は、バックアップサービスのパフォーマンスおよび目標復旧時点 (RPO) に大きく影響するため、絶対に必要でない限り、このコマンドレットは実行しないでください。



</div>

</div>

<div>

## <a name="to-get-the-backup-service-status-for-a-particular-pool"></a>特定のプールのバックアップサービスの状態を取得するには

次のコマンドレットを実行します。

    Get-CsBackupServiceStatus -PoolFqdn <pool-FQDN>

<div>


> [!NOTE]  
> バックアップサービスの同期状態は、プール (P1) からそのバックアッププール (P2) に対して、unidirectionally に定義されています。 P1 から P2 への同期の状態は、P2 から P1 までのものと異なる場合があります。 P1 から P2 では、P1 で行われたすべての変更が同期間隔内に P2 に完全にレプリケートされると、バックアップサービスは "安定した" 状態になります。 これは、P1 から P2 への同期を変更しない場合、"最終" 状態になります。 両方の状態は、コマンドレットが実行された時点でのバックアップサービスのスナップショットを示しています。 返される状態が後のままになることを意味するわけではありません。 特に、"final" 状態は、コマンドレットの実行後に P1 が変更を生成しない場合にのみ保持されます。 これは、p1 が<STRONG>initialize-cspoolfailover</STRONG>実行ロジックの一部として読み取り専用モードに配置された後に、P1 を P2 にフェールオーバーする場合に当てはまります。



</div>

</div>

<div>

## <a name="to-get-information-about-the-backup-relationship-for-a-particular-pool"></a>特定のプールに対するバックアップ関係に関する情報を取得するには

次のコマンドレットを実行します。

    Get-CsPoolBackupRelationship -PoolFQDN <poolFQDN>

</div>

<div>

## <a name="to-force-a-backup-service-sync"></a>バックアップサービスの同期を強制的に実行するには

次のコマンドレットを実行します。

    Invoke-CsBackupServiceSync -PoolFqdn <poolFqdn> [-BackupModule  {All|PresenceFocus|DataConf|CMSMaster}]

</div>

</div>

<span> </span>

</div>

</div>

</div>

