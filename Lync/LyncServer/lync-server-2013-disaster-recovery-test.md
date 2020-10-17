---
title: 'Lync Server 2013: 障害復旧テスト'
description: 'Lync Server 2013: 障害回復テスト。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disaster recovery test
ms:assetid: 04f5e747-d837-4350-9fc0-8605dbf025a7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn747887(v=OCS.15)
ms:contentKeyID: 63969571
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fa22abd37f656134c54381d63f29d3160ff85257
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557663"
---
# <a name="disaster-recovery-test-in-lync-server-2013"></a>Lync Server 2013 での障害復旧テスト

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2015-01-26_

Lync Server 2013 プールサーバーのシステム回復を実行して、ドキュメント化された障害回復プロセスをテストします。 このテストでは、1台のサーバーの完全なハードウェア障害をシミュレートし、リソース、計画、およびデータを回復できるようにするために役立ちます。 組織が異なるサーバーまたは他の機器に障害を発生させないようにするために、毎月テストの焦点を回すようにしてください。

組織が障害回復テストを実行するスケジュールは、どのようなものであるかが異なることに注意してください。 障害復旧テストは無視または放置されていないことが非常に重要です。

<div>


Lync Server 2013 のトポロジ、ポリシー、および構成設定をファイルにエクスポートします。 特に、アップグレード、ハードウェア障害、またはその他の問題によってデータが失われた後に、このファイルを中央管理ストアに復元することができます。

次のコマンドで示すように、Lync Server 2013 のトポロジ、ポリシー、および構成設定を中央管理ストアまたはローカルコンピューターにインポートします。

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

Lync Server 2013 の運用データをバックアップするには、次のようにします。

  - データベースをファイルまたはテープダンプデバイスにダンプするには、標準の SQL Server バックアッププロセスを使用して、RTC および LCSLog データベースをバックアップします。

  - サードパーティ製のバックアップアプリケーションを使用して、データをファイルまたはテープにバックアップします。

  - RTC データベース全体の XML エクスポートを作成するには、Export-CsUserData コマンドレットを使用します。

  - ファイルシステムバックアップまたはサードパーティを使用して、会議コンテンツとコンプライアンスログをバックアップします。

  - Export-CsConfiguration コマンドラインツールを使用して、Lync Server 2013 の設定をバックアップします。

フェールオーバー手順の最初の手順には、運用プールから障害復旧プールへのユーザーの強制移行が含まれます。

運用プールはユーザーの再配置を受け入れることができないため、これは強制的な移動になります。

Lync Server 2013 の移動ユーザープロセスは、実質的には、RTC SQL データベース上のレコードの更新に加えて、ユーザーアカウントオブジェクトの属性を変更します。

このデータは、次の2つのプロセスによって復元できます。

  - RTC データベースは、標準の SQL Server 復元プロセスを使用して、またはサードパーティのバックアップ/復元ユーティリティを使用して、運用 SQL Server から元のバックアップダンプデバイスから復元できます。

  - ユーザーの連絡先データは、運用 SQL Server エクスポートから作成された XML ファイルを使用して、DBIMPEXP.exe ユーティリティを使用して復元できます。

このデータを復元した後は、ユーザーは効果的に Disaster Recovery Lync Server 2013 プールに接続し、通常どおりに動作させることができます。

ユーザーが Disaster Recovery Lync Server 2013 プールに接続できるようにするために、DNS レコードの変更が必要になります。

運用 Lync Server 2013 プールは、次の自動構成および DNS SRV レコードを使用してクライアントによって参照されます。

  - SRV: \_ sip。 \_tls.\<domain\> /CNAME: SIP。\<domain\>

  - CNAME: SIP。\<domain\> /cvc/pool8-1。\<domain\>

フェールオーバーを容易にするために、この CNAME レコードを更新して、次のように、この CNAME レコードを参照する必要があります。

  - CNAME: SIP。\<domain\> /DROCSPool.\<domain\>

  - Sip.\<domain\>

  - AV.\<domain\>

  - fea-webconf-service.\<domain\>

  - OCSServices。\<domain\>

<div>


> [!IMPORTANT]  
> 管理手順の詳細については、「 <A href="lync-server-2013-backing-up-and-restoring-lync-server.md">Lync Server 2013 のバックアップと復元</A>」を参照してください。



</div>

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での高可用性および障害復旧の計画](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
[Lync Server 2013 のバックアップと高可用性のコマンドレット](https://docs.microsoft.com/powershell/module/skype/?view=skype-ps)  


[インポート-CsConfiguration](https://docs.microsoft.com/powershell/module/skype/Import-CsConfiguration)  
[Lync Server 2013 のバックアップと復元](lync-server-2013-backing-up-and-restoring-lync-server.md)  
[Lync Server 2013 の障害復旧、高可用性、およびバックアップサービスの管理](lync-server-2013-managing-lync-server-disaster-recovery-high-availability-and-backup-service.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

