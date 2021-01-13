---
title: Skype for Business Server 2015 での常設チャット管理者の作成
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5c3892e4-ebae-453e-8107-f42ec0436ea2
description: '概要: このトピックでは、常設チャット サーバー管理者の役割を作成して、Skype for Business Server 2015 で常設チャット サービスの初期構成と管理を有効にする方法について説明します。'
ms.openlocfilehash: eea989b0284353e193ebf99a0be99b2d0811e532
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802097"
---
# <a name="create-a-persistent-chat-administrator-in-skype-for-business-server-2015"></a><span data-ttu-id="66a9f-103">Skype for Business Server 2015 での常設チャット管理者の作成</span><span class="sxs-lookup"><span data-stu-id="66a9f-103">Create a Persistent Chat administrator in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="66a9f-104">**概要:** このトピックでは、Skype for Business Server 2015 で常設チャット サービスの初期構成と管理を有効にする常設チャット サーバー管理者の役割を作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="66a9f-104">**Summary:** Read this topic to learn how to create a Persistent Chat Server administrator role to enable initial configuration and management of Persistent Chat services in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="66a9f-105">Skype for Business Server では、特定のタスクを実行するユーザーを 1 つ以上の特定のグループのメンバーとして割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="66a9f-105">In Skype for Business Server, users who perform specific tasks must be assigned as members of one or more specific groups.</span></span> <span data-ttu-id="66a9f-106">Role-Basedアクセス制御 (RBAC) は、定義済みの Skype for Business Server 管理者の役割にユーザーを割り当て、特権を付与するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="66a9f-106">Role-Based Access Control (RBAC) is used to grant privileges by assigning users to predefined Skype for Business Server administrative roles.</span></span> <span data-ttu-id="66a9f-107">これらの役割は、Active Directory ドメイン サービスのユニバーサル セキュリティ グループに対応しています。</span><span class="sxs-lookup"><span data-stu-id="66a9f-107">These roles correspond to universal security groups in Active Directory Domain Services.</span></span> <span data-ttu-id="66a9f-108">常設チャット管理者セキュリティ グループ CsPersistentChatAdministrator のメンバーには、Skype for Business Server 管理シェルまたは Skype for Business Server コントロール パネルを使用して実行できる常設チャット サーバー コマンドレットへのアクセス権が付与されます。</span><span class="sxs-lookup"><span data-stu-id="66a9f-108">Members of the Persistent Chat Administrator security group, CsPersistentChatAdministrator, are granted access to the Persistent Chat Server cmdlets, which can be executed using either the Skype for Business Server Management Shell or the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="66a9f-109">常設チャット サーバーを構成および管理する前に、適切なユーザー権限とアクセス許可が設定され、常設チャット管理者として機能するユーザーが常設チャット管理者セキュリティ グループに追加されます。</span><span class="sxs-lookup"><span data-stu-id="66a9f-109">Before configuring and administering Persistent Chat Server, be sure that the appropriate user rights and permissions are in place, and that any users who will act as Persistent Chat administrators are added to the Persistent Chat Administrator security group.</span></span>
  
> [!NOTE] 
> <span data-ttu-id="66a9f-110">常設チャットは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="66a9f-110">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="66a9f-111">Teams でも同じ機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="66a9f-111">The same functionality is available in Teams.</span></span> <span data-ttu-id="66a9f-112">詳細については、「Microsoft Teams のアップグレード [の開始」を参照してください](/microsoftteams/upgrade-start-here)。</span><span class="sxs-lookup"><span data-stu-id="66a9f-112">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="66a9f-113">常設チャットを使用する必要がある場合は、この機能を必要とするユーザーを Teams に移行するか、Skype for Business Server 2015 を引き続き使用するかのどちらかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="66a9f-113">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span>

## <a name="create-a-persistent-chat-administrator"></a><span data-ttu-id="66a9f-114">常設チャット管理者の作成</span><span class="sxs-lookup"><span data-stu-id="66a9f-114">Create a Persistent Chat administrator</span></span>

<span data-ttu-id="66a9f-115">常設チャット管理者セキュリティ グループ CsPersistentChatAdministrator にユーザーを追加するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="66a9f-115">To add a user to the Persistent Chat Administrator security group, CsPersistentChatAdministrator, perform the following steps:</span></span>
  
1. <span data-ttu-id="66a9f-116">Active Directory グループのメンバーシップを変更するアクセス許可を持つアカウントを使用して、Active Directory ユーザーとコンピューターがインストールされているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="66a9f-116">Using an account that has permission to modify the membership of an Active Directory group, log on to a computer where Active Directory Users and Computers have been installed.</span></span>
    
2. <span data-ttu-id="66a9f-117">[スタート] をクリックし、[すべてのプログラム] をクリックし、[管理ツール] をクリックし、[Active Directory ユーザーおよびコンピューター] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="66a9f-117">Click Start, click All Programs, click Administrative Tools, and then click Active Directory Users and Computers.</span></span>
    
3. <span data-ttu-id="66a9f-118">Active Directory ユーザーおよびコンピューターで、自分のドメインの名前を展開し、[Users] コンテナーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="66a9f-118">In Active Directory Users and Computers, expand the name of your domain and click the Users container.</span></span>
    
4. <span data-ttu-id="66a9f-119">セキュリティ グループ CsPersistentChatAdministrator を右クリックし、[プロパティ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="66a9f-119">Right-click the security group CsPersistentChatAdministrator, and then click Properties.</span></span>
    
5. <span data-ttu-id="66a9f-120">[プロパティ] ダイアログ ボックスの [メンバー] タブで、[追加] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="66a9f-120">In the Properties dialog box, on the Members tab, click Add.</span></span>
    
6. <span data-ttu-id="66a9f-121">[ユーザー、コンピューター、連絡先、またはグループの選択] ダイアログ ボックスで、グループに追加するユーザーのユーザー名または表示名を [選択するオブジェクト名を入力してください] ボックスに入力し、[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="66a9f-121">In the Select Users, Computers, Contact, or Groups dialog box, type the user name or display name of the user to be added to the group in the Enter the object names to select box and then click OK.</span></span>
    
7. <span data-ttu-id="66a9f-122">[プロパティ] ダイアログ ボックスで [OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="66a9f-122">In the Properties dialog box, click OK.</span></span>
    

