---
title: Lync Server 2013 に対して有効なユーザー アカウント
TOCTitle: Lync Server 2013 に対して有効なユーザー アカウント
ms:assetid: 8021087e-5084-4a39-9fef-ab9376c6d371
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg182543(v=OCS.15)
ms:contentKeyID: 48272674
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 に対して有効なユーザー アカウント

 

_**トピックの最終更新日:** 2015-03-09_

このセクションのトピックは、Lync Server 2013 コントロール パネルの \[ユーザー\] ページを使用して実行できるタスクの詳細な手順を示します。


> [!IMPORTANT]
> Lync Server コントロール パネルでは、Active Directory Domain Admins グループ メンバーのユーザーは管理できません。Domain Admins ユーザーの場合 Lync Server コントロール パネルで実行できるのは、読み取り専用の検索操作のみです。Domain Admins ユーザーについて、書き込み操作 ( Lync Server コントロール パネル の有効化や無効化、プールやポリシーの割り当ての変更、テレフォニー設定、SIP アドレスなど) を実行するには、Domain Admins ユーザーとしてログオンした上で Windows PowerShell コマンドレットを使用する必要があります。Windows PowerShell コマンドレットによるユーザー管理の詳細については、「<A href="lync-server-2013-lync-server-management-shell.md">Lync Server 2013 管理シェル</A>」を参照してください。



ユーザーの検索またはユーザー検索結果のフィルター処理を伴う Lync Server 2013 管理タスクを実行する場合、一部のユーザー プロパティは属性として Active Directory ドメイン サービス 内に存在しても、Microsoft Exchange Server が展開されるまではグローバル カタログにレプリケートされません。Microsoft Exchange は、Lync Server と異なり、インストール時に次の属性をグローバル カタログへのレプリケーション用にマークします。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>ユーザー情報:</th>
<th>住所と電話番号:</th>
<th>組織:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>イニシャル</p></td>
<td><p>番地</p>
<p>国/地域</p>
<p>ポケット ベル</p>
<p>FAX</p>
<p>携帯電話</p></td>
<td><p>タイトル</p>
<p>会社</p>
<p>部署</p>
<p>オフィス</p></td>
</tr>
</tbody>
</table>


## このセクション中

  - [Lync Server 2013 で有効なユーザー アカウント情報の表示](lync-server-2013-viewing-information-about-user-accounts-enabled-for-lync-server.md)

  - [Lync Server 2013 のユーザーの有効化または無効化](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)

  - [ユーザーのエンタープライズ VoIP の管理](lync-server-2013-managing-enterprise-voice-for-users.md)

  - [ユーザー アカウント プロパティの変更](lync-server-2013-modifying-user-account-properties.md)

  - [Lync Server 2013 での組織の外部アクセス ポリシーの管理](lync-server-2013-manage-external-access-policy-for-your-organization.md)

  - [ユーザー単位のポリシーの割り当て](lync-server-2013-assigning-per-user-policies.md)

## 関連項目

#### 概念

[ユーザー管理のコマンドレット](lync-server-2013-user-management-cmdlets.md)  

#### その他のリソース

[Lync Server 2013 のユーザー管理](lync-server-2013-managing-users-in-lync-server.md)

