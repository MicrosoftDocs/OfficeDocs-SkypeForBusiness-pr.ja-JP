---
title: Skype for Business Server 2015 への常設チャット コンポーネントのインストール
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
ms.assetid: 61370aa6-9708-4ff8-b531-b258a928806f
description: '概要: このトピックでは、Skype for business Server の展開ウィザードを使用して Skype for Business Server 2015 コンポーネントとサービスをインストールする方法について説明します。'
ms.openlocfilehash: 019700b169c3507540c93a3a152c3741de2681fb
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41795688"
---
# <a name="install-persistent-chat-components-in-skype-for-business-server-2015"></a><span data-ttu-id="4ed53-103">Skype for Business Server 2015 への常設チャット コンポーネントのインストール</span><span class="sxs-lookup"><span data-stu-id="4ed53-103">Install Persistent Chat components in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="4ed53-104">**概要:** このトピックでは、Skype for business Server の展開ウィザードを使用して、Skype for Business Server 2015 のコンポーネントとサービスをインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4ed53-104">**Summary:** Read this topic to learn how to use the Skype for Business Server Deployment Wizard to install Skype for Business Server 2015 components and services.</span></span>
  
<span data-ttu-id="4ed53-105">常設チャットコンポーネントをインストールする前に、必須のハードウェアとソフトウェアを既にインストールしていることを確認し、常設チャットサーバーをサポートする適切なトポロジを作成してください。</span><span class="sxs-lookup"><span data-stu-id="4ed53-105">Before you install Persistent Chat components, be sure you have already installed prerequisite hardware and software, and created the appropriate topology to support Persistent Chat Server.</span></span> <span data-ttu-id="4ed53-106">計画と要件の詳細については、「skype for business[環境の要件](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md)」および「 [Skype for business Server 2015 の常設チャットサーバーの計画](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ed53-106">For details about planning and requirements, see [Requirements for your Skype for Business environment](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md) and [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).</span></span> <span data-ttu-id="4ed53-107">トポロジを更新して、常設チャットサーバーを含める方法については、「 [Skype For Business server 2015 トポロジに常設チャットサーバーを追加](add-persistent-chat-server.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ed53-107">For information about how to update and publish your topology to include Persistent Chat Server, see [Add Persistent Chat Server to your Skype for Business Server 2015 topology](add-persistent-chat-server.md).</span></span>
  
> [!NOTE] 
> <span data-ttu-id="4ed53-108">常設チャットは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="4ed53-108">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="4ed53-109">Teams でも同じ機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="4ed53-109">The same functionality is available in Teams.</span></span> <span data-ttu-id="4ed53-110">詳細については、「 [Microsoft Teams のアップグレードの](/microsoftteams/upgrade-start-here)概要」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ed53-110">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="4ed53-111">常設チャットを使用する必要がある場合は、この機能が必要なユーザーをチームに移行するか、Skype for Business Server 2015 を使い続けるかのいずれかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="4ed53-111">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="install-and-start-services"></a><span data-ttu-id="4ed53-112">サービスをインストールして開始する</span><span class="sxs-lookup"><span data-stu-id="4ed53-112">Install and start services</span></span>

<span data-ttu-id="4ed53-113">Skype for Business Server Deployment ウィザードを使って、[Skype for Business Server System をインストールまたは更新する] を選択し、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="4ed53-113">Using the Skype for Business Server Deployment Wizard, choose Install or Update Skype for Business Server System to perform the following steps:</span></span> 
  
1. <span data-ttu-id="4ed53-114">ローカル構成ストアのインストール</span><span class="sxs-lookup"><span data-stu-id="4ed53-114">Install Local Configuration Store</span></span>
    
2. <span data-ttu-id="4ed53-115">Skype for Business Server コンポーネントのセットアップまたは削除</span><span class="sxs-lookup"><span data-stu-id="4ed53-115">Setup or Remove Skype for Business Server Components</span></span>
    
3. <span data-ttu-id="4ed53-116">証明書の要求、インストール、または割り当て</span><span class="sxs-lookup"><span data-stu-id="4ed53-116">Request, Install or Assign Certificates</span></span>
    
4. <span data-ttu-id="4ed53-117">サービスの開始</span><span class="sxs-lookup"><span data-stu-id="4ed53-117">Start services</span></span>
    
<span data-ttu-id="4ed53-118">展開ウィザードを使用してコンポーネントのインストール、証明書の割り当て、サービスの開始を行う方法について詳しくは、「 [skype For Business server 2015 をインストール](../../deploy/install/install.md)する」と「 [Skype for business server 2015 をトポロジのサーバーにインストール](../../deploy/install/install-skype-for-business-server.md)する」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="4ed53-118">For details on how to use the Deployment Wizard to install components, assign certificates, and start services, see [Install Skype for Business Server 2015](../../deploy/install/install.md) and [Install Skype for Business Server 2015 on servers in the topology](../../deploy/install/install-skype-for-business-server.md).</span></span>
  

