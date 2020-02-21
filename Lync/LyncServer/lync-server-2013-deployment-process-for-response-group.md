---
title: 'Lync Server 2013: 応答グループの展開プロセス'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for Response Group
ms:assetid: d390c8a1-dc6e-44d8-b386-2be1fca9877c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205270(v=OCS.15)
ms:contentKeyID: 48185437
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c592b0ee0ba2794391c539bdc52e9344bc43b27
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198250"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-response-group-in-lync-server-2013"></a>Lync Server 2013 の応答グループの展開プロセス

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-27_

このセクションでは、応答グループアプリケーションの展開に必要なフェーズと手順の概要について説明します。

### <a name="response-group-deployment-process"></a>応答グループの展開プロセス

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
<th>アクセス許可</th>
<th>展開のドキュメント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>応答グループアプリケーションをインストールする</p></td>
<td><p>応答グループアプリケーションは、エンタープライズ Voip を展開するときに既定でインストールされ、アクティブ化されます。</p></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-deploying-enterprise-voice.md">Lync Server 2013 でのエンタープライズ Voip の展開</a></p></td>
</tr>
<tr class="even">
<td><p>応答グループ用のコンポーネントのインストール</p></td>
<td><p>Lync Server コマンドレット、Lync Server コントロールパネル、応答グループ構成ツール、エージェントのサインインとサインアウトコンソール、および応答グループクライアント Web サービスは、Web サービスの一部としてインストールされます。 Web サービスは、Enterprise Edition プールまたは Standard Edition サーバーの展開時にインストールされます。</p></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-deploying-lync-server.md">Lync Server 2013 の展開 </a></p></td>
</tr>
<tr class="odd">
<td><p>Lync 2013 およびエンタープライズ Voip に対してユーザーを有効にする</p></td>
<td><p>Lync Server およびエンタープライズ Voip のエージェントとなるユーザーを有効にします。 ユーザーをエージェント グループに追加する前に、ユーザーを有効にする必要があります。 通常、ユーザーは Enterprise Edition または Standard Edition サーバーの展開時に Lync Server に対して有効になります。 エンタープライズ Voip の展開時に、ユーザーがエンタープライズ Voip に対して有効になります。</p></td>
<td><p>RTCUniversalUserAdmins</p>
<p>CsUserAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">Lync Server 2013 のユーザーアカウントを無効または再度有効にする</a></p>
<p><a href="lync-server-2013-enable-users-for-enterprise-voice.md">Lync Server 2013 のエンタープライズ Voip でユーザーを有効にする</a></p></td>
</tr>
<tr class="even">
<td><p>エージェント グループ、キュー、ワークフローから成る応答グループを作成および構成する</p></td>
<td><ol>
<li><p>Lync Server コントロールパネルまたは Lync Server 管理シェルを使用して、次の操作を行います。</p>
<ol>
<li><p>エージェント グループを作成して構成する</p></li>
<li><p>キューを作成して構成する</p></li>
</ol></li>
<li><p>必要に応じて、Lync Server 管理シェルを使用して、定義済みの応答グループの営業時間と休日を作成します。</p></li>
<li><p>応答グループ構成ツールまたは Lync Server 管理シェルを使用して、カスタムの応答グループの営業時間と休日を含むワークフロー (ハントグループまたは対話型音声応答 (IVR) 通話フロー) を作成します。</p>
<div>

> [!NOTE]  
> 応答グループ構成ツールには、Lync Server コントロールパネルからアクセスできます。


</div></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p>
<p>CsResponseGroupManager</p></td>
<td><p><a href="lync-server-2013-create-response-group-agent-groups.md">応答グループエージェントグループの作成 Lync Server 2013</a></p>
<p><a href="lync-server-2013-create-response-group-queues.md">Lync Server 2013 で応答グループキューを作成する</a></p>
<p><a href="lync-server-2013-optional-define-response-group-business-hours.md">オプションLync Server 2013 で応答グループの営業時間を定義する</a></p>
<p><a href="lync-server-2013-optional-define-response-group-holiday-sets.md">オプションLync Server 2013 で応答グループの休日セットを定義する</a></p>
<p><a href="lync-server-2013-create-or-modify-a-workflow.md">Lync Server 2013 でのワークフローの作成または変更</a></p></td>
</tr>
<tr class="odd">
<td><p>(オプション) アプリケーションレベルの設定をカスタマイズする</p></td>
<td><p>Lync Server 管理シェルを使用して、既定の保留音の構成、既定の保留音のオーディオファイル、エージェントリングバックの猶予期間、呼び出しコンテキストの構成をカスタマイズします。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-managing-application-level-response-group-settings.md">Lync Server 2013 でのアプリケーションレベルの応答グループ設定の管理</a></p></td>
</tr>
<tr class="even">
<td><p>(オプション) 応答グループの管理を委任する</p></td>
<td><p>ユーザーに CsResponseGroupManager ロールを割り当て、応答グループの構成を委任します。 応答グループマネージャーは、それに割り当てられた応答グループを構成できます。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-planning-for-role-based-access-control.md">Lync Server 2013 での役割ベースのアクセス制御の計画</a></p></td>
</tr>
<tr class="odd">
<td><p>応答グループ展開の検証</p></td>
<td><p>ハント グループ ワークフローおよび対話型音声応答ワークフローに対する通話への応答をテストして、構成が予想どおりに機能していることを確認します。</p></td>
<td><p>-</p></td>
<td><p>-</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

