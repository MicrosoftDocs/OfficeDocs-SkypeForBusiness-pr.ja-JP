---
title: 'Lync Server 2013: セットアップのアクセス許可の委任'
TOCTitle: セットアップのアクセス許可の委任
ms:assetid: 9dca1683-4c69-4534-8ebe-6bd635cbae49
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg412735(v=OCS.15)
ms:contentKeyID: 48273037
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でのセットアップのアクセス許可の委任

 

_**トピックの最終更新日:** 2014-02-05_

Lync Server 2013 を展開しているユーザーまたはグループに Domain Admins グループのメンバーシップを付与しない場合は、 Lync Server 2013 を実行しているサーバー上での RTCUniversalServerAdmins グループのメンバーによる **Enable-CsTopology**  Windows PowerShell コマンドレットの実行を許可できます。既定では、RTCUniversalServerAdmins グループのメンバーは、このコマンドレットの実行権限を持ちません。 Lync Server を実行しているサーバー上で **Enable-CsTopology** を実行するための管理者権限とアクセス許可を付与します。それには、 **Grant-CsSetupPermission** コマンドレットを使用して Lync Server 2013 を実行しているサーバーのコンピューター オブジェクトが配置されている組織単位 (OU) を指定してください。

Lync Server のインストール時に行われるドメインの準備では、RTCUniversalServerAdmins グループのメンバーが Enable-CsTopology コマンドレットを実行するためのアクセス許可は、自動的に追加されません。つまり、既定では、トポロジを有効にするためにはドメイン管理者である必要があります。RTCUniversalServerAdmins グループのメンバーにトポロジを有効にする権限を付与するには、Grant-CsSetupPermissions コマンドレットを実行する必要があります。また、Lync Server を実行しているコンピューターが所属する Active Directory コンテナーのそれぞれに対して、このコマンドレットを実行することも必要です。

このコマンドレットは、RTCUniversalServerAdmins グループのみにアクセス許可を付与する点に留意してください。他のセキュリティ グループまたは個別のユーザーにアクセス許可を付与するために使用することはできません。

> [!NOTE]
> <strong>Enable-CsTopology</strong> は、RTCUniversalServerAdmins グループのメンバーが Lync Server 2013 を設定および展開できるようにするための重要なコマンドレットです。


## RTCUniversalServerAdmins グループに、Enable-CsTopology を実行する権限を追加するには

1.  委任されたユーザーが **Enable-CsTopology** を実行する予定のドメインの Domain Admins グループのメンバーとしてサーバーにログオンします。

2.  Lync Server 2013 管理シェルを開きます。 Lync Server 2013 管理シェルは、 フロント エンド サーバーごとまたは Lync Server 2013 管理ツールがインストールされているコンピューターごとに自動でインストールされます。 Lync Server 2013 管理シェルの詳細については、「操作」のドキュメントの「[Lync Server 2013 管理シェル](lync-server-2013-lync-server-management-shell.md)」を参照してください。

3.  Lync Server 2013 管理シェルから、次のコマンドレットを実行します。
    
        Grant-CsSetupPermission -ComputerOU <DN of the OU> -Domain <Domain FQDN>
    
    > [!NOTE]
    > OU が最上位レベルでない場合は、完全ドメイン名を指定する必要があります。
    
    次の例では、OU は、contoso.com ドメインにある "Lync Servers" です。
    
        Grant-CsSetupPermission -ComputerOU "OU=Lync Servers" -Domain contoso.com

