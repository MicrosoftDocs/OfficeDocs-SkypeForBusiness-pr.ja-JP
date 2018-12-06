---
title: 'Lync Server 2013: モビリティの証明書の要件'
TOCTitle: モビリティの証明書の要件
ms:assetid: bb0e97af-cf60-4271-a0ab-654429d884ea
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Hh690044(v=OCS.15)
ms:contentKeyID: 48273421
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 のモビリティの証明書の要件

 

_**トピックの最終更新日:** 2015-03-09_

モビリティ機能を展開しモバイル クライアントで自動検出をサポートする場合は、モバイル クライアントからの安全な接続を確保するために、証明書に特定のサブジェクトの別名エントリを含める必要があります。

以下の証明書に、自動検出に対応するサブジェクトの別名エントリを含める必要があります。

  - ディレクター プール

  - フロント エンド プール

  - リバース プロキシ

このセクションでは、自動検出のために証明書で必要になるサブジェクトの別名エントリについて説明します。

> [!NOTE]
> 通常、内部の証明書機関を使用した証明書の再発行は簡単なプロセスですが、サブジェクトの複数の別名エントリを、リバース プロキシで使用されるパブリック証明書に追加するには、高い費用がかかる可能性があります。多くの SIP ドメインがあり、サブジェクトの別名の追加が高コストになる場合は、最初の自動検出サービス要求で HTTPS (既定の設定) ではなく HTTP を使用するようにリバース プロキシを設定できます。詳細については、「<a href="lync-server-2013-technical-requirements-for-mobility.md">Lync Server 2013 でのモビリティの技術要件</a>」を参照してください。


### ディレクター プールの証明書の要件

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>説明</th>
<th>サブジェクト名の別名エントリ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>内部自動検出サービス URL</p></td>
<td><p>SAN=lyncdiscoverinternal.&lt;sipdomain&gt;</p></td>
</tr>
<tr class="even">
<td><p>外部自動検出サービス URL</p></td>
<td><p>SAN=lyncdiscover.&lt;SIP ドメイン&gt;</p></td>
</tr>
</tbody>
</table>


> [!NOTE]
> または、SAN=*.&lt;sipdomain&gt; を使用することもできます。


### フロントエンド プールの証明書の要件

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>説明</th>
<th>サブジェクト名の別名エントリ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>内部自動検出サービス URL</p></td>
<td><p>SAN=lyncdiscoverinternal.&lt;sipdomain&gt;</p></td>
</tr>
<tr class="even">
<td><p>外部自動検出サービス URL</p></td>
<td><p>SAN=lyncdiscover.&lt;SIP ドメイン&gt;</p></td>
</tr>
</tbody>
</table>


> [!NOTE]
> または、SAN=*.&lt;sipdomain&gt; を使用することもできます。


### リバース プロキシ (パブリック CA) の証明書の要件

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>説明</th>
<th>サブジェクト名の別名エントリ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>外部自動検出サービス URL</p></td>
<td><p>SAN=lyncdiscover.&lt;SIP ドメイン&gt;</p></td>
</tr>
</tbody>
</table>


> [!NOTE]
> リバース プロキシ上の SSL リスナーに割り当てられた証明書にこの SAN を割り当てます。


> [!NOTE]
> リバース プロキシ リスナーには、外部 Web サービス URL (例: SAN=lyncwebextpool01.contoso.com、およびオプションの ディレクターを展開している場合は dirwebexternal.contoso.com) 用のサブジェクトの別名が含まれます。

