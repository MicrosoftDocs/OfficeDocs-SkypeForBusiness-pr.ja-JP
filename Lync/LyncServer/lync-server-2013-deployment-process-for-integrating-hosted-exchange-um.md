---
title: 'Lync Server 2013: ホストされた Exchange UM を統合するための展開プロセス'
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
ms.openlocfilehash: f55e8f573b4000d56a002adb9bd40d03b2021cba
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137176"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-integrating-hosted-exchange-um-with-lync-server-2013"></a>ホストされた Exchange UM と Lync Server 2013 を統合するための展開プロセス

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-25_

ホスティングされた Exchange ユニファイドメッセージング (UM) と Lync Server 2013 の統合を効果的に計画するには、次の点を考慮する必要があります。

  - Lync Server 2013 を hosted Exchange UM と統合するための前提条件

  - 統合プロセス中に必要な手順

<div>

## <a name="deployment-prerequisites-for-integrating-with-hosted-exchange-um"></a>Hosted Exchange UM との統合のための展開の前提条件

統合プロセスを開始する前に、Lync Server 2013 (少なくとも、フロントエンドプールまたは Standard Edition サーバー)、エッジサーバー、Lync 2013、Lync 2010 クライアントを展開しておく必要があります。

</div>

<div>

## <a name="integration-process"></a>統合プロセス

次の表は、ホストされた Exchange UM 統合プロセスの概要を示しています。 展開手順の詳細については、「展開」のドキュメントの「 [Lync Server 2013 ユーザーのボイスメールをホストされた EXCHANGE UM に提供](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md)する」を参照してください。


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
<th>手順</th>
<th>権限とアクセス許可</th>
<th>展開のドキュメント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>エッジサーバーを構成します。</p></td>
<td><ol>
<li><p>フェデレーションのためにエッジ サーバーを構成します。</p></li>
<li><p>エッジサーバーにデータを手動でレプリケートします。</p></li>
<li><p>エッジサーバーのホスティングプロバイダーを構成します。</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-configure-the-edge-server-for-integration-with-hosted-exchange-um.md">ホストされた Exchange UM との統合のためにエッジサーバーを構成する</a></p></td>
</tr>
<tr class="even">
<td><p>ホストボイスメールポリシーを構成します。</p></td>
<td><ol>
<li><p>グローバルホストボイスメールポリシーを変更するか、サイトまたはユーザーごとのスコープを使用して新しいホストボイスメールポリシーを作成します。</p></li>
<li><p>ユーザー単位のスコープを持つポリシーの場合は、ポリシーをユーザーまたはグループに割り当てます。</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-manage-hosted-voice-mail-policies.md">Lync Server 2013 でホストボイスメールポリシーを管理する</a></p></td>
</tr>
<tr class="odd">
<td><p>ホストボイスメールに対してユーザーを有効にします。</p></td>
<td><ul>
<li><p>ホストされた Exchange サービス上にメールボックスがあるユーザーのユーザーアカウントを構成します。</p></li>
</ul></td>
<td><p>RTCUniversalUserAdmins</p></td>
<td><p><a href="lync-server-2013-enable-users-for-hosted-voice-mail.md">Lync Server 2013 でホストボイスメールに対してユーザーを有効にする</a></p></td>
</tr>
<tr class="even">
<td><p>ホストされた連絡先オブジェクトを構成します。</p></td>
<td><ol>
<li><p>Hosted Exchange UM の自動応答連絡先オブジェクトを作成します。</p></li>
<li><p>Hosted Exchange UM のサブスクライバーアクセス連絡先オブジェクトを作成します。</p></li>
</ol></td>
<td><p>RTCUniversalUserAdmins</p>
<div>

> [!NOTE]  
> 連絡先オブジェクトを作成、変更、または削除するには、新しい連絡先オブジェクトが格納されている Active Directory 組織単位への適切なアクセス許可を、新しい-CsExUmContact コマンドを実行しているユーザーが持っている必要があります。 このアクセス許可は、Grant-CsOUPermission コマンドレットを実行することで付与されます。 詳細については、Lync Server 管理シェルのドキュメントを参照してください。


</div></td>
<td><p><a href="lync-server-2013-create-contact-objects-for-hosted-exchange-um.md">Lync Server 2013 で hosted Exchange UM の連絡先オブジェクトを作成する</a></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

