---
title: 音声ビデオ会議の展開チェックリスト
TOCTitle: 音声ビデオ会議の展開チェックリスト
ms:assetid: 6d47426f-6559-407b-9ac1-2453f0b7a2a2
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ619183(v=OCS.15)
ms:contentKeyID: 49115225
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 音声ビデオ会議の展開チェックリスト

 

_**トピックの最終更新日:** 2015-03-09_

他の Lync Server 2013 コンポーネントの場合と同様に、音声ビデオ会議を展開する場合もトポロジ ビルダーを使用して、会議が組み込まれるトポロジを作成して公開する必要があります。

## 展開順序

会議は、最初のトポロジを展開するのと同時に展開するか、あるいは少なくとも 1 つのフロント エンド プールまたは Standard Edition サーバーを展開した後で展開できます。

## 会議展開プロセス

次の表に、既存のトポロジに会議を展開するために必要なステップの概要を示します。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>フェーズ</th>
<th>ステップ</th>
<th>役割とグループ メンバーシップ</th>
<th>ドキュメント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>必要なハードウェアとソフトウェアのインストール</strong></p></td>
<td><p>会議は、フロント エンド プールのフロント エンド サーバーと Standard Edition サーバー上で実行されます。これらのサーバーのインストールに必要なもの以外には、追加のハードウェア要件やソフトウェア要件はありません。</p>

> [!NOTE]
> Lync Server 2013 では、Office Web Apps と Office Web Apps サーバー を使用して、PowerPoint プレゼンテーションオン共有とレンダリングを処理します。Office Web Apps サーバー のインストールと構成の詳細については、「<a href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Lync Server 2013 と Office Web Apps サーバーの統合の構成</a>」を参照してください。

<td><p>ローカルの Administrators グループのメンバーであるドメイン ユーザー</p></td>
<td><p>「サポート」のドキュメントの「<a href="lync-server-2013-supported-hardware.md">Lync Server 2013 でサポートされるハードウェア</a>」</p>
<p>「サポート」のドキュメントの「<a href="lync-server-2013-server-software-and-infrastructure-support.md">Lync Server 2013 でのサーバーのソフトウェアおよびインフラストラクチャ サポート</a>」</p>
<p>「計画」のドキュメントの「<a href="lync-server-2013-determining-your-system-requirements.md">Lync Server 2013 システム要件の決定</a>」</p>
<p>「計画」のドキュメントの「<a href="lync-server-2013-technical-requirements-for-archiving.md">Lync Server 2013 のアーカイブの技術要件</a>」</p>
<p></p></td>
</tr>
<tr class="even">
<td><p><strong>会議をサポートするために適切な内部トポロジの作成</strong></p></td>
<td><p>トポロジ ビルダーを実行して、会議をトポロジに追加した後、そのトポロジを公開します。</p></td>
<td><p>トポロジを定義するには、ローカル ユーザー グループのメンバーであるアカウント</p>
<p>トポロジを公開するには、Domain Admins グループと RTCUniversalServerAdmins グループのメンバーであり、Lync Server 2013 ファイル ストアに使用するファイル共有のフル コントロールのアクセス許可 (読み取り/書き込み/変更) を持つアカウント (トポロジ ビルダーが必要な DACL を構成できるようにするため)。</p></td>
<td><p>「展開」のドキュメントの「<a href="lync-server-2013-define-and-configure-a-topology-in-topology-builder.md">Lync Server 2013 のトポロジ ビルダーでのトポロジの定義と構成</a>」。</p></td>
</tr>
<tr class="odd">
<td><p><strong>会議ポリシーとサポートの構成</strong></p></td>
<td><p>Lync Server 2013 コントロール パネルまたは Lync Server 管理シェルを使用して、会議の設定を構成します。</p></td>
<td><p>RTCUniversalServerAdmins グループ (Windows PowerShell のみ) あるいは [] または CSAdministrator の役割にユーザーを割り当てます。</p></td>
<td><p>「操作」のドキュメントの「<a href="lync-server-2013-conferencing-policies.md">Lync Server 2013 での会議ポリシー</a>」。</p></td>
</tr>
</tbody>
</table>


## 関連項目

#### その他のリソース

[Lync Server 2013 での会議の概要](lync-server-2013-overview-of-conferencing.md)  
[Lync Server 2013 での会議の要件の定義](lync-server-2013-defining-your-requirements-for-conferencing.md)

