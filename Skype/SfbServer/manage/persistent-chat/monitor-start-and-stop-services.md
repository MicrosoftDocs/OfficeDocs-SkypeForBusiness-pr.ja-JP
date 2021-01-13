---
title: Skype for Business Server 2015 での常設チャット サービスの監視、開始、および停止
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b6b28595-f702-4ecf-8115-e4104b87da89
description: '概要: Skype for Business Server 2015 で常設チャット サービスを開始、停止、監視する方法について学習します。'
ms.openlocfilehash: 31285fe5f7eefaa6579f2891a4b29111324de22d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814137"
---
# <a name="monitor-start-and-stop-the-persistent-chat-services-in-skype-for-business-server-2015"></a><span data-ttu-id="b4c5c-103">Skype for Business Server 2015 での常設チャット サービスの監視、開始、および停止</span><span class="sxs-lookup"><span data-stu-id="b4c5c-103">Monitor, start, and stop the Persistent Chat services in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="b4c5c-104">**概要:** Skype for Business Server 2015 で常設チャット サービスを開始、停止、監視する方法について学習します。</span><span class="sxs-lookup"><span data-stu-id="b4c5c-104">**Summary:** Learn how to start, stop, and monitor the Persistent Chat services in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="b4c5c-105">常設チャット サービスと常設チャット コンプライアンス サービスは Skype for Business Server トポロジの一部であるため、次のコマンドレットを使用して監視、停止、および開始できます。</span><span class="sxs-lookup"><span data-stu-id="b4c5c-105">The Persistent Chat services and Persistent Chat Compliance services are part of the Skype for Business Server topology and can therefore be monitored, stopped, and started by using the following cmdlets:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="b4c5c-106">get-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="b4c5c-106">get-CsWindowsService</span></span>  <br/> |<span data-ttu-id="b4c5c-107">Windows サービスとして実行される Skype for Business Server 2015 コンポーネントに関する詳細情報を戻します。</span><span class="sxs-lookup"><span data-stu-id="b4c5c-107">Returns detailed information about Skype for Business Server 2015 components that run as Windows services.</span></span>  <br/> |
|<span data-ttu-id="b4c5c-108">start-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="b4c5c-108">start-CsWindowsService</span></span>  <br/> |<span data-ttu-id="b4c5c-109">サービスを開始します。</span><span class="sxs-lookup"><span data-stu-id="b4c5c-109">Starts the service.</span></span>  <br/> |
|<span data-ttu-id="b4c5c-110">stop-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="b4c5c-110">stop-CsWindowsService</span></span>  <br/> |<span data-ttu-id="b4c5c-111">サービスを停止します。</span><span class="sxs-lookup"><span data-stu-id="b4c5c-111">Stops the service.</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="b4c5c-112">常設チャットは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="b4c5c-112">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="b4c5c-113">Teams でも同じ機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="b4c5c-113">The same functionality is available in Teams.</span></span> <span data-ttu-id="b4c5c-114">詳細については、「Microsoft Teams のアップグレード [の開始」を参照してください](/microsoftteams/upgrade-start-here)。</span><span class="sxs-lookup"><span data-stu-id="b4c5c-114">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="b4c5c-115">常設チャットを使用する必要がある場合は、この機能を必要とするユーザーを Teams に移行するか、Skype for Business Server 2015 を引き続き使用するかのどちらかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="b4c5c-115">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

<span data-ttu-id="b4c5c-116">コマンドレットの使用方法の詳細については [、「Skype for Business Server 2015 Management Shell」を参照してください](../management-shell.md)。</span><span class="sxs-lookup"><span data-stu-id="b4c5c-116">For detailed information about how to use the cmdlets, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  

