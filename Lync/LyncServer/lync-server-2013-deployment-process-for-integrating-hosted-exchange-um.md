---
title: 'Lync Server 2013: Hosted Exchange UM の統合のための展開プロセス'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for integrating hosted Exchange UM with Lync Server
ms:assetid: dbec9c38-7f66-419d-b8c3-c61380052cac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398968(v=OCS.15)
ms:contentKeyID: 48185586
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b314ea3bd7a88264a72c804c7c67ed3baa819972
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762625"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-integrating-hosted-exchange-um-with-lync-server-2013"></a>Hosted Exchange UM と Lync Server 2013 の統合のための展開プロセス

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-25_

Lync Server 2013 とホストされた Exchange ユニファイドメッセージング (UM) との統合について効果的な計画を立てるには、次のことを考慮する必要があります。

  - Lync Server 2013 とホストされている Exchange UM とを統合するための前提条件

  - 統合プロセス中に必要な手順

<div>

## <a name="deployment-prerequisites-for-integrating-with-hosted-exchange-um"></a>ホストされた Exchange UM と統合するための展開の前提条件

統合プロセスを始める前に、Lync Server 2013 (少なくとも、フロントエンドプールまたは Standard Edition サーバー)、エッジサーバー、2013 Lync 2010 クライアントを既に展開しておく必要があります。

</div>

<div>

## <a name="integration-process"></a>統合プロセス

次の表では、ホストされた Exchange UM の統合プロセスの概要を示します。 展開手順の詳細については、展開ドキュメントの「 [Lync Server 2013 ユーザーのボイスメールをホストされた EXCHANGE UM に提供](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md)する」を参照してください。


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
<th>権利と権限</th>
<th>「展開」のドキュメント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>エッジサーバーを構成します。</p></td>
<td><ol>
<li><p>フェデレーションのためにエッジ サーバーを構成します。</p></li>
<li><p>エッジサーバーにデータを手動で複製します。</p></li>
<li><p>エッジサーバーでホスティングプロバイダーを構成します。</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-configure-the-edge-server-for-integration-with-hosted-exchange-um.md">Hosted Exchange UM との統合のためのエッジ サーバーの構成</a></p></td>
</tr>
<tr class="even">
<td><p>ホストされたボイスメールのポリシーを構成します。</p></td>
<td><ol>
<li><p>グローバルでホストされているボイスメールポリシーを変更するか、サイトまたはユーザーごとのスコープを持つ新しいホストされたボイスメールポリシーを作成します。</p></li>
<li><p>ユーザーごとのスコープを持つポリシーの場合は、ユーザーまたはグループにポリシーを割り当てます。</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-manage-hosted-voice-mail-policies.md">Lync Server 2013 でのホスト ボイス メール ポリシーの管理</a></p></td>
</tr>
<tr class="odd">
<td><p>ユーザーがホストされたボイスメールを有効にします。</p></td>
<td><ul>
<li><p>メールボックスがホストされている Exchange サービス上にあるユーザーのユーザーアカウントを構成します。</p></li>
</ul></td>
<td><p>RTCUniversalUserAdmins</p></td>
<td><p><a href="lync-server-2013-enable-users-for-hosted-voice-mail.md">Lync Server 2013 でのホスト型ボイス メールに対するユーザーの有効化</a></p></td>
</tr>
<tr class="even">
<td><p>ホスト型連絡先オブジェクトを構成します。</p></td>
<td><ol>
<li><p>ホストされた Exchange UM 用の自動応答の連絡先オブジェクトを作成します。</p></li>
<li><p>Hosted Exchange UM 用のサブスクライバーアクセスの連絡先オブジェクトを作成します。</p></li>
</ol></td>
<td><p>RTCUniversalUserAdmins</p>
<div>

> [!NOTE]  
> 連絡先オブジェクトを作成、変更、または削除するには、新しい-CsExUmContact を実行しているユーザー、Set-CsExUmContact コマンドレットを実行しているユーザー、または、新しい連絡先オブジェクトが保存されている Active Directory 組織単位への適切なアクセス許可を持っている必要があります。 このアクセス許可は、Grant-CsOUPermission コマンドレットを実行することで付与されます。 詳細については、「Lync Server 管理シェルのドキュメント」を参照してください。


</div></td>
<td><p><a href="lync-server-2013-create-contact-objects-for-hosted-exchange-um.md">Lync Server 2013 での Hosted Exchange UM の連絡先オブジェクトの作成</a></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

