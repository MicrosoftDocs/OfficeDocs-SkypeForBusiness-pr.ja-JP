---
title: 'Lync Server 2013: Standard Edition サーバーのテスト'
description: 'Lync Server 2013: Standard Edition サーバーをテストします。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test the Standard Edition server
ms:assetid: b6ef67bb-9665-43e4-b8b3-eac8898eebf6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412890(v=OCS.15)
ms:contentKeyID: 48185220
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 35dc13fc01979cc8b293d0647a7886b7d65d7669
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576013"
---
# <a name="test-the-standard-edition-server-in-lync-server-2013"></a><span data-ttu-id="034d2-103">Lync Server 2013 での Standard Edition サーバーのテスト</span><span class="sxs-lookup"><span data-stu-id="034d2-103">Test the Standard Edition server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="034d2-104">_**トピックの最終更新日:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="034d2-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="034d2-105">次の手順では、Standard Edition サーバーの展開をテストする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="034d2-105">The following procedure describes how to test the deployment of a Standard Edition server.</span></span>

<div>

## <a name="to-test-the-deployment-of-a-standard-edition-server"></a><span data-ttu-id="034d2-106">Standard Edition サーバーの展開をテストするには</span><span class="sxs-lookup"><span data-stu-id="034d2-106">To test the deployment of a Standard Edition Server</span></span>

1.  <span data-ttu-id="034d2-107">[Active Directory コンピューターとユーザー] を使用して、Lync Server 2013 展開 (Lync Server コントロールパネルがインストールされている) の管理者ロールの Active Directory ユーザーオブジェクトを **Csadministrator** グループに追加します。</span><span class="sxs-lookup"><span data-stu-id="034d2-107">Use Active Directory Computers and Users to add the Active Directory user object of the administrator role for the Lync Server 2013 deployment (on which Lync Server Control Panel is installed) to the **CSAdministrator** group.</span></span>

2.  <span data-ttu-id="034d2-108">ユーザー オブジェクトが現在ログオンしている場合は、ログオフしてから再度ログオンし、新しいグループ割り当てを登録します。</span><span class="sxs-lookup"><span data-stu-id="034d2-108">If the user object is currently logged on, log off and then log on again to register the new group assignment.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="034d2-109">ユーザーアカウントは、Lync Server 2013 Standard Edition を実行しているサーバーのローカル管理者になることはできません。</span><span class="sxs-lookup"><span data-stu-id="034d2-109">The user account cannot be the local administrator of the server running Lync Server 2013, Standard Edition.</span></span> <span data-ttu-id="034d2-110">CsAdministors グループに適切なユーザーとグループを追加しないと、Lync Server 2013 コントロールパネルを開くときに、"権限のない: 役割ベースのアクセス制御 (RBAC) の承認エラーによりアクセスが拒否されました" というエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="034d2-110">If you do not add the appropriate users and groups to the CsAdministors group, you will receive an error when opening Lync Server 2013 Control Panel, which states that “Unauthorized: Access is denied due to a role-based access control (RBAC) authorization failure.”</span></span>

    
    </div>

3.  <span data-ttu-id="034d2-111">管理者アカウントを使用して、Lync Server コントロールパネルがインストールされているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="034d2-111">Use the administrative account to log on to the computer where Lync Server Control Panel is installed.</span></span>

4.  <span data-ttu-id="034d2-112">メッセージが表示されたら、Lync Server コントロールパネルを起動し、資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="034d2-112">Start Lync Server Control Panel and provide credentials, if prompted.</span></span> <span data-ttu-id="034d2-113">Lync Server 2013 コントロールパネルに展開情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="034d2-113">Lync Server 2013 Control Panel displays deployment information.</span></span>

5.  <span data-ttu-id="034d2-114">左側のナビゲーションバーで [ **トポロジ**] をクリックし、サービスの状態が緑色の矢印が表示されているコンピューターのアイコンになっており、展開済みでオンラインになっている各 Lync server サーバーの役割の横に緑のチェックマークが表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="034d2-114">In the left navigation bar, click **Topology**, and then confirm that the service status is a computer icon with a green arrow and there is a green check mark next to each Lync Server server role that has been deployed and brought online.</span></span>

6.  <span data-ttu-id="034d2-115">左側のナビゲーションバーで [ **ユーザー**] をクリックし、Lync Server 2013 の2人のユーザーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="034d2-115">In the left navigation bar, click **Users**, and then enable the two users for Lync Server 2013.</span></span>

7.  <span data-ttu-id="034d2-116">1 人のユーザーがドメインに参加しているコンピューターにログオンし、もう 1 人のユーザーがドメイン内の別のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="034d2-116">Log one user on to a computer that is joined to the domain, and the other user on to another computer in the domain.</span></span>

8.  <span data-ttu-id="034d2-117">2台の各クライアントコンピューターに Lync Server 2013 をインストールしてから、両方のユーザーが Lync Server 2013 にサインインして、互いにインスタントメッセージを送信できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="034d2-117">Install Lync Server 2013 on each of the two client computers, and then verify that both users can sign in to Lync Server 2013 and can send instant messages to each other.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="034d2-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="034d2-118">See Also</span></span>


[<span data-ttu-id="034d2-119">Lync Server 2013 でのクライアントとデバイスの展開</span><span class="sxs-lookup"><span data-stu-id="034d2-119">Deploying clients and devices in Lync Server 2013</span></span>](lync-server-2013-deploying-clients-and-devices.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

