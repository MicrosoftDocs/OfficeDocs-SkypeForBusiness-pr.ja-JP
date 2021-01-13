---
title: Skype for Business Server 2015 での常設チャット コンポーネントのインストール
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
ms.assetid: 61370aa6-9708-4ff8-b531-b258a928806f
description: '概要: このトピックでは、Skype for Business Server 展開ウィザードを使用して Skype for Business Server 2015 のコンポーネントとサービスをインストールする方法について説明します。'
ms.openlocfilehash: c3e68d5b5a41d06544f030df6877828da4b87c9e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802087"
---
# <a name="install-persistent-chat-components-in-skype-for-business-server-2015"></a><span data-ttu-id="13aef-103">Skype for Business Server 2015 での常設チャット コンポーネントのインストール</span><span class="sxs-lookup"><span data-stu-id="13aef-103">Install Persistent Chat components in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="13aef-104">**概要:** このトピックでは、Skype for Business Server 展開ウィザードを使用して Skype for Business Server 2015 のコンポーネントとサービスをインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="13aef-104">**Summary:** Read this topic to learn how to use the Skype for Business Server Deployment Wizard to install Skype for Business Server 2015 components and services.</span></span>
  
<span data-ttu-id="13aef-105">常設チャット コンポーネントをインストールする前に、前提条件となるハードウェアとソフトウェアが既にインストールされ、常設チャット サーバーをサポートする適切なトポロジが作成されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="13aef-105">Before you install Persistent Chat components, be sure you have already installed prerequisite hardware and software, and created the appropriate topology to support Persistent Chat Server.</span></span> <span data-ttu-id="13aef-106">計画と要件の詳細については [、「Skype for Business](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md) 環境の要件」および [「Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)での常設チャット サーバーの計画」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="13aef-106">For details about planning and requirements, see [Requirements for your Skype for Business environment](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md) and [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).</span></span> <span data-ttu-id="13aef-107">常設チャット サーバーを含むトポロジを更新および公開する方法については、「常設チャット サーバーを [Skype for Business Server 2015](add-persistent-chat-server.md)トポロジに追加する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="13aef-107">For information about how to update and publish your topology to include Persistent Chat Server, see [Add Persistent Chat Server to your Skype for Business Server 2015 topology](add-persistent-chat-server.md).</span></span>
  
> [!NOTE] 
> <span data-ttu-id="13aef-108">常設チャットは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="13aef-108">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="13aef-109">Teams でも同じ機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="13aef-109">The same functionality is available in Teams.</span></span> <span data-ttu-id="13aef-110">詳細については、「Microsoft Teams のアップグレード [の開始」を参照してください](/microsoftteams/upgrade-start-here)。</span><span class="sxs-lookup"><span data-stu-id="13aef-110">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="13aef-111">常設チャットを使用する必要がある場合は、この機能を必要とするユーザーを Teams に移行するか、Skype for Business Server 2015 を引き続き使用するかのどちらかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="13aef-111">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="install-and-start-services"></a><span data-ttu-id="13aef-112">サービスのインストールと開始</span><span class="sxs-lookup"><span data-stu-id="13aef-112">Install and start services</span></span>

<span data-ttu-id="13aef-113">Skype for Business Server 展開ウィザードを使用して、Skype for Business Server システムのインストールまたは更新を選択し、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="13aef-113">Using the Skype for Business Server Deployment Wizard, choose Install or Update Skype for Business Server System to perform the following steps:</span></span> 
  
1. <span data-ttu-id="13aef-114">ローカル構成ストアのインストール</span><span class="sxs-lookup"><span data-stu-id="13aef-114">Install Local Configuration Store</span></span>
    
2. <span data-ttu-id="13aef-115">Skype for Business Server コンポーネントのセットアップまたは削除</span><span class="sxs-lookup"><span data-stu-id="13aef-115">Setup or Remove Skype for Business Server Components</span></span>
    
3. <span data-ttu-id="13aef-116">証明書の要求、インストール、または割り当て</span><span class="sxs-lookup"><span data-stu-id="13aef-116">Request, Install or Assign Certificates</span></span>
    
4. <span data-ttu-id="13aef-117">サービスを開始する</span><span class="sxs-lookup"><span data-stu-id="13aef-117">Start services</span></span>
    
<span data-ttu-id="13aef-118">展開ウィザードを使用してコンポーネントをインストールし、証明書を割り当て、サービスを開始する方法の詳細については [、「Skype for Business Server 2015](../../deploy/install/install.md) のインストール」および「トポロジ内のサーバーへの [Skype for Business Server 2015](../../deploy/install/install-skype-for-business-server.md)のインストール」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="13aef-118">For details on how to use the Deployment Wizard to install components, assign certificates, and start services, see [Install Skype for Business Server 2015](../../deploy/install/install.md) and [Install Skype for Business Server 2015 on servers in the topology](../../deploy/install/install-skype-for-business-server.md).</span></span>
  

