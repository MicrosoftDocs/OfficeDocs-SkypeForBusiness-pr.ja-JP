---
title: Skype for Business Server 2015 での常設チャット管理者の作成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5c3892e4-ebae-453e-8107-f42ec0436ea2
description: '概要: このトピックでは、Skype for Business Server 2015 で常設チャットサービスの初期構成と管理を有効にするための、常設チャットサーバー管理者の役割を作成する方法について説明します。'
ms.openlocfilehash: 987183b8ca5cc32e2888040b43d61e5d6fcac09b
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41794105"
---
# <a name="create-a-persistent-chat-administrator-in-skype-for-business-server-2015"></a><span data-ttu-id="82aeb-103">Skype for Business Server 2015 での常設チャット管理者の作成</span><span class="sxs-lookup"><span data-stu-id="82aeb-103">Create a Persistent Chat administrator in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="82aeb-104">**概要:** このトピックでは、Skype for Business Server 2015 の常設チャットサービスの初期構成と管理を有効にするための、常設チャットサーバー管理者の役割を作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="82aeb-104">**Summary:** Read this topic to learn how to create a Persistent Chat Server administrator role to enable initial configuration and management of Persistent Chat services in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="82aeb-105">Skype for Business Server では、特定のタスクを実行するユーザーは、1つ以上の特定のグループのメンバーとして割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="82aeb-105">In Skype for Business Server, users who perform specific tasks must be assigned as members of one or more specific groups.</span></span> <span data-ttu-id="82aeb-106">ロールベースのアクセス制御 (RBAC) を使用して、事前定義された Skype for Business Server の管理者ロールにユーザーを割り当てることによって特権を付与します。</span><span class="sxs-lookup"><span data-stu-id="82aeb-106">Role-Based Access Control (RBAC) is used to grant privileges by assigning users to predefined Skype for Business Server administrative roles.</span></span> <span data-ttu-id="82aeb-107">これらの役割は、Active Directory ドメイン サービスのユニバーサル セキュリティ グループに対応します。</span><span class="sxs-lookup"><span data-stu-id="82aeb-107">These roles correspond to universal security groups in Active Directory Domain Services.</span></span> <span data-ttu-id="82aeb-108">常設チャット管理者セキュリティグループ CsPersistentChatAdministrator のメンバーには、Skype for Business Server 管理シェルまたは Skype for Business を使用して実行できる常設チャットサーバーコマンドレットへのアクセスが許可されます。サーバーコントロールパネル。</span><span class="sxs-lookup"><span data-stu-id="82aeb-108">Members of the Persistent Chat Administrator security group, CsPersistentChatAdministrator, are granted access to the Persistent Chat Server cmdlets, which can be executed using either the Skype for Business Server Management Shell or the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="82aeb-109">常設チャット サーバーを構成および管理する前に、適切なユーザー権限およびアクセス許可があること、および常設チャット管理者として活動するユーザーが常設チャット管理者セキュリティ グループに追加されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="82aeb-109">Before configuring and administering Persistent Chat Server, be sure that the appropriate user rights and permissions are in place, and that any users who will act as Persistent Chat administrators are added to the Persistent Chat Administrator security group.</span></span>
  
> [!NOTE] 
> <span data-ttu-id="82aeb-110">常設チャットは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="82aeb-110">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="82aeb-111">Teams でも同じ機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="82aeb-111">The same functionality is available in Teams.</span></span> <span data-ttu-id="82aeb-112">詳細については、「 [Microsoft Teams のアップグレードの](/microsoftteams/upgrade-start-here)概要」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82aeb-112">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="82aeb-113">常設チャットを使用する必要がある場合は、この機能が必要なユーザーをチームに移行するか、Skype for Business Server 2015 を使い続けるかのいずれかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="82aeb-113">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span>

## <a name="create-a-persistent-chat-administrator"></a><span data-ttu-id="82aeb-114">Create a Persistent Chat administrator</span><span class="sxs-lookup"><span data-stu-id="82aeb-114">Create a Persistent Chat administrator</span></span>

<span data-ttu-id="82aeb-115">常設チャット管理者セキュリティグループ CsPersistentChatAdministrator にユーザーを追加するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="82aeb-115">To add a user to the Persistent Chat Administrator security group, CsPersistentChatAdministrator, perform the following steps:</span></span>
  
1. <span data-ttu-id="82aeb-116">Active Directory グループのメンバーシップを変更できるアクセス許可を持つアカウントを使用して、Active Directory ユーザーおよびコンピューターがインストールされているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="82aeb-116">Using an account that has permission to modify the membership of an Active Directory group, log on to a computer where Active Directory Users and Computers have been installed.</span></span>
    
2. <span data-ttu-id="82aeb-117">[スタート]、[すべてのプログラム]、[管理ツール]、[Active Directory ユーザーとコンピューター] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="82aeb-117">Click Start, click All Programs, click Administrative Tools, and then click Active Directory Users and Computers.</span></span>
    
3. <span data-ttu-id="82aeb-118">[Active Directory ユーザーとコンピューター] で、自分のドメインの名前を展開し、[Users] コンテナーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="82aeb-118">In Active Directory Users and Computers, expand the name of your domain and click the Users container.</span></span>
    
4. <span data-ttu-id="82aeb-119">セキュリティ グループの [CsPersistentChatAdministrator] を右クリックし、[プロパティ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="82aeb-119">Right-click the security group CsPersistentChatAdministrator, and then click Properties.</span></span>
    
5. <span data-ttu-id="82aeb-120">[プロパティ] ダイアログ ボックスの [メンバー] タブで、[追加] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="82aeb-120">In the Properties dialog box, on the Members tab, click Add.</span></span>
    
6. <span data-ttu-id="82aeb-121">[ユーザー、コンピューター、連絡先、またはグループの選択] ダイアログ ボックスの [選択するオブジェクト名を入力してください] ボックスに、グループに追加するユーザーの名前または表示名を入力し、[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="82aeb-121">In the Select Users, Computers, Contact, or Groups dialog box, type the user name or display name of the user to be added to the group in the Enter the object names to select box and then click OK.</span></span>
    
7. <span data-ttu-id="82aeb-122">[プロパティ] ダイアログ ボックスで [OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="82aeb-122">In the Properties dialog box, click OK.</span></span>
    

