---
title: 'Lync Server 2013: 証明書の概要 - 拡張統合エッジ (ロード バランサー機器を使用)'
TOCTitle: 証明書の概要 - 拡張統合エッジ (ロード バランサー機器を使用)
ms:assetid: 894a9f3e-7cba-4915-8fdf-e52f2f25126f
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398692(v=OCS.15)
ms:contentKeyID: 48272751
ms.date: 12/17/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 証明書の概要 - Lync Server 2013 の拡張統合エッジ (ロード バランサー機器を使用)

 

_**トピックの最終更新日:** 2016-12-15_

Microsoft Lync Server 2013 では、他のサーバーとの間の相互認証、およびサーバー間やサーバーとクライアント間のデータの暗号化に証明書が使用されます。証明書では、サーバーに関連付けられているドメイン ネーム システム (DNS) レコードの名前と、証明書のサブジェクト名 (SN) およびサブジェクトの別名 (SAN) の名前が一致している必要があります。サーバー、DNS レコード、および証明書のエントリを正常にマッピングするには、DNS に登録される目的のサーバーの完全修飾ドメイン名、および証明書の SN エントリと SAN エントリを慎重に計画する必要があります。

エッジ サーバーの外部インターフェイスに割り当てられる証明書は、公的証明機関 (CA) に要求して取得します。ユニファイド コミュニケーションのために証明書を提供できる公的 CA は、[http://go.microsoft.com/fwlink/?linkid=3052\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=3052%26clcid=0x411) に掲載されています。証明書を要求する場合は、Lync Server 展開ウィザードによって生成された証明書要求を使用できます。あるいは、手動で依頼を作成するか、または公的 CA が提供するプロセスに従って依頼を作成できます。証明書を割り当てる場合、証明書は アクセス エッジ サービス インターフェイス、Web 会議エッジ サービス インターフェイス、および音声ビデオ認証サービスに割り当てられます。音声ビデオ認証サービスは、音声およびビデオ ストリームの暗号化に証明書を使用しない 音声ビデオ エッジ サービスと混同しないでください。内部 エッジ サーバー インターフェイスでは、(組織) 内部の CA の証明書も、公的 CA の証明書も使用できます。内部インターフェイス証明書では、SN のみが使用され、SAN エントリは使用されません。そのため SAN エントリは必要ありません。

> [!NOTE]
> 次の表では、参考のためにサブジェクトの別名一覧の 2 つ目の SIP エントリ (sip.fabrikam.com) を示しています。組織内の各 SIP ドメインに対して、証明書のサブジェクトの別名一覧に記載されている対応する FQDN を追加する必要があります。


## 拡張統合エッジ (ロード バランサー機器) に必要な証明書


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
<td><p>単一の統合 エッジ サーバー (外部エッジ)</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>webcon.contoso.com</p>
<p>sip.contoso.com</p>
<p>sip.fabrikam.com</p></td>
<td><p>証明書は公的 CA のものである必要があります。また、AOL とのパブリック IM 接続を展開する場合は、サーバー EKU およびクライアント EKU が必要です。さらに、拡張 エッジ サーバーでは、証明書の秘密キーがエクスポートでき、証明書および秘密キーが各 エッジ サーバーにコピーされる必要があります。証明書は、次のエッジの外部エッジ インターフェイスに割り当てられます。</p>
<ul>
<li><p>アクセス エッジ サービス</p></li>
<li><p>Web 会議エッジ サービス</p></li>
<li><p>音声ビデオ エッジ サービス</p></li>
</ul>
<p>SAN は、トポロジ ビルダーの定義に基づいて自動的に証明書に追加されます。追加の SIP ドメインで必要な SAN エントリや、サポートする必要がある他のエントリを追加します。SAN にはサブジェクト名がレプリケートされるため、正常に動作するためにはサブジェクト名が存在している必要があります。</p></td>
</tr>
<tr class="even">
<td><p>単一の統合 エッジ サーバー (内部エッジ)</p></td>
<td><p>lsedge.contoso.net</p></td>
<td><p>SAN 必要なし</p></td>
<td><p>証明書は、公的 CA またはプライベート CA が発行でき、サーバー EKU が含まれている必要があります。証明書は、内部 エッジ サーバー インターフェイスに割り当てられます。</p></td>
</tr>
</tbody>
</table>


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
<td><p>外部/ アクセス エッジ サービス</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>sip.contoso.com</p>
<p>webcon.contoso.com</p>
<p>sip.fabrikam.com</p></td>
<td><p>証明書は公的 CA のものである必要があります。また、AOL とのパブリック IM 接続を展開する場合は、サーバー EKU およびクライアント EKU が必要です。証明書は、次のエッジの外部エッジ インターフェイスに割り当てられます。</p>
<ul>
<li><p>アクセス エッジ サービス</p></li>
<li><p>Web 会議エッジ サービス</p></li>
<li><p>音声ビデオ エッジ サービス</p></li>
</ul>
<p>SAN は、トポロジ ビルダーの定義に基づいて自動的に証明書に追加されます。追加の SIP ドメインで必要な SAN エントリや、サポートする必要がある他のエントリを追加します。SAN にはサブジェクト名がレプリケートされるため、正常に動作するためにはサブジェクト名が存在している必要があります。</p></td>
</tr>
</tbody>
</table>


## Extensible Messaging and Presence Protocol の証明書の概要


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
<td><p>エッジ サーバーまたは エッジ プールの アクセス エッジ サービスに割り当て</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>webcon.contoso.com</p>
<p>sip.contoso.com</p>
<p>sip.fabrikam.com</p>
<p>xmpp.contoso.com</p>
<p><strong>*.contoso.com</strong></p></td>
<td><p>最初の 3 つの SAN 項目は、フル エッジ サーバー向けの通常の SAN 項目です。contoso.com は、ルート ドメイン レベルでの XMPP パートナーとのフェデレーションに必要な項目です。この項目により、末尾が *.contoso.com のすべてのドメインで XMPP が許可されます。</p></td>
</tr>
</tbody>
</table>

