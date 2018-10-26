---
title: 'Lync Server 2013: 監視の展開チェックリスト'
TOCTitle: 監視の展開チェックリスト
ms:assetid: 4e798370-277c-4391-84b4-13a972b45ca6
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ204874(v=OCS.15)
ms:contentKeyID: 48272049
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の監視の展開チェックリスト

 

_**トピックの最終更新日:** 2015-03-09_

監視機能は、各フロントエンド サーバーにインストールされアクティブ化されていますが、Microsoft Lync Server 2013 の監視データを実際に収集できるようになるまでに、いくつかの手順を実行する必要があります。これらの手順を以下のチェックリストで簡単に説明します。


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
<td><p>ステップ</p></td>
<td><p>役割とグループ メンバーシップ</p></td>
<td><p>ドキュメント</p></td>
</tr>
<tr class="even">
<td><p><strong>必要なハードウェアとソフトウェアのインストール</strong></p></td>
<td><p>監視用のバックエンド データ ストアとして機能するコンピューターに、サポートされているバージョンの Microsoft SQL Server をインストールします。</p></td>
<td><p>ローカルの Administrators グループのメンバーでもあるドメイン ユーザー。</p></td>
<td><p>「サポート」のガイドの「<a href="lync-server-2013-supported-hardware.md">Lync Server 2013 でサポートされるハードウェア</a>」</p>
<p>「サポート」のガイドの「<a href="lync-server-2013-server-software-and-infrastructure-support.md">Lync Server 2013 でのサーバーのソフトウェアおよびインフラストラクチャ サポート</a>」</p></td>
</tr>
<tr class="odd">
<td><p><strong>適切な内部トポロジを作成して監視をサポートする</strong></p></td>
<td><p>Lync Server 2013 トポロジ ビルダーを使用して、監視データベースをトポロジに追加し、更新されたトポロジを公開します。</p></td>
<td><p>トポロジを定義する場合は、ローカル ユーザー グループのメンバーであるユーザー。</p>
<p>トポロジを公開する場合は、ドメイン管理者グループと RTCUniversalServerAdmins グループのメンバーであるユーザー。</p></td>
<td><p>「展開」のガイドの「<a href="lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md">フロントエンド プールへの監視ストアの関連付け</a>」</p></td>
</tr>
<tr class="even">
<td><p><strong>適切な監視設定を有効にする</strong></p></td>
<td><p>通話詳細記録 (CDR) と QoE (Quality of Experience) 監視を、グローバル スコープ/サイト スコープで有効にします。</p></td>
<td><p>RTCUniversalServerAdmins グループのメンバーであるユーザー、または CsCdrConfiguration および CsQoEConfiguration コマンドレットにアクセスできる RBAC の役割が割り当てられたユーザー。</p></td>
<td><p>「操作」のガイドの「<a href="lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md">通話詳細記録と QoE (Quality of Experience) 設定の構成</a>」</p></td>
</tr>
</tbody>
</table>

