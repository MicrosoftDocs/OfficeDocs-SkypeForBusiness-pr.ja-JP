---
title: 'Lync Server 2013: 応答グループの展開プロセス'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment process for Response Group
ms:assetid: d390c8a1-dc6e-44d8-b386-2be1fca9877c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205270(v=OCS.15)
ms:contentKeyID: 48185437
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2151532b31f3c1660be98d11ac9d9c337ffecb64
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833458"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-response-group-in-lync-server-2013"></a>Lync Server 2013 の応答グループの展開プロセス

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-27_

このセクションでは、応答グループアプリケーションの展開に関連するフェーズと手順の概要について説明します。

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
<th>ステップ</th>
<th>アクセス許可</th>
<th>「展開」のドキュメント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>応答グループアプリケーションをインストールする</p></td>
<td><p>応答グループアプリケーションは、エンタープライズボイスの展開時に既定でインストールされ、有効になります。</p></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-deploying-enterprise-voice.md">Lync Server 2013 でのエンタープライズボイスの展開</a></p></td>
</tr>
<tr class="even">
<td><p>応答グループのコンポーネントをインストールする</p></td>
<td><p>Lync Server コマンドレット、Lync Server コントロールパネル、応答グループ構成ツール、エージェントのサインインとサインアウトのコンソール、応答グループのクライアント Web サービスは、Web サービスの一部としてインストールされます。 Enterprise Edition プールまたは Standard Edition サーバーを展開すると、Web サービスがインストールされます。</p></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-deploying-lync-server.md">Lync Server 2013 の展開</a></p></td>
</tr>
<tr class="odd">
<td><p>Lync 2013 およびエンタープライズ Voip のユーザーを有効にする</p></td>
<td><p>Lync Server およびエンタープライズ Voip 用のエージェントになるユーザーを有効にします。 ユーザーをエージェント グループに追加する前に、ユーザーを有効にする必要があります。 通常、ユーザーは Enterprise Edition または Standard Edition server の展開中に Lync Server に対して有効になっています。 エンタープライズボイスの展開中に、ユーザーはエンタープライズ Voip に対応しています。</p></td>
<td><p>RTCUniversalUserAdmins</p>
<p>CsUserAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">Lync Server 2013 のユーザーアカウントを無効にするか、再び有効にする</a></p>
<p><a href="lync-server-2013-enable-users-for-enterprise-voice.md">Lync Server 2013 でのエンタープライズ Voip のユーザーの有効化</a></p></td>
</tr>
<tr class="even">
<td><p>エージェント グループ、キュー、ワークフローから構成される応答グループを作成および構成する</p></td>
<td><ol>
<li><p>Lync Server コントロールパネルまたは Lync Server 管理シェルを使用して、次の操作を行います。</p>
<ol>
<li><p>エージェント グループを作成して構成する</p></li>
<li><p>キューを作成して構成する</p></li>
</ol></li>
<li><p>必要に応じて、Lync Server 管理シェルを使用して、定義済みの応答グループの勤務時間および休日を作成します。</p></li>
<li><p>応答グループの構成ツールまたは Lync Server 管理シェルを使用して、カスタム応答グループの営業時間や休日などのワークフロー (ハントグループまたはインタラクティブな音声応答 (IVR) 通話フロー) を作成します。</p>
<div>

> [!NOTE]  
> Lync Server コントロールパネルから応答グループの構成ツールにアクセスできます。


</div></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p>
<p>CsResponseGroupManager</p></td>
<td><p><a href="lync-server-2013-create-response-group-agent-groups.md">Lync Server 2013 での応答グループのエージェント グループの作成</a></p>
<p><a href="lync-server-2013-create-response-group-queues.md">Lync Server 2013 での応答グループのキューの作成</a></p>
<p><a href="lync-server-2013-optional-define-response-group-business-hours.md">省略Lync Server 2013 での応答グループの営業時間の定義</a></p>
<p><a href="lync-server-2013-optional-define-response-group-holiday-sets.md">省略Lync Server 2013 で回答グループの休日セットを定義する</a></p>
<p><a href="lync-server-2013-create-or-modify-a-workflow.md">Lync Server 2013 でワークフローを作成または変更する</a></p></td>
</tr>
<tr class="odd">
<td><p>(オプション) アプリケーションレベルの設定をカスタマイズする</p></td>
<td><p>Lync Server 管理シェルを使用して、既定の音楽保留の構成、既定の音楽の保留中のオーディオファイル、エージェントの ringback 猶予期間、通話コンテキストの構成をカスタマイズします。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-managing-application-level-response-group-settings.md">Lync Server 2013 でのアプリケーションレベルの応答グループの設定の管理</a></p></td>
</tr>
<tr class="even">
<td><p>(オプション) 応答グループの管理を委任する</p></td>
<td><p>ユーザーに CsResponseGroupManager ロールを割り当て、応答グループの構成を委任します。 応答グループマネージャーは、それらに割り当てられた応答グループを構成できます。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-planning-for-role-based-access-control.md">Lync Server 2013 での役割ベースのアクセス制御の計画</a></p></td>
</tr>
<tr class="odd">
<td><p>応答グループ展開を検証する</p></td>
<td><p>ハント グループ ワークフローおよび対話型音声応答ワークフローに対する通話への応答をテストして、構成が正常に機能していることを確認します。</p></td>
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

