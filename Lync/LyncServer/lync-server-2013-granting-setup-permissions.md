---
title: 'Lync Server 2013: セットアップ アクセス許可の付与'
TOCTitle: セットアップ アクセス許可の付与
ms:assetid: 15982bfe-6844-44f6-815a-72dcaf0e4d21
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398225(v=OCS.15)
ms:contentKeyID: 48271363
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でのセットアップ アクセス許可の付与

 

_**トピックの最終更新日:** 2012-08-27_

**Grant-CsSetupPermission** コマンドレットを使用して、Read、Write、ReadSPN、および WriteSPN のアクセス許可を特定の Active Directory 組織単位 (OU) の RTCUniversalServerAdmins グループに追加できます。これにより、その OU の RTCUniversalServerAdmins グループのメンバーは、Domain Admins グループのメンバーでなくても、指定したドメインで Lync Server 2013 を実行するサーバーをインストールできるようになります。

**Grant-CsSetupPermission** コマンドレットを使用して設定したアクセス許可は、**Test-CsSetupPermission** コマンドレットを使用して確認できます。

**Grant-CsSetupPermission** コマンドレットを使用して付与したアクセス許可は、**Revoke-CsSetupPermission** コマンドレットを使用して削除できます。

## セットアップのアクセス許可を付与するには

1.  セットアップのアクセス許可を付与する、ドメイン内の Lync Server 2013 を実行しているコンピューターにログオンします。OU が別の子ドメインに存在する場合、Domain Admins グループまたは Enterprise Admins グループのメンバーであるアカウントを使用します。

2.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

3.  次のコマンドレットを実行します。
    
        Grant-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    指定したドメインの既定の名前付けコンテキストに相対的な ComputerOu パラメーターを指定できます (CN=computer など)。または、このパラメーターに完全な OU 識別名 (DN) を指定することもできます ("CN=computers,DC=Contoso,DC=com" など)。後者の場合、指定するドメインに一致する OU DN を指定する必要があります。
    
    Domain パラメーターを指定しない場合、既定値はローカル ドメインになります。

## セットアップのアクセス許可を確認するには

1.  **Grant-CsSetupPermission** コマンドレットを使用して付与したセットアップのアクセス許可を確認する、ドメイン内の Lync Server 2013 を実行しているコンピューターにログオンします。OU が別の子ドメインに存在する場合、Domain Admins グループまたは Enterprise Admins グループのメンバーであるアカウントを使用します。

2.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

3.  次のコマンドレットを実行します。
    
        Test-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside> [-Domain <Domain FQDN>]
    
    指定したドメインの既定の名前付けコンテキストに相対的な ComputerOu パラメーターを指定できます (CN=computer など)。または、このパラメーターに完全な OU 識別名 (DN) を指定することもできます ("CN=computers,DC=Contoso,DC=com" など)。後者の場合、指定するドメインに一致する OU DN を指定する必要があります。
    
    Domain パラメーターを指定しない場合、既定値はローカル ドメインになります。

## セットアップのアクセス許可を無効にするには

1.  **Grant-CsSetupPermission** コマンドレットを使用して付与したセットアップのアクセス許可を無効にする、ドメイン内の Lync Server 2013 を実行しているコンピューターにログオンします。OU が別の子ドメインに存在する場合、Domain Admins グループまたは Enterprise Admins グループのメンバーであるアカウントを使用します。

2.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

3.  次のコマンドレットを実行します。
    
        Revoke-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    指定したドメインの既定の名前付けコンテキストに相対的な ComputerOu パラメーターを指定できます (CN=computer など)。または、このパラメーターに完全な OU 識別名 (DN) を指定することもできます ("CN=computers,DC=Contoso,DC=com" など)。後者の場合、指定するドメインに一致する OU DN を指定する必要があります。
    
    Domain パラメーターを指定しない場合、既定値はローカル ドメインになります。

