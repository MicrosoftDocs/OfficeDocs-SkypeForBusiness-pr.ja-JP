---
title: Skype for Business 2015 での音声ポリシー、PSTN 使用法レコード、およびボイス ルートの構成
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 1e5a15f9-6f42-4dc6-baaa-24daf54afc4d
description: '概要: ビジネス サーバー 2015 の Skype での音声ポリシー、PSTN 使用法レコード、およびボイス ルートを構成する方法を説明します。'
ms.openlocfilehash: b0d5d9edaf94cb0c8041ef5ef679ad81b9c54edd
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="configure-voice-policies-pstn-usage-records-and-voice-routes-in-skype-for-business-2015"></a><span data-ttu-id="474d8-103">Skype for Business 2015 での音声ポリシー、PSTN 使用法レコード、およびボイス ルートの構成</span><span class="sxs-lookup"><span data-stu-id="474d8-103">Configure voice policies, PSTN usage records, and voice routes in Skype for Business 2015</span></span>
 
<span data-ttu-id="474d8-104">**の概要:** ビジネス サーバー 2015 の Skype での音声ポリシー、PSTN 使用法レコード、およびボイス ルートを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="474d8-104">**Summary:** Learn how to configure voice policies, PSTN usage records, and voice routes in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="474d8-p101">音声ポリシー、PSTN 使用法レコード、およびボイス ルートは、一体的に関わり合っています。音声ポリシーは、一連の通話機能を選択し、PSTN 使用法レコードのセット (音声ポリシーを割り当てられるユーザーまたはグループを対象に、承認される権限を指定します) にポリシーを割り当てることで、構成します。PSTN 使用法レコードは、ボイス ルートにも割り当てられます。これにより、ルートとこの PSTN 使用法レコードの使用を許可されたユーザーが照合されます。つまり、ユーザーはルートと一致する PSTN 使用法レコードが割り当てられている場合のみ、そのルートに電話をかけることができます。</span><span class="sxs-lookup"><span data-stu-id="474d8-p101">Voice policies, PSTN usage records, and voice routes are integrally related. You configure voice policies by selecting a set of calling features and then assigning the policy a set of PSTN usage records, which specify what rights are authorized for the users or groups who are assigned the voice policy. Voice routes are also assigned PSTN usage records, which serve to match routes with the users who are authorized to use them. That is, users can only place calls that use the routes for which they have a matching PSTN usage record.</span></span>
  
<span data-ttu-id="474d8-109">新しいエンタープライズ VoIP を展開する場合の推奨ワークフローは、最初に該当する PSTN 使用法レコードを含む音声ポリシーを構成し、次に、該当するルートを各 PSTN 使用法レコードに割り当てることです。</span><span class="sxs-lookup"><span data-stu-id="474d8-109">The recommended workflow for a new Enterprise Voice deployment is to start by configuring a voice policy that includes the appropriate PSTN usage records, and then associate the appropriate routes to each PSTN usage record.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="474d8-110">*ユーザー*スコープの音声ポリシーを作成し、個々 のユーザーまたはグループに割り当てることができますもします。</span><span class="sxs-lookup"><span data-stu-id="474d8-110">You can also create voice policies with  *user*  scope and assign them to individual users or groups.</span></span>
  
<span data-ttu-id="474d8-111">これらの各タスクを実行するための詳細ステップについては、このセクションの手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="474d8-111">For the detailed steps to perform each of these tasks, see the procedures in this section.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="474d8-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="474d8-112">In this section</span></span>

- [<span data-ttu-id="474d8-113">作成し、音声ポリシーを変更またはビジネス 2015年の Skype の PSTN 使用法レコードを構成します。</span><span class="sxs-lookup"><span data-stu-id="474d8-113">Create or modify a voice policy and configure PSTN usage records in Skype for Business 2015</span></span>](voice-policy-and-pstn-usage-records.md)
    
- [<span data-ttu-id="474d8-114">ビジネス 2015年の Skype でボイス メールのエスケープを構成します。</span><span class="sxs-lookup"><span data-stu-id="474d8-114">Configure voice mail escape in Skype for Business 2015</span></span>](configure-voice-mail-escape.md)
    
- [<span data-ttu-id="474d8-115">ビジネス 2015年の Skype の PSTN 使用法レコードの表示</span><span class="sxs-lookup"><span data-stu-id="474d8-115">View PSTN usage records in Skype for Business 2015</span></span>](view-pstn-usage-records.md)
    
- [<span data-ttu-id="474d8-116">作成またはビジネス 2015年の Skype でのボイス ルートを変更します。</span><span class="sxs-lookup"><span data-stu-id="474d8-116">Create or modify a voice route in Skype for Business 2015</span></span>](create-or-modify-a-voice-route.md)
    
- [<span data-ttu-id="474d8-117">ビジネス 2015年の Skype でボイス ルート構成ファイルをインポートまたはエクスポート</span><span class="sxs-lookup"><span data-stu-id="474d8-117">Export or import a voice route configuration file in Skype for Business 2015</span></span>](voice-route-configuration-import-export.md)
    
- [<span data-ttu-id="474d8-118">発行保留中のビジネス 2015年の Skype で音声ルーティング構成の変更</span><span class="sxs-lookup"><span data-stu-id="474d8-118">Publish pending changes to the voice routing configuration in Skype for Business 2015</span></span>](voice-route-config-changes.md)
    

