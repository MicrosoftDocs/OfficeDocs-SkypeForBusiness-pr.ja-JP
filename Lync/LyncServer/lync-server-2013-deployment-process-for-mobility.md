---
title: 'Lync Server 2013: モビリティの展開プロセス'
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
ms.openlocfilehash: c6f9f7994981a860aaa02d4674d6a3248c3593d6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762595"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-mobility-in-lync-server-2013"></a>Lync Server 2013 のモビリティの展開プロセス

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-19_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013. It is noted accordingly.

このセクションでは、Lync Server 2013 モビリティ機能の展開に必要な一連の手順について説明します。

### <a name="mobility-deployment-process"></a>モバイル展開プロセス

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>段階</th>
<th>ステップ</th>
<th>アクセス許可</th>
<th>「展開」のドキュメント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ドメインネームシステム (DNS) レコードを作成する</p></td>
<td><ul>
<li><p>内部の自動検出サービス URL を解決する内部 DNS CNAME または A (IPv6、AAAA) レコードを作成します。</p></li>
<li><p>外部の自動検出サービス URL を解決するには、外部 DNS CNAME または A (IPv6、AAAA) レコードを作成します。</p></li>
</ul></td>
<td><p>Domain Admins</p>
<p>DnsAdmins</p></td>
<td><p><a href="lync-server-2013-creating-dns-records-for-the-autodiscover-service.md">Lync Server 2013 での自動検出サービスの DNS レコードの作成</a></p></td>
</tr>
<tr class="even">
<td><p>証明書を変更する</p></td>
<td><p>モバイルユーザーへのセキュリティで保護された接続をサポートするために、次の証明書にサブジェクト代替名のエントリを追加します。</p>
<ul>
<li><p>ディレクター証明書</p></li>
<li><p>フロントエンドプールの証明書</p></li>
<li><p>リバースプロキシ証明書</p></li>
</ul></td>
<td><p>ローカル管理者</p></td>
<td><p><a href="lync-server-2013-modifying-certificates-for-mobility.md">Lync Server 2013 でのモビリティに合わせた証明書の変更</a></p></td>
</tr>
<tr class="odd">
<td><p>リバース プロキシを構成する</p></td>
<td><ul>
<li><p>サブジェクトの代替名を使用して、セキュリティで保護されたソケットレイヤー (SSL) リスナーに証明書を割り当てます。</p></li>
<li><p>外部自動検出サービス URL の web 公開ルールを再構成します。</p></li>
<li><p>フロントエンドプールの外部の Lync Server 2013 Web サービスの URL に web 発行ルールが存在することを確認します。</p></li>
</ul>
<p>または</p>
<ul>
<li><p>最初の自動検出要求に HTTP を使用し、証明書のサブジェクト代替名の一覧を更新しない場合は、新しい web 公開ルールを構成するか、ポート 80 HTTP の既存の公開ルールを再設定します。</p></li>
</ul></td>
<td><p>ローカル管理者</p></td>
<td><p><a href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Lync Server 2013 での、モビリティに合わせたリバース プロキシの構成</a></p></td>
</tr>
<tr class="even">
<td><p>Mcx Mobility Service を使用して Lync 2010 Mobile のモバイル展開をテストする</p></td>
<td><p><strong>CsMcxP2PIM</strong>を実行して、1人のユーザーから別のユーザーへのインスタントメッセージの送信をテストします。</p>
<p>オプションの完全な一覧については、「 <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM">CsMcxP2PIM</a>の Lync Server 管理シェルコマンドレット」を参照してください。</p></td>
<td><p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-verifying-your-mobility-deployment.md">Lync Server 2013 でのモビリティ展開の確認</a></p></td>
</tr>
<tr class="odd">
<td><p>UCWA Web コンポーネントを使用して Lync 2013 モバイルクライアント用のモバイル展開をテストする</p></td>
<td><p><strong>CsUcwaConference</strong>コマンドレットを使用して、事前に定義されたテストユーザーまたは実際のユーザーが ucwa を使用して会議を作成し、参加できることを確認します。</p>
<p>オプションの完全な一覧については、「 <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference">CsUcwaConference</a>の Lync Server 管理シェルコマンドレット」を参照してください。</p></td>
<td><p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-verifying-your-mobility-deployment.md">Lync Server 2013 でのモビリティ展開の確認</a></p></td>
</tr>
<tr class="even">
<td><p>プッシュ通知を構成する</p></td>
<td><ul>
<li><p>Lync Server 2013 Edge サーバーの場合は、Lync Server online ホスティングプロバイダーを追加して、ホスティングプロバイダーフェデレーションを構成します。</p></li>
<li><p>Lync Server 2010 Edge サーバーの場合は、Lync Server online ホスティングプロバイダーを追加して、ホスティングプロバイダーフェデレーションを構成します。</p></li>
<li><p>Office Communications Server 2007 R2 Edge サーバーの場合は、フェデレーションパートナーを追加します。</p></li>
<li><p>Wi-fi ネットワーク経由でのプッシュ通知をサポートする場合は、TCP ポート5223用のファイアウォール規則を構成します。</p></li>
<li><p><strong>Set-cspの設定</strong>コマンドレットを使用して、Apple Push notification SERVICE (APNS) と Microsoft プッシュ通知サービス (MPNS) へのプッシュ通知を有効にします。 この機能は既定では無効になっています。</p></li>
<li><p><strong>CsFederatedPartner</strong>コマンドレットを使用して、フェデレーション構成とテスト用<strong>CsMCXPushNotification</strong>コマンドレットをテストして、プッシュ通知をテストします。</p>
<div>

> [!NOTE]  
> Apple デバイスと Windows Phone での Lync 2010 モバイルクライアントでは、プッシュ通知が使われます。<BR>Windows Phone のみの Lync 2013 モバイルクライアントでプッシュ通知が必要


</div></li>
</ul></td>
<td><p>RtcUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-configuring-for-push-notifications.md">Lync Server 2013 でプッシュ通知を構成する</a></p></td>
</tr>
<tr class="odd">
<td><p>モビリティポリシーを構成する</p></td>
<td><p><strong>Set-csmobilitypolicy</strong>コマンドレットを使用して、次の操作を許可または禁止します。</p>
<ul>
<li><p>勤務先から通話</p></li>
<li><p>IP オーディオと IP ビデオを有効にする</p></li>
<li><p>[IP オーディオまたは IP ビデオに WiFi を使用する]</p></li>
</ul></td>
<td><p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configuring-mobility-policy.md">Lync Server 2013 でのモビリティ ポリシーの構成</a></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

