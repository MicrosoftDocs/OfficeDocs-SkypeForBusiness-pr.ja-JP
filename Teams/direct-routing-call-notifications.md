---
title: 電話システムのダイレクト ルーティング
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 10/17/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.reviewer: nmurav
search.appverid: MET150
f1.keywords:
- NOCSH
description: ダイレクト ルーティング呼び出し通知
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: 0320ebc6abfc0e3f3d720fbab03abc698b26849c
ms.sourcegitcommit: 6cfaadec5782ca7316db36472bd0be20217da693
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/29/2020
ms.locfileid: "42341801"
---
# <a name="manage-call-notifications"></a><span data-ttu-id="fddaf-103">着信通知の管理</span><span class="sxs-lookup"><span data-stu-id="fddaf-103">Manage call notifications</span></span>

<span data-ttu-id="fddaf-104">この記事では、ユーザーの通話通知を管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fddaf-104">This article describes how to manage call notifications for your users.</span></span> <span data-ttu-id="fddaf-105">サード パーティのプライベート ブランチ Teams (PBX) またはセッション ボーダー コントローラー (SBC) の両方Exchangeエンドポイントを構成できます。</span><span class="sxs-lookup"><span data-stu-id="fddaf-105">You can configure call endpoints to both Teams and to a third-party Private Branch Exchange (PBX) or Session Border Controller (SBC).</span></span>  <span data-ttu-id="fddaf-106">これは、たとえば、ユーザーの携帯電話とデスクフォンに同時に通話を送信する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="fddaf-106">This is useful, for example, if you want to send a call to a user's mobile and desk phones at the same time.</span></span>   

<span data-ttu-id="fddaf-107">次の図では、ユーザー Irena には 2 つのエンドポイントがあります。</span><span class="sxs-lookup"><span data-stu-id="fddaf-107">In the following diagram, user Irena has two endpoints:</span></span>

- <span data-ttu-id="fddaf-108">エンドポイントTeamsエンドポイント</span><span class="sxs-lookup"><span data-stu-id="fddaf-108">A Teams endpoint</span></span>
- <span data-ttu-id="fddaf-109">サード パーティの SBC に接続されている SIP 電話</span><span class="sxs-lookup"><span data-stu-id="fddaf-109">A SIP phone connected to a third-party SBC</span></span>

<span data-ttu-id="fddaf-110">呼び出しが到着すると、SBC は、ダイレクト ルーティングとサード パーティの SBC 電話システム間の呼び出しをフォークします。</span><span class="sxs-lookup"><span data-stu-id="fddaf-110">When a call arrives, the SBC forks the call between Phone System Direct Routing and the third-party SBC.</span></span>


![フォークされたエンドポイントをTeams図](media/direct-routing-call-notification-1.png)

<span data-ttu-id="fddaf-112">(サード パーティの SBC によって) Fork 2 で呼び出しが受け入れられる場合、Teams"Missed Call" 通知が生成されます。</span><span class="sxs-lookup"><span data-stu-id="fddaf-112">If the call is accepted on Fork 2 (by the third-party SBC), Teams will generate a “Missed Call” notification.</span></span>  

<span data-ttu-id="fddaf-113">次のように、フォーク 1 でキャンセルを送信する SBC を構成することで、"通話不足" 通知を防ぐことが可能です。</span><span class="sxs-lookup"><span data-stu-id="fddaf-113">You can prevent the “Missed Call” notification by configuring the SBC to send a Cancel on Fork 1 as follows:</span></span>

<span data-ttu-id="fddaf-114">理由: SIP;cause=200;text"call completed elsewhere"</span><span class="sxs-lookup"><span data-stu-id="fddaf-114">REASON: SIP; cause=200;text”Call completed elsewhere”</span></span> 

<span data-ttu-id="fddaf-115">この呼び出しは、正常な呼び出しとして Microsoft 電話詳細レコードに登録されない点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="fddaf-115">Note that the call will not be registered in the call detail records of Microsoft Phone System as a successful call.</span></span> <span data-ttu-id="fddaf-116">呼び出しは、Final SIP Code "487"、Final Microsoft サブコード "540200"、最後の SIP コード フレーズ "他の場所で完了しました" を含む "試行" として登録されます。</span><span class="sxs-lookup"><span data-stu-id="fddaf-116">The call will be registered as an “Attempt” with Final SIP Code “487”, Final Microsoft subcode “540200”, and Final SIP Code Phrase “Call completed elsewhere”.</span></span>  <span data-ttu-id="fddaf-117">(通話の詳細レコードを表示するには、[管理Teams分析とレポート、利用状況レポート] に移動し、[PSTN の使用状況] を選択します)。</span><span class="sxs-lookup"><span data-stu-id="fddaf-117">(To view the call detail records, go the Teams Admin portal, Analytics and Reports, Usage Reports, and select PSTN Usage.)</span></span>


<span data-ttu-id="fddaf-118">次の図は、Fork 1 の SIP ラダーを示しています。通話フローと、キャンセル メッセージの予想される理由について説明します。</span><span class="sxs-lookup"><span data-stu-id="fddaf-118">The diagram below illustrates the SIP ladder for Fork 1, explains the call flow, and the expected REASON in the Cancel message.</span></span> 

![フォークされたエンドポイントをTeams図](media/direct-routing-call-notification-2.png)
