---
title: IPSec 例外
TOCTitle: IPSec 例外
ms:assetid: 241f1eca-6f2f-44de-90b1-2cb659cbe27c
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg425719(v=OCS.15)
ms:contentKeyID: 48271501
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# IPSec 例外

 

_**トピックの最終更新日:** 2015-03-09_

企業ネットワーク上でインターネット プロトコル セキュリティ (IPsec) (IETF RFC 4301 ～ 4309 を参照) を導入している場合、音声、ビデオ、およびパノラマ ビデオの配信に使用するポートに対して IPsec を無効にする必要があります。これにより、IPsec のネゴシエーションによってメディア用ポートの割り当てに遅延が生じるのを避けることができます。

次の表に、推奨される IPsec 例外設定を示します。

### 推奨される IPSec 例外設定

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th>ルール名</th>
<th>発信元 IP アドレス</th>
<th>送信先 IP アドレス</th>
<th>プロトコル</th>
<th>送信元ポート</th>
<th>宛先ポート</th>
<th>認証要件</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>内部音声ビデオ エッジ サーバー/受信</p></td>
<td><p>任意</p></td>
<td><p>内部音声ビデオ エッジ サーバー</p></td>
<td><p>UDP および TCP</p></td>
<td><p>任意</p></td>
<td><p>任意</p></td>
<td><p>認証しない</p></td>
</tr>
<tr class="even">
<td><p>外部音声ビデオ エッジ サーバー/受信</p></td>
<td><p>任意</p></td>
<td><p>外部音声ビデオ エッジ サーバー</p></td>
<td><p>UDP および TCP</p></td>
<td><p>任意</p></td>
<td><p>任意</p></td>
<td><p>認証しない</p></td>
</tr>
<tr class="odd">
<td><p>内部音声ビデオ エッジ サーバー/送信</p></td>
<td><p>内部音声ビデオ エッジ サーバー</p></td>
<td><p>任意</p></td>
<td><p>UDP &amp; TCP</p></td>
<td><p>任意</p></td>
<td><p>任意</p></td>
<td><p>認証しない</p></td>
</tr>
<tr class="even">
<td><p>外部音声ビデオ エッジ サーバー/送信</p></td>
<td><p>外部音声ビデオ エッジ サーバー</p></td>
<td><p>任意</p></td>
<td><p>UDP および TCP</p></td>
<td><p>任意</p></td>
<td><p>任意</p></td>
<td><p>認証しない</p></td>
</tr>
<tr class="odd">
<td><p>仲介サーバー/受信</p></td>
<td><p>任意</p></td>
<td><p>仲介</p>
<p>サーバー</p></td>
<td><p>UDP および TCP</p></td>
<td><p>任意</p></td>
<td><p>任意</p></td>
<td><p>認証しない</p></td>
</tr>
<tr class="even">
<td><p>仲介サーバー/送信</p></td>
<td><p>仲介</p>
<p>サーバー</p></td>
<td><p>任意</p></td>
<td><p>UDP および TCP</p></td>
<td><p>任意</p></td>
<td><p>任意</p></td>
<td><p>認証しない</p></td>
</tr>
<tr class="odd">
<td><p>会議アテンダント/受信</p></td>
<td><p>任意</p></td>
<td><p>会議アテンダントを実行するフロントエンド サーバー</p></td>
<td><p>UDP および TCP</p></td>
<td><p>任意</p></td>
<td><p>任意</p></td>
<td><p>認証しない</p></td>
</tr>
<tr class="even">
<td><p>会議アテンダント/送信</p></td>
<td><p>会議アテンダントを実行するフロントエンド サーバー</p></td>
<td><p>任意</p></td>
<td><p>UDP および TCP</p></td>
<td><p>任意</p></td>
<td><p>任意</p></td>
<td><p>認証しない</p></td>
</tr>
<tr class="odd">
<td><p>音声ビデオ会議サーバー/受信</p></td>
<td><p>任意</p></td>
<td><p>フロントエンド サーバー</p></td>
<td><p>UDP および TCP</p></td>
<td><p>任意</p></td>
<td><p>任意</p></td>
<td><p>認証しない</p></td>
</tr>
<tr class="even">
<td><p>音声ビデオ会議/送信</p></td>
<td><p>フロントエンド サーバー</p></td>
<td><p>任意</p></td>
<td><p>UDP および TCP</p></td>
<td><p>任意</p></td>
<td><p>任意</p></td>
<td><p>認証しない</p></td>
</tr>
<tr class="odd">
<td><p>Exchange/受信</p></td>
<td><p>任意</p></td>
<td><p>Exchange ユニファイド メッセージング</p></td>
<td><p>UDP および TCP</p></td>
<td><p>任意</p></td>
<td><p>任意</p></td>
<td><p>認証しない</p></td>
</tr>
<tr class="even">
<td><p>アプリケーション共有サーバー/受信</p></td>
<td><p>任意</p></td>
<td><p>アプリケーション共有サーバー</p></td>
<td><p>TCP</p></td>
<td><p>任意</p></td>
<td><p>任意</p></td>
<td><p>認証しない</p></td>
</tr>
<tr class="odd">
<td><p>アプリケーション共有サーバー/送信</p></td>
<td><p>アプリケーション共有サーバー</p></td>
<td><p>任意</p></td>
<td><p>TCP</p></td>
<td><p>任意</p></td>
<td><p>任意</p></td>
<td><p>認証しない</p></td>
</tr>
<tr class="even">
<td><p>Exchange/送信</p></td>
<td><p>Exchange ユニファイド メッセージング</p></td>
<td><p>任意</p></td>
<td><p>UDP および TCP</p></td>
<td><p>任意</p></td>
<td><p>任意</p></td>
<td><p>認証しない</p></td>
</tr>
<tr class="odd">
<td><p>クライアント</p></td>
<td><p>任意</p></td>
<td><p>任意</p></td>
<td><p>UDP</p></td>
<td><p>指定メディア ポート範囲</p></td>
<td><p>任意</p></td>
<td><p>認証しない</p></td>
</tr>
</tbody>
</table>

