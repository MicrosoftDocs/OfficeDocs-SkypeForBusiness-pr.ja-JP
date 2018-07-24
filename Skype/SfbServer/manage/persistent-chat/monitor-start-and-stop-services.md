---
title: Skype for Business Server 2015 での常設チャット サービスの監視、開始、および停止
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6b28595-f702-4ecf-8115-e4104b87da89
description: '概要: 開始、停止、およびビジネス サーバー 2015 の Skype で永続的なチャット サービスを監視する方法を説明します。'
ms.openlocfilehash: 272ea0f4270b1109ff77b5d809472051705b6f10
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "20991590"
---
# <a name="monitor-start-and-stop-the-persistent-chat-services-in-skype-for-business-server-2015"></a><span data-ttu-id="a00fb-103">Skype for Business Server 2015 での常設チャット サービスの監視、開始、および停止</span><span class="sxs-lookup"><span data-stu-id="a00fb-103">Monitor, start, and stop the Persistent Chat services in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="a00fb-104">**の概要:** 開始、停止、およびビジネス サーバー 2015 の Skype で永続的なチャット サービスを監視する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="a00fb-104">**Summary:** Learn how to start, stop, and monitor the Persistent Chat services in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="a00fb-105">永続的なチャット サービスと永続的なチャットのコンプライアンス ・ サービス ビジネス サーバー トポロジの Skype の一部であることができるため監視、停止、および次のコマンドレットを使用して起動。</span><span class="sxs-lookup"><span data-stu-id="a00fb-105">The Persistent Chat services and Persistent Chat Compliance services are part of the Skype for Business Server topology and can therefore be monitored, stopped, and started by using the following cmdlets:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="a00fb-106">get CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="a00fb-106">get-CsWindowsService</span></span>  <br/> |<span data-ttu-id="a00fb-107">詳細 Windows サービスとして実行されているビジネス サーバー 2015 コンポーネントについて、Skype に関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="a00fb-107">Returns detailed information about Skype for Business Server 2015 components that run as Windows services.</span></span>  <br/> |
|<span data-ttu-id="a00fb-108">開始 CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="a00fb-108">start-CsWindowsService</span></span>  <br/> |<span data-ttu-id="a00fb-109">サービスを開始します。</span><span class="sxs-lookup"><span data-stu-id="a00fb-109">Starts the service.</span></span>  <br/> |
|<span data-ttu-id="a00fb-110">stop CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="a00fb-110">stop-CsWindowsService</span></span>  <br/> |<span data-ttu-id="a00fb-111">サービスを停止します。</span><span class="sxs-lookup"><span data-stu-id="a00fb-111">Stops the service.</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="a00fb-112">永続的なチャットですがビジネス サーバー 2015 の Skype で利用可能なビジネス サーバー 2019 の Skype でサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="a00fb-112">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="a00fb-113">同じ機能は、チームで使用できます。</span><span class="sxs-lookup"><span data-stu-id="a00fb-113">The same functionality is available in Teams.</span></span> <span data-ttu-id="a00fb-114">詳細については、[マイクロソフトのチームにビジネス用の Skype からの旅](/microsoftteams/journey-skypeforbusiness-teams)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a00fb-114">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="a00fb-115">永続的なチャットを使用する場合は、選択肢は、いずれかをチームでは、この機能を必要とするユーザーを移行するまたはビジネス サーバー 2015 の Skype を使用し続ける。</span><span class="sxs-lookup"><span data-stu-id="a00fb-115">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

<span data-ttu-id="a00fb-116">コマンドレットを使用する方法の詳細については、 [Skype ビジネス サーバー 2015 管理シェルに](../management-shell.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a00fb-116">For detailed information about how to use the cmdlets, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  

