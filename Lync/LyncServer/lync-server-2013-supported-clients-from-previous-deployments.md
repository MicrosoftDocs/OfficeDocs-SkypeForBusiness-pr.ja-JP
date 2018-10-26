---
title: 'Lync Server 2013: 以前の展開からサポートされるクライアント'
TOCTitle: 以前の展開からサポートされるクライアント
ms:assetid: 69d427f8-57a5-4244-b2ed-f2eb7600285e
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398499(v=OCS.15)
ms:contentKeyID: 48272393
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 で以前の展開からサポートされるクライアント

 

_**トピックの最終更新日:** 2015-03-09_

共存のシナリオでは、Lync Server 2013 クライアントが以前のバージョンの Lync Server および Office Communications Server によるクライアントと対話できます。以前のリリースとは異なり、Lync Server 2010 は新しい Lync 2013 クライアントをサポートしています。これにより、Lync Server 2010 からアップグレードする組織は新しいクライアントを、Lync Server のアップグレードに関係なく、ロールアウトできます。

## サポートされるサーバーとクライアントの組み合わせ

次の表に、サポートされるクライアント バージョンとサーバー バージョンの組み合わせを示します。Lync Server 2013 では以前の 2 つのクライアント バージョンをサポートしており、Lync Server 2010 では新しい Lync 2013 クライアントをサポートしています。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>クライアント</th>
<th>Lync Server 2013</th>
<th>Lync Server 2010</th>
<th>Office Communications Server 2007 R2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 2013</p></td>
<td><p>サポート対象</p></td>
<td><p>サポート対象</p></td>
<td><p>サポート対象外</p></td>
</tr>
<tr class="even">
<td><p>Lync Web App 2013</p></td>
<td><p>サポート対象</p></td>
<td><p>サポート対象外</p></td>
<td><p>サポート対象外</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2010</p></td>
<td><p>サポート対象</p></td>
<td><p>サポート対象</p></td>
<td><p>サポート対象外</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010 Attendant</p></td>
<td><p>サポート対象</p></td>
<td><p>サポート対象</p></td>
<td><p>サポート対象外</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2010 グループ チャット</p></td>
<td><p>該当なし</p></td>
<td><p>サポート対象1</p></td>
<td><p>該当なし</p></td>
</tr>
<tr class="even">
<td><p>Lync Web App 2010</p></td>
<td><p>サポート対象外</p></td>
<td><p>サポート対象</p></td>
<td><p>サポート対象外</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2010 Attendee</p></td>
<td><p>サポート対象外2</p></td>
<td><p>サポート対象</p></td>
<td><p>サポート対象外</p></td>
</tr>
<tr class="even">
<td><p>Office Communicator 2007 R2</p></td>
<td><p>相互運用可能3</p></td>
<td><p>サポート対象</p></td>
<td><p>サポート対象</p></td>
</tr>
<tr class="odd">
<td><p>Microsoft Office Communications Server 2007 R2 Attendant</p></td>
<td><p>サポート対象外</p></td>
<td><p>サポート対象</p></td>
<td><p>サポート対象</p></td>
</tr>
<tr class="even">
<td><p>Office Communicator 2007</p></td>
<td><p>サポート対象外</p></td>
<td><p>サポート対象</p></td>
<td><p>サポート対象</p></td>
</tr>
<tr class="odd">
<td><p>Office Live Meeting 2007</p></td>
<td><p>サポート対象外</p></td>
<td><p>サポート対象</p></td>
<td><p>サポート対象</p></td>
</tr>
</tbody>
</table>


1Microsoft Lync Server 2010 では、Lync Server 2010 用の信頼されたサードパーティ アプリケーションであるグループ チャット サーバーを使用してグループ チャット機能を使用できました。Lync 2013 クライアントは Lync Server 2010、グループ チャットと互換性がありません。

2Lync Web App 2013 は、コンピューターのオーディオとビデオを含む充実した会議のエクスペリエンスを提供するようになり、Lync 2010 Attendee を置き換えるものとして考えられています。

3Office Communicator 2007 R2 のプレゼンスと IM 機能は Lync Server 2013 と互換性がありますが、会議機能は互換性がありません。 Office Communications Server 2007 R2 からの移行中は、プレゼンスと IM を相互運用するのに Office Communicator 2007 R2 が適していますが、ユーザーは Lync Server 2013 会議に参加するのに Lync Web App 2013 を使用する必要があります。

> [!NOTE]
> Lync Server 2013 クライアントが以前のバージョンの Lync Server と Office Communications Server のクライアントと共存および対話する機能の詳細については、展開に関するドキュメントの「<a href="lync-server-2013-client-interoperability-in-lync-2013.md">Lync 2013 でのクライアント相互運用性</a>」を参照してください。

