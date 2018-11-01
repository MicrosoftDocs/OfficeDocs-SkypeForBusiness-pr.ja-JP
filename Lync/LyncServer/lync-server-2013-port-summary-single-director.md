---
title: 'Lync Server 2013: ポートの概要 - 単一のディレクター'
TOCTitle: ポートの概要 - 単一のディレクター
ms:assetid: 079c1414-723f-4499-b7d4-a0d7121c1626
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ204648(v=OCS.15)
ms:contentKeyID: 48271155
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# ポートの概要 - Lync Server 2013 での単一のディレクター

 

_**トピックの最終更新日:** 2015-03-09_

単一の ディレクターに対するファイアウォール ポートの要件は、内部インターフェイス、またはリバース プロキシの内部接続インターフェイスからディレクターとの通信を確立するために使用されるポート群で構成されます。Microsoft Lync Server 2013 は、既定では、HTTP/TCP ポート 8080 と HTTPS/TCP ポート 4443 がリバース プロキシから、ディレクターと、フロント エンド プールおよび フロント エンド サーバーに対して開かれているものと想定します。また、エッジ サーバーの内部インターフェイスからは、ディレクターと、フロント エンド プールおよび フロント エンド サーバーに対するセッション開始プロトコル (SIP) 通信が存在する必要があります。SIP プロトコルでは、エッジ サーバーから フロント エンド プールおよび フロント エンド サーバーに対しては SIP/MTLS/TCP 5061 を使用します。ディレクター、フロント エンド プール、および フロント エンド サーバーから エッジ サーバーの内部インターフェイスへの SIP/MTLS/TCP 5061 による通信を許可するルールも作成する必要があります。

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
<td><p>ディレクター</p></td>
<td><p>まずリバース プロキシの外部で受信された通信は、ディレクター Web サービスおよび フロント エンド サーバー Web サービスに送信されます。</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP 4443</p></td>
<td><p>リバース プロキシの内部インターフェイス</p></td>
<td><p>ディレクター</p></td>
<td><p>まずリバース プロキシの外部で受信された通信は、ディレクター Web サービスおよび フロント エンド サーバー Web サービスに送信されます。</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP 444</p></td>
<td><p>ディレクター</p></td>
<td><p>フロントエンド サーバーまたはフロントエンド プール</p></td>
<td><p>ディレクターと フロント エンド サーバーの間のサーバー間通信</p></td>
</tr>
<tr class="even">
<td><p>HTTP/TCP 80</p></td>
<td><p>内部クライアント</p></td>
<td><p>ディレクター Web サービス</p></td>
<td><p>ディレクターでは、内部クライアントおよび外部クライアントに Web サービスが提供されます。</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP 443</p></td>
<td><p>内部クライアント</p></td>
<td><p>ディレクター Web サービス</p></td>
<td><p>ディレクターでは、内部クライアントおよび外部クライアントに Web サービスが提供されます。</p></td>
</tr>
<tr class="even">
<td><p>SIP/MTLS/TCP 5061</p></td>
<td><p>エッジ サーバーの内部インターフェイス</p></td>
<td><p>ディレクター</p></td>
<td><p>エッジ サーバーから ディレクターおよび フロント エンド サーバーへの SIP 通信。</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50001</p></td>
<td><p>任意</p></td>
<td><p>エッジ サーバーの内部インターフェイス</p></td>
<td><p>集中ログ サービス コントローラー (ClsController.exe) またはエージェント (ClasAgent.exe) コマンドおよびログ コレクション</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50002</p></td>
<td><p>任意</p></td>
<td><p>エッジ サーバーの内部インターフェイス</p></td>
<td><p>集中ログ サービス コントローラー (ClsController.exe) またはエージェント (ClasAgent.exe) コマンドおよびログ コレクション</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50003</p></td>
<td><p>任意</p></td>
<td><p>エッジ サーバーの内部インターフェイス</p></td>
<td><p>集中ログ サービス コントローラー (ClsController.exe) またはエージェント (ClasAgent.exe) コマンドおよびログ コレクション</p></td>
</tr>
</tbody>
</table>

