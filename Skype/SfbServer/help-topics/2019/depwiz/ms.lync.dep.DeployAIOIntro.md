---
title: 単一の Standard Edition サーバーの準備 (開始)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployAIOIntro
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: fe11d380-54c9-47e7-a676-02b9a59dc93f
ROBOTS: NOINDEX, NOFOLLOW
description: 中央管理ストアとその他の併置されたサービスを保持する Skype for Business Server Standard Edition Server のインストールを開始するには、対象となるサーバーのローカル管理者グループのメンバーとしてログインしている必要があります。Standard Edition サーバー。 [単一の Standard Edition サーバーの準備] ページに、初期インストールの要件が表示されます。 コンピューターが展開先のドメインのメンバーであり、フォレストでスキーマ、フォレスト、およびドメインの準備を正常に完了している必要があります。
ms.openlocfilehash: 437f90fa99efa920479e7c0dc966c3c63fd5eed1
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41796978"
---
# <a name="prepare-single-standard-edition-server-intro"></a><span data-ttu-id="7c57a-105">単一の Standard Edition サーバーの準備 (開始)</span><span class="sxs-lookup"><span data-stu-id="7c57a-105">Prepare Single Standard Edition Server (Intro)</span></span>
 
<span data-ttu-id="7c57a-106">中央管理ストアとその他の併置されたサービスを保持する Skype for Business Server Standard Edition Server のインストールを開始するには、対象となるサーバーのローカル管理者グループのメンバーとしてログインしている必要があります。Standard Edition サーバー。</span><span class="sxs-lookup"><span data-stu-id="7c57a-106">To begin the installation of a Skype for Business Server Standard Edition server that will hold the Central Management store and other collocated services that you select, you must be logged in as a member of the local Administrators group on the server that will become the Standard Edition server.</span></span> <span data-ttu-id="7c57a-107">[**単一の Standard Edition サーバーの準備**] ページに、初期インストールの要件が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7c57a-107">The **Prepare single Standard Edition Server** page details the requirements for the initial install.</span></span> <span data-ttu-id="7c57a-108">コンピューターが展開先のドメインのメンバーであり、フォレストでスキーマ、フォレスト、およびドメインの準備を正常に完了している必要があります。</span><span class="sxs-lookup"><span data-stu-id="7c57a-108">The computer must be a member of the domain in which you are going to deploy it, and you must have successfully completed the Schema, Forest, and Domain prep for your forest.</span></span>
  
<span data-ttu-id="7c57a-109">この特別なタスクは、Standard Edition サーバーをインフラストラクチャの最初のサーバーとして設定するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="7c57a-109">This particular task is designed to set up a Standard Edition server as the first server in your infrastructure.</span></span> <span data-ttu-id="7c57a-110">このタスクは、SQL Server Express の中央管理ストアを Standard Edition Server にインストールします。</span><span class="sxs-lookup"><span data-stu-id="7c57a-110">This task installs the Central Management store, which is SQL Server Express, onto the Standard Edition server.</span></span> <span data-ttu-id="7c57a-111">別の Standard Edition サーバーまたはフロントエンド プールを既に展開している場合は、[**キャンセル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7c57a-111">If you already have another Standard Edition server or Front End pool deployed, you should click **Cancel**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7c57a-112">このタスクが完了したら、トポロジビルダーをインストールし (まだインストールしていない場合)、トポロジドキュメントを構成します。</span><span class="sxs-lookup"><span data-stu-id="7c57a-112">After completing this task, you will install Topology Builder (if you have not already installed it) and configure your topology document.</span></span> <span data-ttu-id="7c57a-113">このトピックで説明するタスクを完了すると展開される中央管理ストアが利用できるようになるまで、トポロジ ドキュメントを公開することはできません。</span><span class="sxs-lookup"><span data-stu-id="7c57a-113">You cannot publish your topology document until you have a Central Management store available—which is deployed by completing the task described in this topic.</span></span> 
  

