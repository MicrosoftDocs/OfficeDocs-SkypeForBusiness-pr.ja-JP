---
title: 'Lync Server 2013: Kerberos 認証アカウント パスワードの設定'
TOCTitle: Kerberos 認証アカウント パスワードの設定
ms:assetid: b435f88e-4a77-4be7-b7e5-c17484303b74
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg412870(v=OCS.15)
ms:contentKeyID: 48273321
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での Kerberos 認証アカウント パスワードの設定

 

_**トピックの最終更新日:** 2010-11-03_

Kerberos 認証アカウントのコンピューター オブジェクトを作成したら、そのアカウント用のパスワードを設定できます。 1 つのサーバーに、Kerberos のアカウント パスワードを設定するには、Windows PowerShell コマンドレットを実行します。 Kerberos 認証のために作成したオブジェクトにパスワードを設定できます。 このパスワードは既知の値に設定することができますが、既定値はランダムなパスワードです。 このパスワードは、このアカウントを使用するすべての Kerberos 認証ソースを利用できます。 Kerberos のアカウント パスワードを設定および管理するには、Windows PowerShell コマンドレットを使用します。

> [!NOTE]
> Kerberos のアカウント オブジェクトはコンピューター オブジェクトですが、参照する Windows PowerShell コマンドレットの操作では UserAccount パラメーターを使用します。 これは間違いではなく、このコマンドレットを Kerberos のアカウントの作成および管理に使用するときの、意図的な動作です。


## このセクション中

  - [Lync Server 2013 でのサーバーへの Kerberos 認証アカウント パスワードの設定](lync-server-2013-set-a-kerberos-authentication-account-password-on-a-server.md)

  - [Lync Server 2013 での Kerberos 認証アカウント パスワードと IIS との同期](lync-server-2013-synchronize-a-kerberos-authentication-account-password-to-iis.md)

