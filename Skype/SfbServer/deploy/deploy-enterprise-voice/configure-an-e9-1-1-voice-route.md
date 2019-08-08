---
title: Skype for Business Server で E9 のボイスルートを設定する
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
ms.assetid: 6933b840-0e7b-4509-ae43-bc9065677547
description: Skype for Business Server Enterprise Voice で E9 のボイスルーティングを構成します。
ms.openlocfilehash: a8121cc7a7345150e485dc2e2b81e062672f5703
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233715"
---
# <a name="configure-an-e9-1-1-voice-route-in-skype-for-business-server"></a><span data-ttu-id="a602b-103">Skype for Business Server で E9 のボイスルートを設定する</span><span class="sxs-lookup"><span data-stu-id="a602b-103">Configure an E9-1-1 voice route in Skype for Business Server</span></span>
 
<span data-ttu-id="a602b-104">Skype for Business Server Enterprise Voice で E9 のボイスルーティングを構成します。</span><span class="sxs-lookup"><span data-stu-id="a602b-104">Configure E9-1-1 voice routes in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="a602b-105">E9-1-1 を展開するには、まず緊急通話用のボイス ルートを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a602b-105">To deploy E9-1-1, you first need to configure an emergency call voice route.</span></span> <span data-ttu-id="a602b-106">ボイスルートの作成の詳細については、「 [Skype For business での音声ルートの作成または変更](create-or-modify-a-voice-route.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a602b-106">For details about creating voice routes, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span> <span data-ttu-id="a602b-107">展開にプライマリ SIP トランクおよびセカンダリ SIP トランクが含まれている場合などは、複数のルートを定義できます。</span><span class="sxs-lookup"><span data-stu-id="a602b-107">You may define more than one route if, for example, your deployment includes a primary SIP trunk and a secondary SIP trunk.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="a602b-108">E9 の招待状に位置情報を含めるには、E9 サービスプロバイダーに接続する SIP トランクをゲートウェイ経由でルーティングするように構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a602b-108">To include location information in an E9-1-1 INVITE, you need to configure the SIP trunk that connects to the E9-1-1 service provider to route emergency calls through the gateway.</span></span> <span data-ttu-id="a602b-109">そのためには、 **set-cstrunkconfiguration**コマンドレットの EnablePIDFLOSupport フラグを True に設定します。</span><span class="sxs-lookup"><span data-stu-id="a602b-109">To do this, set the EnablePIDFLOSupport flag on the **Set-CsTrunkConfiguration** cmdlet to True.</span></span> <span data-ttu-id="a602b-110">EnablePIDFLOSupport の既定値は False です。</span><span class="sxs-lookup"><span data-stu-id="a602b-110">The default value for EnablePIDFLOSupport is False.</span></span> <span data-ttu-id="a602b-111">たとえば`Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.` 、フォールバック公衆交換電話網 (PSTN) ゲートウェイおよび緊急対応の場所識別番号 (ELIN) ゲートウェイの受信場所を有効にする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="a602b-111">For example: `Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.` It is not necessary to enable receiving locations for fallback public switched telephone network (PSTN) gateways and Emergency Location Identification Number (ELIN) gateways.</span></span>
  
### <a name="to-configure-an-e9-1-1-voice-route"></a><span data-ttu-id="a602b-112">E9-1-1 のボイス ルートを構成するには</span><span class="sxs-lookup"><span data-stu-id="a602b-112">To configure an E9-1-1 voice route</span></span>

1. <span data-ttu-id="a602b-113">RTCUniversalServerAdmins グループのメンバーまたは CsVoiceAdministrator 管理者役割のメンバーであるアカウントを使用してコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="a602b-113">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins groups, or a member of the CsVoiceAdministrator administrative role.</span></span>
    
2.  <span data-ttu-id="a602b-114">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="a602b-114">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="a602b-115">次のコマンドレットを実行して、新しい PSTN 使用法レコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="a602b-115">Run the following cmdlet to create a new PSTN usage record.</span></span> 
    
    <span data-ttu-id="a602b-116">これは、[場所のポリシー] の [**PSTN**] 設定で使用する名前と同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="a602b-116">This must be the same name that you will use for the **PSTN** setting in the location policy.</span></span> <span data-ttu-id="a602b-117">展開には複数の電話使用法レコードが含まれますが、次の例では、使用可能な PSTN 使用法の現在の一覧に "Emergency Usage" を追加しています。</span><span class="sxs-lookup"><span data-stu-id="a602b-117">Although your deployment will have multiple phone usage records, the following example adds "Emergency Usage" to the current list of available PSTN usages.</span></span> <span data-ttu-id="a602b-118">詳細については、「 [Skype For business で音声ポリシー、PSTN 使用状況レコード、および音声ルーティングを構成する](voice-and-pstn.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a602b-118">For details, see [Configure voice policies, PSTN usage records, and voice routes in Skype for Business](voice-and-pstn.md).</span></span>
    
   ```
   Set-CsPstnUsage -Usage @{add='EmergencyUsage'}
   ```

4. <span data-ttu-id="a602b-119">次のコマンドレットを実行して、前のステップで作成した PSTN 使用法レコードで新しいボイス ルートを作成します。</span><span class="sxs-lookup"><span data-stu-id="a602b-119">Run the following cmdlet to create a new voice route by using the PSTN usage record that you created in the previous step.</span></span>
    
    <span data-ttu-id="a602b-120">この番号パターンは、[場所のポリシー] の [**緊急ダイヤル文字列**] 設定で使用する番号パターンと同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="a602b-120">The number pattern must be the same number pattern that is used in the **Emergency Dial String** setting in the location policy.</span></span> <span data-ttu-id="a602b-121">Skype for Business は緊急電話に「+」を追加するため、「+」記号が必要です。</span><span class="sxs-lookup"><span data-stu-id="a602b-121">A "+" sign is needed because Skype for Business adds "+" to emergency calls.</span></span> <span data-ttu-id="a602b-122">"Co1-pstngateway-1" は、E9-1-1 サービス プロバイダーの SIP トランク サービス ID または ELIN ゲートウェイ サービス ID です。</span><span class="sxs-lookup"><span data-stu-id="a602b-122">"Co1-pstngateway-1" is the SIP trunk service ID for the E9-1-1 service provider or for the ELIN gateway service ID.</span></span> <span data-ttu-id="a602b-123">次の例では、ボイス ルートの名前として、"EmergencyRoute" を使用しています。</span><span class="sxs-lookup"><span data-stu-id="a602b-123">The following example uses "EmergencyRoute" as the name of the voice route.</span></span>
    
   ```
   New-CsVoiceRoute -Name "EmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="EmergencyUsage"} -PstnGatewayList @{add="co1-pstngateway-1"}
   ```

5. <span data-ttu-id="a602b-124">必要に応じて、SIP トランク接続の場合、E9 サービスプロバイダーの SIP トランクで処理されない通話のローカルルートを作成するには、次のコマンドレットを実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a602b-124">Optionally, for SIP trunk connections, we recommend that you run the following cmdlet to create a local route for calls that are not handled by the E9-1-1 service provider's SIP trunk.</span></span> <span data-ttu-id="a602b-125">このルートは、E9-1-1 サービス プロバイダーへの接続が利用できない場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="a602b-125">This route will be used if the connection to the E9-1-1 service provider is not available.</span></span> 
    
    <span data-ttu-id="a602b-126">次の例では、ユーザーの音声ポリシーに "ローカル" 使用法があることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="a602b-126">The following example assumes that user has "Local" usage in their voice policy.</span></span>
    
   ```
   New-CsVoiceRoute -Name "LocalEmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="Local"} -PstnGatewayList @{add="co1-pstngateway-2"}
   ```


