---
title: 'Lync Server 2013: 監視の展開チェックリスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for monitoring
ms:assetid: 4e798370-277c-4391-84b4-13a972b45ca6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204874(v=OCS.15)
ms:contentKeyID: 48184080
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26fd0c34d51445902e7f00439dd210ddfd64f392
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049469"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-monitoring-in-lync-server-2013"></a>Lync Server 2013 での監視の展開チェックリスト

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-05_

監視は既に各フロントエンドサーバーにインストールされ、アクティブ化されていますが、実際に Microsoft Lync Server 2013 の監視データを収集するには、いくつかの手順を実行する必要があります。 これらの手順を以下のチェックリストで簡単に説明します。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>フェーズ</p></td>
<td><p>手順</p></td>
<td><p>役割とグループ メンバーシップ</p></td>
<td><p>ドキュメント</p></td>
</tr>
<tr class="even">
<td><p><strong>必要なハードウェアとソフトウェアのインストール</strong></p></td>
<td><p>監視用のバックエンド データ ストアとして機能するコンピューターに、サポートされているバージョンの Microsoft SQL Server をインストールします。</p></td>
<td><p>ローカルの Administrators グループのメンバーでもあるドメイン ユーザー。</p></td>
<td><p>「サポート」のガイドの「 <a href="lync-server-2013-supported-hardware.md">Lync Server 2013 でサポートされるハードウェア</a>」</p>
<p>「サポート」のガイドの「 <a href="lync-server-2013-server-software-and-infrastructure-support.md">Lync server 2013 でのサーバーソフトウェアとインフラストラクチャのサポート</a>」</p></td>
</tr>
<tr class="odd">
<td><p><strong>適切な内部トポロジを作成して監視をサポートする</strong></p></td>
<td><p>Lync Server 2013 トポロジビルダーを使用して、監視データベースをトポロジに追加し、更新されたトポロジを公開します。</p></td>
<td><p>トポロジを定義する場合は、ローカル ユーザー グループのメンバーであるユーザー。</p>
<p>トポロジを公開する場合は、ドメイン管理者グループと RTCUniversalServerAdmins グループのメンバーであるユーザー。</p></td>
<td><p>展開ガイドの<a href="lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md">Lync Server 2013 でのフロントエンドプールへの監視ストアの関連付け</a></p></td>
</tr>
<tr class="even">
<td><p><strong>適切な監視設定を有効にする</strong></p></td>
<td><p>通話詳細記録 (CDR) と QoE (Quality of Experience) 監視を、グローバル スコープ/サイト スコープで有効にします。</p></td>
<td><p>RTCUniversalServerAdmins グループのメンバーであるユーザー、または CsCdrConfiguration および CsQoEConfiguration コマンドレットにアクセスできる RBAC の役割が割り当てられたユーザー。</p></td>
<td><p>運用ガイドの<a href="lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md">Lync Server 2013 での通話詳細記録と qoe (Quality Of Experience) 設定の構成</a></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

