---
title: 'Lync Server 2013: 認証済みユーザーのアクセス許可が削除されている'
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
ms.openlocfilehash: 63b9761f96156fdc4dea124d4438cdb8685add26
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722608"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="authenticated-user-permissions-are-removed-in-lync-server-2013"></a><span data-ttu-id="d7852-102">Lync Server 2013 で認証済みユーザーのアクセス許可が削除されている</span><span class="sxs-lookup"><span data-stu-id="d7852-102">Authenticated user permissions are removed in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d7852-103">_**最終更新日:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="d7852-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="d7852-104">ロックダウンされた Active Directory 環境では、認証されたユーザーアクセス制御エントリ (Ace) は、ユーザー、構成、システム、組織単位 (Ou)、ユーザー、コンピューターの場所など、既定の Active Directory コンテナーから削除されます。オブジェクトが保存されます。</span><span class="sxs-lookup"><span data-stu-id="d7852-104">In a locked-down Active Directory environment, authenticated user access control entries (ACEs) are removed from the default Active Directory containers, including the Users, Configuration or System, and organizational units (OUs) where User and Computer objects are stored.</span></span> <span data-ttu-id="d7852-105">認証済みユーザー Ace を削除すると、Active Directory 情報への読み取りアクセスができなくなります。</span><span class="sxs-lookup"><span data-stu-id="d7852-105">Removing authenticated user ACEs prevents read access to Active Directory information.</span></span> <span data-ttu-id="d7852-106">ただし、Ace を削除すると、ユーザーがドメインの準備を実行できるように、これらのコンテナーの読み取りアクセス許可に依存するため、Lync Server 2013 の問題が発生します。</span><span class="sxs-lookup"><span data-stu-id="d7852-106">However, removing the ACEs creates issues for Lync Server 2013 because it depends on read permissions to these containers to allow users to run domain preparation.</span></span>

<span data-ttu-id="d7852-107">この状況では、ドメインの準備、サーバーのアクティブ化、プールの作成を実行するために必要な Domain Admins グループのメンバーシップが、既定のコンテナーに格納されている Active Directory 情報への読み取りアクセス許可を付与することはなくなりました。</span><span class="sxs-lookup"><span data-stu-id="d7852-107">In this situation, membership in the Domain Admins group, which is required to run domain preparation, server activation, and pool creation, no longer grants read access to Active Directory information stored in the default containers.</span></span> <span data-ttu-id="d7852-108">必要なフォレストの準備手順が完了していることを確認するには、フォレストルートドメイン内のさまざまなコンテナーの読み取りアクセス許可を手動で付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d7852-108">You must manually grant read-access permissions on various containers in the forest root domain to check that the prerequisite forest preparation procedure is complete.</span></span>

<span data-ttu-id="d7852-109">フォレスト以外のルートドメインでドメインの準備、サーバーのアクティブ化、またはプールの作成を実行できるようにするには、次のオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="d7852-109">To enable a user to run domain preparation, server activation, or pool creation on any non-forest root domain, you have the following options:</span></span>

  - <span data-ttu-id="d7852-110">エンタープライズ管理者グループのメンバーであるアカウントを使用して、ドメインの準備を実行します。</span><span class="sxs-lookup"><span data-stu-id="d7852-110">Use an account that is a member of the Enterprise Admins group to run domain preparation.</span></span>

  - <span data-ttu-id="d7852-111">Domain Admins グループのメンバーであるアカウントを使用し、フォレストルートドメイン内の次の各コンテナーで、このアカウントに読み取りアクセス許可を付与します。</span><span class="sxs-lookup"><span data-stu-id="d7852-111">Use an account that is a member of the Domain Admins group and grant this account read-access permissions on each of the following containers in the forest root domain:</span></span>
    
      - <span data-ttu-id="d7852-112">Domain</span><span class="sxs-lookup"><span data-stu-id="d7852-112">Domain</span></span>
    
      - <span data-ttu-id="d7852-113">構成またはシステム</span><span class="sxs-lookup"><span data-stu-id="d7852-113">Configuration or System</span></span>

<span data-ttu-id="d7852-114">エンタープライズ管理者グループのメンバーであるアカウントを使用して、ドメインの準備またはその他のセットアップタスクを実行しない場合は、フォレストルートの関連するコンテナーで読み取りアクセスを使用するアカウントを明示的に付与します。</span><span class="sxs-lookup"><span data-stu-id="d7852-114">If you do not want to use an account that is a member of the Enterprise Admins group to run domain preparation or other Setup tasks, explicitly grant the account you want to use read access on the relevant containers in the forest root.</span></span>

<div>

## <a name="to-give-users-read-access-permissions-on-containers-in-the-forest-root-domain"></a><span data-ttu-id="d7852-115">フォレストのルートドメインのコンテナーの読み取りアクセス許可をユーザーに付与するには</span><span class="sxs-lookup"><span data-stu-id="d7852-115">To give users read-access permissions on containers in the forest root domain</span></span>

1.  <span data-ttu-id="d7852-116">フォレストルートドメインの Domain Admins グループのメンバーであるアカウントで、フォレストルートドメインに参加しているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="d7852-116">Log on to the computer joined to the forest root domain with an account that is a member of the Domain Admins group for the forest root domain.</span></span>

2.  <span data-ttu-id="d7852-117">フォレストルートドメインに対して adsiedit を実行します。</span><span class="sxs-lookup"><span data-stu-id="d7852-117">Run adsiedit.msc for the forest root domain.</span></span>
    
    <span data-ttu-id="d7852-118">認証済みユーザー Ace がドメイン、構成、またはシステムコンテナーから削除された場合は、次の手順で説明するように、コンテナーに読み取り専用のアクセス許可を付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d7852-118">If authenticated user ACEs were removed from the Domain, Configuration, or System container, you must grant read-only permissions to the container, as described in the following steps.</span></span>

3.  <span data-ttu-id="d7852-119">コンテナーを右クリックし、[**プロパティ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d7852-119">Right-click the container, and then click **Properties**.</span></span>

4.  <span data-ttu-id="d7852-120">[**セキュリティ**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d7852-120">Click the **Security** tab.</span></span>

5.  <span data-ttu-id="d7852-121">[**詳細設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d7852-121">Click **Advanced**.</span></span>

6.  <span data-ttu-id="d7852-122">[**権限**] タブの [**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d7852-122">On the **Permissions** tab, click **Add**.</span></span>

7.  <span data-ttu-id="d7852-123">次の形式を使用して、アクセス許可を付与するユーザーまたは`domain\account name`グループの名前を入力し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d7852-123">Type the name of the user or group receiving permissions by using the following format: `domain\account name`, and then click **OK**.</span></span>

8.  <span data-ttu-id="d7852-124">[**オブジェクト**] タブの [**適用**対象] で、[**このオブジェクトのみ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d7852-124">On the **Objects** tab, in **Applies To**, click **This Object Only**.</span></span>

9.  <span data-ttu-id="d7852-125">[**権限**] で、[**許可する**列:**リストコンテンツ**]、[すべての**プロパティの読み取り**]、[**アクセス許可の読み取り**] の順にクリックして、次の許可 ace を選択します。</span><span class="sxs-lookup"><span data-stu-id="d7852-125">In **Permissions**, select the following Allow ACEs by clicking the **Allow** column: **List Content**, **Read All Properties**, and **Read Permissions**.</span></span>

10. <span data-ttu-id="d7852-126">[ **OK]** を2回クリックします。</span><span class="sxs-lookup"><span data-stu-id="d7852-126">Click **OK** twice.</span></span>

11. <span data-ttu-id="d7852-127">手順2に示されている関連コンテナーについて、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="d7852-127">Repeat these steps for any of the relevant containers listed in Step 2.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

