---
title: ポートの概要 - パブリック インスタント メッセージング接続
TOCTitle: ポートの概要 - パブリック インスタント メッセージング接続
ms:assetid: f46756ec-1401-4ca2-a4a4-5cd28bcfdc7f
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ618376(v=OCS.15)
ms:contentKeyID: 49115251
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# ポートの概要 - パブリック インスタント メッセージング接続

 

_**トピックの最終更新日:** 2015-03-09_

パブリック インスタント メッセージング接続をサポートするために必要なポートとプロトコル用にファイアウォールを構成するには、まず、パブリック IM プロバイダー内の連絡先が Lync クライアントに連絡したり Lync がパブリック IM 連絡先に連絡したりすることを可能にするために SIP/MTLS/TCP 5061 が双方向性を持っていることに注意します。

Windows Live Messenger は、Lync クライアントとの音声ビデオ通信に参加できます。そのため、ファイアウォール ポートとプロトコルの構成は、Lync クライアントを外部ユーザーとしてサポートするためにファイアウォール上で使用する通常の構成と非常に似たものになります。


> [!IMPORTANT]
> Lync は組織間を接続したり世界中のユーザーと接続したりするための、これまで以上の強力なツールとなります。Windows Live Messenger とのフェデレーションを行うのに、Lync Standard Client Access License (CAL) を超えてユーザー/デバイス ライセンスを追加する必要はありません。Skype フェデレーションがこのリストに追加されることで、Linc ユーザーは IM および音声を使用して数億のユーザーにアクセスできます。<BR>Messenger クライアント連絡先とのフェデレーションは、中国本土を除き、2013 年 3 月 15 日に正式に終了します。Skype がこれまで Messenger を使用していたフェデレーション ユーザーのフェデレーション クライアントになります。



## ファイアウォールの概要 - パブリック インスタント メッセージング接続


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
<td><p>アクセス/SIP (MTLS)/TCP/5061</p></td>
<td><p>パブリック IM 接続パートナー</p></td>
<td><p>エッジ サーバー アクセス インターフェイス</p></td>
<td><p>SIP を使用するフェデレーションおよびパブリック IM 接続用。</p></td>
</tr>
<tr class="even">
<td><p>アクセス/SIP (MTLS)/TCP/5061</p></td>
<td><p>エッジ サーバー アクセス インターフェイス</p></td>
<td><p>パブリック IM 接続パートナー</p></td>
<td><p>SIP を使用するフェデレーションおよびパブリック IM 接続用。</p></td>
</tr>
<tr class="odd">
<td><p>アクセス/SIP (TLS)/TCP/443</p></td>
<td><p>クライアント</p></td>
<td><p>エッジ サーバー アクセス インターフェイス</p></td>
<td><p>外部ユーザー アクセス用のクライアントからサーバーへの SIP トラフィック。</p></td>
</tr>
<tr class="even">
<td><p>音声ビデオ/RTP/TCP/50,000 ～ 59,999</p></td>
<td><p>エッジ サーバー アクセス インターフェイス</p></td>
<td><p>Live Messenger クライアント</p></td>
<td><p>パブリック IM 接続が構成されている場合に、Windows Live Messenger との音声ビデオ セッションに使用されます。</p></td>
</tr>
<tr class="odd">
<td><p>音声ビデオ/STUN、MSTURN/UDP/3478</p></td>
<td><p>エッジ サーバー アクセス インターフェイス</p></td>
<td><p>Live Messenger クライアント</p></td>
<td><p>Windows Live Messenger とのパブリック IM 接続では必須。</p></td>
</tr>
<tr class="even">
<td><p>音声ビデオ/STUN、MSTURN/UDP/3478</p></td>
<td><p>Live Messenger クライアント</p></td>
<td><p>エッジ サーバー アクセス インターフェイス</p></td>
<td><p>Windows Live Messenger とのパブリック IM 接続では必須。</p></td>
</tr>
</tbody>
</table>


## 関連項目

#### 概念

[Lync Server 2013 の外部ユーザー アクセスのシナリオ](lync-server-2013-scenarios-for-external-user-access.md)  
[Lync Server 2013 の外部の音声ビデオ ファイアウォールおよびポートの要件を決定する](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)

