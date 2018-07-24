---
title: Skype for Business Server 2015 への常設チャット コンポーネントのインストール
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 61370aa6-9708-4ff8-b531-b258a928806f
description: '概要: このサーバー 2015 のビジネス コンポーネントとサービスの Skype をインストールするのにはビジネスのサーバーの展開ウィザードの Skype を使用する方法についてを参照できます。'
ms.openlocfilehash: d8c094c09160077dc98f68a9e98e4726f60ecaeb
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "21006882"
---
# <a name="install-persistent-chat-components-in-skype-for-business-server-2015"></a><span data-ttu-id="630da-103">Skype for Business Server 2015 への常設チャット コンポーネントのインストール</span><span class="sxs-lookup"><span data-stu-id="630da-103">Install Persistent Chat components in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="630da-104">**の概要:** サーバー 2015 のビジネス コンポーネントとサービスの Skype をインストールするのにはビジネスのサーバーの展開ウィザードの Skype を使用する方法の詳細については、このトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="630da-104">**Summary:** Read this topic to learn how to use the Skype for Business Server Deployment Wizard to install Skype for Business Server 2015 components and services.</span></span>
  
<span data-ttu-id="630da-105">永続的なチャットのコンポーネントをインストールする前に、既に前提条件となるハードウェアとソフトウェアをインストールし、永続的なチャット サーバーをサポートするために適切なトポロジを作成したことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="630da-105">Before you install Persistent Chat components, be sure you have already installed prerequisite hardware and software, and created the appropriate topology to support Persistent Chat Server.</span></span> <span data-ttu-id="630da-106">計画と要件の詳細については、[ビジネス環境に、Skype の要件](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md)と[ビジネス サーバー 2015 の Skype での永続的なチャット サーバーの計画](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="630da-106">For details about planning and requirements, see [Requirements for your Skype for Business environment](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md) and [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).</span></span> <span data-ttu-id="630da-107">更新し、永続的なチャット サーバーを含むようにトポロジを公開する方法の詳細については、[ビジネス サーバー 2015 トポロジの場合、Skype を永続的なチャットのサーバーを追加](add-persistent-chat-server.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="630da-107">For information about how to update and publish your topology to include Persistent Chat Server, see [Add Persistent Chat Server to your Skype for Business Server 2015 topology](add-persistent-chat-server.md).</span></span>
  
> [!NOTE] 
> <span data-ttu-id="630da-108">永続的なチャットですがビジネス サーバー 2015 の Skype で利用可能なビジネス サーバー 2019 の Skype でサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="630da-108">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="630da-109">同じ機能は、チームで使用できます。</span><span class="sxs-lookup"><span data-stu-id="630da-109">The same functionality is available in Teams.</span></span> <span data-ttu-id="630da-110">詳細については、[マイクロソフトのチームにビジネス用の Skype からの旅](/microsoftteams/journey-skypeforbusiness-teams)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="630da-110">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="630da-111">永続的なチャットを使用する場合は、選択肢は、いずれかをチームでは、この機能を必要とするユーザーを移行するまたはビジネス サーバー 2015 の Skype を使用し続ける。</span><span class="sxs-lookup"><span data-stu-id="630da-111">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="install-and-start-services"></a><span data-ttu-id="630da-112">サービスをインストールして開始する</span><span class="sxs-lookup"><span data-stu-id="630da-112">Install and start services</span></span>

<span data-ttu-id="630da-113">ビジネス サーバーの展開ウィザードで、Skype を使用してインストールまたは更新の Skype ビジネス サーバー システムの次の手順を実行するを選択します。</span><span class="sxs-lookup"><span data-stu-id="630da-113">Using the Skype for Business Server Deployment Wizard, choose Install or Update Skype for Business Server System to perform the following steps:</span></span> 
  
1. <span data-ttu-id="630da-114">ローカル構成ストアのインストール</span><span class="sxs-lookup"><span data-stu-id="630da-114">Install Local Configuration Store</span></span>
    
2. <span data-ttu-id="630da-115">Skype for Business Server コンポーネントのセットアップまたは削除</span><span class="sxs-lookup"><span data-stu-id="630da-115">Setup or Remove Skype for Business Server Components</span></span>
    
3. <span data-ttu-id="630da-116">証明書の要求、インストール、または割り当て</span><span class="sxs-lookup"><span data-stu-id="630da-116">Request, Install or Assign Certificates</span></span>
    
4. <span data-ttu-id="630da-117">サービスの開始</span><span class="sxs-lookup"><span data-stu-id="630da-117">Start services</span></span>
    
<span data-ttu-id="630da-118">コンポーネントをインストールするのには、展開ウィザードを使用する方法の詳細については、証明書を割り当てるサービスを開始、[ビジネス サーバー 2015 の Skype をインストール](../../deploy/install/install.md)し、[トポロジ内のサーバー上のビジネス サーバー 2015 の Skype のインストール](../../deploy/install/install-skype-for-business-server.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="630da-118">For details on how to use the Deployment Wizard to install components, assign certificates, and start services, see [Install Skype for Business Server 2015](../../deploy/install/install.md) and [Install Skype for Business Server 2015 on servers in the topology](../../deploy/install/install-skype-for-business-server.md).</span></span>
  

