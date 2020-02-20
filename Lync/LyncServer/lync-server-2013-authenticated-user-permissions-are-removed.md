---
title: 'Lync Server 2013: 認証済みユーザーのアクセス許可が削除される'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Authenticated user permissions are removed
ms:assetid: 5fcd70a5-813a-4076-9bb6-5b0d47505038
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398425(v=OCS.15)
ms:contentKeyID: 48184304
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 45080baa0839731808aefcc31c1551bfab5293db
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145466"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="authenticated-user-permissions-are-removed-in-lync-server-2013"></a>Lync Server 2013 で認証済みユーザーのアクセス許可が削除される

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-21_

ロックダウンされた Active Directory 環境では、認証されたユーザーアクセス制御エントリ (Ace) は、ユーザー、構成、システム、および組織単位 (Ou) (ユーザーとコンピューター) を含む既定の Active Directory コンテナーから削除されます。オブジェクトが格納されます。 認証済みユーザー Ace を削除すると、Active Directory 情報への読み取りアクセスが禁止されます。 ただし、Ace を削除すると、ユーザーがドメインの準備を実行できるようにするために、これらのコンテナーに対する読み取りアクセス許可に依存するため、Lync Server 2013 の問題が発生します。

この状況では、ドメインの準備、サーバーのアクティブ化、およびプールの作成を実行するのに必要な Domain Admins グループのメンバーシップに対して、既定のコンテナーに格納されている Active Directory 情報への読み取りアクセスが許可されません。前提条件となるフォレストの準備の手順が完了したかどうかを確認するには、フォレストのルート ドメイン内のさまざまなコンテナーに対する読み取りアクセス許可を手動で与える必要があります。

ユーザーがフォレスト以外のルート ドメインでドメインの準備、サーバーのアクティブ化、またはプールの作成を実行できるようにするには、次のいずれかの方法を使用します。

  - エンタープライズ管理者グループのメンバーであるアカウントを使用して、ドメインの準備を実行します。

  - Domain Admins グループのメンバーであるアカウントを使用し、フォレストのルート ドメイン内の次の各コンテナーに対する読み取りアクセス許可をこのアカウントに与える。
    
      - ドメイン
    
      - 構成またはシステム

ドメインの準備またはその他のセットアップ タスクを実行する際に、Enterprise Admins グループのメンバーであるアカウントを使用しない場合は、フォレストのルート内の該当のコンテナーに対する読み取りアクセスを、使用するアカウントに明示的に許可します。

<div>

## <a name="to-give-users-read-access-permissions-on-containers-in-the-forest-root-domain"></a>フォレストのルート ドメイン内のコンテナーに対する読み取りアクセス許可をユーザーに与えるには

1.  フォレストのルート ドメインの Domain Admins グループのメンバーであるアカウントを使用して、このドメインに参加しているコンピューターにログオンします。

2.  フォレストのルート ドメインに対して adsiedit.msc を実行します。
    
    認証済みユーザーの ACE がドメイン コンテナー、構成コンテナー、またはシステム コンテナーから削除されている場合は、次のステップに従って、そのコンテナーに対する読み取り専用アクセス許可を与える必要があります。

3.  コンテナーを右クリックし、[**プロパティ**] をクリックします。

4.  [**セキュリティ**] タブをクリックします。

5.  [**詳細設定**] をクリックします。

6.  [**アクセス許可**] タブで [**追加**] をクリックします。

7.  次の形式`domain\account name`を使用して、アクセス許可を受け取るユーザーまたはグループの名前を入力し、[ **OK]** をクリックします。

8.  [**オブジェクト**] タブの [**適用先**] で [**このオブジェクトのみ**] をクリックします。

9.  [**アクセス許可**] で [**許可**] 列をクリックして、 [**コンテンツの一覧表示**]、[**すべてのプロパティの読み取り**]、および [**読み取りアクセス許可**] を、許可する ACE として選択します。

10. [**OK**] を 2 回クリックします。

11. ステップ 2. でリストアップした該当するすべてのコンテナーについて、上記のステップを繰り返します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

