---
title: 'Lync Server 2013: コンピューター、ユーザー、または InetOrgPerson のコンテナーでアクセス許可の継承が無効になっている'
TOCTitle: コンピューター、ユーザー、または InetOrgPerson のコンテナーでアクセス許可の継承が無効になっている
ms:assetid: c472ad21-a93d-4fcb-a3d9-60a2134a87fa
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg412970(v=OCS.15)
ms:contentKeyID: 48273504
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 のコンピューター、ユーザー、または InetOrgPerson のコンテナーでアクセス許可の継承が無効になっている

 

_**トピックの最終更新日:** 2014-12-19_

Active Directory ドメイン サービス がロックダウンされると、多くの場合、ユーザー オブジェクトとコンピューター オブジェクトは特定の組織単位 (OU) に置かれ、アクセス許可の継承が無効になります。これで管理業務の安全な委任が促進され、グループ ポリシー オブジェクト (GPO) を使用してセキュリティ ポリシーを適用できるようになります。

ドメインの準備とサーバーのアクティブ化では、 Lync Server 2013 で必要とされるアクセス制御エントリ (ACE) を設定します。アクセス許可の継承が無効になると、 Lync Server のセキュリティ グループはこれらの ACE を継承できません。アクセス許可を継承しない場合、 Lync Server のセキュリティ グループは設定にアクセスできず、次の 2 つの問題が生じます。

  - ユーザー、InetOrgPerson、および連絡先の管理やサーバーの操作を行う場合、 Lync Server のセキュリティ グループは、ドメインの準備の手順によって設定された、各ユーザーのプロパティ セット、リアルタイム通信 (RTC)、RTC ユーザー検索、およびパブリック インフォメーションに対する ACE を必要とします。アクセス許可の継承が無効になっている場合、これらの ACE がセキュリティ グループに継承されないので、サーバーまたはユーザーを管理することができません。

  - サーバーやプールを検出するため、 Lync Server を実行するサーバーは、Microsoft コンテナーや Server オブジェクトなどのコンピューター関連オブジェクトでのアクティブ化手順によって設定される ACE を利用します。アクセス許可の継承が無効になると、セキュリティ グループ、サーバー、プールがこれらの ACE を継承しないため、ACE を利用できなくなります。

これらの問題を解決するため、 Lync Server には **Grant-CsOuPermission** コマンドレットが用意されています。このコマンドレットは、指定されたコンテナーおよび組織単位、およびそのコンテナーまたは組織単位内のオブジェクトに、必要な Lync Server ACE を直接設定します。

## ドメインの準備手続き以後のユーザー、InetOrgPerson、および連絡先オブジェクトに対するアクセス許可の設定

ロックダウンされた Active Directory 環境では、アクセス許可の継承が無効になるため、ドメインの準備手続きの中で、ドメイン内のユーザー オブジェクトや InetOrgPerson オブジェクトを収容するコンテナーまたは組織単位に必要な ACE が設定されません。このような状況では、アクセス許可の継承が無効になっているユーザー オブジェクトや InetOrgPerson オブジェクトを収容する各コンテナーまたは OU に対して **Grant-CsOuPermission** コマンドレットを実行する必要があります。展開形態が中央フォレスト トポロジの場合は、連絡先オブジェクトを収容するコンテナーまたは OU に対しても、この手続きを実施する必要があります。中央フォレスト トポロジの詳細については、「サポート」のドキュメントの「[Lync Server 2013 でサポートされている Active Directory トポロジ](lync-server-2013-supported-active-directory-topologies.md)」を参照してください。ObjectType パラメーターは、オブジェクト タイプを指定します。OU パラメーターは組織単位を指定します。

このコマンドレットは、指定したコンテナーまたは OU、およびそのコンテナー内のユーザー オブジェクトまたは InetOrgPerson オブジェクトで、必要な ACE を直接追加します。

このコマンドレットを実行するには、Domain Admins グループ メンバーシップと同等のユーザー権限が必要です。認証済みユーザーの ACE がロックダウン環境でも削除されている場合は、「[Lync Server 2013 で認証済みユーザーのアクセス許可が削除されている](lync-server-2013-authenticated-user-permissions-are-removed.md)」の説明に従い、このアカウントにフォレストのルート ドメイン内の該当コンテナーまたは OU に対する読み取りアクセス ACE を与えるか、または Enterprise Admins グループのメンバー アカウントを使用する必要があります。

**ユーザー、InetOrgPerson、および連絡先オブジェクトに必要な ACE を設定するには**

1.  Domain Admins グループのメンバー アカウントか、それと同等のユーザー権限を持つアカウントを使用して、ドメインに参加しているコンピューターにログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

3.  次のコマンドレットを実行します。
    
        Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> 
        -OU <DN name for the OU container relative to the domain root container DN> [-Domain <Domain FQDN>]
    
    Domain パラメーターを指定しない場合、既定値はローカル ドメインになります。
    
    次に例を示します。
    
        Grant-CsOuPermission -ObjectType "User" -OU "cn=Redmond,dc=contoso,dc=net" -Domain "contoso.net"

4.  ログ ファイルで、各タスクの最後に **\<成功\>** という実行結果が表示されているかどうかを調べ、アクセス許可が設定されたことを確認し、ログ ウィンドウを閉じます。次のコマンドで、アクセス許可が設定されたかどうかを調べることもできます。
    
        Test-CsOuPermission -ObjectType <type of object> 
        -OU <DN name for the OU container relative to the domain root container DN> 
        [-Domain <Domain FQDN>] [-Report <fully qualified path and name of file to create>]
    
    次に例を示します。
    
        Test-CsOuPermission -ObjectType "User" -OU "cn=Redmond,dc=contoso,dc=net" -Domain "contoso.net" -Report "C:\Log\OUPermissionsTest.html"

## ドメイン準備手続き以後のコンピューター オブジェクトに対するアクセス許可の設定

ロックダウンされた Active Directory 環境ではアクセス許可の継承が無効になるため、ドメインの準備では、ドメイン内のコンピューター オブジェクトを収容するコンテナーまたは OU で必要な ACE が設定されません。このような状況では、 Lync Server を実行しているコンピューターを収容し、アクセス許可の継承が無効になっているコンピューターまたは OU に対して、 **Grant-CsOuPermission** コマンドレットを実行する必要があります。ObjectType パラメーターは、オブジェクト タイプを指定します。

この手続きを実行すると、必要な ACE が、指定したコンテナーに直接追加されます。

このコマンドレットを実行するには、Domain Admins グループ メンバーシップと同等のユーザー権限が必要です。認証済みユーザーの ACE も削除されている場合は、「[Lync Server 2013 で認証済みユーザーのアクセス許可が削除されている](lync-server-2013-authenticated-user-permissions-are-removed.md)」の説明に従ってフォレストのルート ドメイン内の該当コンテナーに対する読み取りアクセス ACE をこのアカウントに与えるか、または Enterprise Admins グループのメンバー アカウントを使用する必要があります。

**コンピューター オブジェクトに必要な ACE を設定するには**

1.  Domain Admins グループのメンバー アカウント、またはそれと同等のユーザー権限を持つアカウントを使用して、ドメインのコンピューターにログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

3.  次のコマンドレットを実行します。
    
        Grant-CsOuPermission -ObjectType <Computer> 
        -OU <DN name for the computer OU container relative to the domain root container DN> 
        [-Domain <Domain FQDN>][-Report <fully qualified path and name of output report>]
    
    Domain パラメーターを指定しない場合、既定値はローカル ドメインになります。
    
    次に例を示します。
    
        Grant-CsOuPermission -ObjectType "Computer" -OU "ou=Lync Servers,dc=litwareinc,dc=com" -Report "C:\Logs\OUPermissions.xml"

4.  例のログ ファイル C:\\Logs\\OUPermissions.xml で、各タスクの最後に **\<成功\>** という実行結果が表示されているかどうかを調べ、エラーがないことを確認して、ログ ウィンドウを閉じます。次のコマンドレットを実行してアクセス許可をテストできます。
    
        Test-CsOuPermission -ObjectType <type of object> 
        -OU <DN name for the OU container relative to the domain root container DN> [-Domain <Domain FQDN>]
    
    次に例を示します。
    
        Test-CsOuPermission -ObjectType "user","contact" -OU "cn=Bellevue,dc=contoso,dc=net" -Domain "contoso.net"
    
    > [!NOTE]  
    > ロックダウンされた Active Directory 環境内のフォレストのルート ドメインでドメインの準備を実行する場合、 Lync Server では、Active Directory のスキーマ コンテナーと構成コンテナーへのアクセス権が必要になります。<br />
    > 認証済みユーザーの既定のアクセス許可が AD DS 内のスキーマ コンテナーまたは構成コンテナーから削除されている場合は、Schema Admins グループ (スキーマ コンテナーの場合) または Enterprise Admins グループ (構成コンテナーの場合) のメンバーのみが、このコンテナーへのアクセスを許可されます。Setup.exe、 Lync Server 管理シェル コマンドレット、および Lync Server コントロール パネルはこれらのコンテナーへのアクセス権を必要とするため、インストールを実行するユーザーが Schema Admins と Enterprise Admins のグループ メンバーシップと同等のユーザー権限を持っていない限り、管理ツールのセットアップとインストールは失敗します。<br />
    > この状況に対処するには、RTCUniversalGlobalWriteGroup グループに、スキーマ コンテナーと構成コンテナーへの読み取りおよび書き込みアクセス権を与える必要があります。
