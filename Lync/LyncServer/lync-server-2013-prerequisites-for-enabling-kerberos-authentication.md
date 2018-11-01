---
title: 'Lync Server 2013: Kerberos 認証を有効にするための前提条件'
TOCTitle: Kerberos 認証を有効にするための前提条件
ms:assetid: 3f276a21-7476-4bc0-9fd1-59e844d2e9c1
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg425909(v=OCS.15)
ms:contentKeyID: 48271864
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 で Kerberos 認証を有効にするための前提条件

 

_**トピックの最終更新日:** 2013-02-21_

Kerberos 認証を有効にする前に、前提条件の構成とインフラストラクチャの準備をすべて完了してください。

  - Lync Server 2013 で、Active Directory スキーマが拡張されている。

  - Lync Server 2013 で、Active Directory のフォレスト準備が完了している。

  - Lync Server 2013 で、Active Directory のドメイン準備が完了している。

  - 中央管理ストアが正しくインストールされており、使用できる。

  - トポロジ ビルダーを使用してトポロジを作成および公開済みである。

  - Web サービスを必要とするサーバーと役割 (フロントエンド サーバー、Standard Edition サーバー、ディレクターなど) が定義されており、展開済みである。

  - Lync Server 2013 で、Web サービスをサポートするための推奨の役割サービスを使用して、インターネット インフォメーション サービス (IIS) が構成および展開されている。

これらの前提条件が満たされると、展開で Web サービスのアカウントを 1 つ以上作成し、Kerberos 認証を使用するための準備ができたことになります。 展開ごとに、Kerberos 認証アカウントを 1 つ以上作成する必要があります。 ただし、サイトごとにアカウントを作成し、サイトでローカルの Kerberos 認証を使用できます。 Kerberos 認証アカウントは、1 サイトあたり 1 つしか指定できません。

