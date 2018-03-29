---
title: Active Directory の準備
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/26/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainADPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a8c96311-9e1c-4d39-9870-681fd4e272ff
description: ビジネス サーバー 2015 の Skype のインストールを開始するには、Active Directory ドメイン サービスのスキーマ、フォレスト、およびサーバーとユーザーをホストするドメインを準備する必要があります。 ビジネス サーバーの展開ウィザードの Skype では、Active Directory スキーマを使用して、フォレストの準備をし、開始の準備に必要な手順を説明します。 Active Directory のレプリケーションが成功したことを確認した後、ユーザーまたはサーバーをホストする各ドメインを準備します。
ms.openlocfilehash: 29000132b65350d6b1e723934333209fb3c55b42
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="prepare-active-directory"></a><span data-ttu-id="8e5cd-105">Active Directory の準備</span><span class="sxs-lookup"><span data-stu-id="8e5cd-105">Prepare Active Directory</span></span>
 
<span data-ttu-id="8e5cd-106">ビジネス サーバー 2015 の Skype のインストールを開始するには、Active Directory ドメイン サービスのスキーマ、フォレスト、およびサーバーとユーザーをホストするドメインを準備する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8e5cd-106">To begin the installation of Skype for Business Server 2015, you must prepare the Active Directory Domain Services schema, forest, and domains that will host servers and users.</span></span> <span data-ttu-id="8e5cd-107">ビジネス サーバーの展開ウィザードの Skype では、Active Directory スキーマを使用して、フォレストの準備をし、開始の準備に必要な手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="8e5cd-107">The Skype for Business Server Deployment Wizard will guide you through the steps required to prepare Active Directory, beginning with the schema and then into the forest preparation.</span></span> <span data-ttu-id="8e5cd-108">Active Directory のレプリケーションが成功したことを確認した後、ユーザーまたはサーバーをホストする各ドメインを準備します。</span><span class="sxs-lookup"><span data-stu-id="8e5cd-108">After confirming that Active Directory replication is successful, you then prepare each domain that will host users or servers.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="8e5cd-p103">スキーマの準備を成功させるには、Enterprise Admins グループおよび Schema Admins グループのメンバーとしてログインする必要があります。フォレストを準備するには、Enterprise Admins グループのメンバーとしてログインするか、フォレスト ルートの管理者としてログインする必要があります。ドメインを準備するには、Domain Admins グループのメンバーとしてログインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8e5cd-p103">To successfully prepare the schema, you must be logged in as a member of the Enterprise Admins group and the Schema Admins group. To prepare the forest, you must be logged in as a member of the Enterprise Admins group or logged in as the administrator in the forest root. For domain preparation, you must be logged in as a member of the Domain Admins group.</span></span> 
  
<span data-ttu-id="8e5cd-112">詳細については、サポートされている Active Directory トポロジは、サポート ドキュメントの[アクティブなディレクトリのサポート](http://technet.microsoft.com/library/28ed9ac4-586d-4803-ad45-99c4fa793f54.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e5cd-112">For details about supported Active Directory topologies, see [Active Directory Support](http://technet.microsoft.com/library/28ed9ac4-586d-4803-ad45-99c4fa793f54.aspx) in the Supportability documentation.</span></span> <span data-ttu-id="8e5cd-113">Active Directory の準備についての詳細は、展開に関するドキュメントの[概要の Active Directory ドメイン サービスの準備](http://technet.microsoft.com/library/cdd2a652-6a0d-4728-9950-3fcaa7a80066.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e5cd-113">For details about the Active Directory preparation, see [Overview of Active Directory Domain Services Preparation](http://technet.microsoft.com/library/cdd2a652-6a0d-4728-9950-3fcaa7a80066.aspx) in the Deployment documentation.</span></span>
  

