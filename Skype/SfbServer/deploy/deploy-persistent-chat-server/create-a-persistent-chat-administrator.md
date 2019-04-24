---
title: Skype for Business Server 2015 での常設チャット管理者の作成
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5c3892e4-ebae-453e-8107-f42ec0436ea2
description: '概要: は、初期構成およびビジネス サーバー 2015 の Skype での永続的なチャット サービスの管理を有効にするのには永続的なチャット サーバー管理者ロールを作成する方法の詳細については、このトピックを読みます。'
ms.openlocfilehash: fb8a222f65f6fe579d3600df15a53bb84f65de66
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32225343"
---
# <a name="create-a-persistent-chat-administrator-in-skype-for-business-server-2015"></a><span data-ttu-id="5a60b-103">Skype for Business Server 2015 での常設チャット管理者の作成</span><span class="sxs-lookup"><span data-stu-id="5a60b-103">Create a Persistent Chat administrator in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="5a60b-104">**の概要:** 初期構成およびビジネス サーバー 2015 の Skype での永続的なチャット サービスの管理を有効にするのには永続的なチャット サーバー管理者ロールを作成する方法の詳細については、このトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a60b-104">**Summary:** Read this topic to learn how to create a Persistent Chat Server administrator role to enable initial configuration and management of Persistent Chat services in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="5a60b-105">ビジネス サーバーの Skype は、特定のタスクを実行するユーザーを 1 つまたは複数の特定のグループのメンバーとして割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a60b-105">In Skype for Business Server, users who perform specific tasks must be assigned as members of one or more specific groups.</span></span> <span data-ttu-id="5a60b-106">ビジネス サーバー管理者の役割の定義済みの Skype ユーザーに割り当てることによって権限を付与する役割に基づくアクセス制御 (RBAC) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="5a60b-106">Role-Based Access Control (RBAC) is used to grant privileges by assigning users to predefined Skype for Business Server administrative roles.</span></span> <span data-ttu-id="5a60b-107">これらの役割は、Active Directory ドメイン サービスのユニバーサル セキュリティ グループに対応します。</span><span class="sxs-lookup"><span data-stu-id="5a60b-107">These roles correspond to universal security groups in Active Directory Domain Services.</span></span> <span data-ttu-id="5a60b-108">、CsPersistentChatAdministrator、永続的なチャット管理者セキュリティ グループのメンバーは、永続的なチャット サーバーのコマンドレット、またはを使用してビジネス サーバー管理シェルの Skype、Skype ビジネスを実行することへのアクセスを許可は、サーバーのコントロール パネルです。</span><span class="sxs-lookup"><span data-stu-id="5a60b-108">Members of the Persistent Chat Administrator security group, CsPersistentChatAdministrator, are granted access to the Persistent Chat Server cmdlets, which can be executed using either the Skype for Business Server Management Shell or the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="5a60b-109">常設チャット サーバーを構成および管理する前に、適切なユーザー権限およびアクセス許可があること、および常設チャット管理者として活動するユーザーが常設チャット管理者セキュリティ グループに追加されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="5a60b-109">Before configuring and administering Persistent Chat Server, be sure that the appropriate user rights and permissions are in place, and that any users who will act as Persistent Chat administrators are added to the Persistent Chat Administrator security group.</span></span>
  
> [!NOTE] 
> <span data-ttu-id="5a60b-110">永続的なチャットですがビジネス サーバー 2015 の Skype で利用可能なビジネス サーバー 2019 の Skype でサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="5a60b-110">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="5a60b-111">同じ機能は、チームで使用できます。</span><span class="sxs-lookup"><span data-stu-id="5a60b-111">The same functionality is available in Teams.</span></span> <span data-ttu-id="5a60b-112">詳細については、[マイクロソフトのチームにビジネス用の Skype からの旅](/microsoftteams/journey-skypeforbusiness-teams)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a60b-112">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="5a60b-113">永続的なチャットを使用する場合は、選択肢は、いずれかをチームでは、この機能を必要とするユーザーを移行するまたはビジネス サーバー 2015 の Skype を使用し続ける。</span><span class="sxs-lookup"><span data-stu-id="5a60b-113">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span>

## <a name="create-a-persistent-chat-administrator"></a><span data-ttu-id="5a60b-114">Create a Persistent Chat administrator</span><span class="sxs-lookup"><span data-stu-id="5a60b-114">Create a Persistent Chat administrator</span></span>

<span data-ttu-id="5a60b-115">CsPersistentChatAdministrator、永続的なチャット管理者セキュリティ グループにユーザーを追加するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="5a60b-115">To add a user to the Persistent Chat Administrator security group, CsPersistentChatAdministrator, perform the following steps:</span></span>
  
1. <span data-ttu-id="5a60b-116">Active Directory グループのメンバーシップを変更できるアクセス許可を持つアカウントを使用して、Active Directory ユーザーおよびコンピューターがインストールされているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="5a60b-116">Using an account that has permission to modify the membership of an Active Directory group, log on to a computer where Active Directory Users and Computers have been installed.</span></span>
    
2. <span data-ttu-id="5a60b-117">[スタート]、[すべてのプログラム]、[管理ツール]、[Active Directory ユーザーとコンピューター] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="5a60b-117">Click Start, click All Programs, click Administrative Tools, and then click Active Directory Users and Computers.</span></span>
    
3. <span data-ttu-id="5a60b-118">[Active Directory ユーザーとコンピューター] で、自分のドメインの名前を展開し、[Users] コンテナーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="5a60b-118">In Active Directory Users and Computers, expand the name of your domain and click the Users container.</span></span>
    
4. <span data-ttu-id="5a60b-119">セキュリティ グループの [CsPersistentChatAdministrator] を右クリックし、[プロパティ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5a60b-119">Right-click the security group CsPersistentChatAdministrator, and then click Properties.</span></span>
    
5. <span data-ttu-id="5a60b-120">[プロパティ] ダイアログ ボックスの [メンバー] タブで、[追加] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5a60b-120">In the Properties dialog box, on the Members tab, click Add.</span></span>
    
6. <span data-ttu-id="5a60b-121">[ユーザー、コンピューター、連絡先、またはグループの選択] ダイアログ ボックスの [選択するオブジェクト名を入力してください] ボックスに、グループに追加するユーザーの名前または表示名を入力し、[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5a60b-121">In the Select Users, Computers, Contact, or Groups dialog box, type the user name or display name of the user to be added to the group in the Enter the object names to select box and then click OK.</span></span>
    
7. <span data-ttu-id="5a60b-122">[プロパティ] ダイアログ ボックスで [OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5a60b-122">In the Properties dialog box, click OK.</span></span>
    

