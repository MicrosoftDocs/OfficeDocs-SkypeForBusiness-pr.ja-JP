---
title: 'Lync Server 2013: 障害復旧テスト'
TOCTitle: 障害復旧テスト
ms:assetid: 04f5e747-d837-4350-9fc0-8605dbf025a7
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Dn747887(v=OCS.15)
ms:contentKeyID: 62293540
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での障害復旧テスト

 

_**トピックの最終更新日:** 2015-01-26_

Lync Server 2013 プール サーバーのシステム回復を実行して、ドキュメント化された障害回復プロセスをテストします。このテストは、サーバーの完全なハードウェア エラーをシミュレーションを実行して、リソース、プラン、およびデータを回復に利用できることを保証するのに役立ちます。異なるサーバーやその他の装置のエラーをいつでもテストできるようにテストの焦点を各月で循環させるようにしてください。

組織が障害回復テストを実施するスケジュールは異なることに注意してください。障害回復テストが無視またはなおざりにされないことが非常に重要です。


Lync Server 2013 のトポロジ、ポリシー、および構成設定をファイルにエクスポートします。また、アップグレード、ハードウェア障害、またはその他の問題のためにデータを消失してしまっても、このファイルを使用して、これらの情報を中央管理ストアに復元することができます。

Lync Server 2013 のトポロジ、ポリシー、および構成設定を、以下のコマンドに示すように中央管理ストアまたはローカル コンピューターのどちらかにインポートします。

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

運用 Lync Server 2013 データをバックアップするには、次の手順を実行します。

  - 標準の SQL Server バックアップ プロセスを使用して RTC および LCSLog データベースをバックアップし、データベースをファイルまたはテープ ダンプ デバイスにダンプします。

  - サードパーティ バックアップ アプリケーションを使用してデータをファイルまたはテープにバック アップします。

  - Export-CsUserData コマンドレットを使用して、RTC データベース全体の XML エクスポートを作成します。

  - ファイル システム バックアップまたはサードパーティ バックアップ アプリケーションを使用して、会議コンテンツやコンプライアンス ログをバックアップします。

  - Export-CsConfiguration コマンド ライン ツールを使用して、Lync Server 2013 の設定をバックアップします。

フェールオーバー手順の最初の手順には、運用プールから障害回復プールへのユーザーの強制的な移動が含まれます。

運用プールはユーザーの再配置を受け入れることができないため、これは強制的な移動になります。

Lync Server 2013 のユーザー移動プロセスは、RTC SQL データベース上でのレコードの更新に加え、ユーザー アカウント オブジェクトの属性を効果的に変更します。

このデータは、以下の 2 つの処理を通じて復元できます。

  - RTC データベースは、標準の SQL Server 復元プロセスを使用するか、サーバーパーティ バックアップ/復元ユーティリティを使用して、運用 SQL Server の元のバックアップ ダンプ デバイスから復元できます。

  - ユーザー連絡先データは、運用 SQL Server エクスポートから作成した XML ファイルを使用して、DBIMPEXP.exe ユーティリティで復元できます。

このデータを復元した後、ユーザーは障害回復 Lync Server 2013 プールに効果的に接続して通常どおり操作できます。

ユーザーが障害回復 Lync Server 2013 プールに接続するには、DNS レコードの変更が必要になります。

運用 Lync Server 2013 プールは、クライアントにより 自動構成および次の DNS SRV レコードを使用して参照されます。

  - SRV: \_sip.\_tls.\<domain\> /CNAME: SIP.\<domain\>

  - CNAME: SIP.\<domain\> /cvc-pool-1.\<domain\>

フェールオーバーを促進するために、この CNAME レコードを更新して DROCSPool FQDN を次のように参照する必要があります。

  - CNAME: SIP.\<domain\> /DROCSPool.\<domain\>

  - Sip.\<domain\>

  - AV.\<domain\>

  - webconf.\<domain\>

  - OCSServices.\<domain\>


> [!IMPORTANT]
> 管理および管理手順の詳細については、「<A href="lync-server-2013-backing-up-and-restoring-lync-server.md">Lync Server 2013 のバックアップと復元</A>」を参照してください。



## 関連項目

#### 概念

[Lync Server 2013 での高可用性および障害復旧の計画](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
[バックアップおよび高可用性のコマンドレット](https://docs.microsoft.com/en-us/powershell/module/skype/?view=skype-ps)  

#### その他のリソース

[Import-CsConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Import-CsConfiguration)  
[Lync Server 2013 のバックアップと復元](lync-server-2013-backing-up-and-restoring-lync-server.md)  
[Lync Server 2013 の障害復旧、高可用性およびバックアップ サービスの管理](lync-server-2013-managing-lync-server-disaster-recovery-high-availability-and-backup-service.md)

