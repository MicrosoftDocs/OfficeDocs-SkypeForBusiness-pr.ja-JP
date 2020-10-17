---
title: 'Lync Server 2013: CDR テーブルの詳細'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: CDR table details
ms:assetid: 896198f5-672b-48ea-852f-0211c0c90857
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398693(v=OCS.15)
ms:contentKeyID: 48184730
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47a9554be31e4ea93d7b8a0a2fc0de040d26d78c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508054"
---
# <a name="cdr-table-details-in-lync-server-2013"></a>Lync Server 2013 の CDR テーブルの詳細

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-18_

以下のトピックでは、通話詳細記録 (CDR) データベース スキーマの各テーブル内の列について詳しく説明します。

<div>

## <a name="in-this-section"></a>このセクションの内容

  - [Lync Server 2013 のアプリケーションテーブル](lync-server-2013-application-table.md)

  - [Lync Server 2013 の CallPriorities テーブル](lync-server-2013-callpriorities-table.md)

  - [Lync Server 2013 の CallType テーブル](lync-server-2013-calltype-table.md)

  - [Lync Server 2013 の ClientVersions テーブル](lync-server-2013-clientversions-table.md)

  - [Lync Server 2013 の ConferenceJoinTimeThresholds テーブル](lync-server-2013-conferencejointimethresholds-table.md)

  - [Lync Server 2013 の ConferenceMessageCount テーブル](lync-server-2013-conferencemessagecount-table.md)

  - [Lync Server 2013 の会議テーブル](lync-server-2013-conferences-table.md)

  - [Lync Server 2013 の ConferenceSessionDetails テーブル](lync-server-2013-conferencesessiondetails-table.md)

  - [Lync Server 2013 の ConferenceUris テーブル](lync-server-2013-conferenceuris-table.md)

  - [Lync Server 2013 の ContentTypes テーブル](lync-server-2013-contenttypes-table.md)

  - [Lync Server 2013 の DeRegisterType テーブル](lync-server-2013-deregistertype-table.md)

  - [Lync Server 2013 の Devices テーブル](lync-server-2013-devices-table.md)

  - [Lync Server 2013 のダイアログテーブル](lync-server-2013-dialogs-table.md)

  - [Lync Server 2013 の EdgeServers テーブル](lync-server-2013-edgeservers-table.md)

  - [Lync Server 2013 の ErrorCategory テーブル](lync-server-2013-errorcategory-table.md)

  - [Lync Server 2013 の ErrorDef テーブル](lync-server-2013-errordef-table.md)

  - [Lync Server 2013 の ErrorReport テーブル](lync-server-2013-errorreport-table.md)

  - [Lync Server 2013 の FileTransfers テーブル](lync-server-2013-filetransfers-table.md)

  - [Lync Server 2013 の FocusJoinsAndLeaves テーブル](lync-server-2013-focusjoinsandleaves-table.md)

  - [Lync Server 2013 のフロントエンドテーブル](lync-server-2013-frontend-table.md)

  - [Lync Server 2013 のゲートウェイテーブル](lync-server-2013-gateways-table.md)

  - [Lync Server 2013 の [ハードウェアバージョン表の一覧](lync-server-2013-hardwareversions-table.md)

  - [Lync Server 2013 の IMReportSummary テーブル](lync-server-2013-imreportsummary-table.md)

  - [Lync Server 2013 の場所テーブル](lync-server-2013-locations-table.md)

  - [Lync Server 2013 の [製造元の表」](lync-server-2013-manufacturers-table.md)

  - [Lync Server 2013 の McuJoinsAndLeaves テーブル](lync-server-2013-mcujoinsandleaves-table.md)

  - [Lync Server 2013 の mcu テーブル](lync-server-2013-mcus-table.md)

  - [Lync Server 2013 のメディアテーブル](lync-server-2013-media-table.md)

  - [Lync Server 2013 の MediaList テーブル](lync-server-2013-medialist-table.md)

  - [Lync Server 2013 の MediationServers テーブル](lync-server-2013-mediationservers-table.md)

  - [Lync Server 2013 の MSMQProcessing テーブル](lync-server-2013-msmqprocessing-table.md)

  - [Lync Server 2013 の電話表](lync-server-2013-phones-table.md)

  - [Lync Server 2013 のプールテーブル](lync-server-2013-pools-table.md)

  - [Lync Server 2013 の進捗レポートの表](lync-server-2013-progressreport-table.md)

  - [Lync Server 2013 の PurgeSettings テーブル](lync-server-2013-purgesettings-table.md)

  - [Lync Server 2013 の登録テーブル](lync-server-2013-registration-table.md)

  - [Lync Server 2013 の Roles テーブル](lync-server-2013-roles-table.md)

  - [Lync Server 2013 のサーバーテーブル](lync-server-2013-servers-table.md)

  - [Lync Server 2013 の SessionDetails テーブル](lync-server-2013-sessiondetails-table.md)

  - [Lync Server 2013 の SIPResponseMetaData テーブル](lync-server-2013-sipresponsemetadata-table.md)

  - [Lync Server 2013 の Syndicators テーブル](lync-server-2013-syndicators-table.md)

  - [Lync Server 2013 の SyndicatorsTenantMap テーブル](lync-server-2013-syndicatorstenantmap-table.md)

  - [Lync Server 2013 のタスクテーブル](lync-server-2013-task-table.md)

  - [Lync Server 2013 のテナントテーブル](lync-server-2013-tenants-table.md)

  - [Lync Server 2013 の UriTypes テーブル](lync-server-2013-uritypes-table.md)

  - [Lync Server 2013 のユーザーテーブル](lync-server-2013-users-table.md)

  - [Lync Server 2013 の UserAgentDef テーブル](lync-server-2013-useragentdef-table.md)

  - [Lync Server 2013 の UserStatistics テーブル](lync-server-2013-userstatistics-table.md)

  - [Lync Server 2013 の VoipDetails テーブル](lync-server-2013-voipdetails-table.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

