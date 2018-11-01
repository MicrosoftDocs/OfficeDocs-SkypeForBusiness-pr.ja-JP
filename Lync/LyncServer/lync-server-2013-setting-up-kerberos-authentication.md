---
title: 'Lync Server 2013: Kerberos 認証の設定'
TOCTitle: Kerberos 認証の設定
ms:assetid: dd8009ef-6265-4cc0-b2c7-e474cd1f4b09
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398976(v=OCS.15)
ms:contentKeyID: 48273762
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での Kerberos 認証の設定

 

_**トピックの最終更新日:** 2013-02-21_

Lync Server 2013 では Web サービスの NTLM および Kerberos 認証がサポートされています。 Office Communications Server 2007 と Office Communications Server 2007 R2 では、 Web サービス アプリケーション プールを実行するユーザー アカウントとして既定値の RTCComponentService と RTCService が使用され、サービス プリンシパル名 (SPN) をユーザー アカウントに割り当て、認証プリンシパルとして機能させることができました。 Lync Server では、 Web サービスの実行に NetworkService が使用されます。NetworkService に SPN を割り当てることはできません。

Active Directory オブジェクトに SPN がない問題を解決するために、Lync Server コントロール パネル ではこの目的にコンピューター アカウント オブジェクトを使用できます。コンピューター アカウント オブジェクトは SPN を持つことができます。以前のバージョンでユーザー アカウントを使用しているときには、パスワードの有効期限が問題でしたが、コンピューター アカウント オブジェクトはパスワード有効期限の影響を受けません。

Kerberos 認証を提供するためにコンピューター オブジェクトを構成するには、 Windows PowerShell コマンドレットを使用します。

## このセクション中

  - [Lync Server 2013 で Kerberos 認証を有効にするための前提条件](lync-server-2013-prerequisites-for-enabling-kerberos-authentication.md)

  - [Lync Server 2013 での Kerberos 認証アカウントの作成](lync-server-2013-create-a-kerberos-authentication-account.md)

  - [Lync Server 2013 での、サイトへの Kerberos 認証アカウントの割り当て](lync-server-2013-assign-a-kerberos-authentication-account-to-a-site.md)

  - [Lync Server 2013 での Kerberos 認証アカウント パスワードの設定](lync-server-2013-setting-up-kerberos-authentication-account-passwords.md)

  - [Lync Server 2013 での他のサイトへの Kerberos 認証の追加](lync-server-2013-add-kerberos-authentication-to-other-sites.md)

  - [Lync Server 2013 でのサイトからの Kerberos 認証の削除](lync-server-2013-remove-kerberos-authentication-from-a-site.md)

  - [Lync Server 2013 での Kerberos 認証の状態と割り当てについてのテストおよびレポート](lync-server-2013-testing-and-reporting-the-status-and-assignment-of-kerberos-authentication.md)

