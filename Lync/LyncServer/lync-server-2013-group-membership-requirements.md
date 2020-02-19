---
title: 'Lync Server 2013: グループメンバーシップの要件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Group membership requirements
ms:assetid: 01876843-8717-4e72-baf5-866ac8cceee6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204623(v=OCS.15)
ms:contentKeyID: 48183239
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 93c1a79d39a70c21e353799a43c76599cc7af2b5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140300"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="group-membership-requirements-for-lync-server-2013"></a>Lync Server 2013 のグループメンバーシップ要件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-05_

次の表に、Lync Server 2013 のインストール、管理、およびトラブルシューティングを正常に行うために、個人が所属する必要があるグループをまとめています。


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
<td><p><strong>Setup.exe</strong> – Lync Server 2013 管理ツールのインストールを開始する実行可能ファイル。</p></td>
<td><p>実行可能ファイルを実行するコンピューターでの Local Administrators グループのメンバー。 Active Directory ドメインサービスの情報を読み取るためのドメインユーザーグループのメンバ。 このレベルのアクセス許可が必要なのは、ローカル コンピューターへの必須 MSI パッケージの自動インストールでは、Program Files ディレクトリなどのローカル コンピューターの保護されたリソース、およびローカル コンピューター ハイブなどの保護されたレジストリとの間で読み書きできる特権が必要だからです。</p>
<div>

> [!TIP]  
> セットアップ アクセス許可は、メンバーシップを付与したくない、Domain Admins グループのユーザーやグループに委任することもできます。 詳細については、「展開」のドキュメントの「 <A href="lync-server-2013-granting-setup-permissions.md">Lync Server 2013 でのセットアップのアクセス許可の付与</A>」を参照してください。


</div></td>
</tr>
<tr class="even">
<td><p><strong>deploy.exe</strong> - setup.exe によって呼び出され、サーバーの役割のソフトウェア コンポーネントを展開する処理を実行します。</p></td>
<td><p>実行可能ファイルを実行するコンピューターでの Local Administrators グループのメンバー。 AD DS の情報を読み取る Domain Users グループのメンバー。 このレベルのアクセス許可が必要なのは、ローカル コンピューターへの必須 MSI パッケージの自動インストールでは、Program Files ディレクトリなどのローカル コンピューターの保護されたリソース、およびローカル コンピューター ハイブなどの保護されたレジストリとの間で読み書きできる特権が必要だからです。 中央管理ストアを読み取るには、RtcUniversalReadOnlyAdmins グループのメンバーである必要があります。</p>
<div>

> [!NOTE]  
> Windows Vista オペレーティングシステムまたは Windows 7 オペレーティングシステムを実行している場合は、インストールを続行するためにユーザーアカウント制御 (UAC) によってメッセージが表示されます。 標準のユーザー アカウントでログオンしている場合に、ソフトウェアのインストール アクセス許可を持つアカウントを要求されたときは、Local Administrators グループのメンバーであるユーザーから資格情報の提供を受ける必要があります。


</div></td>
</tr>
<tr class="odd">
<td><p><strong>bootstrapper.exe</strong> - setup.exe によって呼び出され、サーバーの役割を展開および構成する処理を実行します。</p></td>
<td><p>実行可能ファイルを実行するコンピューターでの Local Administrators グループのメンバー。Bootstrapper.exe を実行する RTCUniversalServerAdmins グループのメンバー。AD DS の情報を読み取る Domain Users グループのメンバー。このレベルのアクセス許可が必要なのは、ローカル コンピューターへの必須 MSI パッケージの自動インストールでは、Program Files ディレクトリなどのローカル コンピューターの保護されたリソース、およびローカル コンピューター ハイブなどの保護されたレジストリとの間で読み書きできる特権が必要だからです。</p></td>
</tr>
<tr class="even">
<td><p><strong>TopologyBuilder</strong> – Lync Server 2013 のトポロジを作成、表示、調整、および検証するためのウィザードベースのユーザーインターフェイス。</p></td>
<td><p>実行可能ファイルを実行してトポロジを表示するコンピューターでの Local Administrators グループのメンバー。 構成の設定を変更する RTCUniversalServerAdmins グループのメンバー。 RTCUniversalServerAdmins グループと Domain Admins グループのメンバー、またはトポロジを発行する RTCUniversalServerAdmins グループのメンバー (このグループに委任セットアップ アクセス許可が付与されている場合のみ)。 RTCUniversalServerAdmins グループのメンバーがドメイン管理者グループのメンバーではない状態でトポロジを公開できるようにするための、セットアップのアクセス許可の委任の詳細については、「展開」のドキュメントの「 <a href="lync-server-2013-granting-setup-permissions.md">Lync Server 2013 のセットアップのアクセス許可を付与</a>する」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>AdminUIHost</strong> – Lync Server 2013 を管理するための Web ベースのグラフィカルユーザーインターフェイス。</p></td>
<td><p>CsAdministrator グループのメンバー、または特定の管理タスクが割り当てられる別の役割ベースのアクセス制御 (RBAC) の役割のメンバー。 Lync Server 2013 コントロールパネルは、Lync Server 2013 管理シェルコマンドレットを実行することによって、構成の変更を実装します。 定義済みの役割の一覧とコマンドレットのメンバーの実行を許可する方法については、「計画」のドキュメントの「 <a href="lync-server-2013-planning-for-role-based-access-control.md">planning for roles based access control In Lync Server 2013</a> 」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p>PowerShell: lync server <strong>2013 モジュールが読み込ま</strong>れたコマンドライン管理ツールを使用して、lync server 2013 の管理に固有のコマンドレットを実行します。</p></td>
<td><p>CsAdministrator グループのメンバー、または特定のコマンドレットが割り当てられている別の RBAC の役割のメンバー。 定義済みの役割の一覧とコマンドレットのメンバーの実行を許可する方法については、「計画」のドキュメントの「 <a href="lync-server-2013-planning-for-role-based-access-control.md">planning for roles based access control In Lync Server 2013</a> 」を参照してください。</p>
<p>または、次に示すグループのうち 1 つ以上のメンバー (コマンドレットによる):</p>
<ul>
<li><p>RTCUniversalServerAdmins</p></li>
<li><p>RTCUniversalUserAdmins</p></li>
<li><p>RTCUniversalReadOnlyAdmins</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

