---
title: 'Lync Server 2013: コンピューター、ユーザー、または InetOrgPerson のコンテナーでアクセス許可の継承が無効になっている'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Permissions inheritance Is disabled on computers, users, or InetOrgPerson containers
ms:assetid: c472ad21-a93d-4fcb-a3d9-60a2134a87fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412970(v=OCS.15)
ms:contentKeyID: 48185348
ms.date: 12/19/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 73692539fb5dda38446ffddccbe35c8d366e2d67
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825304"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers-in-lync-server-2013"></a>Lync Server 2013 のコンピューター、ユーザー、または InetOrgPerson のコンテナーでアクセス許可の継承が無効になっている

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-12-19_

ロックダウンされた Active Directory ドメインサービスでは、管理者の委任をセキュリティで保護し、グループポリシーオブジェクト (Gpo) の使用を可能にするために、アクセス許可の継承が無効になっている特定の組織単位 (Ou) に、ユーザーとコンピューターオブジェクトが配置されることがよくあります。セキュリティポリシーを適用するには

ドメインの準備とサーバーのアクティブ化 Lync Server 2013 に必要なアクセス制御エントリ (Ace) を設定します。 権限の継承が無効になっている場合、Lync Server のセキュリティグループはこれらの Ace を継承することはできません。 これらのアクセス許可が継承されない場合、Lync Server セキュリティグループは設定にアクセスできません。次の2つの問題が発生します。

  - ユーザー、InetOrgPersons、連絡先を管理したり、サーバーを操作したりするには、Lync Server のセキュリティグループで、各ユーザーのプロパティセット、リアルタイム通信 (RTC)、RTC ユーザー検索、およびパブリック情報のドメインの準備手順によって設定された Ace が必要です。. 権限の継承が無効になっている場合、セキュリティグループはこれらの Ace を継承せず、サーバーまたはユーザーを管理することはできません。

  - サーバーとプールを見つけるために、Lync Server を実行しているサーバーは、Microsoft Container および Server オブジェクトを含む、コンピューターに関連するオブジェクトのアクティベーションによって設定された Ace に依存しています。 権限の継承が無効になっている場合、セキュリティグループ、サーバー、およびプールにはこれらの Ace は継承されず、これらの Ace を利用することはできません。

これらの問題に対処するために、Lync Server では、**グラント Oupermission**コマンドレットが提供されています。 このコマンドレットは、必要な Lync Server Ace を、指定したコンテナーと組織単位、およびコンテナーまたは組織単位内のオブジェクトに直接設定します。

<div>

## <a name="set-permissions-for-user-inetorgperson-and-contact-objects-after-running-domain-preparation"></a>ドメインの準備が実行された後に、ユーザー、InetOrgPerson、連絡先オブジェクトのアクセス許可を設定する

権限の継承が無効になっているロックダウンされた Active Directory 環境では、ドメインの準備によって、ドメイン内のユーザーまたは InetOrgPerson オブジェクトを保持しているコンテナーまたは組織単位の必要な Ace は設定されません。 この場合は、権限の継承が無効になっているユーザーまたは InetOrgPerson オブジェクトを持つ各コンテナーまたは OU に対して、**グラント Ou権限**コマンドレットを実行する必要があります。 中央フォレストトポロジを使用している場合は、連絡先オブジェクトを保持するコンテナーまたは Ou でもこの手順を実行する必要があります。 セントラルフォレストトポロジの詳細については、サポートドキュメントの「 [Lync Server 2013 でサポートされている Active Directory トポロジ](lync-server-2013-supported-active-directory-topologies.md)」を参照してください。 ObjectType パラメーターは、オブジェクトの種類を指定します。 OU パラメーターは、組織単位を指定します。

このコマンドレットは、指定したコンテナーまたは Ou と、コンテナー内のユーザーまたは InetOrgPerson オブジェクトに、必要な Ace を直接追加します。 このコマンドが実行される OU にユーザーオブジェクトまたは InetOrgPerson オブジェクトを持つ子 Ou がある場合、そのアクセス許可は適用されません。 コマンドは、各子 OU で個別に実行する必要があります。 これは、次のような Lync ホスティング展開 (親 OU = OCS テナント、DC = CONTOSO, dc = LOCAL and child OU = テナント1、OU = OCS テナント、DC = CONTOSO、DC = LOCAL) で一般的なシナリオです。

このコマンドレットを実行するには、ドメイン管理者グループのメンバーシップに相当するユーザー権限が必要です。 ロックダウン環境で認証されたユーザーの Ace も削除されている場合は、「[認証されたユーザーのアクセス許可が Lync で削除される」というように、フォレストルートドメイン内の関連するコンテナーまたは ou で、このアカウントの読み取りアクセス ace を付与する必要があります。サーバー 2013](lync-server-2013-authenticated-user-permissions-are-removed.md)を使うか、Enterprise Admins グループのメンバーであるアカウントを使用します。

**ユーザー、InetOrgPerson、連絡先オブジェクトに必要な Ace を設定するには**

1.  ドメイン管理者グループのメンバーであるか、同等のユーザー権限を持っているアカウントで、ドメインに参加しているコンピューターにログオンします。

2.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

3.  次のコマンドレットを実行します。
    
        Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> 
        -OU <DN name for the OU container relative to the domain root container DN> [-Domain <Domain FQDN>]
    
    Domain パラメーターを指定しない場合、既定値はローカルドメインです。
    
    次に例を示します。
    
        Grant-CsOuPermission -ObjectType "User" -OU "cn=Redmond,dc=contoso,dc=net" -Domain "contoso.net"

4.  ログファイルで、各タスクの最後で** \<成功\> **した実行の結果を探して、アクセス許可が設定されていることを確認し、[ログ] ウィンドウを閉じます。 または、次のコマンドを実行して、アクセス許可が設定されているかどうかを確認することができます。
    
        Test-CsOuPermission -ObjectType <type of object> 
        -OU <DN name for the OU container relative to the domain root container DN> 
        [-Domain <Domain FQDN>] [-Report <fully qualified path and name of file to create>]
    
    次に例を示します。
    
        Test-CsOuPermission -ObjectType "User" -OU "cn=Redmond,dc=contoso,dc=net" -Domain "contoso.net" -Report "C:\Log\OUPermissionsTest.html"

</div>

<div>

## <a name="set-permissions-for-computer-objects-after-running-domain-preparation"></a>ドメインの準備が実行された後に、コンピューターオブジェクトのアクセス許可を設定する

権限の継承が無効になっているロックダウンされた Active Directory 環境では、ドメインの準備によって、ドメイン内のコンピューターオブジェクトを保持するコンテナーまたは Ou に必要な Ace は設定されません。 この場合は、権限の継承が無効になっている Lync Server を実行しているコンピューターを持つ各コンテナーまたは OU に対して、**グラント Ou権限**コマンドレットを実行する必要があります。 ObjectType パラメーターは、オブジェクトの種類を指定します。

この手順では、指定したコンテナーに必要な Ace を直接追加します。

このコマンドレットを実行するには、ドメイン管理者グループのメンバーシップに相当するユーザー権限が必要です。 認証されたユーザーの Ace も削除された場合は、「[認証されたユーザーのアクセス許可が Lync Server 2013 で削除](lync-server-2013-authenticated-user-permissions-are-removed.md)される」または「のアカウントを使用する」の説明に従って、フォレストルートドメイン内の関連するコンテナーに対して、このアカウントに読み取りアクセス ace を与える必要があります。Enterprise Admins グループのメンバー。

**コンピューターオブジェクトに必要な Ace を設定するには**

1.  Domain Admins グループのメンバーであるか、同等のユーザー権限を持つアカウントで、ドメインコンピューターにログオンします。

2.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

3.  次のコマンドレットを実行します。
    
        Grant-CsOuPermission -ObjectType <Computer> 
        -OU <DN name for the computer OU container relative to the domain root container DN> 
        [-Domain <Domain FQDN>][-Report <fully qualified path and name of output report>]
    
    Domain パラメーターを指定しない場合、既定値はローカルドメインです。
    
    次に例を示します。
    
        Grant-CsOuPermission -ObjectType "Computer" -OU "ou=Lync Servers,dc=litwareinc,dc=com" -Report "C:\Logs\OUPermissions.xml"

4.  例として、「log\\file\\C:」と入力すると、各タスクの最後に** \<成功\> **の実行結果が表示され、エラーがないことを確認してから、ログを閉じます。 権限をテストするには、次のコマンドレットを実行します。
    
        Test-CsOuPermission -ObjectType <type of object> 
        -OU <DN name for the OU container relative to the domain root container DN> [-Domain <Domain FQDN>]
    
    次に例を示します。
    
        Test-CsOuPermission -ObjectType "user","contact" -OU "cn=Bellevue,dc=contoso,dc=net" -Domain "contoso.net"
    
    <div>
    

    > [!NOTE]  
    > ロックダウンされた Active Directory 環境でフォレストルートドメインでドメインの準備を実行している場合は、Lync Server で Active Directory スキーマと構成コンテナーへのアクセスが必要になることに注意してください。<BR>既定の認証済みユーザーアクセス許可が、スキーマまたは AD&nbsp;DS の構成コンテナーから削除された場合は、schema Admins グループ (スキーマコンテナー用) または Enterprise Admins グループ (構成コンテナー用) のメンバーのみが許可されます。指定したコンテナーにアクセスします。 Setup.exe、Lync Server 管理シェルコマンドレット、および Lync Server コントロールパネルでは、これらのコンテナーにアクセスする必要があるため、インストールを実行しているユーザーにスキーマに相当するユーザー権限がある場合を除き、管理ツールのセットアップとインストールは失敗します。管理者とエンタープライズ管理者グループのメンバーシップ。<BR>この問題を解決するには、スキーマと構成コンテナーへの書き込みアクセス許可を RTCUniversalGlobalWriteGroup group に付与する必要があります。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

