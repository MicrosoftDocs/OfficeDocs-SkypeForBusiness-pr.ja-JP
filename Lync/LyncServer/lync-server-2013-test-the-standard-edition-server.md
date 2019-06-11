---
title: 'Lync Server 2013: Standard Edition サーバーのテスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test the Standard Edition server
ms:assetid: b6ef67bb-9665-43e4-b8b3-eac8898eebf6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412890(v=OCS.15)
ms:contentKeyID: 48185220
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a960451ebdd1e6e8728bf3b6c7df6e267c49c3f8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848505"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-the-standard-edition-server-in-lync-server-2013"></a><span data-ttu-id="9555b-102">Lync Server 2013 での Standard Edition サーバーのテスト</span><span class="sxs-lookup"><span data-stu-id="9555b-102">Test the Standard Edition server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9555b-103">_**最終更新日:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="9555b-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="9555b-104">次の手順では、Standard Edition サーバーの展開をテストする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9555b-104">The following procedure describes how to test the deployment of a Standard Edition server.</span></span>

<div>

## <a name="to-test-the-deployment-of-a-standard-edition-server"></a><span data-ttu-id="9555b-105">Standard Edition サーバーの展開をテストするには</span><span class="sxs-lookup"><span data-stu-id="9555b-105">To test the deployment of a Standard Edition Server</span></span>

1.  <span data-ttu-id="9555b-106">Active Directory コンピューターとユーザーを使用して、Lync Server 2013 展開用の管理者ロールの Active Directory ユーザーオブジェクト (Lync Server コントロールパネルがインストールされている場合) を**csadministrator**グループに追加します。</span><span class="sxs-lookup"><span data-stu-id="9555b-106">Use Active Directory Computers and Users to add the Active Directory user object of the administrator role for the Lync Server 2013 deployment (on which Lync Server Control Panel is installed) to the **CSAdministrator** group.</span></span>

2.  <span data-ttu-id="9555b-107">ユーザーオブジェクトが現在ログオンしている場合は、ログオフしてから再びログオンして、新しいグループの割り当てを登録します。</span><span class="sxs-lookup"><span data-stu-id="9555b-107">If the user object is currently logged on, log off and then log on again to register the new group assignment.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9555b-108">ユーザーアカウントを、Lync Server 2013、Standard Edition を実行しているサーバーのローカル管理者にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="9555b-108">The user account cannot be the local administrator of the server running Lync Server 2013, Standard Edition.</span></span> <span data-ttu-id="9555b-109">適切なユーザーとグループを CsAdministors グループに追加していない場合、Lync Server 2013 コントロールパネルを開くときにエラーが発生します。これは、"承認されていません。ロールベースのアクセス制御 (RBAC) 認証エラーによりアクセスが拒否されました" というメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9555b-109">If you do not add the appropriate users and groups to the CsAdministors group, you will receive an error when opening Lync Server 2013 Control Panel, which states that “Unauthorized: Access is denied due to a role-based access control (RBAC) authorization failure.”</span></span>

    
    </div>

3.  <span data-ttu-id="9555b-110">管理者アカウントを使用して、Lync Server コントロールパネルがインストールされているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="9555b-110">Use the administrative account to log on to the computer where Lync Server Control Panel is installed.</span></span>

4.  <span data-ttu-id="9555b-111">Lync Server コントロールパネルを起動し、メッセージが表示されたら、資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="9555b-111">Start Lync Server Control Panel and provide credentials, if prompted.</span></span> <span data-ttu-id="9555b-112">Lync Server 2013 コントロールパネルに展開情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9555b-112">Lync Server 2013 Control Panel displays deployment information.</span></span>

5.  <span data-ttu-id="9555b-113">左側のナビゲーションバーで、[**トポロジ**] をクリックし、サービスの状態が緑色の矢印が付いたコンピューターのアイコンであり、展開されてオンラインになった Lync server の各役割の横に緑色のチェックマークが付いていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9555b-113">In the left navigation bar, click **Topology**, and then confirm that the service status is a computer icon with a green arrow and there is a green check mark next to each Lync Server server role that has been deployed and brought online.</span></span>

6.  <span data-ttu-id="9555b-114">左側のナビゲーションバーで [**ユーザー**] をクリックし、Lync Server 2013 の2人のユーザーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="9555b-114">In the left navigation bar, click **Users**, and then enable the two users for Lync Server 2013.</span></span>

7.  <span data-ttu-id="9555b-115">1人のユーザーをドメインに参加しているコンピューターに、もう一方のユーザーがドメイン内の別のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="9555b-115">Log one user on to a computer that is joined to the domain, and the other user on to another computer in the domain.</span></span>

8.  <span data-ttu-id="9555b-116">2台の各クライアントコンピューターに Lync Server 2013 をインストールして、両方のユーザーが Lync Server 2013 にサインインして、互いにインスタントメッセージを送信できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9555b-116">Install Lync Server 2013 on each of the two client computers, and then verify that both users can sign in to Lync Server 2013 and can send instant messages to each other.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9555b-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="9555b-117">See Also</span></span>


[<span data-ttu-id="9555b-118">Lync Server 2013 でのクライアントとデバイスの展開</span><span class="sxs-lookup"><span data-stu-id="9555b-118">Deploying clients and devices in Lync Server 2013</span></span>](lync-server-2013-deploying-clients-and-devices.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

