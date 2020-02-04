---
title: 'Lync Server 2013: 障害復旧テスト'
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
ms.openlocfilehash: f7c6c3b7c3b5d78324fe9c674650dd94338baea4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739197"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disaster-recovery-test-in-lync-server-2013"></a>Lync Server 2013 での障害復旧テスト

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2015-01-26_

Lync Server 2013 プールサーバーのシステム回復を実行して、文書化された障害回復プロセスをテストします。 このテストは、サーバーの完全なハードウェア エラーをシミュレーションを実行して、リソース、プラン、およびデータを回復に利用できることを保証するのに役立ちます。 異なるサーバーやその他の装置のエラーをいつでもテストできるようにテストの焦点を各月で循環させるようにしてください。

組織が障害回復テストを実施するスケジュールは異なることに注意してください。障害回復テストが無視またはなおざりにされないことが非常に重要です。

<div>


Lync Server 2013 のトポロジ、ポリシー、構成設定をファイルにエクスポートします。 また、アップグレード、ハードウェア障害、またはその他の問題のためにデータを消失してしまっても、このファイルを使用して、これらの情報を中央管理ストアに復元することができます。

次のコマンドで示されているように、Lync Server 2013 のトポロジ、ポリシー、構成設定を中央管理ストアまたはローカルコンピューターにインポートします。

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

プロダクション用の Lync Server 2013 データをバックアップするには、次の操作を行います。

  - 標準の SQL Server バックアッププロセスを使用して、RTC と LCSLog データベースのバックアップを作成し、ファイルまたはテープダンプデバイスにデータベースをダンプします。

  - サードパーティ バックアップ アプリケーションを使用してデータをファイルまたはテープにバック アップします。

  - Export-CsUserData コマンドレットを使用して、RTC データベース全体の XML エクスポートを作成します。

  - ファイル システム バックアップまたはサードパーティ バックアップ アプリケーションを使用して、会議コンテンツやコンプライアンス ログをバックアップします。

  - エクスポート-CsConfiguration コマンドラインツールを使用して、Lync Server 2013 の設定をバックアップします。

フェールオーバー手順の最初の手順には、運用プールから障害回復プールへのユーザーの強制的な移動が含まれます。

運用プールはユーザーの再配置を受け入れることができないため、これは強制的な移動になります。

Lync Server 2013 の移動ユーザープロセスは、実質的には、RTC SQL データベースのレコードの更新に加えて、ユーザーアカウントオブジェクトの属性に対する変更になります。

このデータは、以下の 2 つの処理を通じて復元できます。

  - RTC データベースは、標準の SQL Server 復元プロセスを使用するか、サードパーティのバックアップ/復元ユーティリティを使用して、実働 SQL Server から元のバックアップダンプデバイスから復元することができます。

  - ユーザー連絡先データは、運用 SQL Server エクスポートから作成した XML ファイルを使用して、DBIMPEXP.exe ユーティリティで復元できます。

このデータが復元されると、ユーザーは効果的に Disaster Recovery Lync Server 2013 プールに接続し、通常どおりに動作することができます。

ユーザーが Disaster Recovery Lync Server 2013 プールに接続できるようにするには、DNS レコードの変更が必要になります。

プロダクション Lync Server 2013 プールは、次の自動構成と DNS SRV レコードを使用してクライアントから参照されます。

  - SRV: \_sip。\_tls。\<ドメイン\> /CNAME: SIP。\<ドメイン\>

  - CNAME: SIP。\<domain\> /cvc¥ pool1。\<ドメイン\>

フェールオーバーを促進するために、この CNAME レコードを更新して DROCSPool FQDN を次のように参照する必要があります。

  - CNAME: SIP。\<domain\> /DROCSPool.\<ドメイン\>

  - フェデレーション.\<ドメイン\>

  - AV。\<ドメイン名\>

  - webconf\<ドメイン\>

  - OCSServices。\<ドメイン\>

<div>


> [!IMPORTANT]  
> 管理と管理の詳細な手順については、「 <A href="lync-server-2013-backing-up-and-restoring-lync-server.md">Lync Server 2013 のバックアップと復元</A>」を参照してください。



</div>

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での高可用性および障害復旧の計画](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
[Lync Server 2013 のバックアップと高可用性のコマンドレット](https://docs.microsoft.com/powershell/module/skype/?view=skype-ps)  


[インポート-CsConfiguration](https://docs.microsoft.com/powershell/module/skype/Import-CsConfiguration)  
[Lync Server 2013 のバックアップと復元](lync-server-2013-backing-up-and-restoring-lync-server.md)  
[Lync Server 2013 の障害復旧、高可用性およびバックアップ サービスの管理](lync-server-2013-managing-lync-server-disaster-recovery-high-availability-and-backup-service.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

