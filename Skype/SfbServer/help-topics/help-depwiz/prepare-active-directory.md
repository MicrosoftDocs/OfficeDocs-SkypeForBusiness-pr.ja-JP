---
title: Active Directory の準備
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainADPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a8c96311-9e1c-4d39-9870-681fd4e272ff
description: Skype for Business Server 2015 のインストールを開始するには、サーバーとユーザーをホストする Active Directory ドメイン サービスのスキーマ、フォレスト、およびドメインを準備する必要があります。 Skype for Business Server 展開ウィザードでは、スキーマから始まり、フォレストの準備に入り、Active Directory の準備に必要な手順について説明します。 Active Directory のレプリケーションが成功した後、ユーザーまたはサーバーをホストする各ドメインを準備します。
ms.openlocfilehash: 9a741e56166d3235096a154bc2ef86770409adb9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804837"
---
# <a name="prepare-active-directory"></a><span data-ttu-id="25e67-105">Active Directory の準備</span><span class="sxs-lookup"><span data-stu-id="25e67-105">Prepare Active Directory</span></span>

<span data-ttu-id="25e67-106">Skype for Business Server 2015 のインストールを開始するには、サーバーとユーザーをホストする Active Directory ドメイン サービスのスキーマ、フォレスト、およびドメインを準備する必要があります。</span><span class="sxs-lookup"><span data-stu-id="25e67-106">To begin the installation of Skype for Business Server 2015, you must prepare the Active Directory Domain Services schema, forest, and domains that will host servers and users.</span></span> <span data-ttu-id="25e67-107">Skype for Business Server 展開ウィザードでは、スキーマから始まり、フォレストの準備に入り、Active Directory の準備に必要な手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="25e67-107">The Skype for Business Server Deployment Wizard will guide you through the steps required to prepare Active Directory, beginning with the schema and then into the forest preparation.</span></span> <span data-ttu-id="25e67-108">Active Directory のレプリケーションが成功した後、ユーザーまたはサーバーをホストする各ドメインを準備します。</span><span class="sxs-lookup"><span data-stu-id="25e67-108">After confirming that Active Directory replication is successful, you then prepare each domain that will host users or servers.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="25e67-p103">スキーマの準備を成功させるには、Enterprise Admins グループおよび Schema Admins グループのメンバーとしてログインする必要があります。フォレストを準備するには、Enterprise Admins グループのメンバーとしてログインするか、フォレスト ルートの管理者としてログインする必要があります。ドメインを準備するには、Domain Admins グループのメンバーとしてログインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="25e67-p103">To successfully prepare the schema, you must be logged in as a member of the Enterprise Admins group and the Schema Admins group. To prepare the forest, you must be logged in as a member of the Enterprise Admins group or logged in as the administrator in the forest root. For domain preparation, you must be logged in as a member of the Domain Admins group.</span></span>

<span data-ttu-id="25e67-112">サポートされる Active Directory のトポロジの詳細については、「サポート」のドキュメントの「[Active Directory Support](https://technet.microsoft.com/library/28ed9ac4-586d-4803-ad45-99c4fa793f54.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="25e67-112">For details about supported Active Directory topologies, see [Active Directory Support](https://technet.microsoft.com/library/28ed9ac4-586d-4803-ad45-99c4fa793f54.aspx) in the Supportability documentation.</span></span> <span data-ttu-id="25e67-113">Active Directory の準備の詳細については、「展開」のドキュメントの「[Overview of Active Directory Domain Services Preparation](https://technet.microsoft.com/library/cdd2a652-6a0d-4728-9950-3fcaa7a80066.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="25e67-113">For details about the Active Directory preparation, see [Overview of Active Directory Domain Services Preparation](https://technet.microsoft.com/library/cdd2a652-6a0d-4728-9950-3fcaa7a80066.aspx) in the Deployment documentation.</span></span>


