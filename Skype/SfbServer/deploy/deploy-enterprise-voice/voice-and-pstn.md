---
title: Skype for Business で音声ポリシー、PSTN 使用状況レコード、および音声ルートを構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 1e5a15f9-6f42-4dc6-baaa-24daf54afc4d
description: '概要: Skype for Business Server でボイスポリシー、PSTN 使用状況レコード、および音声ルートを構成する方法について説明します。'
ms.openlocfilehash: 3cdc621e163aa8cff4ba2456c3a94ddf30bfcbaf
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239937"
---
# <a name="configure-voice-policies-pstn-usage-records-and-voice-routes-in-skype-for-business"></a><span data-ttu-id="f74f7-103">Skype for Business で音声ポリシー、PSTN 使用状況レコード、および音声ルートを構成する</span><span class="sxs-lookup"><span data-stu-id="f74f7-103">Configure voice policies, PSTN usage records, and voice routes in Skype for Business</span></span>
 
<span data-ttu-id="f74f7-104">**概要:** Skype for Business Server でボイスポリシー、PSTN 使用状況レコード、および音声ルートを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f74f7-104">**Summary:** Learn how to configure voice policies, PSTN usage records, and voice routes in Skype for Business Server.</span></span>
  
<span data-ttu-id="f74f7-p101">音声ポリシー、PSTN 使用法レコード、およびボイス ルートは、一体的に関わり合っています。音声ポリシーは、一連の通話機能を選択し、PSTN 使用法レコードのセット (音声ポリシーを割り当てられるユーザーまたはグループを対象に、承認される権限を指定します) にポリシーを割り当てることで、構成します。PSTN 使用法レコードは、ボイス ルートにも割り当てられます。これにより、ルートとこの PSTN 使用法レコードの使用を許可されたユーザーが照合されます。つまり、ユーザーはルートと一致する PSTN 使用法レコードが割り当てられている場合のみ、そのルートに電話をかけることができます。</span><span class="sxs-lookup"><span data-stu-id="f74f7-p101">Voice policies, PSTN usage records, and voice routes are integrally related. You configure voice policies by selecting a set of calling features and then assigning the policy a set of PSTN usage records, which specify what rights are authorized for the users or groups who are assigned the voice policy. Voice routes are also assigned PSTN usage records, which serve to match routes with the users who are authorized to use them. That is, users can only place calls that use the routes for which they have a matching PSTN usage record.</span></span>
  
<span data-ttu-id="f74f7-109">新しいエンタープライズ VoIP を展開する場合の推奨ワークフローは、最初に該当する PSTN 使用法レコードを含む音声ポリシーを構成し、次に、該当するルートを各 PSTN 使用法レコードに割り当てることです。</span><span class="sxs-lookup"><span data-stu-id="f74f7-109">The recommended workflow for a new Enterprise Voice deployment is to start by configuring a voice policy that includes the appropriate PSTN usage records, and then associate the appropriate routes to each PSTN usage record.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="f74f7-110">また、*ユーザー*のスコープを使用して音声ポリシーを作成し、個々のユーザーまたはグループに割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="f74f7-110">You can also create voice policies with  *user*  scope and assign them to individual users or groups.</span></span>
  
<span data-ttu-id="f74f7-111">これらの各タスクを実行するための詳細ステップについては、このセクションの手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f74f7-111">For the detailed steps to perform each of these tasks, see the procedures in this section.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="f74f7-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="f74f7-112">In this section</span></span>

- [<span data-ttu-id="f74f7-113">Skype for Business で音声ポリシーを作成または変更し、PSTN 使用状況レコードを構成する</span><span class="sxs-lookup"><span data-stu-id="f74f7-113">Create or modify a voice policy and configure PSTN usage records in Skype for Business</span></span>](voice-policy-and-pstn-usage-records.md)
    
- [<span data-ttu-id="f74f7-114">Skype for Business でボイスメールのエスケープを設定する</span><span class="sxs-lookup"><span data-stu-id="f74f7-114">Configure voice mail escape in Skype for Business</span></span>](configure-voice-mail-escape.md)
    
- [<span data-ttu-id="f74f7-115">Skype for Business での PSTN 使用状況レコードの表示</span><span class="sxs-lookup"><span data-stu-id="f74f7-115">View PSTN usage records in Skype for Business</span></span>](view-pstn-usage-records.md)
    
- [<span data-ttu-id="f74f7-116">Skype for Business での音声ルートの作成または変更</span><span class="sxs-lookup"><span data-stu-id="f74f7-116">Create or modify a voice route in Skype for Business</span></span>](create-or-modify-a-voice-route.md)
    
- [<span data-ttu-id="f74f7-117">Skype for Business のボイスルート構成ファイルをエクスポートまたはインポートする</span><span class="sxs-lookup"><span data-stu-id="f74f7-117">Export or import a voice route configuration file in Skype for Business</span></span>](voice-route-configuration-import-export.md)
    
- [<span data-ttu-id="f74f7-118">Skype for Business の音声ルーティング構成に保留中の変更を公開する</span><span class="sxs-lookup"><span data-stu-id="f74f7-118">Publish pending changes to the voice routing configuration in Skype for Business</span></span>](voice-route-config-changes.md)
    

