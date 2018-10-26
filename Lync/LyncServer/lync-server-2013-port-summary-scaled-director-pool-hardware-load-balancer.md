---
title: 'Lync Server 2013: ポートの概要 - 拡張ディレクター プール、ハードウェア ロード バランサー'
TOCTitle: ポートの概要 - 拡張ディレクター プール、ハードウェア ロード バランサー
ms:assetid: 6ae2f4ac-5b64-4e45-8253-133308f5812d
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ204983(v=OCS.15)
ms:contentKeyID: 48272410
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# ポートの概要 - Lync Server 2013 の拡張ディレクター プール、ハードウェア ロード バランサー

 

_**トピックの最終更新日:** 2015-03-09_

ディレクター プールのファイアウォール ポートの要件は、エッジ サーバーの内部インターフェイスまたはリバース プロキシの内部インターフェイスからの ディレクターとの通信を確立するために使用されるポートから成ります。既定では、Microsoft Lync Server 2013 は、ポート HTTP/TCP 8080 と HTTPS/TCP 4443 がリバース プロキシから ディレクター、フロント エンド プール、および フロント エンド サーバーへと開いていると想定します。さらに、エッジ サーバーの内部インターフェイスから ディレクター、フロント エンド プール、および フロント エンド サーバーへのセッション開始プロトコル (SIP) 通信も必要です。SIP プロトコルは、エッジ サーバーから フロント エンド プールおよび フロント エンド サーバーへの通信に SIP/MTLS/TCP 5061 を使用します。ディレクター、フロント エンド プール、および フロント エンド サーバーから エッジ サーバーの内部インターフェイスへの SIP/MTLS/TCP 5061 通信を許可するルールも作成する必要があります。

### ファイアウォール定義用のディレクター ポートとプロトコル

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>役割/プロトコル/TCP または UDP/ポート</th>
<th>送信元 IP アドレス</th>
<th>宛先 IP アドレス</th>
<th>メモ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>HTTP/TCP 8080</p></td>
<td><p>リバース プロキシの内部インターフェイス</p></td>
<td><p>ディレクター ハードウェア ロード バランサーの VIP</p></td>
<td><p>通信は最初にリバース プロキシの外部側で受信され、ディレクターの HLB の VIP および フロント エンド サーバーの Web サービスに送信されます。</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP 4443</p></td>
<td><p>リバース プロキシの内部インターフェイス</p></td>
<td><p>ディレクター ハードウェア ロード バランサーの VIP</p></td>
<td><p>通信は最初にリバース プロキシの外部側で受信され、ディレクターの HLB の VIP および フロント エンド サーバーの Web サービスに送信されます。</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP 444</p></td>
<td><p>ディレクター</p></td>
<td><p>フロント エンド サーバーまたは フロント エンド プール</p></td>
<td><p>ディレクターの HLB の VIP と フロント エンド サーバーの間のサーバー間通信。</p></td>
</tr>
<tr class="even">
<td><p>HTTP/TCP 80</p></td>
<td><p>内部クライアント</p></td>
<td><p>ディレクター ハードウェア ロード バランサーの VIP</p></td>
<td><p>ディレクターは内部および外部クライアントに対して Web サービスを提供します。</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP 443</p></td>
<td><p>内部クライアント</p></td>
<td><p>ディレクター ハードウェア ロード バランサーの VIP</p></td>
<td><p>ディレクターは内部および外部クライアントに対して Web サービスを提供します。</p></td>
</tr>
<tr class="even">
<td><p>SIP/MTLS/TCP 5061</p></td>
<td><p>エッジ サーバーの内部インターフェイス</p></td>
<td><p>ディレクター ハードウェア ロード バランサーの VIP</p></td>
<td><p>エッジ サーバーから ディレクターおよび フロント エンド サーバーへの SIP 通信。</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50001</p></td>
<td><p>任意</p></td>
<td><p>ディレクター</p></td>
<td><p>集中ログ サービス コントローラー (ClsController.exe) またはエージェント (ClsAgent.exe) コマンドおよびログ コレクション</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50002</p></td>
<td><p>任意</p></td>
<td><p>ディレクター</p></td>
<td><p>集中ログ サービス コントローラー (ClsController.exe) またはエージェント (ClsAgent.exe) コマンドおよびログ コレクション</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50003</p></td>
<td><p>任意</p></td>
<td><p>ディレクター</p></td>
<td><p>集中ログ サービス コントローラー (ClsController.exe) またはエージェント (ClsAgent.exe) コマンドおよびログ コレクション</p></td>
</tr>
</tbody>
</table>

