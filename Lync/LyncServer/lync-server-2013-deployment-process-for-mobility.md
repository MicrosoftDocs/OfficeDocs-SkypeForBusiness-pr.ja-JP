---
title: 'Lync Server 2013: モビリティの展開プロセス'
TOCTitle: モビリティの展開プロセス
ms:assetid: 5a1cebda-c14b-4ff4-9c36-f7caa868160f
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Hh690023(v=OCS.15)
ms:contentKeyID: 48272169
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 のモビリティの展開プロセス

 

_**トピックの最終更新日:** 2015-03-09_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013. It is noted accordingly.

このセクションでは、Lync Server 2013 モビリティ機能の展開に必要な手順について説明します。

### モビリティの展開プロセス

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
<th>ステップ</th>
<th>アクセス許可</th>
<th>「展開」のドキュメント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ドメイン ネーム システム (DNS) レコードを作成する</p></td>
<td><ul>
<li><p>自動検出サービスの内部 URL を解決するために、内部 DNS の CNAME または A (ホスト、IPv6 の場合は AAAA) レコードを作成します。</p></li>
<li><p>自動検出サービスの外部 URL を解決するために、外部 DNS の CNAME または A (ホスト、IPv6 の場合は AAAA) レコードを作成します。</p></li>
</ul></td>
<td><p>Domain Admins</p>
<p>DnsAdmins</p></td>
<td><p><a href="lync-server-2013-creating-dns-records-for-the-autodiscover-service.md">Lync Server 2013 での自動検出サービスの DNS レコードの作成</a></p></td>
</tr>
<tr class="even">
<td><p>証明書を変更する</p></td>
<td><p>サブジェクトの別名エントリを以下の証明書に追加し、モバイル ユーザーのセキュリティで保護された接続をサポートします。</p>
<ul>
<li><p>ディレクターの証明書</p></li>
<li><p>フロント エンド プールの証明書</p></li>
<li><p>リバース プロキシの証明書</p></li>
</ul></td>
<td><p>ローカル管理者</p></td>
<td><p><a href="lync-server-2013-modifying-certificates-for-mobility.md">Lync Server 2013 でのモビリティに合わせた証明書の変更</a></p></td>
</tr>
<tr class="odd">
<td><p>リバース プロキシを構成する</p></td>
<td><ul>
<li><p>サブジェクトの別名で更新された証明書を SSL (Secure Sockets Layer) リスナーに割り当てます。</p></li>
<li><p>自動検出サービスの外部 URL の Web 公開ルールを再構成します。</p></li>
<li><p>外部 Lync Server 2013 Web サービス URL の Web 公開ルールが フロント エンド プールに存在することを確認します。</p></li>
</ul>
<p>または</p>
<ul>
<li><p>自動検出の初期要求に HTTP を使用し、証明書のサブジェクトの別名リストを更新しない場合は、HTTP ポート 80 の新しい Web 公開ルールを構成するか、既存の公開ルールを再構成します。</p></li>
</ul></td>
<td><p>ローカル管理者</p></td>
<td><p><a href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Lync Server 2013 での、モビリティに合わせたリバース プロキシの構成</a></p></td>
</tr>
<tr class="even">
<td><p>Mcx Mobility Service を使用して、Lync 2010 Mobile のモビリティ展開をテストします。</p></td>
<td><p><strong>Test-CsMcxP2PIM</strong> を実行し、ユーザー間のインスタント メッセージの送信をテストします。</p>
<p>オプションの完全な一覧については、Lync Server 管理シェル コマンドレット ドキュメントの <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsMcxP2PIM">Test-CsMcxP2PIM</a> を参照してください。</p></td>
<td><p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-verifying-your-mobility-deployment.md">Lync Server 2013 でのモビリティ展開の確認</a></p></td>
</tr>
<tr class="odd">
<td><p>UCWA Web コンポーネントを使用して、Lync 2013 モバイル クライアントのモビリティ展開をテストします。</p></td>
<td><p><strong>Test-CsUcwaConference</strong> コマンドレットを使用して、定義済みテスト ユーザーをテストおよび確認します。また 2 人の実際のユーザーが UCWA を使用して会議を作成し、参加することもできます。</p>
<p>オプションの完全な一覧については、Lync Server 管理シェル コマンドレット ドキュメントの <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsUcwaConference">Test-CsUcwaConference</a> を参照してください。</p></td>
<td><p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-verifying-your-mobility-deployment.md">Lync Server 2013 でのモビリティ展開の確認</a></p></td>
</tr>
<tr class="even">
<td><p>プッシュ通知を構成する</p></td>
<td><ul>
<li><p>Lync Server 2013エッジ サーバーの場合、Lync Server オンライン ホスティング プロバイダーを追加し、ホスティング プロバイダーのフェデレーションを構成します。</p></li>
<li><p>Lync Server 2010エッジ サーバーの場合、Lync Server オンライン ホスティング プロバイダーを追加し、ホスティング プロバイダーのフェデレーションを構成します。</p></li>
<li><p>Office Communications Server 2007 R2エッジ サーバーの場合、フェデレーション パートナーを追加します。</p></li>
<li><p>Wi-Fi ネットワーク経由のプッシュ通知をサポートする場合は、TCP ポート 5223 の発信ファイアウォール ルールを構成します。</p></li>
<li><p><strong>Set-CsPushNotificationConfiguration</strong> コマンドレットを使用して、Apple Push Notification Service (APNS) および Microsoft Push Notification Service (MPNS) へのプッシュ通知を有効にします。この機能は、既定で無効にされています。</p></li>
<li><p><strong>Test-CsFederatedPartner</strong> コマンドレットを使用してフェデレーション構成をテストし、<strong>Test-CsMCXPushNotification</strong> コマンドレットを使用してプッシュ通知をテストします。</p>

> [!NOTE]
> プッシュ通知は、Apple デバイスおよび Windows Phone の Lync 2010 Mobile クライアントで使用されます。<br />
プッシュ通知は、Windows Phone の Lync 2013 モバイル クライアントでのみ必要です。

</div></li>
</ul></td>
<td><p>RtcUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-configuring-for-push-notifications.md">Lync Server 2013 でプッシュ通知を構成する</a></p></td>
</tr>
<tr class="odd">
<td><p>モビリティ ポリシーを構成する</p></td>
<td><p><strong>Set-CsMobilityPolicy</strong> コマンドレットを使用して、次の機能を許可または禁止します。</p>
<ul>
<li><p>勤務先から通話</p></li>
<li><p>IP オーディオと IP ビデオの有効化</p></li>
<li><p>IP Audio および IP ビデオに対して WiFi を必須にする</p></li>
</ul></td>
<td><p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configuring-mobility-policy.md">Lync Server 2013 でのモビリティ ポリシーの構成</a></p></td>
</tr>
</tbody>
</table>

