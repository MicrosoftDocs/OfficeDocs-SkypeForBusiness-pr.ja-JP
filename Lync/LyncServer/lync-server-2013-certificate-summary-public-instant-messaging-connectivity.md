---
title: 証明書の概要  - パブリック インスタント メッセージング接続
TOCTitle: 証明書の概要  - パブリック インスタント メッセージング接続
ms:assetid: 2b3687ee-50c2-4c1c-880e-8dcf8bd4f309
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ618370(v=OCS.15)
ms:contentKeyID: 49115208
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 証明書の概要 - パブリック インスタント メッセージング接続

 

_**トピックの最終更新日:** 2015-03-09_

パブリック インスタント メッセージング接続の証明書の構成は、America Online (AOL) では独自の証明書の構成を必要とする点を除いて、他の種類の SIP フェデレーションや標準のエッジ サーバー証明書とまったく同じです。America Online では、使用する 1 つまたは複数 (エッジ プールの場合) の証明書に、通常のサーバーの拡張キー使用法 (EKU) に加えて、クライアント EKU も含める必要があります。クライアント EKU は証明書に追加されるものであり、エッジ サーバーに割り当てられる外部パブリック証明書の一部に含まれます。

## 証明書の概要 - パブリック インスタント メッセージング接続


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>コンポーネント</th>
<th>サブジェクト名</th>
<th>サブジェクトの別名 (SAN)/順序</th>
<th>コメント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>外部/アクセス エッジ</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>sip.contoso.com</p>
<p>webcon.contoso.com</p>
<p>sip.fabrikam.com</p></td>
<td><p>証明書は公的 CA のものである必要があります。また、AOL とのパブリック IM 接続を展開する場合は、サーバー EKU およびクライアント EKU が必要です。証明書は、次のエッジの外部エッジ サーバー インターフェイスに割り当てられます。</p>
<ul>
<li><p>アクセス エッジ サービス</p></li>
<li><p>Web 会議エッジ サービス</p></li>
<li><p>音声ビデオ エッジ サービス</p></li>
</ul>
<p>SAN は、トポロジ ビルダーの定義に基づいて自動的に証明書に追加されます。追加の SIP ドメインで必要な SAN エントリや、サポートする必要がある他のエントリを追加します。SAN にはサブジェクト名がレプリケートされるため、正常に動作するためにはサブジェクト名が存在している必要があります。</p></td>
</tr>
</tbody>
</table>


## 関連項目

#### 概念

[Lync Server 2013 の外部ユーザー アクセスのシナリオ](lync-server-2013-scenarios-for-external-user-access.md)

