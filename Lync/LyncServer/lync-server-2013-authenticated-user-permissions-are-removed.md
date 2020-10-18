---
title: 'Lync Server 2013: 認証済みユーザーのアクセス許可が削除される'
description: 'Lync Server 2013: 認証済みユーザーのアクセス許可が削除されます。'
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
ms.openlocfilehash: 59da0ec893395405010afdd0263bd6be5d646881
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573023"
---
# <a name="authenticated-user-permissions-are-removed-in-lync-server-2013"></a><span data-ttu-id="af7cf-103">Lync Server 2013 で認証済みユーザーのアクセス許可が削除される</span><span class="sxs-lookup"><span data-stu-id="af7cf-103">Authenticated user permissions are removed in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="af7cf-104">_**トピックの最終更新日:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="af7cf-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="af7cf-105">ロックダウンされた Active Directory 環境では、認証されたユーザーアクセス制御エントリ (Ace) は、ユーザー、構成、システム、およびユーザーとコンピューターオブジェクトが格納される組織単位 (Ou) を含む、既定の Active Directory コンテナーから削除されます。</span><span class="sxs-lookup"><span data-stu-id="af7cf-105">In a locked-down Active Directory environment, authenticated user access control entries (ACEs) are removed from the default Active Directory containers, including the Users, Configuration or System, and organizational units (OUs) where User and Computer objects are stored.</span></span> <span data-ttu-id="af7cf-106">認証済みユーザー Ace を削除すると、Active Directory 情報への読み取りアクセスが禁止されます。</span><span class="sxs-lookup"><span data-stu-id="af7cf-106">Removing authenticated user ACEs prevents read access to Active Directory information.</span></span> <span data-ttu-id="af7cf-107">ただし、Ace を削除すると、ユーザーがドメインの準備を実行できるようにするために、これらのコンテナーに対する読み取りアクセス許可に依存するため、Lync Server 2013 の問題が発生します。</span><span class="sxs-lookup"><span data-stu-id="af7cf-107">However, removing the ACEs creates issues for Lync Server 2013 because it depends on read permissions to these containers to allow users to run domain preparation.</span></span>

<span data-ttu-id="af7cf-p102">この状況では、ドメインの準備、サーバーのアクティブ化、およびプールの作成を実行するのに必要な Domain Admins グループのメンバーシップに対して、既定のコンテナーに格納されている Active Directory 情報への読み取りアクセスが許可されません。前提条件となるフォレストの準備の手順が完了したかどうかを確認するには、フォレストのルート ドメイン内のさまざまなコンテナーに対する読み取りアクセス許可を手動で与える必要があります。</span><span class="sxs-lookup"><span data-stu-id="af7cf-p102">In this situation, membership in the Domain Admins group, which is required to run domain preparation, server activation, and pool creation, no longer grants read access to Active Directory information stored in the default containers. You must manually grant read-access permissions on various containers in the forest root domain to check that the prerequisite forest preparation procedure is complete.</span></span>

<span data-ttu-id="af7cf-110">ユーザーがフォレスト以外のルート ドメインでドメインの準備、サーバーのアクティブ化、またはプールの作成を実行できるようにするには、次のいずれかの方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="af7cf-110">To enable a user to run domain preparation, server activation, or pool creation on any non-forest root domain, you have the following options:</span></span>

  - <span data-ttu-id="af7cf-111">エンタープライズ管理者グループのメンバーであるアカウントを使用して、ドメインの準備を実行します。</span><span class="sxs-lookup"><span data-stu-id="af7cf-111">Use an account that is a member of the Enterprise Admins group to run domain preparation.</span></span>

  - <span data-ttu-id="af7cf-112">Domain Admins グループのメンバーであるアカウントを使用し、フォレストのルート ドメイン内の次の各コンテナーに対する読み取りアクセス許可をこのアカウントに与える。</span><span class="sxs-lookup"><span data-stu-id="af7cf-112">Use an account that is a member of the Domain Admins group and grant this account read-access permissions on each of the following containers in the forest root domain:</span></span>
    
      - <span data-ttu-id="af7cf-113">ドメイン</span><span class="sxs-lookup"><span data-stu-id="af7cf-113">Domain</span></span>
    
      - <span data-ttu-id="af7cf-114">構成またはシステム</span><span class="sxs-lookup"><span data-stu-id="af7cf-114">Configuration or System</span></span>

<span data-ttu-id="af7cf-115">ドメインの準備またはその他のセットアップ タスクを実行する際に、Enterprise Admins グループのメンバーであるアカウントを使用しない場合は、フォレストのルート内の該当のコンテナーに対する読み取りアクセスを、使用するアカウントに明示的に許可します。</span><span class="sxs-lookup"><span data-stu-id="af7cf-115">If you do not want to use an account that is a member of the Enterprise Admins group to run domain preparation or other Setup tasks, explicitly grant the account you want to use read access on the relevant containers in the forest root.</span></span>

<div>

## <a name="to-give-users-read-access-permissions-on-containers-in-the-forest-root-domain"></a><span data-ttu-id="af7cf-116">フォレストのルート ドメイン内のコンテナーに対する読み取りアクセス許可をユーザーに与えるには</span><span class="sxs-lookup"><span data-stu-id="af7cf-116">To give users read-access permissions on containers in the forest root domain</span></span>

1.  <span data-ttu-id="af7cf-117">フォレストのルート ドメインの Domain Admins グループのメンバーであるアカウントを使用して、このドメインに参加しているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="af7cf-117">Log on to the computer joined to the forest root domain with an account that is a member of the Domain Admins group for the forest root domain.</span></span>

2.  <span data-ttu-id="af7cf-118">フォレストのルート ドメインに対して adsiedit.msc を実行します。</span><span class="sxs-lookup"><span data-stu-id="af7cf-118">Run adsiedit.msc for the forest root domain.</span></span>
    
    <span data-ttu-id="af7cf-119">認証済みユーザーの ACE がドメイン コンテナー、構成コンテナー、またはシステム コンテナーから削除されている場合は、次のステップに従って、そのコンテナーに対する読み取り専用アクセス許可を与える必要があります。</span><span class="sxs-lookup"><span data-stu-id="af7cf-119">If authenticated user ACEs were removed from the Domain, Configuration, or System container, you must grant read-only permissions to the container, as described in the following steps.</span></span>

3.  <span data-ttu-id="af7cf-120">コンテナーを右クリックし、[**プロパティ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="af7cf-120">Right-click the container, and then click **Properties**.</span></span>

4.  <span data-ttu-id="af7cf-121">[**セキュリティ**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="af7cf-121">Click the **Security** tab.</span></span>

5.  <span data-ttu-id="af7cf-122">[**詳細設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="af7cf-122">Click **Advanced**.</span></span>

6.  <span data-ttu-id="af7cf-123">[**アクセス許可**] タブで [**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="af7cf-123">On the **Permissions** tab, click **Add**.</span></span>

7.  <span data-ttu-id="af7cf-124">次の形式を使用して、アクセス許可を受け取るユーザーまたはグループの名前を入力し、 `domain\account name` [ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="af7cf-124">Type the name of the user or group receiving permissions by using the following format: `domain\account name`, and then click **OK**.</span></span>

8.  <span data-ttu-id="af7cf-125">[**オブジェクト**] タブの [**適用先**] で [**このオブジェクトのみ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="af7cf-125">On the **Objects** tab, in **Applies To**, click **This Object Only**.</span></span>

9.  <span data-ttu-id="af7cf-126">[**アクセス許可**] で [**許可**] 列をクリックして、 [**コンテンツの一覧表示**]、[**すべてのプロパティの読み取り**]、および [**読み取りアクセス許可**] を、許可する ACE として選択します。</span><span class="sxs-lookup"><span data-stu-id="af7cf-126">In **Permissions**, select the following Allow ACEs by clicking the **Allow** column: **List Content**, **Read All Properties**, and **Read Permissions**.</span></span>

10. <span data-ttu-id="af7cf-127">[**OK**] を 2 回クリックします。</span><span class="sxs-lookup"><span data-stu-id="af7cf-127">Click **OK** twice.</span></span>

11. <span data-ttu-id="af7cf-128">ステップ 2. でリストアップした該当するすべてのコンテナーについて、上記のステップを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="af7cf-128">Repeat these steps for any of the relevant containers listed in Step 2.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

