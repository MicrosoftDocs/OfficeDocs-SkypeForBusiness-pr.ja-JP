---
title: Active Directory の準備
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainADPrep
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: a8c96311-9e1c-4d39-9870-681fd4e272ff
ROBOTS: NOINDEX, NOFOLLOW
description: Skype for Business Server のインストールを開始するには、サーバーとユーザーをホストする Active Directory ドメイン サービススキーマ、フォレスト、およびドメインを準備する必要があります。 Skype for Business Server 展開ウィザードでは、Active Directory の準備に必要な手順を、スキーマからフォレストの準備まで順に説明します。 Active Directory レプリケーションが成功したと確認したら、ユーザーまたはサーバーをホストする各ドメインを準備します。
ms.openlocfilehash: fcc77ed8dab3a6e3e643c2022dc45623e855dfde
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51097363"
---
# <a name="prepare-active-directory"></a><span data-ttu-id="881b7-105">Active Directory の準備</span><span class="sxs-lookup"><span data-stu-id="881b7-105">Prepare Active Directory</span></span>

<span data-ttu-id="881b7-106">Skype for Business Server のインストールを開始するには、サーバーとユーザーをホストする Active Directory ドメイン サービススキーマ、フォレスト、およびドメインを準備する必要があります。</span><span class="sxs-lookup"><span data-stu-id="881b7-106">To begin the installation of Skype for Business Server, you must prepare the Active Directory Domain Services schema, forest, and domains that will host servers and users.</span></span> <span data-ttu-id="881b7-107">Skype for Business Server 展開ウィザードでは、Active Directory の準備に必要な手順を、スキーマからフォレストの準備まで順に説明します。</span><span class="sxs-lookup"><span data-stu-id="881b7-107">The Skype for Business Server Deployment Wizard will guide you through the steps required to prepare Active Directory, beginning with the schema and then into the forest preparation.</span></span> <span data-ttu-id="881b7-108">Active Directory レプリケーションが成功したと確認したら、ユーザーまたはサーバーをホストする各ドメインを準備します。</span><span class="sxs-lookup"><span data-stu-id="881b7-108">After confirming that Active Directory replication is successful, you then prepare each domain that will host users or servers.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="881b7-p103">スキーマの準備を成功させるには、Enterprise Admins グループおよび Schema Admins グループのメンバーとしてログインする必要があります。フォレストを準備するには、Enterprise Admins グループのメンバーとしてログインするか、フォレスト ルートの管理者としてログインする必要があります。ドメインを準備するには、Domain Admins グループのメンバーとしてログインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="881b7-p103">To successfully prepare the schema, you must be logged in as a member of the Enterprise Admins group and the Schema Admins group. To prepare the forest, you must be logged in as a member of the Enterprise Admins group or logged in as the administrator in the forest root. For domain preparation, you must be logged in as a member of the Domain Admins group.</span></span>

<span data-ttu-id="881b7-112">サポートされる Active Directory のトポロジの詳細については、「サポート」のドキュメントの「[Active Directory Support](/previous-versions/office/lync-server-2013/lync-server-2013-active-directory-support)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="881b7-112">For details about supported Active Directory topologies, see [Active Directory Support](/previous-versions/office/lync-server-2013/lync-server-2013-active-directory-support) in the Supportability documentation.</span></span> <span data-ttu-id="881b7-113">Active Directory の準備の詳細については、「展開」のドキュメントの「[Overview of Active Directory Domain Services Preparation](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-active-directory-domain-services-preparation)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="881b7-113">For details about the Active Directory preparation, see [Overview of Active Directory Domain Services Preparation](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-active-directory-domain-services-preparation) in the Deployment documentation.</span></span>