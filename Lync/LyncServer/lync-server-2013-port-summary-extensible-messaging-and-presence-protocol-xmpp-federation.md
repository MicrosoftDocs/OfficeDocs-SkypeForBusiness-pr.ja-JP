---
title: ポートの概要  - XMPP (Extensible Messaging and Presence Protocol) フェデレーション
TOCTitle: ポートの概要  - XMPP (Extensible Messaging and Presence Protocol) フェデレーション
ms:assetid: 62e98fab-7add-4983-a3fa-dbe74e1c3849
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ618371(v=OCS.15)
ms:contentKeyID: 49115222
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# ポートの概要 - XMPP (Extensible Messaging and Presence Protocol) フェデレーション

 

_**トピックの最終更新日:** 2015-03-09_

エッジ サーバーに展開される XMPP (eXtensible Messaging and Presence Pprotocol) プロキシ用に定義されるポートとプロトコルによって、XMPP フェデレーション パートナーからエッジ サーバーへの通信が可能になります。さらに、ユーザーのエッジ サーバーから XMPP フェデレーション パートナーへの通信が可能になります。ルールは、フロント エンド サーバーまたはフロント エンド プールからエッジ サーバーまたはエッジ プールへの内部ファイアウォールにも定義されます。

## XMPP のファイアウォールの概要


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>プロトコル/TCP または UDP/ポート</th>
<th>送信元 (IP アドレス)</th>
<th>宛先 (IP アドレス)</th>
<th>コメント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XMPP/TCP/5269</p></td>
<td><p>任意</p></td>
<td><p>アクセス エッジ サービス インターフェイス IP アドレス</p></td>
<td><p>XMPP 用の標準的なサーバー間通信。XMPP パートナーからエッジ サーバー XMPP プロキシへの通信を可能にします。</p></td>
</tr>
<tr class="even">
<td><p>XMPP/TCP/5269</p></td>
<td><p>アクセス エッジ サービス インターフェイス IP アドレス</p></td>
<td><p>任意</p></td>
<td><p>XMPP 用の標準的なサーバー間通信。エッジ サーバー XMPP プロキシからフェデレーション XMPP パートナーへの通信を可能にします。</p></td>
</tr>
<tr class="odd">
<td><p>XMPP/MTLS/23456</p></td>
<td><p>任意</p></td>
<td><p>内部エッジ サーバー インターフェイス IP</p></td>
<td><p>フロント エンド サーバーまたはフロント エンド プールの XMPP ゲートウェイからエッジ サーバーへの内部 XMPP トラフィック。</p></td>
</tr>
</tbody>
</table>


## 関連項目

#### タスク

[Lync Server 2013 での XMPP 構成の例 - Google Talk との XMPP フェデレーション](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  

#### その他のリソース

[Lync Server 2013 での組織の XMPP フェデレーション パートナーの管理](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)

