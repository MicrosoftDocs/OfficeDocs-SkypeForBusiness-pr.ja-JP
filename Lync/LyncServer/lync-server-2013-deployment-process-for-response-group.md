---
title: 'Lync Server 2013: 応答グループの展開プロセス'
TOCTitle: 応答グループの展開プロセス
ms:assetid: d390c8a1-dc6e-44d8-b386-2be1fca9877c
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205270(v=OCS.15)
ms:contentKeyID: 48273668
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の応答グループの展開プロセス

 

_**トピックの最終更新日:** 2015-03-09_

ここでは、 応答グループ アプリケーションの展開に含まれるフェーズとステップの概要を説明します。.

### 応答グループの展開プロセス

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
<td><p>応答グループ アプリケーションをインストールする</p></td>
<td><p>応答グループ アプリケーションは、 エンタープライズ VoIP を展開すると既定でインストールおよびアクティブ化されます。</p></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-deploying-enterprise-voice.md">Lync Server 2013 でのエンタープライズ VoIP の展開</a></p></td>
</tr>
<tr class="even">
<td><p>応答グループのコンポーネントをインストールする</p></td>
<td><p>Lync Server コマンドレット、 Lync Server コントロール パネル、 応答グループ構成ツール、エージェントのサインインおよびサインアウト コンソール、および応答グループ クライアント Web サービスが、Web サービスの一部としてインストールされます。Web サービスは、 Enterprise Edition プールまたは Standard Edition サーバーの展開時にインストールされます。</p></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-deploying-lync-server.md">Lync Server 2013 の展開</a></p></td>
</tr>
<tr class="odd">
<td><p>ユーザーを Lync 2013 および エンタープライズ VoIP に対して有効にする</p></td>
<td><p>Lync Server および エンタープライズ VoIP のエージェントにする予定のユーザーを有効にします。ユーザーをエージェント グループに追加する前に、ユーザーを有効にする必要があります。通常、ユーザーは、 Enterprise Edition または Standard Edition サーバーの展開中に、 Lync Server に対して有効化されます。また、 エンタープライズ VoIP の展開中に、 エンタープライズ VoIP に対して有効化されます。</p></td>
<td><p>RTCUniversal-UserAdmins</p>
<p>CsUserAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">Lync Server 2013 ユーザー アカウントの再有効化または無効化</a></p>
<p><a href="lync-server-2013-enable-users-for-enterprise-voice.md">Lync Server 2013 でのエンタープライズ VoIP に対するユーザーの有効化</a></p></td>
</tr>
<tr class="even">
<td><p>エージェント グループ、キュー、ワークフローから成る応答グループを作成および構成する</p></td>
<td><ol>
<li><p>Lync Server コントロール パネルまたは Lync Server 管理シェルを使用して、次のことを行います。</p>
<ol>
<li><p>エージェント グループを作成して構成する</p></li>
<li><p>キューを作成して構成する</p></li>
</ol></li>
<li><p>オプションで、 Lync Server 管理シェルを使用して、事前定義される応答グループの営業時間と休日を作成します。</p></li>
<li><p>応答グループ構成ツールまたは Lync Server 管理シェルを使用して、カスタム応答グループの営業時間と休日を含む、ワークフロー (ハント グループまたは対話型音声応答 (IVR) 通話フロー) を作成します。</p>

> [!NOTE]
> 応答グループ構成ツールには、 Lync Server コントロール パネルからアクセスできます。

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
<p><a href="lync-server-2013-optional-define-response-group-business-hours.md">(オプション) Lync Server 2013 での応答グループの営業時間の定義</a></p>
<p><a href="lync-server-2013-optional-define-response-group-holiday-sets.md">(オプション) 応答グループ休日セットの定義</a></p>
<p><a href="lync-server-2013-create-or-modify-a-workflow.md">ワークフローの作成または変更</a></p></td>
</tr>
<tr class="odd">
<td><p>(オプション) アプリケーションレベルの設定をカスタマイズする</p></td>
<td><p>Lync Server 管理シェルを使用して、既定の保留音構成、既定の保留音オーディオ ファイル、エージェントのリングバックの猶予期間、および呼び出しコンテキスト構成をカスタマイズします。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-managing-application-level-response-group-settings.md">アプリケーション レベルの応答グループ設定の管理</a></p></td>
</tr>
<tr class="even">
<td><p>(オプション) 応答グループの管理を委任する</p></td>
<td><p>ユーザーに CsResponseGroupManager ロールを割り当て、応答グループの構成を委任します。 応答グループ Manager は割り当てられた応答グループの構成を行うことが可能になります。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-planning-for-role-based-access-control.md">Lync Server 2013 での役割ベースのアクセス制御の計画</a></p></td>
</tr>
<tr class="odd">
<td><p>応答グループ展開を検証する</p></td>
<td><p>ハント グループ ワークフローおよび対話型音声応答ワークフローに対する通話への応答をテストして、構成が予想どおりに機能していることを確認します。</p></td>
<td><p>-</p></td>
<td><p>-</p></td>
</tr>
</tbody>
</table>

