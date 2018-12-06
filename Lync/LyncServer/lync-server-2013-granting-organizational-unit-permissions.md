---
title: 'Lync Server 2013: 組織単位アクセス許可の付与'
TOCTitle: 組織単位アクセス許可の付与
ms:assetid: 95ee5ffa-39b1-4d80-87a2-27bb364f7396
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398763(v=OCS.15)
ms:contentKeyID: 48272904
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での組織単位アクセス許可の付与

 

_**トピックの最終更新日:** 2012-05-14_

**Grant-CsOuPermission** コマンドレットを使って、特定の組織単位 (OU) ごとにオブジェクトに対するアクセス許可を出すことができます。そうすることで、フォレストの準備によって作成された RTC ユニバーサル グループのメンバーが、Domain Admins グループのメンバーにならなくともそれらのオブジェクトにアクセスすることが可能になります。特定の OU に追加されたアクセス許可は、 **Enable-CsAdDomain** コマンドレットがドメインの準備中にコンピューターおよびユーザー コンテナーに追加するのと同じアクセス許可です。

**Test-CsOuPermission** コマンドレットを使用して設定したアクセス許可は、 **Grant-CsOuPermission** コマンドレットを使用して確認できます。

**Revoke-CsOuPermission** コマンドレットを使用して付与したアクセス許可は、 **Grant-CsOuPermission** コマンドレットを使用して削除できます。

## OU アクセス許可を付与するには

1.  OU アクセス許可を付与したいドメインで、 Lync Server 2013 を実行しているコンピューターへログオンします。OU が別の子ドメインに存在する場合、Domain Admins グループまたは Enterprise Admins グループのメンバーであるアカウントを使用します。

2.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

3.  次のコマンドレットを実行します。
    
        Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    Domain パラメーターを指定しない場合、既定値はローカル ドメインになります。

## OU アクセス許可を確認するには

1.  **Grant-CsOuPermission** コマンドレットを使って付与した OU アクセス許可を確認したいドメインで、 Lync Server 2013 を実行しているコンピューターにログオンします。OU が別の子ドメインに存在する場合、Domain Admins グループまたは Enterprise Admins グループのメンバーであるアカウントを使用します。

2.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

3.  次のコマンドレットを実行します。
    
        Test-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    Domain パラメーターを指定しない場合、既定値はローカル ドメインになります。

## OU アクセス許可を無効にするには

1.  **Grant-CsOuPermission** コマンドレットを使って設定した OU アクセス許可を無効にしたいドメインで、 Lync Server 2013 を実行しているコンピューターにログオンします。OU が別の子ドメインに存在する場合、Domain Admins グループまたは Enterprise Admins グループのメンバーであるアカウントを使用します。

2.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

3.  次のコマンドレットを実行します。
    
        Revoke-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    Domain パラメーターを指定しない場合、既定値はローカル ドメインになります。

