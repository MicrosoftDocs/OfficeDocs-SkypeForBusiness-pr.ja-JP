---
title: 'Lync Server 2013: ポートの概要 - DNS および HLB による負荷分散'
TOCTitle: ポートの概要 - DNS および HLB による負荷分散
ms:assetid: b07c37e4-820e-46ee-a678-1da95d1b87af
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205179(v=OCS.15)
ms:contentKeyID: 48273286
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# ポートの概要 - Lync Server 2013 における DNS および HLB による負荷分散

 

_**トピックの最終更新日:** 2015-03-09_

1 つの ディレクターのファイアウォール ポート要件は、リバース プロキシの内部インターフェイスまたは内部ネットワークから ディレクターとの通信を確立するために使用されるポートで構成されます。既定では、 Microsoft Lync Server 2013 は、リバース プロキシから ディレクター、 フロント エンド プール、および フロント エンド サーバーに対してポート HTTP/TCP 8080 および HTTPS/TCP 4443 が開くことを想定しています。また、 エッジ サーバー内部インターフェイスから ディレクター、 フロント エンド プール、および フロント エンド サーバーに対しては、セッション開始プロトコル (SIP) 通信がある必要があります。SIP プロトコルは、 エッジ サーバーから フロント エンド プールおよび フロント エンド サーバーに対して SIP/MTLS/TCP 5061 を使用します。 ディレクター、 フロント エンド プール、および フロント エンド サーバーから エッジ サーバー内部インターフェイスに対して SIP/MTLS/TCP 5061 通信を許可するルールも作成する必要があります。

### ファイアウォール定義のための 1 つの ディレクター ポートおよびプロトコル

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
<td><p>通信はリバース プロキシの外部側で最初に受信され、 ディレクター HLB VIP および フロント エンド サーバー Web サービスに送信されます。</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP 4443</p></td>
<td><p>リバース プロキシの内部インターフェイス</p></td>
<td><p>ディレクター ハードウェア ロード バランサーの VIP</p></td>
<td><p>通信はリバース プロキシの外部側で最初に受信され、 ディレクター HLB VIP および フロント エンド サーバー Web サービスに送信されます。</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP 444</p></td>
<td><p>ディレクター</p></td>
<td><p>フロント エンド プールまたはフロント エンド サーバー</p></td>
<td><p>ディレクター HLB VIP とフロント エンド サーバーまたはフロント エンド サーバーの間のサーバー間通信。</p></td>
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
<td><p>ディレクター</p></td>
<td><p>エッジ サーバーから ディレクターおよび フロント エンド サーバーに対しての SIP 通信。</p></td>
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

