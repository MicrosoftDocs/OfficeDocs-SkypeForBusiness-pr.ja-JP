---
title: 'Lync Server 2013: モビリティの展開プロセス'
description: 'Lync Server 2013: モビリティの展開プロセス。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for mobility
ms:assetid: 5a1cebda-c14b-4ff4-9c36-f7caa868160f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690023(v=OCS.15)
ms:contentKeyID: 48184220
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b49d69af899f6d9f2ac1db5040d017a9d62ce9eb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551043"
---
# <a name="deployment-process-for-mobility-in-lync-server-2013"></a>Lync Server 2013 でのモビリティの展開プロセス

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-19_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013. It is noted accordingly.

このセクションでは、Lync Server 2013 モビリティ機能を展開するために必要な一連の手順について説明します。

### <a name="mobility-deployment-process"></a>モビリティの展開プロセス

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>フェーズ</th>
<th>手順</th>
<th>アクセス許可</th>
<th>展開のドキュメント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ドメイン ネーム システム (DNS) レコードを作成する</p></td>
<td><ul>
<li><p>内部の自動検出サービス URL を解決するための内部 DNS CNAME または A (host、if IPv6、AAAA) レコードを作成します。</p></li>
<li><p>外部の自動検出サービス URL を解決する外部 DNS CNAME または A (host、if IPv6、AAAA) レコードを作成します。</p></li>
</ul></td>
<td><p>Domain Admins</p>
<p>DnsAdmins</p></td>
<td><p><a href="lync-server-2013-creating-dns-records-for-the-autodiscover-service.md">Lync Server 2013 での自動検出サービスの DNS レコードの作成</a></p></td>
</tr>
<tr class="even">
<td><p>証明書を変更する</p></td>
<td><p>サブジェクトの別名エントリを以下の証明書に追加し、モバイル ユーザーのセキュリティで保護された接続をサポートします。</p>
<ul>
<li><p>ディレクター証明書</p></li>
<li><p>フロントエンドプールの証明書</p></li>
<li><p>リバース プロキシの証明書</p></li>
</ul></td>
<td><p>ローカル管理者</p></td>
<td><p><a href="lync-server-2013-modifying-certificates-for-mobility.md">Lync Server 2013 でのモビリティの証明書の変更</a></p></td>
</tr>
<tr class="odd">
<td><p>リバース プロキシを構成する</p></td>
<td><ul>
<li><p>サブジェクトの別名で更新された証明書を SSL (Secure Sockets Layer) リスナーに割り当てます。</p></li>
<li><p>外部自動検出サービス URL の web 公開ルールを再構成します。</p></li>
<li><p>フロントエンドプールに外部 Lync Server 2013 Web サービス URL 用の web 公開ルールが存在することを確認してください。</p></li>
</ul>
<p>または</p>
<ul>
<li><p>最初の自動検出要求に HTTP を使用し、証明書のサブジェクトの別名リストを更新しない場合は、新しい web 公開ルールを構成するか、ポート 80 HTTP の既存の公開ルールを再構成します。</p></li>
</ul></td>
<td><p>ローカル管理者</p></td>
<td><p><a href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Lync Server 2013 でのモビリティのリバースプロキシの構成</a></p></td>
</tr>
<tr class="even">
<td><p>Mcx Mobility Service を使用して Lync 2010 Mobile のモビリティ展開をテストする</p></td>
<td><p><strong>Test-CsMcxP2PIM</strong> を実行し、ユーザー間のインスタント メッセージの送信をテストします。</p>
<p>オプションの完全な一覧については、「 <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM">test-csmcxp2pim</a> 」の Lync Server Management Shell コマンドレットのドキュメントを参照してください。</p></td>
<td><p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-verifying-your-mobility-deployment.md">Lync Server 2013 でのモビリティの展開の確認</a></p></td>
</tr>
<tr class="odd">
<td><p>UCWA Web コンポーネントを使用して Lync 2013 Mobile クライアントのモビリティ展開をテストする</p></td>
<td><p><strong>Test-csucwaconference</strong>コマンドレットを使用して、定義済みのテストユーザーまたは実際のユーザーのペアが、ucwa を使用して会議を作成して参加できることを確認します。</p>
<p>オプションの完全な一覧については、「 <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference">test-csucwaconference</a> 」の Lync Server Management Shell コマンドレットのドキュメントを参照してください。</p></td>
<td><p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-verifying-your-mobility-deployment.md">Lync Server 2013 でのモビリティの展開の確認</a></p></td>
</tr>
<tr class="even">
<td><p>プッシュ通知を構成する</p></td>
<td><ul>
<li><p>Lync Server 2013 エッジサーバーの場合は、Lync Server online ホスティングプロバイダーを追加し、ホスティングプロバイダーフェデレーションを構成します。</p></li>
<li><p>Lync Server 2010 エッジサーバーの場合は、Lync Server online ホスティングプロバイダーを追加し、ホスティングプロバイダーフェデレーションを構成します。</p></li>
<li><p>Office Communications Server 2007 R2 エッジサーバーの場合は、フェデレーションパートナーを追加します。</p></li>
<li><p>Wi-Fi ネットワーク経由のプッシュ通知をサポートする場合は、TCP ポート5223に対する送信ファイアウォールルールを構成します。</p></li>
<li><p>Apple Push Notification Service (APNS) および Microsoft プッシュ通知サービス (MPNS) へのプッシュ通知を有効にするには、 <strong>Set-Cspの Notificationconfiguration</strong> コマンドレットを使用します。 既定では、この機能は無効になっています。</p></li>
<li><p>プッシュ通知をテストするには、 <strong>test-csfederatedpartner</strong> コマンドレットを使用してフェデレーション構成をテストし、 <strong>CsMCXPushNotification</strong> コマンドレットをテストします。</p>
<div>

> [!NOTE]  
> プッシュ通知は、Apple デバイスおよび Windows Phone の Lync 2010 モバイルクライアントで使用されます。<BR>Windows Phone のみの Lync 2013 モバイルクライアントでプッシュ通知が必要


</div></li>
</ul></td>
<td><p>RtcUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-configuring-for-push-notifications.md">Lync Server 2013 でのプッシュ通知の構成</a></p></td>
</tr>
<tr class="odd">
<td><p>モビリティポリシーを構成する</p></td>
<td><p><strong>Get-csmobilitypolicy</strong>コマンドレットを使用して、次のことを許可または禁止します。</p>
<ul>
<li><p>勤務先から通話</p></li>
<li><p>IP オーディオと IP ビデオを有効にする</p></li>
<li><p>IP オーディオまたは IP ビデオに WiFi が必要</p></li>
</ul></td>
<td><p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configuring-mobility-policy.md">Lync Server 2013 でのモビリティポリシーの構成</a></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

