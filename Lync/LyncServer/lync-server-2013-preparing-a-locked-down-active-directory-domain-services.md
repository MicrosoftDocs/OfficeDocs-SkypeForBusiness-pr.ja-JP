---
title: 'Lync Server 2013: ロックダウンされた Active Directory ドメイン サービスの準備'
TOCTitle: ロックダウンされた Active Directory ドメイン サービスの準備
ms:assetid: 68bde963-3fa3-4102-88d6-ac931c1dd2d7
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398492(v=OCS.15)
ms:contentKeyID: 48272380
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でのロックダウンされた Active Directory ドメイン サービスの準備

 

_**トピックの最終更新日:** 2012-05-14_

多くの場合、組織は、セキュリティ リスクを軽減するために Active Directory ドメイン サービス をロックダウンしています。 しかし、ロックダウンされた Active Directory 環境では、Lync Server 2013 で必要なアクセス許可が制限される場合があります。Lync Server 2013 用にロックダウンされた Active Directory 環境を適切に準備するには、追加の考慮事項の検討と追加のステップの実行が必要です。

ロックダウンされた Active Directory 環境でアクセス許可が制限されるのは、一般に次の 2 つの場合です。

  - 認証済みユーザーのアクセス制御エントリ (ACE) がコンテナーから削除されている。

  - ユーザー オブジェクト、連絡先オブジェクト、InetOrgPerson オブジェクト、またはコンピューター オブジェクトのコンテナーでアクセス許可の継承が無効になっている。

## このセクション中

  - [Lync Server 2013 で認証済みユーザーのアクセス許可が削除されている](lync-server-2013-authenticated-user-permissions-are-removed.md)

  - [Lync Server 2013 のコンピューター、ユーザー、または InetOrgPerson のコンテナーでアクセス許可の継承が無効になっている](lync-server-2013-permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers.md)

