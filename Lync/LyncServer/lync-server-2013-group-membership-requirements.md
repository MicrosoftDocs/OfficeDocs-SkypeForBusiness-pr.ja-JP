---
title: 'Lync Server 2013: グループ メンバーシップの要件'
TOCTitle: グループ メンバーシップの要件
ms:assetid: 01876843-8717-4e72-baf5-866ac8cceee6
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ204623(v=OCS.15)
ms:contentKeyID: 48271061
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 のグループ メンバーシップの要件

 

_**トピックの最終更新日:** 2015-03-09_

次の表に、Lync Server 2013 のインストール、管理、およびトラブルシューティングを正常に行うためにユーザーが所属する必要があるグループの概要を示します。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Lync Server 2013 実行可能ファイル</th>
<th>必要なグループ メンバーシップ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>setup.exe</strong> - Lync Server 2013 管理ツールのインストールを開始する実行可能ファイル。</p></td>
<td><p>実行可能ファイルを実行するコンピューターでの Local Administrators グループのメンバー。Active Directory ドメイン サービス の情報を読み取る Domain Users グループのメンバー。このレベルのアクセス許可が必要なのは、ローカル コンピューターへの必須 MSI パッケージの自動インストールでは、Program Files ディレクトリなどのローカル コンピューターの保護されたリソース、およびローカル コンピューター ハイブなどの保護されたレジストリとの間で読み書きできる特権が必要だからです。</p>

> [!TIP]
> セットアップ アクセス許可は、メンバーシップを付与したくない、Domain Admins グループのユーザーやグループに委任することもできます。詳細については、「展開」のドキュメントの「<A href="lync-server-2013-granting-setup-permissions.md">Lync Server 2013 でのセットアップ アクセス許可の付与</A>」を参照してください。



</tr>
<tr class="even">
<td><p><strong>deploy.exe</strong> - setup.exe によって呼び出され、サーバーの役割のソフトウェア コンポーネントを展開する処理を実行します。</p></td>
<td><p>実行可能ファイルを実行するコンピューターでの Local Administrators グループのメンバー。AD DS の情報を読み取る Domain Users グループのメンバー。このレベルのアクセス許可が必要なのは、ローカル コンピューターへの必須 MSI パッケージの自動インストールでは、Program Files ディレクトリなどのローカル コンピューターの保護されたリソース、およびローカル コンピューター ハイブなどの保護されたレジストリとの間で読み書きできる特権が必要だからです。中央管理ストアを読み取るには、RtcUniversalReadOnlyAdmins グループのメンバーシップが必要です。</p>

> [!NOTE]
> Windows Vista オペレーティング システムまたは Windows 7 オペレーティング システムを実行している場合、ユーザー アクセス制御 (UAC) からインストールの続行を指示するメッセージが表示されます。標準のユーザー アカウントでログオンしている場合に、ソフトウェアのインストール アクセス許可を持つアカウントを要求されたときは、Local Administrators グループのメンバーであるユーザーから資格情報の提供を受ける必要があります。

</div></td>
</tr>
<tr class="odd">
<td><p><strong>bootstrapper.exe</strong> - setup.exe によって呼び出され、サーバーの役割を展開および構成する処理を実行します。</p></td>
<td><p>実行可能ファイルを実行するコンピューターでの Local Administrators グループのメンバー。Bootstrapper.exe を実行する RTCUniversalServerAdmins グループのメンバー。AD DS の情報を読み取る Domain Users グループのメンバー。このレベルのアクセス許可が必要なのは、ローカル コンピューターへの必須 MSI パッケージの自動インストールでは、Program Files ディレクトリなどのローカル コンピューターの保護されたリソース、およびローカル コンピューター ハイブなどの保護されたレジストリとの間で読み書きできる特権が必要だからです。</p></td>
</tr>
<tr class="even">
<td><p><strong>TopologyBuilder</strong> - Lync Server 2013 トポロジの作成、表示、調整、および検証に使用するウィザード駆動型ユーザー インターフェイス。</p></td>
<td><p>実行可能ファイルを実行してトポロジを表示するコンピューターでの Local Administrators グループのメンバー。構成の設定を変更する RTCUniversalServerAdmins グループのメンバー。RTCUniversalServerAdmins グループと Domain Admins グループのメンバー、またはトポロジを発行する RTCUniversalServerAdmins グループのメンバー (このグループに委任セットアップ アクセス許可が付与されている場合のみ)。セットアップ アクセス許可を委任して RTCUniversalServerAdmins グループのメンバーが Domain Admins グループのメンバーでなくてもトポロジを発行できるようにする方法の詳細については、「展開」のドキュメントの「<a href="lync-server-2013-granting-setup-permissions.md">Lync Server 2013 でのセットアップ アクセス許可の付与</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>AdminUIHost</strong> - Lync Server 2013 の管理に使用する Web ベースのグラフィカル ユーザー インターフェイス。</p></td>
<td><p>CsAdministrator グループのメンバー、または特定の管理タスクが割り当てられる別の役割ベースのアクセス制御 (RBAC) の役割のメンバー。Lync Server 2013 コントロール パネルでは、Lync Server 2013 管理シェル コマンドレットを使用して構成の変更を実装します。あらかじめ定義されている役割の一覧と、メンバーによる実行が許可されているコマンドレットについては、「計画」のドキュメントの「<a href="lync-server-2013-planning-for-role-based-access-control.md">Lync Server 2013 での役割ベースのアクセス制御の計画</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>Lync Server 2013 モジュールが読み込まれた PowerShell.exe</strong> - Lync Server 2013 の管理専用のコマンドレットを持つコマンドライン管理ツール。</p></td>
<td><p>CsAdministrator グループのメンバー、または特定のコマンドレットが割り当てられている別の RBAC の役割のメンバー。あらかじめ定義されている役割の一覧と、メンバーによる実行が許可されているコマンドレットについては、「計画」のドキュメントの「<a href="lync-server-2013-planning-for-role-based-access-control.md">Lync Server 2013 での役割ベースのアクセス制御の計画</a>」を参照してください。</p>
<p>または、次に示すグループのうち 1 つ以上のメンバー (コマンドレットによる):</p>
<ul>
<li><p>RTCUniversalServerAdmins</p></li>
<li><p>RTCUniversal-UserAdmins</p></li>
<li><p>RTCUniversalReadOnlyAdmins</p></li>
</ul></td>
</tr>
</tbody>
</table>

