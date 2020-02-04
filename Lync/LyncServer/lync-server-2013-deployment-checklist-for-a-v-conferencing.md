---
title: Lync Server 2013 for A/V 会議用の展開チェックリスト
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for A/V conferencing
ms:assetid: 6d47426f-6559-407b-9ac1-2453f0b7a2a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619183(v=OCS.15)
ms:contentKeyID: 49733684
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 736719475d77f67932b350e1684b4af26ca2fbd6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740787"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-av-conferencing-in-lync-server-2013"></a>Lync Server 2013 での A/V 会議の展開チェックリスト

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-30_

他の Lync Server 2013 コンポーネントの展開と同じように、A/V 会議の展開では、会議を組み込んだトポロジを作成して公開するために、トポロジビルダーを使用する必要があります。

<div>

## <a name="deployment-sequence"></a>展開シーケンス

最初のトポロジを展開するとき、または少なくとも1つのフロントエンドプールまたは Standard Edition サーバーを展開した後で、会議を展開することができます。

</div>

<div>

## <a name="conferencing-deployment-process"></a>会議展開プロセス

次の表は、既存のトポロジに会議を展開するために必要な手順の概要を示しています。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>段階</th>
<th>手順</th>
<th>役割とグループ メンバーシップ</th>
<th>ドキュメント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>必要なハードウェアとソフトウェアのインストール</strong></p></td>
<td><p>会議は、フロントエンドプールと Standard Edition サーバーのフロントエンドサーバー上で実行されます。 これらのサーバーのインストールに必要なもの以外には、追加のハードウェア要件やソフトウェア要件はありません。</p>
<div>

> [!NOTE]  
> Lync Server 2013 は、PowerPoint プレゼンテーションの共有とレンダリングを処理するために、Office Web Apps と Office Web Apps サーバーを使用します。 Office Web Apps サーバーのインストールと構成の詳細については、「 <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Office Web Apps サーバーおよび Lync server 2013 との統合を構成する</A>」を参照してください。


</div></td>
<td><p>ローカル Administrators グループのメンバーであるドメイン ユーザー</p></td>
<td><p><a href="lync-server-2013-supported-hardware.md">サポートされているドキュメントの Lync Server 2013 でサポートされているハードウェア</a></p>
<p>サポートドキュメントの<a href="lync-server-2013-server-software-and-infrastructure-support.md">Lync server 2013 でのサーバーソフトウェアとインフラストラクチャのサポート</a></p>
<p>計画ドキュメントの<a href="lync-server-2013-determining-your-system-requirements.md">Lync Server 2013 のシステム要件を決定</a>する。</p>
<p>計画ドキュメントの<a href="lync-server-2013-technical-requirements-for-archiving.md">Lync Server 2013 でのアーカイブの技術要件</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>会議をサポートするために適切な内部トポロジの作成</strong></p></td>
<td><p>トポロジに会議を追加するには、トポロジビルダーを実行して、トポロジを公開します。</p></td>
<td><p>トポロジを定義するには、ローカル Users グループのメンバーであるアカウント</p>
<p>トポロジを公開するには、ドメイン管理者グループと RTCUniversalServerAdmins グループのメンバーであり、Lync Server 2013 ファイルストアで使用するフルコントロールのアクセス許可 (読み取り/書き込み/変更) を持つアカウント (トポロジビルダーが必要な Dacl を構成できるようにする)</p></td>
<td><p>展開ドキュメントで、「<a href="lync-server-2013-define-and-configure-a-topology-in-topology-builder.md">トポロジビルダーでの Lync Server 2013 のトポロジを定義して構成する」</a>を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>会議のポリシーとサポートを構成する</strong></p></td>
<td><p>Lync Server 2013 コントロールパネルまたは Lync Server 管理シェルを使用して、会議の設定を構成します。</p></td>
<td><p>RTCUniversalServerAdmins group (Windows PowerShell のみ) またはユーザーを [] または [CSAdministrator] の役割に割り当てる</p></td>
<td><p>運用ドキュメントの<a href="lync-server-2013-conferencing-policies.md">Lync Server 2013 での会議ポリシー</a> 。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での会議の概要](lync-server-2013-overview-of-conferencing.md)  
[Lync Server 2013 での会議の要件の定義](lync-server-2013-defining-your-requirements-for-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

