---
title: Skype for Business Server 2015 での常設チャット サービスの監視、開始、および停止
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6b28595-f702-4ecf-8115-e4104b87da89
description: '概要: Skype for Business Server 2015 で常設チャットサービスの開始、停止、監視を行う方法について説明します。'
ms.openlocfilehash: 161bda3cb02bf6208b4db9f1c6825d3fe433eeca
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279292"
---
# <a name="monitor-start-and-stop-the-persistent-chat-services-in-skype-for-business-server-2015"></a><span data-ttu-id="0203e-103">Skype for Business Server 2015 での常設チャット サービスの監視、開始、および停止</span><span class="sxs-lookup"><span data-stu-id="0203e-103">Monitor, start, and stop the Persistent Chat services in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="0203e-104">**概要:** Skype for Business Server 2015 で常設チャットサービスの開始、停止、監視を行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0203e-104">**Summary:** Learn how to start, stop, and monitor the Persistent Chat services in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="0203e-105">常設チャットサービスと常設チャットのコンプライアンスサービスは、Skype for Business Server トポロジの一部であり、次のコマンドレットを使用して、監視、停止、開始することができます。</span><span class="sxs-lookup"><span data-stu-id="0203e-105">The Persistent Chat services and Persistent Chat Compliance services are part of the Skype for Business Server topology and can therefore be monitored, stopped, and started by using the following cmdlets:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="0203e-106">get-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="0203e-106">get-CsWindowsService</span></span>  <br/> |<span data-ttu-id="0203e-107">Windows サービスとして実行される Skype for Business Server 2015 コンポーネントに関する詳細情報を返します。</span><span class="sxs-lookup"><span data-stu-id="0203e-107">Returns detailed information about Skype for Business Server 2015 components that run as Windows services.</span></span>  <br/> |
|<span data-ttu-id="0203e-108">start-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="0203e-108">start-CsWindowsService</span></span>  <br/> |<span data-ttu-id="0203e-109">サービスを開始します。</span><span class="sxs-lookup"><span data-stu-id="0203e-109">Starts the service.</span></span>  <br/> |
|<span data-ttu-id="0203e-110">stop-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="0203e-110">stop-CsWindowsService</span></span>  <br/> |<span data-ttu-id="0203e-111">サービスを停止します。</span><span class="sxs-lookup"><span data-stu-id="0203e-111">Stops the service.</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="0203e-112">常設チャットは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="0203e-112">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="0203e-113">Teams でも同じ機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="0203e-113">The same functionality is available in Teams.</span></span> <span data-ttu-id="0203e-114">詳細については、「 [Skype For business から Microsoft Teams への旅](/microsoftteams/journey-skypeforbusiness-teams)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0203e-114">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="0203e-115">常設チャットを使用する必要がある場合は、この機能が必要なユーザーをチームに移行するか、Skype for Business Server 2015 を使い続けるかのいずれかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="0203e-115">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

<span data-ttu-id="0203e-116">これらのコマンドレットの使用法の詳細については、「[Skype for Business Server 2015 Management Shell](../management-shell.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0203e-116">For detailed information about how to use the cmdlets, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  

