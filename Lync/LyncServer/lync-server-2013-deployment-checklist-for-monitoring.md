---
title: 'Lync Server 2013: 監視の展開チェックリスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment checklist for monitoring
ms:assetid: 4e798370-277c-4391-84b4-13a972b45ca6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204874(v=OCS.15)
ms:contentKeyID: 48184080
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3cbf14920ef0103f2d6e8aa6088a2c0b35e17654
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833497"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-monitoring-in-lync-server-2013"></a>Lync Server 2013 の監視の展開チェックリスト

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-05_

監視は既に各フロントエンドサーバーにインストールされてライセンス認証されていますが、Microsoft Lync Server 2013 の監視データを実際に収集する前に、いくつかの手順を実行する必要があります。 これらの手順については、次のチェックリストで説明します。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>段階</p></td>
<td><p>手順</p></td>
<td><p>役割とグループのメンバーシップ</p></td>
<td><p>ドキュメント</p></td>
</tr>
<tr class="even">
<td><p><strong>必要なハードウェアとソフトウェアのインストール</strong></p></td>
<td><p>監視用のバックエンドデータストアとして機能する、サポートされているバージョンの Microsoft SQL Server をコンピューターにインストールします。</p></td>
<td><p>ローカル管理者グループのメンバーでもあるドメインユーザー。</p></td>
<td><p><a href="lync-server-2013-supported-hardware.md">サポートガイドの Lync Server 2013 でサポートされているハードウェア</a></p>
<p>サポートガイドの<a href="lync-server-2013-server-software-and-infrastructure-support.md">Lync server 2013 でのサーバーソフトウェアとインフラストラクチャのサポート</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>監視をサポートする適切な内部トポロジを作成する</strong></p></td>
<td><p>Lync Server 2013 トポロジビルダーを使用して、監視データベースをトポロジに追加した後、更新されたトポロジを公開します。</p></td>
<td><p>トポロジ (ローカルユーザーグループのメンバーであるユーザー) を定義するには、[] を選びます。</p>
<p>トポロジを公開するには、ドメイン管理者グループと RTCUniversalServerAdmins グループのメンバーであるユーザー。</p></td>
<td><p>展開ガイドの<a href="lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md">Lync Server 2013 でのフロントエンドプールへの監視ストアの関連付け</a></p></td>
</tr>
<tr class="even">
<td><p><strong>適切な監視設定を有効にする</strong></p></td>
<td><p>グローバルまたはサイトのスコープで、通話の詳細記録 (CDR) と Quality of Experience (QoE) 監視を有効にします。</p></td>
<td><p>RTCUniversalServerAdmins グループのメンバーであるか、CsCdrConfiguration と CsQoEConfiguration コマンドレットへのアクセスを提供する RBAC の役割が割り当てられているユーザー。</p></td>
<td><p>運用ガイドの<a href="lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md">Lync Server 2013 での通話の記録と音質の設定を構成する</a></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

