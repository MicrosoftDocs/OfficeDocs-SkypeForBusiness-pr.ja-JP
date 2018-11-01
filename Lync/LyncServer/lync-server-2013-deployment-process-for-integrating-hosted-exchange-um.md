---
title: 'Lync Server 2013: Hosted Exchange UM の統合のための展開プロセス'
TOCTitle: Hosted Exchange UM と Lync Server の統合のための展開プロセス
ms:assetid: dbec9c38-7f66-419d-b8c3-c61380052cac
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398968(v=OCS.15)
ms:contentKeyID: 48273747
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Hosted Exchange UM と Lync Server 2013 の統合のための展開プロセス

 

_**トピックの最終更新日:** 2015-03-09_

Lync Server 2013 と Hosted Exchange ユニファイド メッセージング (UM) の統合を効果的に計画するには、次のことを考慮する必要があります。

  - Lync Server 2013 と Hosted Exchange UM を統合するための前提条件

  - 統合プロセス中に必要なステップ

## Hosted Exchange UM との統合のための展開に関する前提条件

統合プロセスを開始する前に、 Lync Server 2013 (少なくともフロントエンド プールまたは Standard Edition サーバー)、エッジ サーバー、および Lync 2013 または Lync 2010 のクライアントを展開しておく必要があります。

## 統合プロセス

次の表では、Hosted Exchange UM 統合プロセスの概要を説明します。展開ステップの詳細については、「展開」のドキュメントの「[Lync Server 2013 ユーザーに Hosted Exchange UM のボイス メールを提供する](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md)」を参照してください。


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
<th>権限とアクセス許可</th>
<th>「展開」のドキュメント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>エッジ サーバーの構成。</p></td>
<td><ol>
<li><p>フェデレーションのためにエッジ サーバーを構成します。</p></li>
<li><p>エッジ サーバーにデータを手動でレプリケートします。</p></li>
<li><p>エッジ サーバーのホスティング プロバイダーを構成します。</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-configure-the-edge-server-for-integration-with-hosted-exchange-um.md">Hosted Exchange UM との統合のためのエッジ サーバーの構成</a></p></td>
</tr>
<tr class="even">
<td><p>ホスト ボイス メール ポリシーの構成。</p></td>
<td><ol>
<li><p>グローバル ホスト ボイス メール ポリシーを変更するか、サイト スコープまたはユーザー単位のスコープでホスト ボイス メール ポリシーを新規作成します。</p></li>
<li><p>スコープがユーザー単位のポリシーの場合には、ポリシーをユーザーまたはグループに割り当てます。</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-manage-hosted-voice-mail-policies.md">Lync Server 2013 でのホスト ボイス メール ポリシーの管理</a></p></td>
</tr>
<tr class="odd">
<td><p>ホスト ボイス メールへのユーザー対応の有効化。</p></td>
<td><ul>
<li><p>Hosted Exchange サービスのメールボックスを使用するユーザーのユーザー アカウントを構成します。</p></li>
</ul></td>
<td><p>RTCUniversal-UserAdmins</p></td>
<td><p><a href="lync-server-2013-enable-users-for-hosted-voice-mail.md">Lync Server 2013 でのホスト型ボイス メールに対するユーザーの有効化</a></p></td>
</tr>
<tr class="even">
<td><p>ホスト連絡先オブジェクトの構成。</p></td>
<td><ol>
<li><p>Hosted Exchange UM の自動応答連絡先オブジェクトを作成します。</p></li>
<li><p>Hosted Exchange UM のサブスクライバー アクセス連絡先オブジェクトを作成します。</p></li>
</ol></td>
<td><p>RTCUniversal-UserAdmins</p>

> [!NOTE]
> 連絡先オブジェクトを作成、変更、または削除する場合、コマンドレット New-CsExUmContact、Set-CsExUmContact、または Remove-CsExUmContact を実行するユーザーには、新たな連絡先オブジェクトが格納されている Active Directory の組織単位への適切なアクセス許可が必要です。このアクセス許可は、Grant-CsOUPermission コマンドレットを実行することで付与されます。詳細については、 Lync Server 管理シェルのドキュメントを参照してください。

</div></td>
<td><p><a href="lync-server-2013-create-contact-objects-for-hosted-exchange-um.md">Lync Server 2013 での Hosted Exchange UM の連絡先オブジェクトの作成</a></p></td>
</tr>
</tbody>
</table>

