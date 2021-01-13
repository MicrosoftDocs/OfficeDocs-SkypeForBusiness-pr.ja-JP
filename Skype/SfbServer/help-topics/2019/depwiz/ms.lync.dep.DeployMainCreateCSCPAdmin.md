---
title: Skype for Business Server コントロール パネル管理者の作成
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainCreateCSCPAdmin
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 3312926a-4671-4030-bb92-90ac24c778dd
ROBOTS: NOINDEX, NOFOLLOW
description: Skype for Business Server へのアクセスを許可するには、次の操作を行います。
ms.openlocfilehash: cb1449aa4fcca534e01b4d8a47a7ac9c39cd64c7
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824967"
---
# <a name="create-skype-for-business-server-control-panel-administrators"></a><span data-ttu-id="32a29-103">Skype for Business Server コントロール パネル管理者の作成</span><span class="sxs-lookup"><span data-stu-id="32a29-103">Create Skype for Business Server Control Panel Administrators</span></span>
 
<span data-ttu-id="32a29-104">Skype for Business Server へのアクセスを許可するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="32a29-104">To grant access to the Skype for Business Server, do the following:</span></span>
  
1. <span data-ttu-id="32a29-105">Domain Admins グループまたは RTCUniversalServerAdmins グループのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="32a29-105">Log on as a member of the Domain Admins group or the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="32a29-106">[**Active Directory ユーザーとコンピューター**] を開き、ドメインを展開して [**ユーザー**] コンテナーを右クリックし、[**プロパティ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="32a29-106">Open **Active Directory Users and Computers**, expand your domain, right-click the **Users** container, and then click **Properties**.</span></span>
    
3. <span data-ttu-id="32a29-107">[**CSAdministrator のプロパティ**] で、[**メンバー**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="32a29-107">In **CSAdministrator Properties**, click the **Members** tab.</span></span>
    
4. <span data-ttu-id="32a29-p101">[メンバー] タブで [**追加**] をクリックします。[**ユーザー、連絡先、コンピューター、サービス アカウント、またはグループの選択**] で、[**選択するオブジェクト名を入力してください**] を見つけます。CSAdministrators グループに追加するユーザー名またはグループ名を入力します。[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="32a29-p101">On the Members tab, click **Add**. In **Select Users, Contacts, Computers, Service Accounts, or Groups**, locate the **Enter the object names to select**. Type the user name(s) or group name(s) to add to the group CSAdministrators. Click **OK**.</span></span>
    
5. <span data-ttu-id="32a29-p102">[メンバー] タブで、選択したユーザーまたはグループが表示されていることを確認します。[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="32a29-p102">On the Members tab, confirm that the users or groups that you selected are present. Click **OK**.</span></span>
    
> [!TIP]
> <span data-ttu-id="32a29-114">Skype for Business Server コントロール パネルは、役割ベースのアクセス制御ツールです。</span><span class="sxs-lookup"><span data-stu-id="32a29-114">The Skype for Business Server Control Panel is a role-based access control tool.</span></span> <span data-ttu-id="32a29-115">CsAdministrator グループのメンバーシップにより、Skype for Business Server コントロール パネルを使用しているユーザーは、使用可能なすべての構成機能を完全に制御できます。</span><span class="sxs-lookup"><span data-stu-id="32a29-115">Membership in the CsAdministrator group gives a user who is using the Skype for Business Server Control Panel full control for all the configuration functions available.</span></span> <span data-ttu-id="32a29-116">特定の機能向けに設計されたその他の役割も使用できます。</span><span class="sxs-lookup"><span data-stu-id="32a29-116">There are other roles available that are designed for specific functions.</span></span> <span data-ttu-id="32a29-117">ユーザーが管理グループのメンバーになるには、Skype for Business Server を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="32a29-117">Users do not have to be enabled for Skype for Business Server in order to be made members of the management groups.</span></span> 
  
<span data-ttu-id="32a29-118">その他の役割は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="32a29-118">Other roles include:</span></span>
  
- <span data-ttu-id="32a29-119">**CsArchiving:** このグループのメンバーは、アーカイブ サーバーの役割の構成や管理など、すべてのアーカイブ機能を実行できます。</span><span class="sxs-lookup"><span data-stu-id="32a29-119">**CsArchiving:** Members of this group can perform all archiving functions, such as configuring and managing the Archiving Server role.</span></span>
    
- <span data-ttu-id="32a29-p104">**CsHelpDesk:** このグループのメンバーは、ユーザーのプロパティやポリシーを含む構成と展開を表示できます。またメンバーは、特定のトラブルシューティング タスクも実行できます。</span><span class="sxs-lookup"><span data-stu-id="32a29-p104">**CsHelpDesk:** Members of this group can view the configuration and deployment, including user properties and policies. Members can also perform specific troubleshooting tasks.</span></span>
    
- <span data-ttu-id="32a29-p105">**CsLocationAdministrator:** メンバーは、Enhanced 9-1-1 (E9-1-1) の管理と関連付けられた最小限のユーザー権限を持ちます。E9-1-1 の場所およびネットワーク識別子を作成し、展開内でそれらを関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="32a29-p105">**CsLocationAdministrator:** Members have the lowest level of user rights associated with Enhanced 9-1-1 (E9-1-1) management. They can create E9-1-1 locations and network identifiers and associate those in the deployment.</span></span>
    
- <span data-ttu-id="32a29-124">**CsResponseGroupAdministrator:** メンバーは、応答グループ サービスを管理および構成できます。</span><span class="sxs-lookup"><span data-stu-id="32a29-124">**CsResponseGroupAdministrator:** Members can manage and configure the Response Group service.</span></span>
    
- <span data-ttu-id="32a29-125">**CsServerAdministrator:** メンバーは、Skype for Business Server を実行しているすべてのサーバーを管理、監視、およびトラブルシューティングできます。</span><span class="sxs-lookup"><span data-stu-id="32a29-125">**CsServerAdministrator:** Members can manage, monitor, and troubleshoot all servers running Skype for Business Server.</span></span>
    
- <span data-ttu-id="32a29-126">**CsUserAdministrator:** メンバーは、ユーザーの管理、有効化および無効化、ユーザーへの既存ポリシーの割り当てを実行できます。</span><span class="sxs-lookup"><span data-stu-id="32a29-126">**CsUserAdministrator:** Members can manage, enable and disable users, and assign existing policies to users.</span></span>
    
- <span data-ttu-id="32a29-127">**CsViewOnlyAdministrator:** メンバーは、サーバー情報の展開と構成を表示できます。</span><span class="sxs-lookup"><span data-stu-id="32a29-127">**CsViewOnlyAdministrator:** Members can view the deployment and configuration of the server information.</span></span> <span data-ttu-id="32a29-128">このメンバーシップにより、メンバーは Skype for Business Server を実行しているサーバーの正常性を監視できます。</span><span class="sxs-lookup"><span data-stu-id="32a29-128">This membership enables a member to monitor the health of the servers running Skype for Business Server.</span></span>
    
- <span data-ttu-id="32a29-129">**CsVoiceAdministrator:** メンバーは、Skype for Business Server で音声関連の設定を作成、構成、および管理できます。</span><span class="sxs-lookup"><span data-stu-id="32a29-129">**CsVoiceAdministrator:** Members can create, configure, and manage voice-related settings in Skype for Business Server.</span></span>
    
<span data-ttu-id="32a29-130">セキュリティと役割ベースのアクセス制御の整合性を維持するために、Skype for Business Server 展開の管理でユーザーが実行する役割を定義するグループにユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="32a29-130">To help retain security and role-based access control integrity, add users to the groups that define what role the user performs in management of the Skype for Business Server deployment.</span></span>
  

