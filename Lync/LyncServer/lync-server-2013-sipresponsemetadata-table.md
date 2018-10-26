---
title: SIPResponseMetaData テーブル
TOCTitle: SIPResponseMetaData テーブル
ms:assetid: cf723737-4a75-4352-829b-f4954aa59716
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205294(v=OCS.15)
ms:contentKeyID: 48273680
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# SIPResponseMetaData テーブル

 

_**トピックの最終更新日:** 2015-03-09_

SIPResponseMetaDataTable には、SIP 応答コードと、各コードの分類と定義の一覧が含まれます。これらのコードは SIP デバイスおよび SIP 通信セッションに影響を与えるイベントへの応答して生成されます。たとえば、応答コード 403 は、SIP デバイスが要求を行い、サーバーがその要求の実行を拒否したときに生成されます。

このテーブルは、Microsoft Lync Server 2013 で導入されました。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>列</th>
<th>データ型</th>
<th>キー/インデックス</th>
<th>詳細</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td><p>主/プライマリ</p></td>
<td><p>SIP 応答コードを表す数値。</p></td>
</tr>
<tr class="even">
<td><p><strong>Class</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>応答コードの一般的な分類。以下の分類があります。</p>
<ul>
<li><p>1 – 情報応答</p></li>
<li><p>2 – 正常応答</p></li>
<li><p>3 – リダイレクト応答</p></li>
<li><p>4 – クライアント エラー応答</p></li>
<li><p>5 - サーバー エラー応答</p></li>
<li><p>6 – グローバル エラー応答</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p></p></td>
<td><p>SIP 応答コードの説明。たとえば、コード 181 には以下の説明があります。</p>
<p>Call Is Being Forwarded (呼び出しを転送中)</p></td>
</tr>
</tbody>
</table>

