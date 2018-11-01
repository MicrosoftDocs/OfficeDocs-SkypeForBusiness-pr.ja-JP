---
title: クライアント認証をサポートする AD FS 2.0 の構成
TOCTitle: クライアント認証をサポートする AD FS 2.0 の構成
ms:assetid: 4d93d400-ccaa-4da8-a71b-d05d7ba79d93
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Dn308565(v=OCS.15)
ms:contentKeyID: 56270068
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# クライアント認証をサポートする AD FS 2.0 の構成

 

_**トピックの最終更新日:** 2016-12-08_

AD FS 2.0 でスマート カードを使用した認証をサポートできるように構成可能な認証の種類が 2 つあります。

  - フォーム ベース認証 (FBA)

  - トランスポート層セキュリティ クライアント認証

フォーム ベース認証を使用すると、ユーザー名/パスワードを使用した認証またはスマート カードと PIN を使用した認証をユーザーに許可できる Web ページを開発できます。このトピックでは、AD FS 2.0 でトランスポート層セキュリティ クライアント認証を実装する方法を説明します。AD FS 2.0 の認証の種類の詳細については、「How to Change the Local Authentication Type」([http://go.microsoft.com/fwlink/p/?LinkId=313384](http://go.microsoft.com/fwlink/p/?linkid=313384)) を参照してください。


**クライアント認証をサポートするように AD FS 2.0 を構成するには**

1.  ドメイン管理者のアカウントを使用して AD FS 2.0 コンピューターにログインします。

2.  エクスプローラーを起動します。

3.  C:\\inetpub\\adfs\\ls に移動します。

4.  既存の web.config ファイルのバックアップ コピーを作成します。

5.  メモ帳を使用して既存の web.config ファイルを開きます。

6.  メニュー バーの \[**編集**\] をクリックし、\[**検索**\] をクリックします。

7.  「**\<localAuthenticationTypes\>**」を検索します。
    
    4 つの認証の種類が 1 行に 1 つずつ表示されます。

8.  TLSClient 認証の種類を含む行をセクションの一覧の一番上に移動します。

9.  web.config ファイルを保存して閉じます。

10. 管理者特権でコマンド プロンプトを起動します。

11. 次のコマンドを実行して IIS を再起動します。
    
        IISReset /Restart /NoForce

