---
title: 'Lync Server 2013: バックアップ サービスの構成と監視'
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
ms.openlocfilehash: 9992f0466ceb2e01fa54cb2b2d511eeb96af755a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726537"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-and-monitoring-the-backup-service-in-lync-server-2013"></a>Lync Server 2013 でのバックアップ サービスの構成と監視

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-11-01_

次の Lync Server 管理シェルコマンドを使用して、バックアップサービスの構成と監視を行うことができます。

<div>


> [!NOTE]  
> RTCUniversalServerAdmins グループは、既定で<STRONG>Get-CsBackupServiceStatus</STRONG>を実行する権限を持つ唯一のグループです。 このコマンドレットを使うには、このグループのメンバーとしてログオンします。 または、 <STRONG>CsBackupServiceConfiguration</STRONG>コマンドレットを使用して、このコマンドへのアクセス権を他のグループ (たとえば、csadministrator) に付与することができます。



</div>

<div>

## <a name="to-see-the-backup-service-configuration"></a>バックアップサービスの構成を確認するには

次のコマンドレットを実行します。

    Get-CsBackupServiceConfiguration

SyncInterval の既定値は2分です。

</div>

<div>

## <a name="to-set-the-backup-service-sync-interval"></a>バックアップサービスの同期間隔を設定するには

次のコマンドレットを実行します。

    Set-CsBackupServiceConfiguration -SyncInterval interval

たとえば、次のように間隔を3分に設定します。

    Set-CsBackupServiceConfiguration -SyncInterval 00:03:00

<div>


> [!IMPORTANT]  
> バックアップサービスの既定の同期間隔を変更するには、このコマンドレットを使用できますが、同期間隔はバックアップサービスのパフォーマンスと回復ポイントの目標 (RPO) に大きな影響を与えるため、絶対に必要な場合以外は、この操作を行わないでください。



</div>

</div>

<div>

## <a name="to-get-the-backup-service-status-for-a-particular-pool"></a>特定のプールのバックアップサービスの状態を取得するには

次のコマンドレットを実行します。

    Get-CsBackupServiceStatus -PoolFqdn <pool-FQDN>

<div>


> [!NOTE]  
> バックアップサービスの同期状態は、プール (P1) からバックアッププール (P2) にまで1つずつ定義されています。 P1 から P2 への同期状態は、P2 から P1 までと異なる場合があります。 P1 から P2 の場合、P1 で行ったすべての変更が同期間隔で P2 に完全に複製されている場合、バックアップサービスは "定常" 状態になります。 P1 から P2 への同期が必要な変更がない場合は、"最終" 状態になります。 どちらの状態も、コマンドレットが実行された時点でのバックアップサービスのスナップショットを示します。 返される状態が後のままになるというわけではありません。 特に、コマンドレットが実行された後も、P1 が変更を生成しない場合に限り、"final" 状態が保持されます。 これは、p1 が<STRONG>CsPoolfailover</STRONG>実行ロジックの一部として読み取り専用モードに配置された後に、P1 を P2 に移行した場合に当てはまります。



</div>

</div>

<div>

## <a name="to-get-information-about-the-backup-relationship-for-a-particular-pool"></a>特定のプールのバックアップ関係に関する情報を取得するには

次のコマンドレットを実行します。

    Get-CsPoolBackupRelationship -PoolFQDN <poolFQDN>

</div>

<div>

## <a name="to-force-a-backup-service-sync"></a>バックアップサービスを強制的に同期するには

次のコマンドレットを実行します。

    Invoke-CsBackupServiceSync -PoolFqdn <poolFqdn> [-BackupModule  {All|PresenceFocus|DataConf|CMSMaster}]

</div>

</div>

<span> </span>

</div>

</div>

</div>

